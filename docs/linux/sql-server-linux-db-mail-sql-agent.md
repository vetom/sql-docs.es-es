---
title: Correo electrónico de base de datos y las alertas de correo electrónico con el Agente SQL en Linux | Documentos de Microsoft
description: Este artículo describe cómo usar alertas de correo electrónico y correo electrónico de base de datos con SQL Server en Linux
author: meet-bhagdev
ms.author: meetb
manager: craigg
ms.date: 02/20/2018
ms.topic: article
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: ''
ms.suite: sql
ms.custom: sql-linux
ms.technology: database-engine
ms.assetid: tbd
ms.workload: Inactive
ms.openlocfilehash: 4d05f3b9a0af56e640cdb3176a5114183410ccef
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="db-mail-and-email-alerts-with-sql-agent-on-linux"></a>Correo electrónico de base de datos y las alertas de correo electrónico con el Agente SQL en Linux

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Los pasos siguientes muestran cómo configurar el correo electrónico de base de datos y usar con el agente de SQL Server (**agente de server mssql**) en Linux. 

## <a name="1-enable-db-mail"></a>1. Habilitar correo electrónico de base de datos

```sql
USE master 
GO 
sp_configure 'show advanced options',1 
GO 
RECONFIGURE WITH OVERRIDE 
GO 
sp_configure 'Database Mail XPs', 1 
GO 
RECONFIGURE  
GO  
```

## <a name="2-create-a-new-account"></a>2. Crear nueva cuenta
```sql
EXECUTE msdb.dbo.sysmail_add_account_sp 
@account_name = 'SQLAlerts', 
@description = 'Account for Automated DBA Notifications', 
@email_address = 'sqlagenttest@gmail.com', 
@replyto_address = 'sqlagenttest@gmail.com', 
@display_name = 'SQL Agent', 
@mailserver_name = 'smtp.gmail.com', 
@port = 587, 
@enable_ssl = 1, 
@username = 'sqlagenttest@gmail.com', 
@password = '<password>' 
GO
```

## <a name="3-create-a-default-profile"></a>3. Crear un perfil predeterminado

```sql
EXECUTE msdb.dbo.sysmail_add_profile_sp 
@profile_name = 'default', 
@description = 'Profile for sending Automated DBA Notifications' 
GO
```

## <a name="4-add-the-database-mail-account-to-a-database-mail-profile"></a>4. Agregar la cuenta de correo electrónico de base de datos a un perfil de correo electrónico de base de datos
```sql
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp 
@profile_name = 'default', 
@principal_name = 'public', 
@is_default = 1 ; 
 ```
 
## <a name="5-add-account-to-profile"></a>5. Agregar cuenta al perfil 
```sql
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp   
@profile_name = 'default',   
@account_name = 'SQLAlerts',   
@sequence_number = 1;  
 ```
 
## <a name="6-send-test-email"></a>6. Enviar correo electrónico de prueba
> [!NOTE]
> Es posible que deba ir a su cliente de correo electrónico y habilitar la "Permitir menos seguros clientes enviar correo electrónico". No todos los clientes reconocen el correo electrónico de base de datos como un demonio del correo electrónico.

```
EXECUTE msdb.dbo.sp_send_dbmail 
@profile_name = 'default', 
@recipients = 'recipient-email@gmail.com', 
@Subject = 'Testing DBMail', 
@Body = 'This message is a test for DBMail' 
GO
```

## <a name="7-set-db-mail-profile-using-mssql-conf-or-environment-variable"></a>7. Establezca el perfil de correo electrónico de base de datos mediante la variable de entorno o mssql-conf
Puede usar la utilidad mssql-conf o variables de entorno para registrar su perfil de correo electrónico de base de datos. En este caso, vamos a llamar a nuestro predeterminados de perfil.

```bash
# via mssql-conf
sudo /opt/mssq/bin/mssql-conf set sqlagent.databasemailprofile default
# via environment variable
MSSQL_AGENT_EMAIL_PROFILE=default
```

## <a name="8-set-up-an-operator-for-sqlagent-job-notifications"></a>8. Configurar un operador para notificaciones del trabajo SQLAgent 

```sql
EXEC msdb.dbo.sp_add_operator 
@name=N'JobAdmins',  
@enabled=1, 
@email_address=N'recipient-email@gmail.com',  
@category_name=N'[Uncategorized]' 
GO 
```

## <a name="9-send-email-when-agent-test-job-succeeds"></a>9. Enviar correo electrónico cuando se realiza correctamente en 'Trabajo del agente de prueba' 

```
EXEC msdb.dbo.sp_update_job 
@job_name='Agent Test Job', 
@notify_level_email=1, 
@notify_email_operator_name=N'JobAdmins' 
GO
```

## <a name="next-steps"></a>Pasos siguientes
Para obtener más información sobre cómo usar el Agente SQL Server para crear, programar y ejecutar trabajos, consulte [ejecutar un trabajo de agente SQL Server en Linux](sql-server-linux-run-sql-server-agent-job.md).

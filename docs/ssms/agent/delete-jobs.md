---
title: Eliminar trabajos | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 88ac43adddb2614b7fd0c000b439098f894161b4
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="delete-jobs"></a>eliminar trabajos
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> En [Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance), la mayoría de las características de agente SQL Server son compatibles actualmente, aunque no todas. Vea [Diferencias de T-SQL en Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) para obtener más información.

Un trabajo es una serie específica de operaciones que el Agente SQL Server realiza secuencialmente. De forma predeterminada, los trabajos no se eliminan cuando finaliza la ejecución. Puede eliminar uno o más trabajos del Agente [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] independientemente del éxito o del fracaso del trabajo. También puede configurar el Agente [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] para que elimine los trabajos automáticamente cuando se realizan correctamente, con error o se completan.  
  
De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden ejecutar el procedimiento almacenamiento del sistema [sp_delete_job (Transact-SQL)](http://msdn.microsoft.com/en-us/b85db6e4-623c-41f1-9643-07e5ea38db09) para eliminar un trabajo. Al resto de usuarios se les debe conceder uno de los siguientes roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] en la base de datos **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
Para detalles sobre los permisos de estos roles, consulte [Roles fijos de base de datos del Agente SQL Server](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
Los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_delete_job** para eliminar cualquier trabajo. Un usuario que no sea miembro del rol fijo de servidor **sysadmin** solo puede eliminar los trabajos de los que sea propietario.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|||  
|-|-|  
|**Descripción**|**Tema**|  
|Describe cómo eliminar uno o varios de los trabajos del Agente [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .|[Eliminar uno o más trabajos](../../ssms/agent/delete-one-or-more-jobs.md)|  
|Describe cómo configurar el Agente [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] para que elimine los trabajos automáticamente cuando se realizan correctamente, con error o se completan.|[Automatically Delete a Job](../../ssms/agent/automatically-delete-a-job.md)|  
  

---
title: sp_add_log_shipping_secondary_database (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_add_log_shipping_secondary_database
- sp_add_log_shipping_secondary_database_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_add_log_shipping_secondary_database
ms.assetid: d29e1c24-3a3c-47a4-a726-4584afa6038a
caps.latest.revision: 22
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c2cc8460059274458016d24e106e554f78394618
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="spaddlogshippingsecondarydatabase-transact-sql"></a>sp_add_log_shipping_secondary_database (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Configura una base de datos secundaria de trasvase de registros.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_add_log_shipping_secondary_database  
[ @secondary_database = ] 'secondary_database',  
[ @primary_server = ] 'primary_server',   
[ @primary_database = ] 'primary_database',  
[, [ @restore_delay = ] 'restore_delay']  
[, [ @restore_all = ] 'restore_all']  
[, [ @restore_mode = ] 'restore_mode']  
[, [ @disconnect_users = ] 'disconnect_users']  
[, [ @block_size = ] 'block_size']  
[, [ @buffer_count = ] 'buffer_count']  
[, [ @max_transfer_size = ] 'max_transfer_size']  
[, [ @restore_threshold = ] 'restore_threshold']   
[, [ @threshold_alert = ] 'threshold_alert']   
[, [ @threshold_alert_enabled = ] 'threshold_alert_enabled']   
[, [ @history_retention_period = ] 'history_retention_period']  
```  
  
## <a name="arguments"></a>Argumentos  
 [ **@secondary_database** =] '*secondary_database*'  
 Es el nombre de la base de datos secundaria. *secondary_database* es **sysname**, no tiene ningún valor predeterminado.  
  
 [ **@primary_server** =] '*primary_server*'  
 El nombre de la instancia principal de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en la configuración de trasvase de registros. *primary_server* es **sysname** y no puede ser NULL.  
  
 [ **@primary_database** =] '*primary_database*'  
 Es el nombre de la base de datos en el servidor principal. *primary_database* es **sysname**, no tiene ningún valor predeterminado.  
  
 [ **@restore_delay** =] '*restore_delay*'  
 Cantidad de tiempo, en minutos, que espera el servidor secundario antes de restaurar un archivo de copia de seguridad dado. *restore_delay* es **int** y no puede ser NULL. El valor predeterminado es 0.  
  
 [ **@restore_all** =] '*restore_all*'  
 Si se establece en 1, el servidor secundario restaura todas las copias de seguridad disponibles del registro de transacciones cuando se ejecuta el trabajo de restauración. De lo contrario, se detiene tras haberse restaurado un archivo. *restore_all* es **bits** y no puede ser NULL.  
  
 [ **@restore_mode** =] '*restore_mode*'  
 Modo de restauración para la base de datos secundaria.  
  
 0 = Restaurar registro con NORECOVERY.  
  
 1 = Restaurar registro con STANDBY.  
  
 *restaurar* es **bits** y no puede ser NULL.  
  
 [ **@disconnect_users** =] '*disconnect_users*'  
 Si se establece en 1, los usuarios están desconectados de la base de datos secundaria cuando se realiza una operación de restauración. Valor predeterminado = 0. *desconectar* usuarios es **bits** y no puede ser NULL.  
  
 [ **@block_size** =] '*block_size*'  
 Tamaño, en bytes, que se utiliza como tamaño de bloque para el dispositivo de copia de seguridad. *block_size* es **int** con un valor predeterminado de -1.  
  
 [ **@buffer_count** =] '*buffer_count*'  
 Número total de búferes utilizados por la operación de copia de seguridad o restauración. *buffer_count* es **int** con un valor predeterminado de -1.  
  
 [ **@max_transfer_size** =] '*max_transfer_size*'  
 Tamaño, en bytes, de la solicitud de entrada o salida máxima emitida por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al dispositivo de copia de seguridad. *max_transfersize* es **int** y puede ser NULL.  
  
 [ **@restore_threshold** =] '*restore_threshold*'  
 Número de minutos permitido entre las operaciones de restauración antes de que se genere una alerta. *restore_threshold* es **int** y no puede ser NULL.  
  
 [ **@threshold_alert** =] '*threshold_alert*'  
 Es la alerta que se generará cuando se sobrepase el umbral de copia de seguridad. *threshold_alert* es **int**, su valor predeterminado es 14,420.  
  
 [ **@threshold_alert_enabled** =] '*threshold_alert_enabled*'  
 Especifica si se generará una alerta cuando *backup_threshold* se supera. El valor uno (1), predeterminado, significa que se generará la alerta. *threshold_alert_enabled* es **bits**.  
  
 [ **@history_retention_period** =] '*history_retention_period*'  
 Es la cantidad de tiempo en minutos durante la que se retiene el historial. *history_retention_period* es **int**, su valor predeterminado es null. Si no se especifica ningún valor, se utiliza 14420.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 None  
  
## <a name="remarks"></a>Comentarios  
 **sp_add_log_shipping_secondary_database** se debe ejecutar desde la **maestro** base de datos en el servidor secundario. Este procedimiento almacenado hace lo siguiente:  
  
1.  **sp_add_log_shipping_secondary_primary** debe llamarse antes de este procedimiento almacenado para inicializar la información de la base de datos en el servidor secundario de trasvase de registros principal.  
  
2.  Agrega una entrada para la base de datos secundaria en **log_shipping_secondary_databases** con los argumentos proporcionados.  
  
3.  Agrega un registro de monitor local en **log_shipping_monitor_secondary** en el servidor secundario utilizando los argumentos proporcionados.  
  
4.  Si el servidor de supervisión es diferente del servidor secundario, agrega un registro de monitor en **log_shipping_monitor_secondary** en el monitor de servidor con los argumentos proporcionados.  
  
## <a name="permissions"></a>Permissions  
 Solo los miembros de la **sysadmin** rol fijo de servidor puede ejecutar este procedimiento.  
  
## <a name="examples"></a>Ejemplos  
 En este ejemplo se muestra cómo utilizar el **sp_add_log_shipping_secondary_database** procedimiento almacenado para agregar la base de datos **LogShipAdventureWorks** como una base de datos secundaria en una configuración de trasvase de registros con la base de datos principal [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] reside en el servidor principal TRIBECA.  
  
```  
EXEC master.dbo.sp_add_log_shipping_secondary_database   
@secondary_database = N'LogShipAdventureWorks'   
,@primary_server = N'TRIBECA'   
,@primary_database = N'AdventureWorks2012'   
,@restore_delay = 0   
,@restore_mode = 1   
,@disconnect_users = 0   
,@restore_threshold = 45     
,@threshold_alert_enabled = 0   
,@history_retention_period = 1440 ;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Acerca del trasvase de registros & #40; SQL Server & #41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

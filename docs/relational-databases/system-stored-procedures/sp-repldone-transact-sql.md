---
title: sp_repldone (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_repldone
- sp_repldone_TSQL
helpviewer_keywords:
- sp_repldone
ms.assetid: 045d3cd1-712b-44b7-a56a-c9438d4077b9
caps.latest.revision: 19
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: c7813442909a5641076b54d5dadeaef2d2f1683b
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="sprepldone-transact-sql"></a>sp_repldone (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Actualiza el registro que identifica la última transacción distribuida del servidor. Este procedimiento almacenado se ejecuta en el publicador de la base de datos de publicación.  
  
> [!CAUTION]  
>  Si ejecuta **sp_repldone** manualmente, puede invalidar el orden y la coherencia de las transacciones entregadas. **sp_repldone** solo debe usarse para solucionar problemas de replicación como se indica por un profesional de soporte técnico experto en replicación.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_repldone [ @xactid= ] xactid   
        , [ @xact_seqno= ] xact_seqno   
    [ , [ @numtrans= ] numtrans ]   
    [ , [ @time= ] time   
    [ , [ @reset= ] reset ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@xactid=**] *xactid*  
 Es el número de secuencia de registro (LSN) del primer registro de la última transacción distribuida del servidor. *xactid* es **binary (10)**, no tiene ningún valor predeterminado.  
  
 [  **@xact_seqno=**] *xact_seqno*  
 Es el LSN del último registro de la última transacción distribuida del servidor. *xact_seqno* es **binary (10)**, no tiene ningún valor predeterminado.  
  
 [  **@numtrans=**] *numtrans*  
 Es el número de transacciones distribuidas. *numtrans* es **int**, no tiene ningún valor predeterminado.  
  
 [  **@time=**] *tiempo*  
 Es el número de milisegundos, si se especifica, necesarios para distribuir el último lote de transacciones. *tiempo* es **int**, no tiene ningún valor predeterminado.  
  
 [  **@reset=**] *restablecer*  
 Es el estado de la restauración. *restablecer* es **int**, no tiene ningún valor predeterminado. Si **1**, replicados de todas las transacciones en el registro se marcan como distribuidas. Si **0**, el registro de transacciones se restablece a la primera transacción replicada y no hay transacciones replicadas se marcan como distribuidas. *restablecer* solo es válido cuando ambos *xactid* y *xact_seqno* son NULL.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_repldone** se utiliza en la replicación transaccional.  
  
 **sp_repldone** usa el proceso del lector de registro para realizar un seguimiento de las transacciones que se han distribuido.  
  
 Con **sp_repldone**, puede indicar manualmente al servidor que se ha replicado una transacción (que se envían al distribuidor). También le permite cambiar la transacción que está marcada como la siguiente en espera de la replicación. Puede desplazarse hacia delante y hacia atrás en la lista de transacciones replicadas. (Todas las transacciones menores o iguales que esa transacción se marcan como distribuidas.)  
  
 Los parámetros necesarios *xactid* y *xact_seqno* puede obtenerse mediante **sp_repltrans** o **sp_replcmds**.  
  
## <a name="permissions"></a>Permissions  
 Los miembros de la **sysadmin** rol fijo de servidor o el **db_owner** rol fijo de base de datos puede ejecutar **sp_repldone**.  
  
## <a name="examples"></a>Ejemplos  
 Cuando *xactid* es NULL, *xact_seqno* es NULL, y *restablecer* es **1**, replicados de todas las transacciones en el registro se marcan como distribuidas. Esto resulta útil cuando, por ejemplo, hay transacciones replicadas en el registro de transacciones que ya no son válidas y desea truncar el registro:  
  
```  
EXEC sp_repldone @xactid = NULL, @xact_segno = NULL, @numtrans = 0,     @time = 0, @reset = 1  
```  
  
> [!CAUTION]  
>  Este procedimiento se puede utilizar en situaciones de emergencia para permitir que se trunque el registro de transacciones cuando existen transacciones pendientes de replicación.  
  
## <a name="see-also"></a>Vea también  
 [sp_replcmds &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_replflush &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md)   
 [sp_repltrans &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-repltrans-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

---
title: Sys.sp_rda_reconcile_indexes (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-stretch
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_rda_reconcile_indexes
- sp_rda_reconcile_indexes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_reconcile_indexes stored procedure
ms.assetid: 96b31ab9-bf84-46d6-9990-81f5c51f885a
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3b0a36d2b0af0e9abda2d8013475e70868f76cc3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="syssprdareconcileindexes-transact-sql"></a>Sys.sp_rda_reconcile_indexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Pone en cola una tarea de esquema para conciliar los índices de la tabla remota. Cuando esta tarea finaliza correctamente, la tabla remota tiene los mismos índices que existen en la tabla habilitada para Stretch local.  
  
 Si no hay otra tarea en cola para conciliar los índices cuando se llama a **sp_rda_reconcile_indexes**, este procedimiento almacenado no poner en cola una tarea duplicada.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_rda_reconcile_indexes [@objname = ] 'objname'  
  
```  
  
## <a name="arguments"></a>Argumentos  
 [@objname =] *'objname'*  
 Es el nombre calificado o no calificado de la tabla habilitada para Stretch para la que desea conciliar los índices. Las comillas solo son necesarias si se especifica un objeto completo.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o >0 (error)  
  
## <a name="see-also"></a>Vea también  
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  

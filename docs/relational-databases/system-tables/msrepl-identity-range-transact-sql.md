---
title: MSrepl_identity_range (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSrepl_identity_range_TSQL
- MSrepl_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_identity_range system table
ms.assetid: 6e92a8e8-7667-4c98-b1c4-46735bac50d8
caps.latest.revision: 27
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 83dcaf5b06f5664699e0d6fe9cd6ca509ce46930
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="msreplidentityrange-transact-sql"></a>MSrepl_identity_range (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  El **MSrepl_identity_range** tabla proporciona soporte de administración de intervalo de identidad. Esta tabla se almacena en las bases de datos de publicaciones, distribución y suscripciones.  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**publicador**|**sysname**|El nombre del publicador.|  
|**publisher_db**|**sysname**|El nombre de la base de datos de publicación.|  
|**nombre de tabla**|**sysname**|Nombre de la tabla.|  
|**identity_support**|**int**|Especifica si se habilita el control automático de intervalo de identidad. 0 especifica que no se habilita el control automático de intervalo de identidad.|  
|**next_seed**|**bigint**|Si se habilita el intervalo automático de identidad, indica el punto de inicio del siguiente intervalo.|  
|**pub_range**|**bigint**|Tamaño del intervalo de identidad del publicador.|  
|**intervalo**|**bigint**|Tamaño de los valores de identidad consecutivos que podrían asignarse a los suscriptores en un ajuste.|  
|**max_identity**|**bigint**|Límite máximo del intervalo de identidad.|  
|**Umbral**|**int**|Porcentaje de umbral del intervalo de identidad.|  
|**current_max**|**bigint**|Máximo actual que se puede asignar, aunque no necesariamente.|  
  
## <a name="see-also"></a>Vea también  
 [Tablas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vistas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  

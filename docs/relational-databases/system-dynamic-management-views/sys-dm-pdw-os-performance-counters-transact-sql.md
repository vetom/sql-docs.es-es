---
title: Sys.dm_pdw_os_performance_counters (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: pdw
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 0673a8f8-8bed-41eb-8959-a9e3e9e03a65
caps.latest.revision: 8
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: f0b160ce33a469f02b47b29f76752db39b678dd3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmpdwosperformancecounters-transact-sql"></a>Sys.dm_pdw_os_performance_counters (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Contiene información sobre los contadores de rendimiento de Windows para los nodos en [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
|Nombre de la columna|Tipo de datos|Description|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|El identificador del nodo que contiene el contador.<br /><br /> pdw_node_id y Nombre_contador forman la clave para esta vista.|Vea node_id en [sys.dm_pdw_nodes &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md).|  
|counter_name|**nvarchar(255)**|Nombre del contador de rendimiento de Windows.||  
|counter_category|**nvarchar(255)**|Nombre de categoría de contador de rendimiento de Windows.||  
|nombre_instancia|**nvarchar(255)**|Nombre de la instancia específica del contador.||  
|counter_value|**Decimal(38,10)**|Valor actual del contador.||  
|last_update_time|**Datetime2(3)**|Marca de tiempo de la última vez que se actualizó el valor.||  
  
## <a name="see-also"></a>Vea también  
 [Vistas de administración dinámica del almacenamiento de datos en paralelo y almacén de datos SQL &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  

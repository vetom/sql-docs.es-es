---
title: Sys.dm_pdw_os_event_logs (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: pdw
ms.reviewer: ''
ms.service: ''
ms.component: dmv's
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: a0daa8cf-72e2-4349-8be1-d3cc0f9b1e02
caps.latest.revision: 7
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: c341882b510f5a602f7c534ca653208b1784b426
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmpdwoseventlogs-transact-sql"></a>sys.dm_pdw_os_event_logs (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Contiene información sobre los distintos eventos de Windows inicia sesión en los distintos nodos.  
  
|Nombre de la columna|Tipo de datos|Description|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|Este registro procede de un nodo de dispositivo.<br /><br /> pdw_node_id y nombreDelRegistro forman la clave para esta vista.||  
|nombreDelRegistro|**nvarchar(255)**|Nombre de registro de eventos de Windows.<br /><br /> pdw_node_id y nombreDelRegistro forman la clave para esta vista.||  
|log_source|**nvarchar(255)**|Nombre de origen del registro de eventos de Windows.||  
|event_id|**int**|Identificador del evento. No es único.||  
|event_type|**nvarchar(255)**|Tipo de evento, identificación de gravedad.|'Información', 'Advertencia', 'Error'|  
|event_message|**nvarchar(4000)**|Detalles del evento.||  
|generate_time|**datetime**|Tiempo que se creó el evento.||  
|write_time|**datetime**|El evento se ha escrito realmente en el registro de tiempo.||  
  
 Para obtener información sobre el número máximo de filas conserva esta vista, vea la sección valores máximos de vista de sistema en el [valores mínimo y máximo (SQL Server PDW)](http://msdn.microsoft.com/en-us/5243f018-2713-45e3-9b61-39b2a57401b9) tema.  
  
## <a name="see-also"></a>Vea también  
 [Vistas de administración dinámica del almacenamiento de datos en paralelo y almacén de datos SQL &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  

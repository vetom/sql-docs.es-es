---
title: Sys.pdw_column_distribution_properties (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/03/2017
ms.prod: ''
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 46b74f99-2e22-4dbd-872a-533fce0e239c
caps.latest.revision: 5
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: fa134f563dfc7bd83a2db4ccded4344bc060b769
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="syspdwcolumndistributionproperties-transact-sql"></a>Sys.pdw_column_distribution_properties (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Contiene información de distribución de columnas.  
  
|Nombre de la columna|Tipo de datos|Description|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|**object_id**|**int**|Id. del objeto al que pertenece la columna.||  
|**column_id**|**int**|Identificador de la columna.||  
|**distribution_ordinal**|**tinyint**|Ordinal (basado en 1) en el conjunto de distribución.|0 = no es una columna de distribución. 1 = [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] es utilizar esta columna para distribuir la tabla primaria.|  
  
## <a name="see-also"></a>Vea también  
 [Almacenamiento de datos SQL y vistas de catálogo del almacén de datos en paralelo](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  

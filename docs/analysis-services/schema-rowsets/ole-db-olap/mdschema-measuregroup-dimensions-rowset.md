---
title: Conjunto de filas MDSCHEMA_MEASUREGROUP_DIMENSIONS | Documentos de Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- MDSCHEMA_MEASUREGROUP_DIMENSIONS
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- MDSCHEMA_MEASUREGROUP_DIMENSIONS rowset
ms.assetid: c731c06a-7382-4e50-ba0e-d8cee3ab4f28
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 62ee9e17d9f53d981e5e44918ec690c9abceddbb
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2018
---
# <a name="mdschemameasuregroupdimensions-rowset"></a>Conjunto de filas MDSCHEMA_MEASUREGROUP_DIMENSIONS
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Enumera las dimensiones de grupos de medida.  
  
## <a name="rowset-columns"></a>Columnas del conjunto de filas  
 El conjunto de filas **MDSCHEMA_MEASUREGROUP_DIMENSIONS** contiene las siguientes columnas.  
  
|Nombre de columna|Indicador de tipo|Longitud|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**||El nombre del catálogo al que pertenece este grupo de medida. **NULL** si el proveedor no admite catálogos.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**||No compatible.|  
|**RESTRICCIONES OBLIGATORIAS CUBE_NAME**|**DBTYPE_WSTR**||Nombre del cubo al que pertenece este grupo de medida.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**||Nombre del grupo de medida.|  
|**MEASUREGROUP_CARDINALITY**|**DBTYPE_WSTR**||El número de instancias que puede tener una medida en el grupo de medida para un único miembro de dimensión. Los valores posibles incluyen:<br /><br /> **UNO**<br /><br /> **MUCHOS**|  
|**DIMENSION_UNIQUE_NAME**|**DBTYPE_WSTR**||Nombre único de la dimensión.|  
|**DIMENSION_CARDINALITY**|**DBTYPE_WSTR**||El número de instancias que un miembro de dimensión puede tener para una instancia única de una medida de grupo de medida. Los valores posibles incluyen:<br /><br /> **UNO**<br /><br /> **MUCHOS**|  
|**DIMENSION_IS_VISIBLE**|**DBTYPE_BOOL**||Un valor booleano que indica si las jerarquías en la dimensión están visibles.<br /><br /> Devuelve **TRUE** si una o más jerarquías en la dimensión están visibles; en caso contrario, **FALSE**.|  
|**DIMENSION_IS_FACT_DIMENSION**|**DBTYPE_BOOL**||Un valor booleano que indica si la dimensión es una dimensión de hechos.<br /><br /> Devuelve **TRUE** si la dimensión de una dimensión de hechos; en caso contrario, **FALSE**.|  
|**DIMENSION_PATH**|**DBTYPE_HCHAPTER**||Una lista de dimensiones para la dimensión de la referencia.|  
|**DIMENSION_GRANULARITY**|**DBTYPE_WSTR**||Nombre único de la jerarquía de granularidad.|  
  
 El conjunto de filas admite ordenando en **CATALOG_NAME**, **SCHEMA_NAME**, **CUBE_NAME**, **MEASUREGROUP_NAME**, **DIMENSION_UNIQUE_NAME**.  
  
## <a name="restriction-columns"></a>Columnas de restricción  
 El conjunto de filas **MDSCHEMA_MEASUREGROUP_DIMENSIONS** puede tener restricciones en las columnas que se muestran en la tabla siguiente.  
  
|Nombre de columna|Indicador de tipo|Estado de restricción|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**RESTRICCIONES OBLIGATORIAS CUBE_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**DIMENSION_UNIQUE_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**DIMENSION_VISIBILITY**|**DBTYPE_UI2**|(Opcional) Mapa de bits con uno de los siguientes valores válidos:<br /><br /> 1 Visible<br /><br /> 2 no visible<br /><br /> La restricción predeterminada es un valor de 1.|  
  
## <a name="see-also"></a>Vea también  
 [OLE DB para los conjuntos de filas de esquema OLAP](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  

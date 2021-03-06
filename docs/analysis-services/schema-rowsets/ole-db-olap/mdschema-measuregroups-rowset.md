---
title: Conjunto de filas MDSCHEMA_MEASUREGROUPS | Documentos de Microsoft
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
- MDSCHEMA_MEASUREGROUPS
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- MDSCHEMA_MEASUREGROUPS rowset
ms.assetid: bab1bbd0-421b-4fad-9aee-e6511e0e1f1b
caps.latest.revision: 28
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: aebac1aafd7d49e6b5b5c21343161184ba19da34
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2018
---
# <a name="mdschemameasuregroups-rowset"></a>Conjunto de filas MDSCHEMA_MEASUREGROUPS
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Describe los grupos de medida dentro de una base de datos.  
  
## <a name="rowset-columns"></a>Columnas del conjunto de filas  
 El conjunto de filas **MDSCHEMA_MEASUREGROUPS** contiene las siguientes columnas.  
  
|Nombre de columna|Indicador de tipo|Longitud|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**||El nombre del catálogo al que pertenece este grupo de medida. **NULL** si el proveedor no admite catálogos.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**||No compatible.|  
|**RESTRICCIONES OBLIGATORIAS CUBE_NAME**|**DBTYPE_WSTR**||Nombre del cubo al que pertenece este grupo de medida.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**||Nombre del grupo de medida.|  
|**DESCRIPTION**|**DBTYPE_WSTR**||Descripción legible del miembro.|  
|**IS_WRITE_ENABLED**|**DBTYPE_BOOL**||Un valor booleano que indica si el grupo de medida tiene permiso de escritura.<br /><br /> Devuelve **true** si el grupo de medida tiene permiso de escritura.|  
|**MEASUREGROUP_CAPTION**|**DBTYPE_WSTR**||El título de presentación para el grupo de medida.|  
  
 Este conjunto de filas de esquema no está ordenado.  
  
## <a name="restriction-columns"></a>Columnas de restricción  
 El conjunto de filas **MDSCHEMA_MEASUREGROUPS** puede tener restricciones en las columnas que se muestran en la tabla siguiente.  
  
|Nombre de columna|Indicador de tipo|Estado de restricción|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**RESTRICCIONES OBLIGATORIAS CUBE_NAME**|**DBTYPE_WSTR**|Opcional.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**|Opcional.|  
  
## <a name="see-also"></a>Vea también  
 [OLE DB para los conjuntos de filas de esquema OLAP](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  

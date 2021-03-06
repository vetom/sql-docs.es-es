---
title: Actualizar resincronización propiedad dinámicos (ADO) | Documentos de Microsoft
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Update Resync property [ADO]
ms.assetid: 8a3bb608-66d7-4128-a3ef-84cb0556de0d
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d79953a8ae35c2e3b7da1edecd4db4a73f14462f
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="update-resync-property-dynamic-ado"></a>Propiedad dinámica Update Resync (ADO)
Especifica si el [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) método va seguido de un modo implícito [Resync](../../../ado/reference/ado-api/resync-method.md) operación del método y si es así, el ámbito de esa operación.  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece o devuelve uno o varios de los [ADCPROP_UPDATERESYNC_ENUM](../../../ado/reference/ado-api/adcprop-updateresync-enum.md) valores.  
  
## <a name="remarks"></a>Comentarios  
 Los valores de ADCPROP_UPDATERESYNC_ENUM se pueden combinar, excepto adResyncAll, que ya representa la combinación del resto de los valores.  
  
 La constante **adResyncConflicts** almacena los valores de resincronización como valores subyacentes, pero no reemplaza los cambios pendientes.  
  
 **Actualizar resincronización** es una propiedad dinámica que se anexa a la [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) objeto [propiedades](../../../ado/reference/ado-api/properties-collection-ado.md) colección cuando la [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) propiedad está establecida en **adUseClient**.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)

---
title: Clustered, propiedad (clase SqlService) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: wmi
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Clustered Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
helpviewer_keywords:
- Clustered property
ms.assetid: f714e7f5-c2db-45c6-9536-6ca2cb5b42aa
caps.latest.revision: 35
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4c50b97b407d926841fadc95391a08b7685217bd
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="clustered-property-sqlservice-class"></a>Propiedad Clustered (clase SqlService)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Obtiene el valor de propiedad booleano que especifica si el servicio forma parte de una instancia en clúster.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object.Clustered [= value]  
```  
  
## <a name="parts"></a>Partes  
 *objeto*  
 Objeto de la [clase SqlService](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) que representa el servicio.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Valor booleano que especifica si el servicio forma parte de una instancia en clúster: **true** si el servicio forma parte de una instancia en clúster o **false** si no forma parte.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="see-also"></a>Vea también  
 [Iniciar y detener servicios](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  

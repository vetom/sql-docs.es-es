---
title: Método SetServiceAccountPassword (clase SqlService) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/04/2017
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
- SetServiceAccountPassword Method (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
caps.latest.revision: 36
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 07b3db70f8f4a4bb50c3c613501feebf7296f58e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a>Método SetServiceAccountPassword (clase SqlService)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Modifica la contraseña de la cuenta en la que se ejecuta el servicio al que se hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object.SetServiceAccountPassword(AccountOldPassword , ServiceStartPassword)  
```  
  
## <a name="parts"></a>Partes  
 *objeto*  
 Objeto de la [clase SqlService](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) que representa el servicio.  
  
#### <a name="parameters"></a>Parámetros  
 *AccountOldPassword*  
 Valor de cadena que especifica la contraseña existente para la cuenta.  
  
 *ServiceStartPassword*  
 Valor de cadena que especifica la nueva contraseña para la cuenta.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Valor **uint32** que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.  
  
## <a name="remarks"></a>Comentarios  
  

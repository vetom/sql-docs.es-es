---
title: Método getParameterCount (SQLServerParameterMetaData) | Documentos de Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: jdbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- SQLServerParameterMetaData.getParameterCount
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7dbbdacb-74ef-42e7-9bdc-a3229505dad8
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a1c55e36b506136993052b492cc9bcffd4237c97
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="getparametercount-method-sqlserverparametermetadata"></a>Método getParameterCount (SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el número de parámetros en el [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) objeto para el que este [SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md) objeto contiene información.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public int getParameterCount()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un **int** que indica el número de parámetros.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método getParameterCount especificado por el método getParameterCount en la interfaz java.sql.ParameterMetaData.  
  
## <a name="see-also"></a>Vea también  
 [Métodos SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [Miembros de SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [Clase SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  

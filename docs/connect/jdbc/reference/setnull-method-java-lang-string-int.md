---
title: Método setNull (java.lang.String, int) | Documentos de Microsoft
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
- SQLServerCallableStatement.setNull (java.lang.String, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e1d7e267-d9de-407a-b1a9-abdc2623478d
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f8c89939aba3dd8b2f86b424ebd6ea2fa2711774
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="setnull-method-javalangstring-int"></a>Método setNull (java.lang.String, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el parámetro designado en un valor NULL, según en tipo de parámetro que se va a establecer.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setNull(java.lang.String sCol,  
                    int nType)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *sCol*  
  
 A **cadena** que contiene el nombre del parámetro.  
  
 *nLas*  
  
 Un código de tipo JDBC que es definido por java.sql.Types.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método setNull es especificado por el método setNull en la interfaz java.sql.CallableStatement.  
  
## <a name="see-also"></a>Vea también  
 [Método setNull &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/setnull-method-sqlservercallablestatement.md)   
 [Miembros de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Clase SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

---
title: Método getString (int) | Documentos de Microsoft
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
- SQLServerCallableStatement.getString (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f3fce8bf-8d6e-476f-aa6d-992daa79b899
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d0564b2ce44b0c77328bd427d9de488847233e7f
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="getstring-method-int"></a>Método getString (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el valor del parámetro designado como un **cadena** en el lenguaje según el índice de parámetro de programación Java.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.lang.String getString(int index)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *index*  
  
 Un **int** que indica el índice del parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 A **cadena** valor.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método getString especificado por el método getString de la interfaz java.sql.CallableStatement.  
  
 Todas las columnas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] puede devolverse como una cadena. Lo cual indica que se puede devolver una representación de cadena de todos los tipos basados en número y en caracteres y una representación de una cadena hexadecimal de columnas binarias como binary, varbinary, varbinary(max), image, timestamp y uniqueidentifier.  
  
 Tipos de dependientes de la ubicación como money, smallmoney, datetime, smalldatetime, float, real, decimal y numeric devolverán el formato canónico toString() para el valor subyacente del tipo.  
  
 Los tipos definidos por el usuario se devuelven como valores de cadena.  
  
## <a name="see-also"></a>Vea también  
 [Método getString &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getstring-method-sqlservercallablestatement.md)   
 [Miembros de SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Clase SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  

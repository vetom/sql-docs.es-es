---
title: setClientInfo (método) (java.lang.String, java.lang.String) | Documentos de Microsoft
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
ms.assetid: 8d050831-8305-48a8-bd22-207932111040
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 42cb5ed2bef213c9c57f4aa71309a1afeb54b0eb
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="setclientinfo-method-javalangstring-javalangstring"></a>Método setClientInfo (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el valor de la propiedad de información de cliente especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setClientInfo (java.lang.String name,  
                           java.lang.String value)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *Nombre*  
  
 Una cadena que contiene el nombre de la propiedad de información de cliente para establecer.  
  
 *value*  
  
 Una cadena que contiene el valor para establecer la propiedad de información de cliente.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método setClientInfo especificado por el método setClientInfo en la interfaz java.sql.Connection.  
  
 El [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] no admite las propiedades de información de cliente. En el controlador JDBC 2.0, este método genera una advertencia para una propiedad. Las aplicaciones deben utilizar [getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md) método de la [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) clase para recuperar una advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Método setClientInfo &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)   
 [Miembros de SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Clase SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  

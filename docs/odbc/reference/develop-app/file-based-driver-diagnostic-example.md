---
title: Ejemplo de diagnóstico de controlador basados en archivos | Documentos de Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file-based driver diagnostic [ODBC]
- diagnostic information [ODBC], examples
- error messages [ODBC], diagnostic messages
ms.assetid: 0575fccd-4641-478d-a3cc-5a764e35bae2
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 8dd8323e268ec31c33db3b850ee2b449264ed3f1
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="file-based-driver-diagnostic-example"></a>Ejemplo de diagnóstico de controlador basados en archivos
Un controlador de archivo actúa como un controlador ODBC y como un origen de datos. Por lo tanto, puede generar errores y advertencias como un componente en una conexión ODBC y como un origen de datos. Dado que también es el componente que interactúa con el Administrador de controladores, da formato y devuelve los argumentos para **SQLGetDiagRec**.  
  
 Por ejemplo, si un controlador de Microsoft® para dBASE no pudo asignar suficiente memoria, podrían devolver los siguientes valores de **SQLGetDiagRec**:  
  
```  
SQLSTATE:         "HY001"  
Native Error:      42052  
Diagnostic Msg:   "[Microsoft][ODBC dBASE Driver]Unable to allocate sufficient memory."  
```  
  
 Porque este error no estaba relacionada con el origen de datos, el controlador solo agrega prefijos para el mensaje de diagnóstico para el proveedor ([Microsoft]) y el controlador ([ODBC dBASE controlador]).  
  
 Si el controlador no pudo encontrar el archivo Employee.dbf, podría devolver los siguientes valores de **SQLGetDiagRec**:  
  
```  
SQLSTATE:         "42S02"  
Native Error:      -1305  
Diagnostic Msg:   "[Microsoft][ODBC dBASE Driver][dBASE]No such table or object"  
```  
  
 Dado que este error se relacionado con el origen de datos, el controlador agrega el formato de archivo del origen de datos ([dBASE]) como prefijo para el mensaje de diagnóstico. Dado que el controlador también fue el componente de interfaz con el origen de datos, agregar prefijos para el proveedor ([Microsoft]) y el controlador ([ODBC dBASE controlador]).

---
title: Recuperar marcadores | Documentos de Microsoft
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
- retrieving bookmarks [ODBC]
- result sets [ODBC], bookmarks
- bookmarks [ODBC]
ms.assetid: a34c8f09-b786-4835-a44b-b7294c970aff
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0d31e012efba212b1acbac0d4127459147508fd1
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="retrieving-bookmarks"></a>Recuperar marcadores
Si la aplicación va a utilizar marcadores, se debe establecer el atributo de instrucción de SQL_ATTR_USE_BOOKMARKS a SQL_UB_VARIABLE antes de preparar o ejecutar la instrucción. Esto es necesario porque crear y mantener marcadores pueden ser una operación costosa, por tanto marcadores deben habilitarse únicamente cuando una aplicación puede hacer buen usan de los mismos.  
  
 Los marcadores se devuelven como columna 0 del conjunto de resultados. Hay tres maneras de que una aplicación puede recuperarlos:  
  
-   Enlazar la columna 0 del conjunto de resultados. **SQLFetch** o **SQLFetchScroll** devuelve los marcadores para cada fila del conjunto de filas junto con los datos para otras columnas enlazadas.  
  
-   Llame a **SQLSetPos** para situarse en una fila del conjunto de filas y, a continuación, llamar a **SQLGetData** para la columna 0. Si un controlador es compatible con marcadores, siempre debe admitir la capacidad de llamar a **SQLGetData** para la columna 0, incluso si no permite a las aplicaciones llamen a **SQLGetData** de otras columnas antes el último límite columna.  
  
-   Llame a **SQLBulkOperations** con el *operación* argumento establecido en SQL_ADD y la columna 0 enlazado. El cursor inserta la fila y devuelve el marcador de la fila en el búfer de enlazado.

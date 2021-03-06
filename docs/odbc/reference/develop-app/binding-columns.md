---
title: Enlazar columnas | Documentos de Microsoft
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
- result sets [ODBC], binding columns
- binding columns [ODBC]
ms.assetid: c4407694-c8e1-4b0b-a39d-b007e6c3b54d
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 02368c6294ab3eae345c756692cde83a1bc6aed6
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="binding-columns"></a>Enlazar columnas
Datos capturados desde el origen de datos se devuelven a la aplicación en las variables que se asignó la aplicación para este propósito. Para ello, debe asociar la aplicación, o *enlazar*, establecen estas variables a las columnas del resultado; conceptualmente, este proceso es el mismo que enlazar variables de aplicación a los parámetros de la instrucción. Cuando la aplicación enlaza una variable a un conjunto de resultados columna, se describe esa variable: dirección, tipo de datos etc., para el controlador. El controlador almacena esta información en la estructura se mantiene para esa instrucción y usa la información para devolver el valor de la columna cuando se captura la fila.  
  
 Esta sección contiene los temas siguientes.  
  
-   [Columnas del conjunto de resultados de enlace](../../../odbc/reference/develop-app/binding-result-set-columns.md)  
  
-   [Uso de SQLBindCol](../../../odbc/reference/develop-app/using-sqlbindcol.md)

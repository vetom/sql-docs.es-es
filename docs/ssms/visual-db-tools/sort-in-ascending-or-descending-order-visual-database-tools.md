---
title: Ordenar en orden ascendente o descendente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1323343c3328e90f35cbb61afc0b617d6ac3765d
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a>Ordenar en orden ascendente o descendente (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Puede ordenar los resultados de la consulta en orden ascendente o descendente en una o más columnas del conjunto de resultados utilizando las palabras clave **ASC** o **DESC** con la cláusula **ORDER BY** .  
  
> [!NOTE]  
> La secuencia de intercalación de la columna determina en parte el criterio de ordenación. La secuencia de intercalación se puede modificar en el [cuadro de diálogo Intercalación](../../ssms/visual-db-tools/collation-dialog-box-visual-database-tools.md).  
  
El procedimiento siguiente asume que en el Diseñador de consultas y vistas hay una consulta abierta que utiliza la cláusula ORDER BY para ordenar una o más columnas.  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a>Para especificar o cambiar el criterio de ordenación de los resultados  
  
1.  En el [panel Criterios](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md), haga clic en el campo **Tipo de orden** de la columna que desea reordenar.  
  
2.  Elija **Ascendente** o **Descendente** para especificar el criterio de ordenación de la columna.  
  
Observe que cuando se trabaja en el panel Criterios, la cláusula UNION de la consulta cambia para coincidir con las acciones más recientes.  
  
> [!NOTE]  
> Al ordenar los resultados por más de una columna, especifique el orden de prioridad que se seguirá al realizar búsquedas en las columnas utilizando la columna Criterio de ordenación. Para más información, consulte [Ordenar varias columnas en las consultas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/sort-multiple-columns-in-queries-visual-database-tools.md).  
  
## <a name="see-also"></a>Ver también  
[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
  

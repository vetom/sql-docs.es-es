---
title: Orígenes de datos ODBC subclave | Documentos de Microsoft
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
- subkeys [ODBC], for data sources
- data sources [ODBC], subkeys
- registry entries for data sources [ODBC], subkeys
ms.assetid: 0a8ccb80-c573-4418-84e5-f04a2b0e2ac1
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: bbe6d0e7e424f2bea8d90eb4e9c5993f50370848
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="odbc-data-sources-subkey"></a>Subclave de orígenes de datos ODBC
Los valores bajo la subclave de orígenes de datos ODBC enumeran los orígenes de datos. El formato de estos valores es como se muestra en la tabla siguiente.  
  
|Nombre|Tipo de datos|data|  
|----------|---------------|----------|  
|*nombre del origen de datos*|REG_SZ|*Descripción del controlador*|  
  
 El *nombre de origen de datos* valor está definido por el programa de administración (que normalmente se pide al usuario para él), y *descripción del controlador* definido por el programador del controlador (suele ser el nombre de la DBMS asociado con el controlador).  
  
 Por ejemplo, suponga que se han definido tres orígenes de datos: inventario, que usa SQL Server; Nómina, que utiliza dBASE; y personal, archivos de texto de formato que utiliza. Los valores bajo la subclave de orígenes de datos ODBC podrían ser el siguiente:  
  
```  
Inventory : REG_SZ : SQL Server  
Payroll : REG_SZ : dBASE  
Personnel : REG_SZ : Text  
```

---
title: GETDATE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.service: ''
ms.component: expressions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
caps.latest.revision: 35
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 29c3f28f3efa22a1691cc47e105300e7dd92543e
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="getdate-ssis-expression"></a>GETDATE (expresión de SSIS)
  Devuelve la fecha actual del sistema con formato DT_DBTIMESTAMP. La función GETDATE no tiene argumentos.  
  
> [!NOTE]  
>  El resultado devuelto de la función GETDATE tiene una longitud de 29 caracteres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a>Argumentos  
 None  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_DBTIMESTAMP  
  
## <a name="expression-examples"></a>Ejemplos de expresiones  
 Este ejemplo devuelve el año de la fecha actual.  
  
```  
DATEPART("year",GETDATE())  
```  
  
 Este ejemplo devuelve el número de días entre una fecha de la columna **ModifiedDate** y la fecha actual.  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 Este ejemplo agrega tres meses a la fecha actual.  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a>Ver también  
 [GETUTCDATE &#40;expresión de SSIS&#41;](../../integration-services/expressions/getutcdate-ssis-expression.md)   
 [Funciones &#40;expresión de SSIS&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  

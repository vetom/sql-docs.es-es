---
title: '&lt;(Menor que) (DMX) | Documentos de Microsoft'
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- less than (<)
- < (less than operator)
ms.assetid: 61d257ce-7ffd-4124-a795-49e5f8a6d72f
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: e4583c095c2507f13be0d23904d97f5100d2f63d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2018
---
# <a name="lt-less-than-dmx"></a>&lt;(Menor que) (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Realiza una operación de comparación que determina si el valor de una expresión DMX (Extensiones de minería de datos) es menor que el valor de otra expresión DMX.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
DMX_Expression < DMX_Expression  
```  
  
#### <a name="parameters"></a>Parámetros  
 *DMX_Expression*  
 Expresión DMX válida.  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor booleano que contiene TRUE si ambos parámetros son no NULL y el valor del primer parámetro es menor que el valor del segundo parámetro. El valor booleano contiene FALSE si ambos parámetros son no NULL y el valor del primer parámetro es igual o mayor que el valor del segundo parámetro. El valor booleano contiene un valor NULL si uno de los parámetros o ambos parámetros se evalúan como un valor NULL.  
  
## <a name="see-also"></a>Vea también  
 [Operadores de comparación &#40; DMX &#41;](../dmx/operators-comparison.md)   
 [Extensiones de minería de datos &#40; DMX &#41; Referencia de operadores](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Operadores &#40; DMX &#41;](../dmx/operators-dmx.md)  
  
  

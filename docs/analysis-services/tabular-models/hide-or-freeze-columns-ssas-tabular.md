---
title: Ocultar o Inmovilizar columnas | Documentos de Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 05503ab615b5f22bfd8a6dfd94144648659d4a26
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2018
---
# <a name="hide-or-freeze-columns"></a>Ocultar o Inmovilizar columnas 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
Si en el diseñador de modelos hay columnas que no desea mostrar en una tabla, puede ocultarlas temporalmente. Si oculta una columna, dispone de más espacio en la pantalla para agregar columnas nuevas o para trabajar solo con las columnas de datos pertinentes. Puede ocultar y mostrar columnas desde el menú **Columna** del diseñador de modelos y desde el menú contextual disponible en cada encabezado de columna. Para mantener visible un área de un modelo mientras se desplaza a otra área del modelo, puede inmovilizar columnas específicas para bloquearlas.  
  
> [!IMPORTANT]  
>  La capacidad de ocultar columnas no tiene como finalidad la seguridad de los datos; solo pretende simplificar y acortar la lista de columnas visibles en el diseñador de modelos o en los informes. Para proteger los datos, puede definir roles de seguridad. Los roles solo pueden restringir los metadatos y los datos visibles a los objetos definidos en el rol. Para obtener más información, consulte [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md).  
  
 A la hora de ocultar una columna, tiene la opción de ocultarla mientras trabaja en el diseñador de modelos o en los informes. Si oculta todas las columnas, la tabla aparece vacía en su totalidad en el Diseñador de modelos.  
  
> [!NOTE]  
>  Si necesita ocultar muchas columnas, puede crear una perspectiva en lugar de ocultarlas y mostrarlas. Una perspectiva es una vista personalizada de los datos que facilita el trabajo con subconjuntos de datos relacionados. Para obtener más información, vea [crear y administrar perspectivas](../../analysis-services/tabular-models/create-and-manage-perspectives-ssas-tabular.md)  
  
### <a name="to-hide-an-individual-column"></a>Para ocultar una sola columna  
  
1.  En el diseñador de modelos, seleccione la tabla que contenga la columna que desee ocultar.  
  
2.  Haga clic con el botón derecho en la columna, haga clic en **Ocultar columnas**y, después, haga clic en **Desde el Diseñador e Informes**, **Desde informes**o **Desde diseñador**.  
  
### <a name="to-hide-multiple-columns"></a>Para ocultar varias columnas  
  
1.  En el diseñador de modelos, seleccione la tabla que contenga las columnas que desee ocultar.  
  
2.  Haga clic en el menú **Columnas** y, a continuación, en **Ocultar y mostrar**.  
  
3.  En el cuadro de diálogo **Ocultar y mostrar columnas** , busque cada columna que desee ocultar y, a continuación, anule la selección de una de las opciones **En diseñador** y **En informes**, o ambas.  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="to-freeze-columns"></a>Para inmovilizar columnas  
  
1.  En el diseñador de modelos, seleccione la tabla que contenga las columnas que desee inmovilizar.  
  
2.  Seleccione las columnas que desee inmovilizar.  
  
3.  Haga clic en el menú **Columnas** y, a continuación, en **Inmovilizar**.  
  
    > [!NOTE]  
    >  Cuando se inmovilizan columnas, estas se mueven a la izquierda (o delante) de la tabla en el diseñador. Cuando se libera una columna, esta no recupera su ubicación original.  
  
## <a name="see-also"></a>Vea también  
 [Tablas y columnas](../../analysis-services/tabular-models/tables-and-columns-ssas-tabular.md)   
 [Perspectivas](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
  
  

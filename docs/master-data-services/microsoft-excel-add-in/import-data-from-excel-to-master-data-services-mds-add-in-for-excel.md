---
title: Importación de datos de Excel en Master Data Services (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.service: ''
ms.component: microsoft-excel-add-in
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
caps.latest.revision: 10
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: af930e9254d5f38533f15431b421fdf5e6bd8e61
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="import-data-from-excel-to-master-data-services-mds-add-in-for-excel"></a>Importación de datos de Excel en Master Data Services (complemento MDS para Excel)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], puede publicar los datos en el repositorio MDS cuando termine de trabajar en Excel y desee guardar los cambios para que otros usuarios tengan acceso a ellos.  
  
> [!NOTE]  
>  -   Al publicar los cambios, se eliminan los comentarios de las celdas administradas por MDS.  
> -   Una fórmula no se admite en una celda administrada por MDS. Una fórmula en una celda administrada por MDS se trata como un valor de texto.  
  
## <a name="prerequisites"></a>Prerequisites  
 Para realizar este procedimiento:  
  
-   Debe disponer de permiso de acceso al área funcional **Explorador** .  
  
-   La hoja de cálculo activa debe contener datos administrados por MDS y debe haber realizado cambios o adiciones a los datos administrados por MDS.  
  
-   Si agrega miembros, no tiene que especificar un valor de **Código** si los códigos para la entidad se generan automáticamente. Para obtener más información, consulte [Creación automática de código &#40;Master Data Services&#41;](../../master-data-services/automatic-code-creation-master-data-services.md).  
  
### <a name="to-publish-data-to-the-mds-repository"></a>Publicar datos en el repositorio MDS  
  
1.  En el grupo **Publicar y validar** , haga clic en **Publicar**.  
  
2.  Opcional. Si aparece el cuadro de diálogo **Publicar y anotar** , elija compartir la misma anotación (comentario) para todas las actualizaciones o anotar cada cambio de forma individual.  
  
3.  Opcional. Active la casilla **No volver a mostrar este cuadro de diálogo** . Puede mostrar siempre el cuadro de diálogo en el futuro si elije **Configuración** y activa la casilla **Mostrar el cuadro de diálogo Publicar y anotar al publicar** .  
  
4.  Haga clic en **Publicar**.  
  
> [!NOTE]  
>  Si agrega nuevos miembros (filas) en la hoja de cálculo y no puede publicarlos correctamente en el repositorio MDS, es posible que no tenga el permiso **Actualizar** para todos los atributos de la hoja de cálculo. En la pestaña **Revisar** , en el grupo **Cambios** , haga clic en **Desproteger hoja** e intente publicarla de nuevo.  
  
## <a name="next-steps"></a>Next Steps  
 [Aplicar reglas de negocios &#40;complemento MDS para Excel&#41;](../../master-data-services/microsoft-excel-add-in/apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a>Ver también  
 [Información general: Importación de datos desde Excel &#40;complemento MDS para Excel&#41;](../../master-data-services/microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md)   
 [Validar datos &#40;complemento MDS para Excel&#41;](../../master-data-services/microsoft-excel-add-in/validating-data-mds-add-in-for-excel.md)  
  
  

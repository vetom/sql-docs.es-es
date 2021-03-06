---
title: Iniciar el Generador de informes | Microsoft Docs
ms.custom: 
ms.date: 05/30/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.service: 
ms.component: report-builder
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Report Builder, launching
- launching Report Builder
- SharePoint integration [Reporting Services], starting Report Builder
- starting Report Builder
ms.assetid: 8c8c7d2e-b315-418d-bf65-90e7685e4259
caps.latest.revision: "56"
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 53fba534d61d2fe1a1358daa1571ec66a1fab663
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="start-report-builder"></a>Iniciar el Generador de informes

[!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] es un entorno de creación de informes independiente. Con él, puede crear informes paginados y publicarlos en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instalado en modo nativo o modo integrado de SharePoint.  
  
 La primera vez que inicie [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] desde el portal web de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en el modo integrado de SharePoint, se le pedirá que lo descargue del Centro de descarga de Microsoft. 
 
![generador-informes-obtener-generador-informes](../../reporting-services/report-builder/media/report-builder-get-report-builder.png) 
 
 El usuario o un administrador también pueden [instalar el Generador de informes en el equipo desde el Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=219138). Vea "Instalación con Systems Manager Server" en [Instalar el Generador de informes](../../reporting-services/install-windows/install-report-builder.md) para obtener más detalles.
 
 [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] no se instala al instalar SQL Server Reporting Services; debe descargarlo e instalarlo por separado.  
  
 Al iniciar [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] desde el portal web o un sitio de SharePoint, si una versión anterior de [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] se abre, póngase en contacto con el administrador, que puede actualizar la versión en el portal web o en un sitio de SharePoint.  
  
## <a name="to-start-includessrbnoversionincludesssrbnoversion-mdmd-from-the-includessrsnoversionincludesssrsnoversion-mdmd-web-portal"></a>Para iniciar [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] desde el portal web de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
1.  En el explorador web, escriba la dirección URL del servidor de informes en la barra de direcciones. De forma predeterminada, la dirección URL es http://\<*nombreDeServidor*>/reports.  
  
2.  En la barra superior del portal web, seleccione **Nuevo** > **Informe paginado**.  
  
     ![PBI_SSMRP_NewMenu](../../reporting-services/mobile-reports/media/pbi-ssmrp-newmenu.png "PBI_SSMRP_NewMenu")  
  
     La primera vez, se le pedirá que [instale el Generador de informes](../../reporting-services/install-windows/install-report-builder.md). 
  
     Después de esta primera vez, [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] se abre y puede crear un informe paginado o abrir uno en el servidor de informes.  
  
## <a name="to-start-includessrbnoversionincludesssrbnoversion-mdmd-in-sharepoint-integrated-mode"></a>Para iniciar [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] en el modo integrado de SharePoint  
  
1.  Navegue al sitio de SharePoint que contenga la biblioteca que desee.  
  
2.  Abra la biblioteca.  
  
3.  Haga clic en **Documentos**.  
  
4.  En el menú **Nuevo documento** , haga clic en **Informe del Generador de informes**.  
  
     La primera vez, se inicia el Asistente para el [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] de SQL Server. Vea [Install Report Builder](../../reporting-services/install-windows/install-report-builder.md) para obtener más detalles.  
  
     [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion-md.md)] se abre y puede crear un informe paginado o abrir un informe en el servidor de informes.  
  
     **Nota** Si en el menú **Nuevo documento** no aparecen las opciones **Informe del Generador de informes**, **Modelo del Generador de informes**u **Origen de datos de informe**, será necesario agregar sus tipos de contenido a la biblioteca de SharePoint. Para obtener más información, vea [Add Reporting Services Content Types to a SharePoint Library (Agregar los tipos de contenido de Reporting Services a una biblioteca de SharePoint)](../../reporting-services/report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md).  

## <a name="next-steps"></a>Pasos siguientes

[Generador de informes en SQL Server 2016](../../reporting-services/report-builder/report-builder-in-sql-server-2016.md)   
[Establecimiento de opciones predeterminadas para el Generador de informes](../../reporting-services/report-builder/set-default-options-for-report-builder.md)  

¿Tiene alguna pregunta más? [Puede plantear sus dudas en el foro de Reporting Services](http://go.microsoft.com/fwlink/?LinkId=620231).

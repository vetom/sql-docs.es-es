---
title: Descargar SQL Server Data Tools (SSDT) | Microsoft Docs
ms.custom: 
ms.date: 03/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssdt
ms.tgt_pltfrm: 
ms.topic: article
keywords:
- "instalar ssdt, descargar ssdt, ssdt más reciente"
ms.assetid: b0fc4987-d260-4d0a-9dd1-98099835b361
caps.latest.revision: 113
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 681ad2f6d7aeb88db45dde3f2e695db672b97dbd
ms.lasthandoff: 04/11/2017

---
# <a name="download-sql-server-data-tools-ssdt"></a>Descargar SQL Server Data Tools (SSDT)

**[SQL Server Data Tools](https://msdn.microsoft.com/mt186501)** es una herramienta de desarrollo moderna que puede descargar de forma gratuita para crear bases de datos relacionales de SQL Server, bases de datos SQL de Azure, paquetes de Integration Services, modelos de datos de Analysis Services e informes de Reporting Services. Gracias a SSDT, puede diseñar e implementar cualquier tipo de contenido de SQL Server con la misma facilidad con la que desarrollaría una aplicación en Visual Studio. Esta versión es compatible con las versiones comprendidas entre SQL Server 2005 y SQL Server 2016, y ofrece el entorno de diseño necesario para agregar características nuevas de SQL Server 2016.  
    
    
| ![descarga](../ssdt/media/download.png) Descargar SQL Server Data Tools para Visual Studio 2015  | Descargar Data-Tier Application Framework (DacFx) ||
|:---|:---|:---|
|**[Descargar SQL Server Data Tools (16.5)](https://msdn.microsoft.com/mt186501)**|[**Descargar DacFx y SqlPackage.exe (16.5)**](https://www.microsoft.com/download/details.aspx?id=54106) |Versión de disponibilidad general actual para su uso en producción.|
|[**Descargar SQL Server Data Tools: versión candidata para lanzamiento**](../ssdt/sql-server-data-tools-ssdt-release-candidate.md)| [**Descargar DacFx y SqlPackage.exe: versión candidata para lanzamiento**](../ssdt/sql-server-data-tools-ssdt-release-candidate.md) |Incluye compatibilidad con SQL Server vNext.|



## <a name="download-visual-studio"></a>Descargar Visual Studio

* [**Descargar Visual Studio Community 2015**](https://www.visualstudio.com/products/visual-studio-community-vs.aspx)

### <a name="use-ssdt-in-visual-studio-2017"></a>Usar SSDT en Visual Studio 2017

* [**Descargar Visual Studio 2017**](https://www.visualstudio.com/) ([comparar las características de Visual Studio 2017 por edición](https://www.visualstudio.com/vs/compare/))

Para usar los proyectos de bases de datos relacionales, se recomienda comprobar la carga de trabajo de **procesamiento y almacenamiento de datos** durante la instalación. También se incluye la compatibilidad con proyectos de bases de datos de SSDT en varias otras cargas de trabajo, las que incluyen *Azure*, *ASP.Net y Desarrollo web* y *Desarrollo multiplataforma de .NET Core*.

Si usa SSDT con Visual Studio 2017, instale los componentes de AS y RS:
* [Analysis Services](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects)
* [Reporting Services](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio)


## <a name="installing-ssdt-without-visual-studio-pre-installed"></a>Instalación de SSDT sin Visual Studio instalado previamente

Si no tiene Visual Studio instalado en la máquina, al instalar SSDT para Visual Studio 2015 también se instalará una versión mínima de "shell integrado" de Visual Studio 2015. La instalación de esta versión de Visual Studio es gratuita y se puede usar en tantas máquinas como quiera. Proporciona todos los tipos de proyecto de SQL Server, además del Explorador de objetos de SQL Server y otras experiencias de herramientas de SQL.

Si tiene [Visual Studio 2015 Community Edition (o superior)](https://www.visualstudio.com/products/visual-studio-community-vs.aspx) instalado en su máquina, al instalar SSDT se agregará el conjunto completo de herramientas de SQL Server en la instalación de Visual Studio existente. Visual Studio incluye numerosas características que podrían interesarle, como la integración del control de código fuente y la compatibilidad con lenguajes que no son SQL. Se recomienda usar Visual Studio 2015 Community o posterior para obtener la mejor experiencia de desarrollo de T-SQL.

## <a name="supported-sql-versions"></a>Versiones de SQL admitidas
  
|Plantillas de proyectos|Plataformas SQL compatibles|  
|-------------------|--------------------|  
Bases de datos relacionales|  SQL Server 2005* - SQL Server 2016 <br /><br />Base de datos SQL de Azure<br /><br />Azure SQL Data Warehouse (solo admite consultas, todavía no se admiten proyectos de base de datos)<br /><br />  * La compatibilidad con SQL Server 2005 está en desuso,<br /><br /> Cambie a una versión de SQL oficialmente compatible.|
  |Modelos de Analysis Services<br /><br />Informes de Reporting Services | SQL Server 2008 - SQL Server 2016|
  |paquetes de Integration Services| SQL Server 2012 - SQL Server 2016    |
  
## <a name="next-steps"></a>Pasos siguientes  
Después de instalar SSDT, siga estos tutoriales para aprender a crear bases de datos, paquetes, modelos de datos e informes mediante SSDT:  
  
-   [Desarrollo de bases de datos sin conexión orientado a proyectos](https://msdn.microsoft.com/library/hh272702(v=vs.103).aspx)  
  
-   [Tutorial de SSIS: Crear un paquete ETL sencillo](https://msdn.microsoft.com/library/ms169917.aspx)  
  
-   [Tutoriales de Analysis Services (SSAS)](https://msdn.microsoft.com/library/hh231701.aspx)  
  
-   [Crear un informe de tabla básico (Tutorial de SSRS)](https://msdn.microsoft.com/library/ms167305.aspx)  
  
## <a name="see-also"></a>Vea también  
[Herramientas de datos de SQL Server](https://msdn.microsoft.com/library/hh272686(v=vs.103).aspx)  
[Foro MSDN de SSDT](https://social.msdn.microsoft.com/Forums/sqlserver/home?forum=ssdt)  
[Blog del equipo de SSDT](http://blogs.msdn.com/b/ssdt/)  
[Comentarios Connect sobre SSDT](https://connect.microsoft.com/SQLServer/Feedback)  
[Documentación de SSDT](https://msdn.microsoft.com/library/hh272686(v=vs.103).aspx)  
[Referencia de la API de DACFx](https://msdn.microsoft.com/library/dn645454.aspx)  
[Descarga de SQL Server Management Studio (SSMS)](../ssms/download-sql-server-management-studio-ssms.md)  

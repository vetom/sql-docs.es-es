---
title: Base de datos ReadWriteModes | Documentos de Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases [Analysis Services], read/write
- databases [Analysis Services], read-only
ms.assetid: 03d7cb5c-7ff0-4e15-bcd2-7075d1b0dd69
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: ea794ce008d5e7acc6aa01a23b8ca7629546efc0
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
# <a name="database-readwritemodes"></a>Modos de la propiedad de base de datos ReadWriteMode
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Con frecuencia, se producen situaciones en las que un administrador de base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quiere cambiar una base de datos de lectura y escritura a una base de datos de solo lectura o viceversa. Estas situaciones suelen responder a necesidades empresariales, como compartir la misma carpeta de base de datos entre varios servidores para la ampliación horizontal de una solución y la mejora del rendimiento. En estos casos, la propiedad de base de datos **ReadWriteMode** permite al administrador de bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cambiar con facilidad el modo de funcionamiento de la base de datos.  
  
## <a name="readwritemode-database-property"></a>Propiedad de base de datos ReadWriteMode  
 La propiedad de base de datos **ReadWriteMode** especifica si la base de datos está en modo de lectura y escritura o en modo de solo lectura. Éstos son los dos únicos valores posibles de la propiedad. Cuando la base de datos está en modo de solo lectura, no puede aplicársele ningún cambio ni actualización. Sin embargo, cuando está en modo de lectura/escritura, se pueden producir cambios y actualizaciones. La propiedad de base de datos **ReadWriteMode** se define como una propiedad de solo lectura (solo se puede establecer con un comando **Attach** ).  
  
 Cuando una base de datos está en modo de solo lectura, se le aplican ciertas restricciones que afectan al conjunto ordinario de operaciones permitidas en la base de datos. Consulte la tabla siguiente para conocer las operaciones restringidas.  
  
|Modo ReadOnly|Operaciones restringidas|  
|-------------------|---------------------------|  
|Comandos XML/A<br /><br /> <br /><br /> Nota: Se produce un error al ejecutar cualquiera de estos comandos.|**Crear**<br /><br /> **Alter**<br /><br /> **Delete**<br /><br /> **Procesar**<br /><br /> **MergePartitions**<br /><br /> **DesignAggregations**<br /><br /> **CommitTransaction**<br /><br /> **Restore**<br /><br /> **Sincronizar**<br /><br /> **Insert**<br /><br /> **Update**<br /><br /> **Drop**<br /><br /> <br /><br /> Nota: La reescritura de celda está permitida en las bases de datos configuradas como de solo lectura; sin embargo, los cambios no se pueden confirmar.|  
|Instrucciones MDX<br /><br /> <br /><br /> Nota: Se produce un error al ejecutar cualquiera de estas instrucciones.|**COMMIT TRAN**<br /><br /> **CREATE SESSION CUBE**<br /><br /> **ALTER CUBE**<br /><br /> **ALTER DIMENSION**<br /><br /> **CREATE DIMENSION MEMBER**<br /><br /> **DROP DIMENSION MEMBER**<br /><br /> **ALTER DIMENSION**<br /><br /> <br /><br /> Nota: Los usuarios de Excel no pueden utilizar la característica de agrupación en las tablas dinámicas porque esa característica se implementa internamente utilizando los comandos **CREATE SESSION CUBE** .|  
|Instrucciones DMX<br /><br /> <br /><br /> Nota: Se produce un error al ejecutar cualquiera de estas instrucciones.|**CREATE [SESSION] MINING STRUCTURE**<br /><br /> **ALTER MINING STRUCTURE**<br /><br /> **DROP MINING STRUCTURE**<br /><br /> **CREATE [SESSION] MINING MODEL**<br /><br /> **DROP MINING MODEL**<br /><br /> **IMPORT**<br /><br /> **SELECT INTO**<br /><br /> **INSERT**<br /><br /> **UPDATE**<br /><br /> **DELETE**|  
|Operaciones en segundo plano|Se deshabilita cualquier operación en segundo plano que pueda modificar la base de datos. Esto incluye el procesamiento diferido y el almacenamiento en caché automático.|  
  
## <a name="readwritemode-usage"></a>Uso de ReadWriteMode  
 La propiedad de base de datos **ReadWriteMode** debe utilizarse como parte de un comando de base de datos **Attach** . El comando **Attach** permite establecer la propiedad de base de datos en **ReadWrite** o **ReadOnly**. El valor de la propiedad de base de datos **ReadWriteMode** no se puede actualizar directamente porque la propiedad está definida como de solo lectura. Las bases de datos se crean con la propiedad **ReadWriteMode** establecida en **ReadWrite**. No es posible crear una base de datos en modo de solo lectura.  
  
 Para cambiar la propiedad de base de datos **ReadWriteMode** entre **ReadWrite** y **ReadOnly**, necesita emitir una secuencia de comandos **Detach/Attach** .  
  
 Con la excepción de **Attach**, todas las operaciones de base de datos mantienen la propiedad de base de datos **ReadWriteMode** en su estado actual. Por ejemplo, operaciones como **Alter**, **Backup**, **Restore**y **Synchronize** conservan el valor de **ReadWriteMode** .  
  
> [!NOTE]  
>  Se pueden crear cubos locales a partir de una base de datos de solo lectura.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.AnalysisServices.Database.Detach%2A>   
 [Adjuntar y separar bases de datos de Analysis Services](../../analysis-services/multidimensional-models/attach-and-detach-analysis-services-databases.md)   
 [Mover una base de datos de Analysis Services](../../analysis-services/multidimensional-models/move-an-analysis-services-database.md)   
 [Elemento Detach](../../analysis-services/xmla/xml-elements-commands/detach-element.md)   
 [Elemento Attach](../../analysis-services/xmla/xml-elements-commands/attach-element.md)  
  
  

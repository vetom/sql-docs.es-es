---
title: Propiedades personalizadas de archivo plano | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.service: ''
ms.component: data-flow
ms.reviewer: ''
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5d94a8d758255f4b17f1f2e6fedb10344205ceee
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="flat-file-custom-properties"></a>Propiedades personalizadas de archivo plano
  **Propiedades personalizadas de origen**  
  
 El origen de archivo plano tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.  
  
 En la tabla siguiente se describen las propiedades personalizadas del origen de archivo plano. Todas las propiedades son de lectura y escritura.  
  
|Nombre de propiedad|Tipo de datos|Description|  
|-------------------|---------------|-----------------|  
|FileNameColumnName|String|Nombre de una columna de salida que contiene el nombre de archivo. Si no se especifica ningún nombre, se generará ninguna columna de salida que contenga el nombre de archivo.<br /><br /> Nota: Esta propiedad no está disponible en el **Editor de origen de archivos planos**, pero se puede establecer mediante el **Editor avanzado**.|  
|RetainNulls|Boolean|Valor que especifica si retener los valores Null del archivo de origen como tales cuando el motor de canalización de transformación de datos procesa los datos. El valor predeterminado de esta propiedad es **False**.|  
  
 La salida del origen de archivo plano no tiene ninguna propiedad personalizada.  
  
 En la tabla siguiente se describen las propiedades personalizadas de las columnas de salida del origen de archivo plano. Todas las propiedades son de lectura y escritura.  
  
|Nombre de propiedad|Tipo de datos|Description|  
|-------------------|---------------|-----------------|  
|FastParse|Boolean|Valor que indica si la columna usa las rutinas de análisis más rápidas que no distinguen la configuración regional y permiten un análisis rápido que DTS proporciona, o las rutinas de análisis estándar que sí distinguen la configuración regional. Para obtener más información, consulte [Fast Parse](http://msdn.microsoft.com/library/6688707d-3c5b-404e-aa2f-e13092ac8d95) y [Standard Parse](http://msdn.microsoft.com/library/dfe835b1-ea52-4e18-a23a-5188c5b6f013). El valor predeterminado de esta propiedad es **False**.<br /><br /> Nota: Esta propiedad no está disponible en el **Editor de origen de archivos planos**, pero se puede establecer mediante el **Editor avanzado**.|  
  
 Para más información, consulte [Flat File Source](../../integration-services/data-flow/flat-file-source.md).  
  
 **Propiedades personalizadas de los destinos**  
  
 El destino de archivo plano tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.  
  
 En la tabla siguiente se describen las propiedades personalizadas del destino Archivo plano. Todas las propiedades son de lectura y escritura.  
  
|Nombre de propiedad|Tipo de datos|Description|  
|-------------------|---------------|-----------------|  
|Encabezado|String|Bloque de texto que se inserta en el archivo antes de que se escriban datos.<br /><br /> Puede especificar el valor de esta propiedad con una expresión de propiedad.|  
|Sobrescribir|Boolean|Valor que especifica si sobrescribir o anexar a un archivo de destino existente que tiene el mismo nombre. El valor predeterminado de esta propiedad es **True**.|  
  
 La entrada y las columnas de entrada del destino de archivo plano no tienen ninguna propiedad personalizada.  
  
 Para más información, consulte [Flat File Destination](../../integration-services/data-flow/flat-file-destination.md).  
  
## <a name="see-also"></a>Ver también  
 [Common Properties](http://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
  

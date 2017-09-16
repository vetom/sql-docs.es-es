---
title: FULLTEXTCATALOGPROPERTY (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- FULLTEXTCATALOGPROPERTY_TSQL
- FULLTEXTCATALOGPROPERTY
dev_langs:
- TSQL
helpviewer_keywords:
- full-text catalogs [SQL Server], properties
- FULLTEXTCATALOGPROPERTY function
- status information [SQL Server], full-text catalogs
ms.assetid: f841dc79-2044-4863-aff0-56b8bb61f250
caps.latest.revision: 50
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 383eafdda02f402d1c398183bfedac6dde85d9ce
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="fulltextcatalogproperty-transact-sql"></a>FULLTEXTCATALOGPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Devuelve información acerca de las propiedades de catálogo de texto completo de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
FULLTEXTCATALOGPROPERTY ('catalog_name' ,'property')  
```  
  
## <a name="arguments"></a>Argumentos  
  
> [!NOTE]  
>  Las siguientes propiedades se quitará en futuras versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **LogSize** y **PopulateStatus**. Evite el uso de estas propiedades en nuevos trabajos de desarrollo y piense en modificar las aplicaciones que las usan actualmente.  
  
 *Catalog_Name*  
 Es una expresión que contiene el nombre del catálogo de texto completo.  
  
 *propiedad*  
 Es una expresión que contiene el nombre de la propiedad del catálogo de texto completo. La tabla presenta las propiedades y proporciona descripciones de la información que se devuelve.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|**AccentSensitivity**|Opción de distinción de acentos.<br /><br /> 0 = No distinguir acentos<br /><br /> 1 = Distinguir acentos|  
|**IndexSize**|Tamaño lógico del catálogo de texto completo en megabytes (MB). Incluye el tamaño de los índices semánticos de similitud de documentos y frases clave.<br /><br /> Para obtener más información, vea la sección "Comentarios" más adelante en este tema.|  
|**ItemCount**|Número de elementos indizados que incluyen todos los índices de similitud de documentos, frases clave y texto completo en un catálogo|  
|**LogSize**|Se admite únicamente por compatibilidad con versiones anteriores. Siempre devuelve 0.<br /><br /> Tamaño, en bytes, del conjunto combinado de los registros de errores asociados a un catálogo de texto completo de los servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Search.|  
|**MergeStatus**|Si hay una combinación maestra en curso.<br /><br /> 0 = La mezcla principal no está en curso.<br /><br /> 1 = La mezcla principal está en curso.|  
|**PopulateCompletionAge**|Diferencia, en segundos, entre la terminación del último rellenado del índice de texto completo y 01/01/1990 00:00:00.<br /><br /> Solo se actualiza para rastreos completos e incrementales. Devuelve 0 si no se ha producido ningún rellenado.|  
|**PopulateStatus**|0 = Inactivo<br /><br /> 1 = Rellenado completo en curso<br /><br /> 2 = En pausa<br /><br /> 3 = Acelerado<br /><br /> 4 = En recuperación<br /><br /> 5 = Apagado<br /><br /> 6 = Rellenado incremental en curso<br /><br /> 7 = Generación del índice<br /><br /> 8 = El disco está lleno. En pausa.<br /><br /> 9 = Seguimiento de cambios|  
|**UniqueKeyCount**|Número de claves únicas en el catálogo de texto completo.|  
|**ImportStatus**|Si se va a importar el catálogo de texto completo.<br /><br /> 0 = Si no se va a importar el catálogo de texto completo.<br /><br /> 1 = Si se va a importar el catálogo de texto completo.|  
  
## <a name="return-types"></a>Tipos devueltos  
 **int**  
  
## <a name="exceptions"></a>Excepciones  
 Devuelve NULL si se produce un error o si el autor de la llamada no tiene permiso para ver el objeto.  
  
 En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], un usuario solo puede ver los metadatos de elementos protegibles que posea o para los que se le haya concedido permiso. Esto significa que las funciones integradas de emisión de metadatos, como FULLTEXTCATALOGPROPERTY, pueden devolver NULL si el usuario no tiene ningún permiso para el objeto. Para obtener más información, vea [sp_help_fulltext_catalogs &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-help-fulltext-catalogs-transact-sql.md).  
  
## <a name="remarks"></a>Comentarios  
 FULLTEXTCATALOGPROPERTY ('*catalog_name*','**IndexSize**') solo mira en fragmentos con el estado 4 ó 6 tal y como se muestra en [sys.fulltext_index_fragments](../../relational-databases/system-catalog-views/sys-fulltext-index-fragments-transact-sql.md). Estos fragmentos forman parte del índice lógico. Por lo tanto, la **IndexSize** propiedad devuelve solo el tamaño del índice lógico. Sin embargo, durante una mezcla de índice, el tamaño de índice real podría ser el doble de su tamaño lógico. Para buscar el tamaño real utilizado por un índice de texto completo durante una combinación, use la [sp_spaceused](../../relational-databases/system-stored-procedures/sp-spaceused-transact-sql.md) procedimiento almacenado del sistema. Ese procedimiento mira en todos los fragmentos asociados a un índice de texto completo. Si limita el crecimiento del archivo de catálogo de texto completo y no permite suficiente espacio para el proceso de mezcla, el relleno de texto completo puede producir un error. En este caso, FULLTEXTCATALOGPROPERTY ('catalog_name' ,'IndexSize') devuelve 0 y se escribe el error siguiente en el registro de texto completo:  
  
 `Error: 30059, Severity: 16, State: 1. A fatal error occurred during a full-text population and caused the population to be cancelled. Population type is: FULL; database name is FTS_Test (id: 13); catalog name is t1_cat (id: 5); table name t1 (id: 2105058535). Fix the errors that are logged in the full-text crawl log. Then, resume the population. The basic Transact-SQL syntax for this is: ALTER FULLTEXT INDEX ON table_name RESUME POPULATION.`  
  
 Es importante que las aplicaciones no esperan en un bucle ajustado, buscando la **PopulateStatus** propiedad esté inactivo (lo que indica que se ha completado el llenado) porque este proceso tarda ciclos de CPU fuera de la base de datos y de texto completo los procesos de búsqueda y los tiempos de espera de las causas. Además, suele ser una mejor opción para comprobar la correspondiente **PopulateStatus** propiedad en el nivel de tabla, **TableFullTextPopulateStatus** en la función del sistema OBJECTPROPERTYEX. Ésta y otras nuevas propiedades de texto completo en OBJECTPROPERTYEX proporcionan información más detallada sobre las tablas de indización de texto completo. Para obtener más información, vea [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](../../t-sql/functions/objectpropertyex-transact-sql.md).  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se devuelve el número de elementos de texto completo indizados que se encuentran en el catálogo de texto completo `Cat_Desc`.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT fulltextcatalogproperty('Cat_Desc', 'ItemCount');  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [FULLTEXTSERVICEPROPERTY &#40; Transact-SQL &#41;](../../t-sql/functions/fulltextserviceproperty-transact-sql.md)   
 [Funciones de metadatos &#40; Transact-SQL &#41;](../../t-sql/functions/metadata-functions-transact-sql.md)   
 [sp_help_fulltext_catalogs &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-catalogs-transact-sql.md)  
  
  
---
title: sp_help_fulltext_tables (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_fulltext_tables
- sp_help_fulltext_tables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_fulltext_tables
ms.assetid: 86e24a5f-a869-43f6-b83e-c52b7b01b5ff
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: daf707e38b2b543302abc21611aa95a242d71085
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="sphelpfulltexttables-transact-sql"></a>sp_help_fulltext_tables (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Devuelve una lista de tablas registradas para la indización de texto completo.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Use **sys.fulltext_indexes** vista de catálogo en su lugar. Para obtener más información, consulte [sys.fulltext_indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md).  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_help_fulltext_tables [ [ @fulltext_catalog_name = ] 'fulltext_catalog_name' ]   
     [ , [ @table_name = ] 'table_name' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@fulltext_catalog_name=**] **'***fulltext_catalog_name***'**  
 Es el nombre del catálogo de texto completo. *fulltext_catalog_name* es **sysname**, su valor predeterminado es null. Si *fulltext_catalog_name* se omite o es NULL, se devuelven todas las tablas indizadas de texto completo asociadas a la base de datos. Si *fulltext_catalog_name* se especifica, pero *table_name* se omite o es NULL, se recupera la información de índice de texto completo para cada tabla indizada de texto completo asociado a este catálogo. Si ambos *fulltext_catalog_name* y *table_name* se especifica, se devuelve una fila si *table_name* está asociado a *fulltext_catalog_name*; en caso contrario, se produce un error.  
  
 [  **@table_name=**] **'***table_name***'**  
 Es el nombre de tabla de una o dos partes para la que se solicitan los metadatos de texto completo. *table_name* es **nvarchar (517)**, su valor predeterminado es null. Si solo *table_name* se especifica, solo la fila relevante para *table_name* se devuelve.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**TABLE_OWNER**|**sysname**|Propietario de la tabla. Es el nombre del usuario de la base de datos que ha creado la tabla.|  
|**TABLE_NAME**|**sysname**|Nombre de la tabla.|  
|**FULLTEXT_KEY_INDEX_NAME**|**sysname**|Índice que impone la restricción UNIQUE a la columna designada como columna de clave única.|  
|**FULLTEXT_KEY_COLID**|**int**|Id. de columna del índice único que identifica FULLTEXT_KEY_NAME.|  
|**FULLTEXT_INDEX_ACTIVE**|**int**|Especifica si las columnas de esta tabla marcadas para indización de texto completo pueden utilizarse en consultas:<br /><br /> 0 = Inactivo <br /><br /> 1 = Activo|  
|**FULLTEXT_CATALOG_NAME**|**sysname**|Catálogo de texto completo en el que residen los datos de índice de texto completo.|  
  
## <a name="permissions"></a>Permissions  
 De forma predeterminada, los permisos de ejecución corresponden a los miembros del rol **public** .  
  
## <a name="examples"></a>Ejemplos  
 En este ejemplo se obtienen los nombres de las tablas con índice de texto completo asociadas al catálogo de texto completo `Cat_Desc`.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_help_fulltext_tables 'Cat_Desc';  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [INDEXPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/indexproperty-transact-sql.md)   
 [OBJECTPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/objectproperty-transact-sql.md)   
 [sp_fulltext_table &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-fulltext-table-transact-sql.md)   
 [sp_help_fulltext_tables_cursor &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-tables-cursor-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

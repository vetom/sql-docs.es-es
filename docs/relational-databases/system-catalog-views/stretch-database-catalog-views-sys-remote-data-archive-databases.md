---
title: Sys.remote_data_archive_databases (Transact-SQL) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-stretch
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.remote_data_archive_databases
- sys.remote_data_archive_databases_TSQL
- remote_data_archive_databases
- remote_data_archive_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.remote_data_archive_databases catalog view
ms.assetid: 25bffb0c-9821-40b4-88cf-75f854891a09
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b67f68c2208ab54cfa87a04db98d6e953a25ede0
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="stretch-database-catalog-views---sysremotedataarchivedatabases"></a>Ajustar las vistas de catálogo de base de datos - sys.remote_data_archive_databases
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Contiene una fila por cada base de datos remota que almacena los datos de una base de datos local habilitada para Stretch.  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**remote_database_id**|**int**|El identificador local generada automáticamente de la base de datos remota.|  
|**remote_database_name**|**sysname**|El nombre de la base de datos remota.|  
|**data_source_id**|**int**|El origen de datos utilizado para conectarse al servidor remoto|  
  
## <a name="see-also"></a>Vea también  
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  

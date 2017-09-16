---
title: DBCC CHECKALLOC (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 09/07/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CHECKALLOC_TSQL
- DBCC CHECKALLOC
- DBCC_CHECKALLOC_TSQL
- CHECKALLOC
dev_langs:
- TSQL
helpviewer_keywords:
- DBCC CHECKALLOC statement
- checking database space allocation
- database space allocation [SQL Server]
- consistency [SQL Server], disk space allocations
- space allocation [SQL Server]
- allocation checks
- disk space [SQL Server], allocation consistency checks
- space allocation [SQL Server], checking
ms.assetid: bc1218eb-ffff-44ce-8122-6e4fa7d68a79
caps.latest.revision: 76
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 05976158e43d7dfafaf02289462d1537f5beeb36
ms.openlocfilehash: 4cecbb77add5a9afbde3f69bf17ac2bd11bd592b
ms.contentlocale: es-es
ms.lasthandoff: 09/08/2017

---
# <a name="dbcc-checkalloc-transact-sql"></a>DBCC CHECKALLOC (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Comprueba la coherencia de las estructuras de asignación de espacio en disco de una base de datos determinada.
  
![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Sintaxis  
  
```sql
DBCC CHECKALLOC   
[  
    ( database_name | database_id | 0   
      [ , NOINDEX   
      | , { REPAIR_ALLOW_DATA_LOSS | REPAIR_FAST | REPAIR_REBUILD } ]  
    )  
    [ WITH   
        {   
          [ ALL_ERRORMSGS ]  
          [ , NO_INFOMSGS ]   
          [ , TABLOCK ]   
          [ , ESTIMATEONLY ]   
        }  
    ]  
]  
```  
  
## <a name="arguments"></a>Argumentos  
 *database_name* | *database_id* | 0   
 El nombre o el identificador de la base de datos que se va a comprobar el uso de la asignación y la página.
Si no se especifica o se especifica 0, se utiliza la base de datos actual.
Nombres de base de datos deben seguir las reglas para [identificadores](../../relational-databases/databases/database-identifiers.md).

 NOINDEX  
 Especifica que no se deben comprobar los índices no clúster de las tablas de usuario.<br>NOINDEX solo se mantiene por compatibilidad con versiones anteriores y no afecta a DBCC CHECKALLOC.

 REPAIR_ALLOW_DATA_LOSS \| REPAIR_FAST \| REPAIR_REBUILD  
 Especifica que DBCC CHECKALLOC repare los errores que encuentre. *database_name* debe estar en modo de usuario único.

 REPAIR_ALLOW_DATA_LOSS  
 Intenta reparar los errores encontrados. Estas reparaciones pueden ocasionar alguna pérdida de datos. REPAIR_ALLOW_DATA_LOSS es la única opción que permite la reparación de los errores de asignación.

 REPAIR_FAST  
 La sintaxis solo se mantiene por razones de compatibilidad con versiones anteriores. No se realizan acciones de reparación.

 REPAIR_REBUILD  
 No aplicable.  
 Utilice las opciones REPAIR solo como último recurso. Para reparar errores, se recomienda restaurar a partir de una copia de seguridad. Las operaciones de reparación no tienen en cuenta ninguna de las restricciones que puede haber en las tablas o entre ellas. Si la tabla especificada está implicada en una o más restricciones, se recomienda ejecutar DBCC CHECKCONSTRAINTS tras una operación de reparación. Si debe utilizar REPAIR, ejecute DBCC CHECKDB sin una opción de reparación para localizar el nivel de reparación que se va a utilizar. Si utiliza el nivel REPAIR_ALLOW_DATA_LOSS, se recomienda realizar una copia de seguridad de la base de datos antes de ejecutar DBCC CHECKDB con esta opción.

 por  
 Habilita la especificación de opciones.

 ALL_ERRORMSGS  
 Muestra todos los mensajes de error. De forma predeterminada, se muestran todos los mensajes de error. Especificar u omitir esta opción no tiene ningún efecto.

 NO_INFOMSGS  
 Suprime todos los mensajes informativos y el informe del espacio utilizado.

 TABLOCK  
 Hace que el comando DBCC obtenga un bloqueo de base de datos exclusivo.

 ESTIMATE ONLY  
 Muestra la cantidad estimada de espacio de tempdb que se necesita para ejecutar DBCC CHECKALLOC cuando todas las demás opciones están especificadas.
  
## <a name="remarks"></a>Comentarios  
DBCC CHECKALLOC comprueba la asignación de todas las páginas de la base de datos, independientemente del tipo de página u objeto al que pertenezcan. También valida las diversas estructuras internas que se utilizan para realizar un seguimiento de estas páginas y de las relaciones entre ellas.
Si no se especifica NO_INFOMSGS, DBCC CHECKALLOC recopila información sobre uso de espacio de todos los objetos de la base de datos. Esta información se imprimirá junto con los errores que se encuentran.
  
> [!NOTE]  
>La funcionalidad de DBCC CHECKALLOC se incluye en [DBCC CHECKDB](../../t-sql/database-console-commands/dbcc-checkdb-transact-sql.md) y [DBCC CHECKFILEGROUP](../../t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql.md). Esto significa que no tiene que ejecutar DBCC CHECKALLOC independientemente de estas instrucciones.   DBCC CHECKALLOC no comprueba los FILESTREAM datos. FILESTREAM almacena los objetos binarios grandes (BLBS) en el sistema de archivos.  
  
## <a name="internal-database-snapshot"></a>Instantánea de base de datos interna  
DBCC CHECKALLOC utiliza una instantánea interna de base de datos para proporcionar la coherencia transaccional necesaria para realizar estas comprobaciones. Si no es posible crear una instantánea o se especifica TABLOCK, DBCC CHECKALLOC intenta adquirir un bloqueo exclusivo (X) de la base de datos para obtener la coherencia necesaria.
  
> [!NOTE]  
> Al ejecutar DBCC CHECKALLOC en tempdb no realiza ninguna comprobación. Esto es debido a que, por motivos de rendimiento, las instantáneas de base de datos no están disponibles en tempdb. Eso significa que no es posible obtener la coherencia transaccional necesaria. Detener e iniciar el servicio MSSQLSERVER para resolver los problemas de asignación de tempdb. Esta acción quita y vuelve a crea la base de datos tempdb.  
  
## <a name="understanding-dbcc-error-messages"></a>Descripción de los mensajes de error de DBCC  
Cuando finaliza el comando DBCC CHECKALLOC, se escribe un mensaje en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Si el comando DBCC se ejecuta correctamente, el mensaje lo indica, así como el tiempo de ejecución del comando. Si el comando DBCC se detiene antes de completar la comprobación debido a un error, el mensaje indica que se ha cancelado el comando, un valor de estado y la cantidad de tiempo de ejecución del comando. En la tabla siguiente se muestran y describen los valores de estado que pueden aparecer en el mensaje.
  
|State|Description|  
|---|---|  
|0|Se ha generado el error número 8930. Indica un daño en los metadatos que provoca la cancelación del comando DBCC.|  
|1|Se ha generado el error número 8967. Error DBCC interno.|  
|2|Error durante una reparación de base de datos en modo de emergencia.|  
|3|Indica un daño en los metadatos que provoca la cancelación del comando DBCC.|  
|4|Se ha detectado una infracción de acceso o aserción.|  
|5|Error desconocido que cancela el comando DBCC.|  
  
## <a name="error-reporting"></a>Informes de errores  
Un archivo de minivolcado (SQLDUMP*nnnn*.txt) se crea en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] directorio de registro cada vez que DBCC CHECKALLOC detecta un error por daños. Si la recopilación de datos de uso de características y la creación informes de errores están habilitadas para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el archivo se reenvía automáticamente a [!INCLUDE[msCoName](../../includes/msconame-md.md)]. Los datos recopilados se utilizan para mejorar la funcionalidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].
El archivo de volcado contiene los resultados del comando DBCC CHECKALLOC y salida de diagnóstico adicional. El archivo tiene listas de control de acceso discrecional (DACL) restringidas. Acceso está limitado a la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta y los miembros del rol sysadmin de servicio. De forma predeterminada, el rol de administrador del sistema contiene a todos los miembros del grupo BUILTIN\Administradores de Windows y grupo de administradores local. El comando DBCC no producirá error en caso de que se produzca un error en el proceso de recopilación de datos.
  
## <a name="resolving-errors"></a>Resolver errores  
Si DBCC CHECKALLOC informa de algún error, se recomienda restaurar la base de datos a partir de su copia de seguridad en lugar de ejecutar una reparación. Si no existe una copia de seguridad, la ejecución de una reparación puede corregir los errores; no obstante, puede exigir la eliminación de algunas páginas y, por lo tanto, de datos.
Es posible realizar una reparación en una transacción de usuario. Esto permite revertir los cambios. Si se revierten los cambios, la base de datos seguirá conteniendo errores y deberá ser restaurada a partir de una copia de seguridad. Una vez finalizadas las reparaciones, realice una copia de seguridad de la base de datos.
  
## <a name="result-sets"></a>Conjuntos de resultados  
En las siguientes tablas se describe la información que devuelve DBCC CHECKALLOC.
  
|Elemento|Description|  
|---|---|  
|FirstIAM|Exclusivamente para uso interno.|  
|Root|Exclusivamente para uso interno.|  
|Dpages|Recuento de páginas de datos.|  
|Pages used|Páginas asignadas.|  
|Dedicated extents|Extensiones asignadas al objeto.<br /><br /> Si se utilizan páginas de asignación mixtas, puede haber páginas asignadas sin extensiones.|  
  
DBCC CHECKALLOC también devuelve un resumen de asignación de cada índice y partición de los archivos. En este resumen se describe la distribución de los datos.
  
|Elemento|Description|  
|---|---|  
|Reserved pages|Páginas asignadas al índice y páginas no utilizadas en extensiones asignadas.|  
|Used pages|Páginas asignadas y utilizadas por el índice.|  
|Id. de partición|Exclusivamente para uso interno.|  
|Alloc Unit ID|Exclusivamente para uso interno.|  
|Datos de fila|Las páginas contienen datos de índice o de montón.|  
|Datos LOB|Las páginas contienen **varchar (max)**, **nvarchar (max)**, **varbinary (max)**, **texto**, **ntext**, **xml**, y **imagen** datos.|  
|Datos de desbordamiento de fila|Las páginas contienen datos de columna de longitud variable que se han insertado de manera no consecutiva.|  
  
DBCC CHECKALLOC devuelve el siguiente conjunto de resultados (los valores pueden variar), excepto si se especifica ESTIMATEONLY o NO_INFOMSGS.
  
```sql
DBCC results for 'master'.  
***************************************************************  
Table sysobjects                Object ID 1.  
Index ID 1         FirstIAM (1:11)   Root (1:12)    Dpages 22.  
    Index ID 1. 24 pages used in 5 dedicated extents.  
Index ID 2         FirstIAM (1:1368)   Root (1:1362)    Dpages 10.  
    Index ID 2. 12 pages used in 2 dedicated extents.  
Index ID 3         FirstIAM (1:1392)   Root (1:1408)    Dpages 4.  
    Index ID 3. 6 pages used in 0 dedicated extents.  
Total number of extents is 7.  
***************************************************************  
'...'  
***************************************************************  
Table spt_server_info                Object ID 1938105945.  
Index ID 1         FirstIAM (1:520)   Root (1:508)    Dpages 1.  
    Index ID 1. 3 pages used in 0 dedicated extents.  
Total number of extents is 0.  
***************************************************************  
Processed 52 entries in sysindexes for database ID 1.  
File 1. Number of extents = 210, used pages = 1126, reserved pages = 1280.  
           File 1 (number of mixed extents = 73, mixed pages = 184).  
    Object ID 1, Index ID 0, data extents 5, pages 24, mixed extent pages 9.  
'...'  
    Object ID 1938105945, Index ID 0, data extents 0, pages 3, mixed extent pages 3.  
Total number of extents = 210, used pages = 1126, reserved pages = 1280 in this database.  
       (number of mixed extents = 73, mixed pages = 184) in this database.  
CHECKALLOC found 0 allocation errors and 0 consistency errors in database 'master'.  
DBCC results for 'master'.  
***************************************************************  
Table sys.sysrowsetcolumns                Object ID 4.  
Index ID 1, partition ID 262144, alloc unit ID 262144 (type In-row data). FirstIAM (1:98). Root (1:94). Dpages 7.  
Index ID 1, partition ID 262144, alloc unit ID 262144 (type In-row data). 9 pages used in 1 dedicated extents.  
Index ID 1, partition ID 262144, alloc unit ID 262398 (type Row-overflow data). FirstIAM (0:0). Root (0:0). Dpages 0.  
Index ID 1, partition ID 262144, alloc unit ID 262398 (type Row-overflow data). 0 pages used in 0 dedicated extents.  
Total number of extents is 1.  
...  
***************************************************************  
Processed 201 entries in system catalog for database ID 1.  
File 1. Number of extents = 44, used pages = 300, reserved pages = 345.  
           File 1 (number of mixed extents = 29, mixed pages = 225).  
    Object ID 4, index ID 1, partition ID 262144, alloc unit ID 262144 (type In-row data), data extents 1, pages 9, mixed extent pages 8.  
    Object ID 5, index ID 1, partition ID 327680, alloc unit ID 327680 (type In-row data), data extents 0, pages 2, mixed extent pages 2.  
    Object ID 7, index ID 1, partition ID 458752, alloc unit ID 458752 (type In-row data), data extents 0, pages 5, mixed extent pages 5.  
    Object ID 8, index ID 0, partition ID 524288, alloc unit ID 524288 (type In-row data), data extents 0, pages 2, mixed extent pages 2.  
    Object ID 13, index ID 1, partition ID 851968, alloc unit ID 851968 (type In-row data), data extents 1, pages 9, mixed extent pages 8.  
    Object ID 15, index ID 1, partition ID 983040, alloc unit ID 983040 (type In-row data), data extents 0, pages 2, mixed extent pages 2.  
    Object ID 26, index ID 1, partition ID 281474978414592, alloc unit ID 1703937 (type In-row data), data extents 0, pages 3, mixed extent pages 3.  
    Object ID 27, index ID 1, partition ID 281474978480128, alloc unit ID 1769473 (type In-row data), data extents 0, pages 3, mixed extent pages 3.  
    Object ID 27, index ID 2, partition ID 562949955190784, alloc unit ID 1769474 (type In-row data), index extents 0, pages 3, mixed extent pages 3.  
...  
    Object ID 1179151246, index ID 1, partition ID 72057594038845440, alloc unit ID 13435136 (type In-row data), data extents 2, pages 18, mixed extent pages 8.  
    Object ID 1179151246, index ID 2, partition ID 72057594038910976, alloc unit ID 13566208 (type In-row data), index extents 1, pages 16, mixed extent pages 8.  
    Object ID 1911677858, index ID 0, partition ID 72057594039631872, alloc unit ID 15073536 (type In-row data), data extents 0, pages 2, mixed extent pages 2.  
Total number of extents = 41, used pages = 289, reserved pages = 323 in this database.  
       (number of mixed extents = 27, mixed pages = 211) in this database.  
CHECKALLOC found 0 allocation errors and 0 consistency errors in database 'master'.  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
Cuando se especifica ESTIMATEONLY, DBCC CHECKALLOC devuelve el siguiente conjunto de resultados.
  
```sql
Estimated TEMPDB space needed for CHECKALLOC (KB)   
-------------------------------------------------   
34  
  
(1 row(s) affected)  
  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
## <a name="permissions"></a>Permissions  
Requiere la pertenencia al rol fijo de servidor sysadmin o la función fija de base de datos db_owner.
  
## <a name="examples"></a>Ejemplos  
En el ejemplo siguiente se ejecuta `DBCC CHECKALLOC` para la base de datos actual y para la base de datos `AdventureWorks2012`.
  
```sql  
-- Check the current database.  
DBCC CHECKALLOC;  
GO  
-- Check the AdventureWorks2012 database.  
DBCC CHECKALLOC (AdventureWorks2012);  
GO  
```  
  
## <a name="see-also"></a>Vea también  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)
  
  


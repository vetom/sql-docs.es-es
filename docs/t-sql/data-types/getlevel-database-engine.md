---
title: GetLevel (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 7/22/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: t-sql|data-types
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- GetLevel
- GetLevel_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- GetLevel [Database Engine]
ms.assetid: 81577d7e-8ff6-4e73-b7f4-94c03d4921e7
caps.latest.revision: 17
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5867c961bb4bf56406be9b272aa4fe879e8d94df
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="getlevel-database-engine"></a>GetLevel (motor de base de datos)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Devuelve un entero que representa la profundidad del nodo *this* en el árbol.
  
## <a name="syntax"></a>Sintaxis  
  
```sql
-- Transact-SQL syntax  
node.GetLevel ( )   
```  
  
```sql
-- CLR syntax  
SqlInt16 GetLevel ( )   
```  
  
## <a name="return-types"></a>Tipos devueltos  
**Tipo de valor devuelto de SQL Server: smallint**
  
**Tipo de valor devuelto de CLR: SqlInt16**
  
## <a name="remarks"></a>Notas  
Se utiliza para determinar el nivel de uno o más nodos o para filtrar los nodos a los miembros de un nivel especificado. La raíz del árbol de jerarquía tiene el nivel 0.
  
GetLevel resulta muy útil en los índices de búsqueda con prioridad a la amplitud. Para más información, vea [Datos jerárquicos &#40;SQL Server&#41;](../../relational-databases/hierarchical-data-sql-server.md).
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-returning-the-hierarchy-level-as-a-column"></a>A. Devolver el nivel de jerarquía como una columna  
En el siguiente ejemplo se devuelve una representación de texto del objeto **hierarchyid** y, después, el nivel de jerarquía como la columna **EmpLevel** para todas las filas de la tabla:
  
```sql
SELECT OrgNode.ToString() AS Text_OrgNode,   
OrgNode.GetLevel() AS EmpLevel, *  
FROM HumanResources.EmployeeDemo;  
```  
  
### <a name="b-returning-all-members-of-a-hierarchy-level"></a>B. Devolver todos los miembros de un nivel de jerarquía  
El ejemplo siguiente devuelve todas las filas de la tabla que están en el nivel de jerarquía 2:
  
```sql
SELECT OrgNode.ToString() AS Text_OrgNode,   
OrgNode.GetLevel() AS EmpLevel, *  
FROM HumanResources.EmployeeDemo  
WHERE OrgNode.GetLevel() = 2;  
```  
  
### <a name="c-returning-the-root-of-the-hierarchy"></a>C. Devolver la raíz de la jerarquía  
El ejemplo siguiente devuelve la raíz del nivel de jerarquía:
  
```sql
SELECT OrgNode.ToString() AS Text_OrgNode,   
OrgNode.GetLevel() AS EmpLevel, *  
FROM HumanResources.EmployeeDemo  
WHERE OrgNode.GetLevel() = 0;  
```  
  
### <a name="d-clr-example"></a>D. Ejemplo de CLR  
En el siguiente fragmento de código se llama al método GetLevel():
  
```sql
this.GetLevel()  
```  
  
## <a name="see-also"></a>Vea también
[Referencia de los métodos del tipo de datos hierarchyid](http://msdn.microsoft.com/library/01a050f5-7580-4d5f-807c-7f11423cbb06)  
[Datos jerárquicos &#40;SQL Server&#41;](../../relational-databases/hierarchical-data-sql-server.md)  
[hierarchyid &#40;Transact-SQL&#41;](../../t-sql/data-types/hierarchyid-data-type-method-reference.md)
  
  

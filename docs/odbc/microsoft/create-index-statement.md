---
title: Instrucción CREATE INDEX | Documentos de Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CREATE INDEX [ODBC]
- SQL grammar [ODBC], create index
ms.assetid: 69438247-eef3-44c5-bef2-acef4e146f41
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 61d1532e457748b432e5aa14a55e9e68b4486c9c
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="create-index-statement"></a>Instrucción CREATE INDEX
La sintaxis de la instrucción CREATE INDEX es:  
  
 CREATE [UNIQUE] INDEX *nombre del índice* ON *nombre de la tabla* (*identificador de la columna* [ASC] [DESC] [, *identificador de la columna* [ASC][DESC]...]) CON \< *lista de opciones de índice*>  
  
 donde \< *lista de opciones de índice*> puede ser: principal &#124; DISALLOW NULL &#124; IGNORE NULL  
  
 Sólo el controlador de Microsoft Access utiliza las opciones de índice DISALLOW NULL y IGNORE NULL. Los controladores de Paradox y dBASE aceptan la sintaxis, pero que omita la presencia de cualquiera de las opciones.  
  
 Cuando se utiliza el controlador de Paradox, la instrucción CREATE INDEX crea archivos de clave principales de Paradox y archivos secundarios.  
  
 Esta instrucción no es compatible con los controladores de Microsoft Excel o texto.

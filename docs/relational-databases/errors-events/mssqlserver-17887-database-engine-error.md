---
title: MSSQLSERVER_17887 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
caps.latest.revision: 17
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5ab8751d454b52ec797d5b879816abd967b9498d
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="mssqlserver17887"></a>MSSQLSERVER_17887
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|17887|  
|Origen del evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|SRV_IO_COMP_LISTENER_NONYIELDING|  
|Texto del mensaje|Parece que la escucha de finalización de E/S (0x%lx) Trabajo 0x%p no rinde en el nodo %ld. Uso de CPU (aprox.): kernel %I64d ms, usuario %I64d ms, Intervalo: %I64d.|  
  
## <a name="explanation"></a>Explicación  
Indica que hay un posible problema con la escucha del puerto de finalización de E/S en el nodo especificado al ejecutar la rutina de finalización de E/S para un evento de lectura/escritura de red. Este error desaparecerá cuando la escucha del puerto de finalización de E/S vuelva de ejecutar la rutina de finalización de E/S.  
  
## <a name="user-action"></a>Acción del usuario  
Póngase en contacto con los servicios de soporte al cliente de Microsoft (CSS).  
  

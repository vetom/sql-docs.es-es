---
title: Almacenamiento de la administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
caps.latest.revision: 11
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 26fdbaaba0d0483d4cb8b7c626459f92646a38b4
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="policy-based-management-storage"></a>Almacenamiento de la administración basada en directivas
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Las directivas se almacenan en la base de datos msdb. Después de cambiar una directiva o condición, se debería hacer una copia de seguridad de la base de datos msdb. Para obtener más información, vea [Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md).  
  
## <a name="storing-policies"></a>Almacenar directivas  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] incluye directivas que se pueden utilizar para supervisar una sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Estas directivas no están instaladas en [!INCLUDE[ssDE](../../includes/ssde-md.md)] de forma predeterminada, pero se pueden importar desde la ubicación de instalación predeterminada C:\Archivos de programa (x86)\Microsoft SQL Server\140\Tools\Policies\DatabaseEngine\1033.  
  
 Puede crear directamente las directivas usando el menú **Archivo/Nuevo** y guardándolas después en un archivo. Esto le permite crear directivas cuando no esté conectado a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
 El historial de las directivas evaluadas en la instancia actual de [!INCLUDE[ssDE](../../includes/ssde-md.md)] se mantiene en las tablas del sistema de msdb. El historial de las directivas aplicadas a otras instancias de [!INCLUDE[ssDE](../../includes/ssde-md.md)] o a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no se conserva.  
  
  

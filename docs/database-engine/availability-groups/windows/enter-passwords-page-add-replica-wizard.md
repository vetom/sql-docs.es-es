---
title: Página Escribir contraseñas (Asistente para agregar réplica) | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: availability-groups
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql13.swb.addreplicawizard.enterpasswords.f1
ms.assetid: e69207a0-c5c4-44e4-ae9a-4afbb67251d1
caps.latest.revision: 7
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9222f0b5d941cbdac38dc04afc3f770c9d487029
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="enter-passwords-page-add-replica-wizard"></a>Página Escribir contraseñas (Asistente para agregar réplica)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  En este tema de Ayuda se describen las opciones de la página **Escribir contraseñas** . Este tema se aplica al [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 Si las réplicas que seleccionó en la página **Especificar réplicas** contienen bases de datos que tienen una clave maestra de base de datos, aparecerá la página Escribir contraseñas.  
  
## <a name="enter-passwords-options"></a>Opciones para escribir contraseñas  
 La cuadrícula **Usar bases de datos en esta instancia de SQL Server** muestra cada base de datos de usuario local. Estas son sus columnas:  
  
 **Nombre**  
 Muestra el nombre de una base de datos de usuario local.  
  
 **Tamaño**  
 Muestra el tamaño de la base de datos, si el tamaño está disponible para el asistente.  
  
 **Estado**  
 Indica **Se requiere contraseña** en bases de datos que tienen una clave maestra de base de datos. Después de escribir las contraseñas para las claves maestras de base de datos en la columna **Contraseñas** , haga clic en **Actualizar**. Si ha especificado la contraseña correctamente, la columna **Estado** indica **Password entered**(Contraseña escrita).  
  
 Si la base de datos no tiene una clave maestra de base de datos, el **estado** columna indica **No se necesita contraseña**.  
  
 **Contraseña**  
 Si la columna **Estado** indica **Se requiere contraseña**, escriba la contraseña de la clave maestra de base de datos.  
  
 **Actualizar**  
 Haga clic para actualizar la cuadrícula. Esto es útil después de escribir las contraseñas necesarias.  
  
## <a name="related-tasks"></a>Related Tasks  
  
-   [Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a>Ver también  
 [Requisitos previos, restricciones y recomendaciones para Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md)  
  
  

---
title: Propiedades de Agente SQL Server (página Avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql13.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: d50b03c11723eecbcb73ac9b90cbf6e774c1b704
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="sql-server-agent-properties-advanced-page"></a>Propiedades de Agente SQL Server (página Avanzadas)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> En [Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance), la mayoría de las características de agente SQL Server son compatibles actualmente, aunque no todas. Vea [Diferencias de T-SQL en Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) para obtener más información.

Utilice esta página para ver y modificar las propiedades avanzadas del servicio del Agente [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
## <a name="options"></a>Opciones  
**Reenvío de eventos de SQL Server**  
Las opciones de esta categoría activan y configuran el reenvío de eventos.  
  
**Reenviar eventos a otro servidor**  
Reenvía los eventos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] a otro servidor.  
  
**Server**  
Seleccione el nombre del servidor al que se reenvían los eventos.  
  
**Eventos no controlados**  
Solo reenvía eventos no controlados al servidor especificado. [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] solo reenvía eventos a los que no responde ninguna alerta.  
  
**Todos los eventos**  
Reenvía todos los eventos. Cuando una alerta de la instancia local responde al evento, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] reenvía el evento y procesa la alerta.  
  
**Si el evento tiene una gravedad de o por encima de**  
Solo reenvía eventos con el nivel de gravedad igual o superior al especificado.  
  
**Condición de CPU inactiva**  
Las opciones de esta categoría definen las condiciones en las que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ejecuta trabajos programados para ejecutarse en la programación de CPU inactiva.  
  
**Definir condición de CPU inactiva**  
Define las condiciones en las que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] considera que la CPU está inactiva.  
  
**El promedio de uso de la CPU baja de**  
Porcentaje de uso de CPU por debajo del cual se considera inactiva la CPU.  
  
**Y permanece por debajo durante**  
Cantidad de tiempo que el promedio de uso de la CPU debe situarse por debajo del nivel especificado antes de que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ejecute trabajos en la programación de CPU inactiva.  
  
## <a name="see-also"></a>Ver también  
[Crear y adjuntar programaciones a trabajos](../../ssms/agent/create-and-attach-schedules-to-jobs.md)  
[Administrar eventos](../../ssms/agent/manage-events.md)  
  

---
title: Creación de la directiva Finance Name | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-query-tuning
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
caps.latest.revision: 26
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 40191000a42899df68820bd8288bf2f8b6ae604a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="lesson-2-1---create-the-finance-name-policy"></a>Lección 2-1: Creación de la directiva Finance Name
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
En esta tarea, creará una base de datos denominada Finance y después una condición que requiera que los nombres de todas las tablas comiencen con las letras **fintbl**. A continuación, creará una directiva y una categoría de directivas para exigir una denominación estándar para las tablas de la base de datos Finance.  
  
### <a name="to-create-the-finance-database"></a>Para crear la base de datos Finance  
  
1.  En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra una ventana de consulta y ejecute la instrucción siguiente:  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  En el Explorador de objetos, haga clic en **Bases de datos**y, a continuación, presione F5 para actualizar la lista de bases de datos.  
  
### <a name="to-create-the-finance-tables-condition"></a>Para crear la condición Finance Tables  
  
1.  En el Explorador de objetos, expanda **Administración**, expanda **Administración de directivas**, haga clic con el botón derecho en **Condiciones**y, después, haga clic en **Nueva condición**.  
  
2.  En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba **Finance Tables**.  
  
3.  En la lista **Faceta** , seleccione **Nombre de varias partes**.  
  
4.  En el cuadro de diálogo **Expresión** , en el cuadro **Campo** , seleccione **@Name**; en el cuadro **Operador** , seleccione **Like**; y en el cuadro **Valor** , escriba **'fintbl%'** para hacer que todos los nombres de tabla comiencen con las letras **fintbl**.  
  
5.  En la página **Descripción** , escriba **Los nombres de tablas de finanzas deben comenzar con fintbl**y, a continuación, haga clic en **Aceptar** para crear la condición.  
  
### <a name="to-create-the-finance-name-policy"></a>Para crear la directiva Finance Name  
  
1.  En el Explorador de objetos, haga clic con el botón derecho en **Directivas**y, después, haga clic en **Nueva directiva**.  
  
2.  En el cuadro de diálogo **Crear nueva directiva** , en el cuadro **Nombre** , escriba **Finance Name**.  
  
3.  En la lista **Condición de comprobación** , seleccione **Finance Tables**. Está en el área **Nombre de varias partes** .  
  
4.  En el área **Contra** verá una lista de los objetos de base de datos que podrían aplicar esta directiva. Active la casilla de **Cada tabla**.  
  
5.  En el área **Cada base de datos** , expanda **Cada**y, a continuación, haga clic en **Nueva condición**.  
  
6.  En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba **Finance Database**.  
  
7.  En el cuadro **Expresión**, complete la expresión para incluir **@Name = 'Finance'** y, después, haga clic en **Aceptar** para cerrar la página de la condición.  
  
    > [!NOTE]  
    > Es posible que tenga que salir del cuadro **Valor** para habilitar el botón **Aceptar** .  
  
8.  En la lista **Modo de evaluación** , seleccione **Al cambiar: impedir**. Esto exigirá la directiva creando un desencadenador de base de datos en la base de datos Finance.  
  
9. Seleccione la lista **Habilitado** . (El cuadro **Habilitado** no se aplica a las directivas **A petición** ).  
  
10. En la lista **Restricción de servidor** , seleccione **Ninguna**.  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a>Para crear la categoría de directivas Finance  
  
1.  En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Administración de directivas**y, después, haga clic en **Administrar categorías**.  
  
2.  En el cuadro de diálogo **Administrar categorías de directivas** , en **Nombre**, escriba **Finance** en el cuadro en blanco y, a continuación, anule la selección de **Suscripciones de base de datos de mandatos**. **Suscripciones de base de datos de mandatos** exigirá que cada base de datos en la instancia se suscriba a las directivas que pertenecen a esta categoría de directiva. Para esta lección, solo la base de datos Finance debería suscribirse a la directiva Finance Name.  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a>Siguiente tarea de la lección  
[Suscribirse a, y comprobar, la directiva Finance Name](../../relational-databases/policy-based-management/lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
  

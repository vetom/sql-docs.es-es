---
title: srv_rpcnumber (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: extended-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- srv_rpcnumber
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
caps.latest.revision: 29
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 82a08518dae6683d6868d3b8ea9adf4604ac0cd5
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="srvrpcnumber-extended-stored-procedure-api"></a>srv_rpcnumber (API de procedimiento almacenado extendido)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Use la integración con CLR en su lugar.  
  
 Devuelve el componente de nombre de la llamada a procedimiento almacenado remoto actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto). La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.  
  
## <a name="returns"></a>Devuelve  
 El componente de número para el procedimiento almacenado remoto actual. Si el cliente no usa un componente de número al ejecutar el procedimiento almacenado remoto o si no hay ningún procedimiento almacenado remoto actual, devuelve - 1.  
  
## <a name="remarks"></a>Comentarios  
 Esta función únicamente devuelve el componente de número del procedimiento almacenado remoto. No incluye los especificadores opcionales propietario, nombre del procedimiento almacenado remoto y nombre de la base de datos.  
  
> [!IMPORTANT]  
>  Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción. Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  

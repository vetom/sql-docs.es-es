---
title: Jerarquías derivadas con límites explícitos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.service: ''
ms.component: non-specific
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
caps.latest.revision: 7
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d4580f3a5cf82e45b342df1d028f4d158d991afd
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a>Jerarquías derivadas con límites explícitos (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], el hecho de que los niveles de una jerarquía explícita se utilicen como niveles superiores de una jerarquía derivada, se denomina jerarquía derivada con límites explícitos.  
  
 La jerarquía explícita debe estar basada en la misma entidad que la entidad del nivel superior de la jerarquía derivada.  
  
 En la interfaz de usuario de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , para crear este tipo de jerarquía, arrastre una jerarquía explícita hasta la parte superior de una jerarquía derivada.  
  
 ![mds_conc_explicit_cap_UI_structure](../master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")  
  
## <a name="derived-hierarchy-with-explicit-cap-example"></a>Ejemplo de jerarquía derivada con límite explícito  
 En este ejemplo, los miembros de la jerarquía explícita son los de la entidad Subcategory. En la jerarquía derivada, los miembros de nivel superior también son los de la entidad Subcategory.  
  
 ![mds_conc_explicit_cap_UI_example](../master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")  
  
 Al usar la jerarquía explícita en el nivel superior de una jerarquía derivada, la jerarquía derivada queda desigual.  
  
## <a name="rules"></a>Reglas  
  
-   No puede tener más de una jerarquía explícita en una jerarquía derivada con límites explícitos.  
  
-   Puede utilizar la misma jerarquía explícita como límite para varias jerarquías derivadas.  
  
-   No puede asignar permisos a los miembros de jerarquías derivadas con límites explícitos. Si asigna individualmente permisos a la jerarquía explícita o a la jerarquía derivada, los permisos afectan a ambas.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descripción de la tarea|Tema|  
|----------------------|-----------|  
|Crear una jerarquía derivada.|[Crear una jerarquía derivada &#40;Master Data Services&#41;](../master-data-services/create-a-derived-hierarchy-master-data-services.md)|  
|Crear una jerarquía explícita.|[Crear una jerarquía explícita &#40;Master Data Services&#41;](../master-data-services/create-an-explicit-hierarchy-master-data-services.md)|  
|Eliminar una jerarquía derivada existente.|[Eliminar una jerarquía derivada &#40;Master Data Services&#41;](../master-data-services/delete-a-derived-hierarchy-master-data-services.md)|  
|||  
  
## <a name="related-content"></a>Contenido relacionado  
  
-   [Jerarquías derivadas &#40;Master Data Services&#41;](../master-data-services/derived-hierarchies-master-data-services.md)  
  
-   [Jerarquías explícitas &#40;Master Data Services&#41;](../master-data-services/explicit-hierarchies-master-data-services.md)  
  
  

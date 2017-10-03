---
title: "Implementación de puertos y Assemblies1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- deployment, ports
- deployment, assemblies
- assemblies, deploying
ms.assetid: e259f7fe-c443-4015-a630-f08220e5437a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2515cd5ee80f62a55e0b26b33bb93c3685ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a>Implementar puertos y ensamblados
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino. El asistente exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.  
  
 Mediante BizTalk Server se pueden realizar las tareas siguientes:  
  
-   Implementar o quitar ensamblados de BizTalk Server en una base de datos de configuración de BizTalk.  
  
-   Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
-   Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace.  
  
 Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  El adaptador de Microsoft BizTalk para TIBCO Rendezvous solo necesita que tenga Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Comprobar la configuración de implementación](../core/verifying-the-deployment-setup3.md)  
  
-   [Cómo limpiar el equipo de destino](../core/how-to-clean-the-target-computer1.md)
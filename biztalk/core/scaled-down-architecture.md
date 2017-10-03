---
title: Arquitectura reducida | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a112f3f737a1a5aec0cfac16b7689d3dada1e8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture"></a>Arquitectura reducida
Para obtener información completa sobre la arquitectura del sistema para[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación, consulte [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La siguiente ilustración muestra un ejemplo de arquitectura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que combina algunos de los dominios y servidores de BizTalk Server para reducir el número de servidores y firewalls necesarios. Aunque esta arquitectura no es la más distribuida, separa los servidores de BizTalk Server basándose en sus funciones.  
  
 ![Arquitectura reducida](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")  
  
        Scaled Down Architecture  
  
 En la ilustración anterior, los servidores del dominio de servicios e interfaces de servicio se corresponden con hosts de BizTalk, no con servidores físicos. Aunque se recomienda mantener el servidor secreto principal y las herramientas administrativas en equipos independientes, puede haber instancias de hosts de seguimiento, procesamiento, envío y recepción ejecutándose en varios equipos. Asimismo, los servidores de la red perimetral se corresponden con ubicaciones lógicas.  
  
 Los servidores de la red perimetral para SMTP, Message Queue Server, archivo y SQL se corresponden con los servidores de correo, cola de mensajes, directorios y SQL Server, respectivamente, desde los que reciben y envían mensajes los hosts de recepción y envío de BizTalk del dominio de procesamiento y servicios.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura reducida con servicios de trabajadores de información](../core/scaled-down-architecture-with-information-worker-services.md)   
 [Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md)   
 [Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)
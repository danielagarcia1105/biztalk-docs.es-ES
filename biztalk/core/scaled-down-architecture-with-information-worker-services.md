---
title: Arquitectura reducida con servicios de trabajadores de información | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d02558e5904bf740c09ea0db614b2189555ac75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269252"
---
# <a name="scaled-down-architecture-with-information-worker-services"></a>Arquitectura reducida con Servicios de trabajadores de la información
Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La siguiente ilustración muestra un ejemplo de arquitectura de BizTalk Server que incluye los servicios de trabajadores de la información y combina algunos de los dominios y servidores de BizTalk Server para reducir el número de servidores y servidores de seguridad necesarios. Aunque esta arquitectura no es la más distribuida, separa los servidores de BizTalk Server basándose en sus funciones.  
  
 ![Topología Scaledown](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")  
  
        Scaled Down Architecture with Information Worker Services  
  
 En la ilustración anterior, los servidores del dominio de servicios e interfaces de servicio se corresponden con hosts de BizTalk, no con servidores físicos. Aunque se recomienda mantener el servidor secreto principal y las herramientas administrativas en equipos independientes, puede haber instancias de hosts de seguimiento, procesamiento, envío y recepción ejecutándose en varios equipos. Asimismo, los servidores de la red perimetral se corresponden con ubicaciones lógicas.  
  
 Los servidores de la red perimetral para SMTP, Message Queue de Windows (MSMQ), archivo y SQL se corresponden con los servidores de correo, cola de mensajes, directorios y SQL Server, respectivamente, desde los que reciben y envían mensajes los hosts de recepción y envío de BizTalk del dominio de interfaces de servicio.  
  
 Las bases de datos de SAE del domino de datos son las de importación principal, análisis, esquema de estrella y archivo de SAE. Las bases de datos de seguimiento y análisis del dominio de datos son los que utiliza BizTalk Server para almacenar información de seguimiento.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura reducida](../core/scaled-down-architecture.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Diseñar una arquitectura segura](../core/designing-a-secure-architecture.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)
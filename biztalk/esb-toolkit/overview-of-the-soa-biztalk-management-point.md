---
title: "Información general sobre el punto de administración de BizTalk de SOA | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-soa-biztalk-management-point"></a>Información general sobre el punto de administración de BizTalk de SOA
El punto de administración de BizTalk forma nativa se integra con los productos de administrador de servicios de SOA y área de trabajo. Al contrario que el punto de administración de servicios Web típica, esta implementación está asociada con los servicios proporcionados por el entorno de Microsoft BizTalk Server, expresado en términos de BizTalk Server ubicaciones de recepción y puertos de envío. Debido a la arbitrario naturaleza de ubicaciones de recepción y envío puertos (configurados con una variedad de adaptadores de BizTalk Server), estos servicios no están necesariamente asociados con los servicios Web, pero se puede tratar como servicios Web en términos de SOA Service Manager y el área de trabajo SOA.  
  
 La figura 1 muestra la aplicación Web de administrador de servicios de SOA de mostrar la página de área de trabajo para una aplicación de ejemplo. La vista de árbol de la izquierda permite a los usuarios navegar por las aplicaciones y servicios instalados en el servidor BizTalk Server y el panel de la derecha permite a los usuarios ver los detalles de la aplicación, las operaciones, puertos de acceso, categorías, reglas e información de supervisión.  
  
 ![Ch9 &#45; SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")  
  
 **Figura 1**  
  
 **El Administrador de servicios de SOA que muestra las características de supervisión disponibles en la página de área de trabajo**  
  
 Puede supervisar todas las operaciones dentro de una aplicación (todos los puertos de envío y ubicaciones de recepción), o las operaciones concretas; se muestra en el área de trabajo una lista de los mensajes que pasan a través de los puertos de envío y ubicaciones de recepción. Al hacer doble clic en un mensaje en la lista, el área de trabajo muestra los detalles del mensaje y sus propiedades de contexto (si está habilitada la grabación). Como alternativa, puede seleccionar un servicio específico y un monitor de mensajes en tiempo real que se pasan a través de ese servicio.
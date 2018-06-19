---
title: Usar un componente de canalización para almacenar en caché un itinerario de petición-respuesta | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b6822a4f4ca70e88ee86277e00645982595b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294996"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a>Uso de un componente de canalización para almacenar en caché un itinerario para envíos de solicitud-respuesta
Los mensajes enviados mediante un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario en rampa puede atravesar un itinerario unidireccional o un itinerario bidireccional (solicitud-respuesta). Para admitir itinerarios de solicitud-respuesta, el mecanismo de itinerarios debe proporcionar almacenamiento en caché para puertos de envío de petición-respuesta dinámicos de BizTalk.  
  
 El componente de canalización de ESB itinerario caché coloca el itinerario almacenado en el contexto de mensaje saliente en la memoria caché y lo adjunta al mensaje de respuesta; se devuelve el puerto de envío con la clave de almacenamiento en caché configurable. Esto permite al servicio itinerario procesar y ejecutar los servicios siguientes definidos después del servicio actual en el itinerario.  
  
 De forma predeterminada, el componente de canalización de ESB itinerario caché reside en la canalización ItineraryReceiveSend BizTalk, tal como se muestra en la figura 1. Esta canalización debe usarse únicamente como la canalización de recepción para un puerto de envío de petición-respuesta.  
  
 ![Caché de componentes de canalización](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")  
  
 **Figura 1**  
  
 **El componente de canalización de caché de itinerario de ESB**  
  
 Utilice el componente de canalización de caché de itinerario de ESB en BizTalk canalización de recepción para un puerto de envío de petición-respuesta.
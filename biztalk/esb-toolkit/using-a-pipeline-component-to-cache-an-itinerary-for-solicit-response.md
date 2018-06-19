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
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a><span data-ttu-id="13ece-102">Uso de un componente de canalización para almacenar en caché un itinerario para envíos de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="13ece-102">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>
<span data-ttu-id="13ece-103">Los mensajes enviados mediante un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerario en rampa puede atravesar un itinerario unidireccional o un itinerario bidireccional (solicitud-respuesta).</span><span class="sxs-lookup"><span data-stu-id="13ece-103">Messages submitted through a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary on-ramp can go through either a one-way itinerary or a two-way (request-response) itinerary.</span></span> <span data-ttu-id="13ece-104">Para admitir itinerarios de solicitud-respuesta, el mecanismo de itinerarios debe proporcionar almacenamiento en caché para puertos de envío de petición-respuesta dinámicos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="13ece-104">To support request-response itineraries, the itinerary mechanism must provide caching for BizTalk dynamic Solicit-Response send ports.</span></span>  
  
 <span data-ttu-id="13ece-105">El componente de canalización de ESB itinerario caché coloca el itinerario almacenado en el contexto de mensaje saliente en la memoria caché y lo adjunta al mensaje de respuesta; se devuelve el puerto de envío con la clave de almacenamiento en caché configurable.</span><span class="sxs-lookup"><span data-stu-id="13ece-105">The ESB Itinerary Cache pipeline component places the itinerary stored in the outbound message context into the cache and attaches it to the response message; it is returned by the send port using the configurable caching key.</span></span> <span data-ttu-id="13ece-106">Esto permite al servicio itinerario procesar y ejecutar los servicios siguientes definidos después del servicio actual en el itinerario.</span><span class="sxs-lookup"><span data-stu-id="13ece-106">This allows the itinerary service to process and execute subsequent services defined after the current service in the itinerary.</span></span>  
  
 <span data-ttu-id="13ece-107">De forma predeterminada, el componente de canalización de ESB itinerario caché reside en la canalización ItineraryReceiveSend BizTalk, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="13ece-107">By default, the ESB Itinerary Cache pipeline component resides in the ItineraryReceiveSend BizTalk pipeline, as shown in Figure 1.</span></span> <span data-ttu-id="13ece-108">Esta canalización debe usarse únicamente como la canalización de recepción para un puerto de envío de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ece-108">This pipeline should be used only as the receive pipeline for a Solicit-Response send port.</span></span>  
  
 <span data-ttu-id="13ece-109">![Caché de componentes de canalización](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span><span class="sxs-lookup"><span data-stu-id="13ece-109">![Pipeline Component Cache](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span></span>  
  
 <span data-ttu-id="13ece-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="13ece-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="13ece-111">**El componente de canalización de caché de itinerario de ESB**</span><span class="sxs-lookup"><span data-stu-id="13ece-111">**The ESB Itinerary Cache Pipeline component**</span></span>  
  
 <span data-ttu-id="13ece-112">Utilice el componente de canalización de caché de itinerario de ESB en BizTalk canalización de recepción para un puerto de envío de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ece-112">Use the ESB Itinerary Cache Pipeline component in a BizTalk receive pipeline for a Solicit-Response send port.</span></span>
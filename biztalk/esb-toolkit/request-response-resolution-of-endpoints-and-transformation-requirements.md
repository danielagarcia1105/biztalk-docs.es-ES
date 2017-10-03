---
title: "Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f442f1d9df457a3c1384f1d717e29c17b433f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="d04f7-102">Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación</span><span class="sxs-lookup"><span data-stu-id="d04f7-102">Request-Response Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="d04f7-103">En este caso de uso, una aplicación cliente envía un mensaje de solicitud para un aumento y recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="d04f7-103">In this use case, a client application submits a request message to an on-ramp and receives a response.</span></span> <span data-ttu-id="d04f7-104">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] actúa como mediador entre el cliente y el punto de conexión de servicio de destino y utiliza la resolución de ESB y el marco de trabajo para realizar la transformación del mensaje dinámico y el enrutamiento de acuerdo con la configuración de en rampa, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="d04f7-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acts as mediator between the client and the target service endpoint and uses the ESB Resolver and Adapter Framework to perform the dynamic message transformation and routing in accordance with the on-ramp configuration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="d04f7-105">![Solicitud &#45; Respuesta de resolución de extremos](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span><span class="sxs-lookup"><span data-stu-id="d04f7-105">![Request&#45;Response Resolution of Endpoints](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span></span>  
  
 <span data-ttu-id="d04f7-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="d04f7-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="d04f7-107">**Resolución de solicitudes y respuestas de puntos de conexión y los requisitos de transformación**</span><span class="sxs-lookup"><span data-stu-id="d04f7-107">**Request-response resolution of endpoints and transformation requirements**</span></span>  
  
 <span data-ttu-id="d04f7-108">El ejemplo de resolución dinámica que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="d04f7-108">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="d04f7-109">Muestra cómo aplicar transformación dinámica y la resolución de escenarios bidireccionales mediante XML Path Language (XPath), Universal Description, Discovery y Integration (UDDI), estático, o las directivas en el motor de reglas de negocio de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d04f7-109">It shows how to apply dynamic transformation and resolution for two-way scenarios using XML Path Language (XPath), Universal Description, Discovery, and Integration (UDDI), STATIC, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="d04f7-110">Para obtener más información, consulte el escenario de mensajería bidireccional descrito en [instalar y ejecutar el ejemplo de resolución dinámicos](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d04f7-110">For more information, see the two-way messaging scenario described in [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>
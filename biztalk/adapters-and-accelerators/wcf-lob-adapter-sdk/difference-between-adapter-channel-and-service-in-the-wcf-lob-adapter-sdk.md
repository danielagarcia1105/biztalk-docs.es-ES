---
title: Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24d41d96-0ea1-4a97-bd45-b65afdbbd923
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8583b615e6a6e8fcd999e5120bca531d3c74090d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010039"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="21e1a-102">Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="21e1a-102">Difference between adapter channel and service in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="21e1a-103">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cada una proporciona un conjunto de API que se pueden usar para exponer la funcionalidad de la aplicación para consumir las aplicaciones en el mismo equipo o a través de una red.</span><span class="sxs-lookup"><span data-stu-id="21e1a-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] each provide a set of APIs that can be used to expose application functionality to consuming applications on the same computer or across a network.</span></span> <span data-ttu-id="21e1a-104">Para elegir el marco de trabajo más adecuada, debe tener en cuenta las propiedades de la aplicación del sistema de destino que está exponiendo, así como los requisitos empresariales de la funcionalidad expuesta.</span><span class="sxs-lookup"><span data-stu-id="21e1a-104">To choose the most appropriate framework, you must consider the properties of the target system application you are exposing as well as the business requirements for the exposed functionality.</span></span> <span data-ttu-id="21e1a-105">Este tema proporciona directrices que puede usar para elegir el marco de trabajo adecuado.</span><span class="sxs-lookup"><span data-stu-id="21e1a-105">This topic provides guidelines that you can use to choose the appropriate framework.</span></span>  
  
## <a name="when-to-write-an-adapter"></a><span data-ttu-id="21e1a-106">Cuándo se debe escribir un adaptador</span><span class="sxs-lookup"><span data-stu-id="21e1a-106">When to Write an Adapter</span></span>  
 <span data-ttu-id="21e1a-107">Considere la posibilidad de escribir un adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] cuando:</span><span class="sxs-lookup"><span data-stu-id="21e1a-107">Consider writing an adapter using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] when:</span></span>  
  
- <span data-ttu-id="21e1a-108">El sistema de destino es una existente, que no sean de*Web habilitadas para los servicios* sistema</span><span class="sxs-lookup"><span data-stu-id="21e1a-108">The target system is an existing, non-*Web services-enabled* system</span></span>  
  
- <span data-ttu-id="21e1a-109">El sistema de destino es dinámico y se puede mejorar con nuevas operaciones</span><span class="sxs-lookup"><span data-stu-id="21e1a-109">The target system is dynamic and can be enhanced with new operations</span></span>  
  
- <span data-ttu-id="21e1a-110">El sistema de destino tiene una gran cantidad de metadatos</span><span class="sxs-lookup"><span data-stu-id="21e1a-110">The target system has a large amount of metadata</span></span>  
  
- <span data-ttu-id="21e1a-111">Hay un número grande, diverso de usuarios para los datos del sistema de destino</span><span class="sxs-lookup"><span data-stu-id="21e1a-111">There is a large, diverse number of users for the target system's data</span></span>  
  
- <span data-ttu-id="21e1a-112">Aplicaciones de consumo necesitan la funcionalidad de detección de metadatos de aplicación enriquecida</span><span class="sxs-lookup"><span data-stu-id="21e1a-112">Consuming applications need rich application metadata discovery functionality</span></span>  
  
  <span data-ttu-id="21e1a-113">Por ejemplo, si el sistema de destino contiene centenares de operaciones para administrar las reclamaciones de atención médica y las operaciones son dinámicas (es decir, los usuarios pueden agregar nuevas operaciones que llevan a cabo tareas adicionales), tiene sentido para exponer esta funcionalidad mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21e1a-113">For example, if the target system contains hundreds of operations for managing health care claims, and the operations are dynamic (meaning users can add new operations that perform additional tasks), it makes sense to expose this functionality using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="21e1a-114">Esto garantizará que nuevas operaciones son reconocibles en las aplicaciones que utilizan el adaptador.</span><span class="sxs-lookup"><span data-stu-id="21e1a-114">This will ensure that new operations are discoverable by applications using the adapter.</span></span> <span data-ttu-id="21e1a-115">Con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], tendría que modificar el contrato de servicio porque es estático.</span><span class="sxs-lookup"><span data-stu-id="21e1a-115">With [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], you would have to modify the service contract because it is static.</span></span>  
  
## <a name="when-to-write-a-service"></a><span data-ttu-id="21e1a-116">Cuándo se debe escribir un servicio</span><span class="sxs-lookup"><span data-stu-id="21e1a-116">When to Write a Service</span></span>  
 <span data-ttu-id="21e1a-117">Use la *modelo de servicio WCF* para crear un servicio cuando:</span><span class="sxs-lookup"><span data-stu-id="21e1a-117">Use the *WCF Service Model* to create a service when:</span></span>  
  
- <span data-ttu-id="21e1a-118">El sistema de destino es estático y tiene un conjunto fijo de operaciones</span><span class="sxs-lookup"><span data-stu-id="21e1a-118">The target system is static and has a fixed set of operations</span></span>  
  
- <span data-ttu-id="21e1a-119">El sistema de destino tiene poca o ninguna de metadatos</span><span class="sxs-lookup"><span data-stu-id="21e1a-119">The target system has little or no metadata</span></span>  
  
- <span data-ttu-id="21e1a-120">Los desarrolladores de servicios tienen información detallada de la aplicación se exponga</span><span class="sxs-lookup"><span data-stu-id="21e1a-120">Service developers have detailed knowledge of the application to be exposed</span></span>  
  
- <span data-ttu-id="21e1a-121">Exposición de una aplicación nueva</span><span class="sxs-lookup"><span data-stu-id="21e1a-121">A brand new application is being exposed</span></span>  
  
- <span data-ttu-id="21e1a-122">Creación de adaptadores de transporte genérico</span><span class="sxs-lookup"><span data-stu-id="21e1a-122">You are creating generic transport adapters</span></span>  
  
  <span data-ttu-id="21e1a-123">Por ejemplo, si el sistema de destino contiene 20 operaciones para administrar equipos deportivos, puede exponer las operaciones de forma estática del contrato utilizando [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21e1a-123">For example, if the target system contains 20 operations for managing sports teams, you can expose the operations as a static contract using [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="21e1a-124">Al hacerlo, evita tener que implementar funciones de metadatos innecesarios y potencialmente puede minimizar el tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="21e1a-124">By doing so, you avoid implementing unnecessary metadata features and you can potentially minimize development time.</span></span>  
  
## <a name="when-to-write-a-channel"></a><span data-ttu-id="21e1a-125">Cuándo se debe escribir un canal</span><span class="sxs-lookup"><span data-stu-id="21e1a-125">When to Write a Channel</span></span>  
 <span data-ttu-id="21e1a-126">Use la *modelo del canal WCF* para crear un canal cuando:</span><span class="sxs-lookup"><span data-stu-id="21e1a-126">Use the *WCF Channel Model* to create a channel when:</span></span>  
  
-   <span data-ttu-id="21e1a-127">Creación de un protocolo de conexión.</span><span class="sxs-lookup"><span data-stu-id="21e1a-127">Creating a wire protocol.</span></span> <span data-ttu-id="21e1a-128">Ejemplos de protocolos de conexión que incluyen WS-ReliableMessaging protocolo.</span><span class="sxs-lookup"><span data-stu-id="21e1a-128">Examples of wire protocols include WS-ReliableMessaging Protocol.</span></span>  
  
-   <span data-ttu-id="21e1a-129">Enviar y recibir mensajes WCF a través de un transporte que no sean las que se incluyen en WCF (TCP, HTTP, canalizaciones con nombre, MSMQ y PeerChannel).</span><span class="sxs-lookup"><span data-stu-id="21e1a-129">Send/receive WCF messages over a transport other than ones that are included in WCF (TCP, HTTP, Named Pipes, MSMQ and PeerChannel).</span></span> <span data-ttu-id="21e1a-130">Por ejemplo, puede escribir un transporte UDP, TIBCO o un transporte de servicio de mensajería de Java (JMS).</span><span class="sxs-lookup"><span data-stu-id="21e1a-130">For example, you can write a UDP transport, TIBCO, or a Java Messaging Service (JMS) transport.</span></span>  
  
-   <span data-ttu-id="21e1a-131">La integración con un sistema que no se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="21e1a-131">Integrating with a system that is not exposed as a Web service.</span></span>  <span data-ttu-id="21e1a-132">En este caso, el transporte actúa como un adaptador adaptar los mensajes de WCF en formato de mensaje del sistema existente o API que permite que a un cliente WCF para comunicarse directamente con el sistema existente.</span><span class="sxs-lookup"><span data-stu-id="21e1a-132">In this case your transport acts as an adapter adapting WCF messages to the existing system's message format or API allowing a WCF client to talk directly to the existing system.</span></span> <span data-ttu-id="21e1a-133">Un ejemplo de esto es el transporte TCP de Web Services Enhancement (WSE) 3.0.</span><span class="sxs-lookup"><span data-stu-id="21e1a-133">An example of this is the Web Services Enhancement (WSE) 3.0 TCP transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e1a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="21e1a-134">See Also</span></span>  
 <span data-ttu-id="21e1a-135">[Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="21e1a-135">[Plan and design an adapter using the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="21e1a-136">Comprender el sistema LOB con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="21e1a-136">Understand the LOB system with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)
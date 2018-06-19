---
title: Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF | Documentos de Microsoft
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
ms.openlocfilehash: 2e377568887d3d626e288fc47f82714b189d44b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225012"
---
# <a name="difference-between-adapter-channel-and-service-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="d426f-102">Diferencia entre el canal del adaptador y el servicio en el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="d426f-102">Difference between adapter channel and service in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="d426f-103">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cada uno de ellos proporcionan un conjunto de API que pueden utilizarse para exponer la funcionalidad de la aplicación para consumir las aplicaciones en el mismo equipo o a través de una red.</span><span class="sxs-lookup"><span data-stu-id="d426f-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] each provide a set of APIs that can be used to expose application functionality to consuming applications on the same computer or across a network.</span></span> <span data-ttu-id="d426f-104">Para elegir el marco de trabajo más adecuado, debe tener en cuenta las propiedades de la aplicación del sistema de destino que está exponiendo así como los requisitos empresariales de la funcionalidad expuesta.</span><span class="sxs-lookup"><span data-stu-id="d426f-104">To choose the most appropriate framework, you must consider the properties of the target system application you are exposing as well as the business requirements for the exposed functionality.</span></span> <span data-ttu-id="d426f-105">Este tema proporcionan instrucciones que puede usar para elegir el marco de trabajo adecuado.</span><span class="sxs-lookup"><span data-stu-id="d426f-105">This topic provides guidelines that you can use to choose the appropriate framework.</span></span>  
  
## <a name="when-to-write-an-adapter"></a><span data-ttu-id="d426f-106">Cuando se escribe un adaptador</span><span class="sxs-lookup"><span data-stu-id="d426f-106">When to Write an Adapter</span></span>  
 <span data-ttu-id="d426f-107">Considere la posibilidad de escribir un adaptador mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] cuando:</span><span class="sxs-lookup"><span data-stu-id="d426f-107">Consider writing an adapter using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] when:</span></span>  
  
-   <span data-ttu-id="d426f-108">El sistema de destino sea una existente, no es*Web habilitadas para los servicios* sistema</span><span class="sxs-lookup"><span data-stu-id="d426f-108">The target system is an existing, non-*Web services-enabled* system</span></span>  
  
-   <span data-ttu-id="d426f-109">El sistema de destino es dinámico y puede mejorarse con nuevas operaciones</span><span class="sxs-lookup"><span data-stu-id="d426f-109">The target system is dynamic and can be enhanced with new operations</span></span>  
  
-   <span data-ttu-id="d426f-110">El sistema de destino tiene una gran cantidad de metadatos</span><span class="sxs-lookup"><span data-stu-id="d426f-110">The target system has a large amount of metadata</span></span>  
  
-   <span data-ttu-id="d426f-111">Hay un número grande, distintos de los usuarios para los datos del sistema de destino</span><span class="sxs-lookup"><span data-stu-id="d426f-111">There is a large, diverse number of users for the target system's data</span></span>  
  
-   <span data-ttu-id="d426f-112">Aplicaciones de consumo necesitan funcionalidad de detección de metadatos de aplicación enriquecida</span><span class="sxs-lookup"><span data-stu-id="d426f-112">Consuming applications need rich application metadata discovery functionality</span></span>  
  
 <span data-ttu-id="d426f-113">Por ejemplo, si el sistema de destino contiene centenares de operaciones para administrar notificaciones sanitarios y las operaciones son dinámicas (es decir, los usuarios pueden agregar nuevas operaciones que realizan tareas adicionales), tiene sentido para exponer esta funcionalidad mediante la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d426f-113">For example, if the target system contains hundreds of operations for managing health care claims, and the operations are dynamic (meaning users can add new operations that perform additional tasks), it makes sense to expose this functionality using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="d426f-114">Esto garantizará que nuevas operaciones son reconocibles las aplicaciones que utilizan el adaptador.</span><span class="sxs-lookup"><span data-stu-id="d426f-114">This will ensure that new operations are discoverable by applications using the adapter.</span></span> <span data-ttu-id="d426f-115">Con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], tendría que modificar el contrato de servicio, puesto que es estático.</span><span class="sxs-lookup"><span data-stu-id="d426f-115">With [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], you would have to modify the service contract because it is static.</span></span>  
  
## <a name="when-to-write-a-service"></a><span data-ttu-id="d426f-116">Cuándo se debe escribir un servicio</span><span class="sxs-lookup"><span data-stu-id="d426f-116">When to Write a Service</span></span>  
 <span data-ttu-id="d426f-117">Use la *modelo de servicio de WCF* para crear un servicio cuando:</span><span class="sxs-lookup"><span data-stu-id="d426f-117">Use the *WCF Service Model* to create a service when:</span></span>  
  
-   <span data-ttu-id="d426f-118">El sistema de destino es estático y tiene un conjunto fijo de operaciones</span><span class="sxs-lookup"><span data-stu-id="d426f-118">The target system is static and has a fixed set of operations</span></span>  
  
-   <span data-ttu-id="d426f-119">El sistema de destino tiene poca o ninguna metadatos</span><span class="sxs-lookup"><span data-stu-id="d426f-119">The target system has little or no metadata</span></span>  
  
-   <span data-ttu-id="d426f-120">Los programadores del servicio tener información detallada de la aplicación que se puedan exponer</span><span class="sxs-lookup"><span data-stu-id="d426f-120">Service developers have detailed knowledge of the application to be exposed</span></span>  
  
-   <span data-ttu-id="d426f-121">Se expone una nueva aplicación</span><span class="sxs-lookup"><span data-stu-id="d426f-121">A brand new application is being exposed</span></span>  
  
-   <span data-ttu-id="d426f-122">Va a crear adaptadores de transporte genérico</span><span class="sxs-lookup"><span data-stu-id="d426f-122">You are creating generic transport adapters</span></span>  
  
 <span data-ttu-id="d426f-123">Por ejemplo, si el sistema de destino contiene 20 operaciones para administrar equipos deportivos, puede exponer las operaciones como un contrato estática mediante [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d426f-123">For example, if the target system contains 20 operations for managing sports teams, you can expose the operations as a static contract using [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="d426f-124">De esta forma, evita tener que implementar funciones de metadatos innecesarios y potencialmente puede minimizar el tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d426f-124">By doing so, you avoid implementing unnecessary metadata features and you can potentially minimize development time.</span></span>  
  
## <a name="when-to-write-a-channel"></a><span data-ttu-id="d426f-125">Cuándo se debe escribir un canal</span><span class="sxs-lookup"><span data-stu-id="d426f-125">When to Write a Channel</span></span>  
 <span data-ttu-id="d426f-126">Use la *modelo del canal WCF* para crear un canal cuando:</span><span class="sxs-lookup"><span data-stu-id="d426f-126">Use the *WCF Channel Model* to create a channel when:</span></span>  
  
-   <span data-ttu-id="d426f-127">Creación de un protocolo de conexión.</span><span class="sxs-lookup"><span data-stu-id="d426f-127">Creating a wire protocol.</span></span> <span data-ttu-id="d426f-128">Ejemplos de protocolos de conexión incluyen el protocolo WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="d426f-128">Examples of wire protocols include WS-ReliableMessaging Protocol.</span></span>  
  
-   <span data-ttu-id="d426f-129">Enviar y recibir mensajes WCF a través de un transporte que no sea de los que se incluyen en WCF (TCP, HTTP, canalizaciones con nombre, MSMQ y PeerChannel).</span><span class="sxs-lookup"><span data-stu-id="d426f-129">Send/receive WCF messages over a transport other than ones that are included in WCF (TCP, HTTP, Named Pipes, MSMQ and PeerChannel).</span></span> <span data-ttu-id="d426f-130">Por ejemplo, puede escribir un transporte UDP, TIBCO o un transporte de servicio de mensajería Java (JMS).</span><span class="sxs-lookup"><span data-stu-id="d426f-130">For example, you can write a UDP transport, TIBCO, or a Java Messaging Service (JMS) transport.</span></span>  
  
-   <span data-ttu-id="d426f-131">Integración con un sistema que no se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="d426f-131">Integrating with a system that is not exposed as a Web service.</span></span>  <span data-ttu-id="d426f-132">En este caso, su transporte actúa como un adaptador adaptar los mensajes de WCF para el formato del mensaje del sistema existente o API que permite que a un cliente de WCF para comunicarse directamente con el sistema existente.</span><span class="sxs-lookup"><span data-stu-id="d426f-132">In this case your transport acts as an adapter adapting WCF messages to the existing system's message format or API allowing a WCF client to talk directly to the existing system.</span></span> <span data-ttu-id="d426f-133">Un ejemplo de esto es el transporte TCP de Web Services Enhancement (WSE) 3.0.</span><span class="sxs-lookup"><span data-stu-id="d426f-133">An example of this is the Web Services Enhancement (WSE) 3.0 TCP transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d426f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d426f-134">See Also</span></span>  
 <span data-ttu-id="d426f-135">[Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="d426f-135">[Plan and design an adapter using the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="d426f-136">Comprender el sistema LOB con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="d426f-136">Understand the LOB system with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)
---
title: "Usar el enrutamiento dinámico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-routing"></a><span data-ttu-id="3256b-102">Usar el enrutamiento dinámico</span><span class="sxs-lookup"><span data-stu-id="3256b-102">Using Dynamic Routing</span></span>
<span data-ttu-id="3256b-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite enrutamiento dinámico de mensajes mediante un proceso integrado y un agente de entrega genérico; también admite enrutamiento dinámico de mensajes en la capa de mensajería con los componentes de canalización ESB distribuidor o distribuidor de ESB desensamblar.</span><span class="sxs-lookup"><span data-stu-id="3256b-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports dynamic routing of messages using a built-in process and a generic delivery agent; it also supports dynamic routing of messages at the messaging layer using the ESB Dispatcher or ESB Dispatcher Disassemble pipeline components.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="3256b-104">Información general</span><span class="sxs-lookup"><span data-stu-id="3256b-104">Overview</span></span>  
 <span data-ttu-id="3256b-105">El mecanismo de resolución dinámica de [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] habilita la detección de puntos de conexión cuando llega un mensaje o inmediatamente antes de que se entrega un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3256b-105">The dynamic resolution mechanism in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] enables discovery of endpoints when a message arrives or immediately before a message is delivered.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="3256b-106">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="3256b-106">How It Works</span></span>  
 <span data-ttu-id="3256b-107">El agente de entrega genérico proporcionado con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es un ejemplo y una guía para el desarrollo y el uso de técnicas de enrutamientos dinámicas.</span><span class="sxs-lookup"><span data-stu-id="3256b-107">The generic delivery agent provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is both a sample and a guide to the development and usage of dynamic routing techniques.</span></span> <span data-ttu-id="3256b-108">Puede crear a agentes de entrega adicionales o implementar a agentes de entrega que consta de un puerto de envío (que no implementan una orquestación) fácilmente.</span><span class="sxs-lookup"><span data-stu-id="3256b-108">You can easily create additional delivery agents or implement delivery agents consisting of just a send port (which do not implement an orchestration).</span></span> <span data-ttu-id="3256b-109">De forma predeterminada, los componentes de canalización de envío de ESB y desensamblador de envío de ESB ofrecen mucho más con optimización para la capacidad de enrutamiento dinámica.</span><span class="sxs-lookup"><span data-stu-id="3256b-109">By default, the ESB Dispatch and ESB Dispatch Disassembler pipeline components offer a much more optimized dynamic routing capability.</span></span>  
  
 <span data-ttu-id="3256b-110">El agente de entrega genérico implementa una orquestación que se suscribe a mensajes donde la **nombre** atributo del elemento actual **ServiceInstance** elemento en el itinerario es  **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="3256b-110">The generic delivery agent itself implements an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Routing**.</span></span> <span data-ttu-id="3256b-111">El agente realiza la siguiente secuencia de operaciones:</span><span class="sxs-lookup"><span data-stu-id="3256b-111">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="3256b-112">Recibe un mensaje sin tipo (System.Xml.XmlDocument).</span><span class="sxs-lookup"><span data-stu-id="3256b-112">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="3256b-113">Intenta resolver n número de puntos de conexión mediante el Administrador de resolución.</span><span class="sxs-lookup"><span data-stu-id="3256b-113">It attempts to resolve n number of endpoints using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="3256b-114">Usa el Administrador de adaptador para establecer las propiedades de punto de conexión de contexto del mensaje y el puerto dinámico lógico.</span><span class="sxs-lookup"><span data-stu-id="3256b-114">It uses the adapter manager to set the endpoint properties of the message context and the logical dynamic port.</span></span>  
  
4.  <span data-ttu-id="3256b-115">Publica el mensaje a través del puerto de envío de enlace directo, lo que desencadena la suscripción de servidor BizTalk Server en el puerto de envío dinámico para enrutar los mensajes adicionales.</span><span class="sxs-lookup"><span data-stu-id="3256b-115">It publishes the message through the direct-bound send port, which triggers the BizTalk Server subscription on the dynamic send port for further message routing.</span></span>  
  
## <a name="how-to-configure-dynamic-routing"></a><span data-ttu-id="3256b-116">Cómo configurar el enrutamiento dinámico</span><span class="sxs-lookup"><span data-stu-id="3256b-116">How to Configure Dynamic Routing</span></span>  
 <span data-ttu-id="3256b-117">Para obtener más información acerca de cómo configurar el enrutamiento dinámico mediante el Diseñador de itinerario, vea Crear itinerarios uso itinerario del diseñador.</span><span class="sxs-lookup"><span data-stu-id="3256b-117">For more information about how to configure dynamic routing using the Itinerary Designer, see Creating Itineraries Using Itinerary Designer.</span></span>  
  
## <a name="dynamic-routing-errors"></a><span data-ttu-id="3256b-118">Errores de enrutamiento dinámicos</span><span class="sxs-lookup"><span data-stu-id="3256b-118">Dynamic Routing Errors</span></span>  
 <span data-ttu-id="3256b-119">El mecanismo de enrutamiento dinámico se crear y publicar un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] mensaje de error en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="3256b-119">The dynamic routing mechanism will create and publish an [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="3256b-120">El agente de entrega no puede determinar el punto de conexión durante la resolución de just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="3256b-120">The delivery agent cannot determine the endpoint during just-in-time (JIT) resolution.</span></span>  
  
-   <span data-ttu-id="3256b-121">Se produce un error de entrega.</span><span class="sxs-lookup"><span data-stu-id="3256b-121">A delivery failure occurs.</span></span>  
  
-   <span data-ttu-id="3256b-122">No existe ningún suscriptor para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="3256b-122">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="3256b-123">Se produce cualquier excepción del sistema.</span><span class="sxs-lookup"><span data-stu-id="3256b-123">Any system exception occurs.</span></span>
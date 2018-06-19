---
title: Información general sobre el Kit de herramientas ESB en BizTalk Server | Documentos de Microsoft
description: Explicación del Kit de herramientas de ESB, y lo que hace en BizTalk Server
caps.latest.revision: 6
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 9ce0bbe3710530a63127701447db87b0a3135b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296732"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a><span data-ttu-id="0cfba-103">¿Qué es el Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0cfba-103">What is the BizTalk ESB Toolkit</span></span>

## <a name="overview"></a><span data-ttu-id="0cfba-104">Información general</span><span class="sxs-lookup"><span data-stu-id="0cfba-104">Overview</span></span>
<span data-ttu-id="0cfba-105">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía las capacidades de BizTalk Server para admitir una arquitectura de mensajería con acoplamiento flexible.</span><span class="sxs-lookup"><span data-stu-id="0cfba-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the capabilities of BizTalk Server to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="0cfba-106">Mayoría de los desarrolladores está familiarizada con los paradigmas de desarrollo orientado al código, procedimientos u orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="0cfba-106">Most developers are familiar with code-oriented, procedural, or object-oriented development paradigms.</span></span> <span data-ttu-id="0cfba-107">Sin embargo, al empezar a desarrollar soluciones de BizTalk, los desarrolladores suelen pasar por alto las capacidades orientado a mensajes de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-107">However, when starting to develop BizTalk solutions, developers tend to overlook the message-oriented capabilities of BizTalk Server.</span></span>  
  
 <span data-ttu-id="0cfba-108">BizTalk Server incluye un mecanismo eficaz de publicación/suscripción que funciona mediante la creación y rellenar las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0cfba-108">BizTalk Server includes a powerful publish/subscribe mechanism that works by creating and filling subscriptions.</span></span> <span data-ttu-id="0cfba-109">Cuando llega un mensaje nuevo en la base de datos de cuadro de mensaje de BizTalk, un agente de mensaje identifica los suscriptores y envía el mensaje a los puntos de conexión que tienen suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0cfba-109">When a new message arrives in the BizTalk Message Box database, a message agent identifies subscribers and sends the message to any endpoints that have subscriptions.</span></span> <span data-ttu-id="0cfba-110">Se pueden crear suscripciones de varias maneras, incluyendo enlazar una orquestación a un puerto de recepción, tener una recepción correlacionada espera un mensaje, o crear un puerto de envío con una condición de filtro que coincide con una propiedad del mensaje (por ejemplo, el tipo, la recepción punto, o el valor de una propiedad enrutable).</span><span class="sxs-lookup"><span data-stu-id="0cfba-110">Subscriptions can be created in several ways, including binding an orchestration to a receive port, having a correlated receive waiting for a message, or creating a send port with a filter condition that matches a property of the message (such as the type, the receive point, or the value of a routable property).</span></span>  
  
 <span data-ttu-id="0cfba-111">Al proporcionar este enfoque eficaz y escalable, BizTalk Server permite a los desarrolladores crear una serie de subprocesos discretos, defina los tipos de mensajes que desencadenan su invocación y no se preocupe acerca de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0cfba-111">By providing this efficient and scalable approach, BizTalk Server enables developers to create a series of discrete sub-processes, define the types of messages that trigger their invocation, and not worry about the sequence.</span></span> <span data-ttu-id="0cfba-112">Un proceso iniciado por la llegada de un mensaje realice su procesamiento en el mensaje; Después de procesar el mensaje, puede entregar este u otro mensaje a la base de datos de cuadro de mensaje, que a su vez, puede activar uno o varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0cfba-112">A process initiated by the arrival of a message performs its processing on the message; after it processes the message, it can deliver this or another message to the Message Box database, which, in turn, may activate one or more sub-processes.</span></span>  
  
 <span data-ttu-id="0cfba-113">Microsoft proporciona los bloques de creación claves que son necesarios para la creación de infraestructuras de orientada al servicio completa, incluido Windows Server, .NET Framework y BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-113">Microsoft provides key building blocks that are required for building comprehensive Service-Oriented Infrastructures, including Windows Server, the .NET Framework, and BizTalk Server.</span></span> <span data-ttu-id="0cfba-114">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se basa en BizTalk Server porque proporciona la base para los servicios ESB más comunes, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cfba-114">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is based on BizTalk Server because it provides the basis for the most common ESB services, including the following:</span></span>  
  
-   <span data-ttu-id="0cfba-115">Enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="0cfba-115">Message routing</span></span>  
  
-   <span data-ttu-id="0cfba-116">Validación del mensaje</span><span class="sxs-lookup"><span data-stu-id="0cfba-116">Message validation</span></span>  
  
-   <span data-ttu-id="0cfba-117">Transformación de mensajes</span><span class="sxs-lookup"><span data-stu-id="0cfba-117">Message transformation</span></span>  
  
-   <span data-ttu-id="0cfba-118">Marco extensible para la conectividad</span><span class="sxs-lookup"><span data-stu-id="0cfba-118">Extensible adapter framework for connectivity</span></span>  
  
-   <span data-ttu-id="0cfba-119">Orquestación de servicios</span><span class="sxs-lookup"><span data-stu-id="0cfba-119">Service orchestration</span></span>  
  
-   <span data-ttu-id="0cfba-120">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="0cfba-120">Business rules engine</span></span>  
  
-   <span data-ttu-id="0cfba-121">Supervisión de la actividad de negocio</span><span class="sxs-lookup"><span data-stu-id="0cfba-121">Business activity monitoring</span></span>  
  
-   <span data-ttu-id="0cfba-122">Y servicios Web WS-\* integración (adaptador de WCF)</span><span class="sxs-lookup"><span data-stu-id="0cfba-122">Web service and WS-\* integration (WCF adapter)</span></span>  

## <a name="core-capabilities"></a><span data-ttu-id="0cfba-123">Capacidades principales</span><span class="sxs-lookup"><span data-stu-id="0cfba-123">Core capabilities</span></span>  
 <span data-ttu-id="0cfba-124">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server proporciona una gama de nuevas capacidades que se centra en crear aplicaciones sólidas, conectadas, orientadas a servicios.</span><span class="sxs-lookup"><span data-stu-id="0cfba-124">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications.</span></span> <span data-ttu-id="0cfba-125">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] trata los componentes de BizTalk Server como unidades de trabajo que se puede conectar, según sea necesario formar débilmente acoplados soluciones.</span><span class="sxs-lookup"><span data-stu-id="0cfba-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] treats BizTalk Server components as individual units of work that can be connected, as desired, to form loosely coupled solutions.</span></span> <span data-ttu-id="0cfba-126">Los siguientes son algunas de las capacidades básicas de que el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona para mejorar las capacidades de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="0cfba-126">The following are some of the core capabilities that the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides to enhance the capabilities of BizTalk Server:</span></span>  
  
-   <span data-ttu-id="0cfba-127">**Controlada por mediación de directivas.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-127">**Policy driven mediation.**</span></span> <span data-ttu-id="0cfba-128">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfba-128">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="0cfba-129">Proporciona el enrutamiento basado en itinerario que admite composición ligera del servicio en el momento de publicación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0cfba-129">It provides itinerary-based routing that supports lightweight service composition at the time of message publication.</span></span> <span data-ttu-id="0cfba-130">Este enfoque permite la detección dinámica de extremos de servicio y requisitos de mediación para enrutar los mensajes con un registro de servicio o la directiva de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="0cfba-130">This approach allows dynamic discovery of service endpoints and mediation requirements for message routing using a service registry or the business rules policy.</span></span>  
  
    -   <span data-ttu-id="0cfba-131">Agrega compatibilidad para centralizar la directiva de enrutamiento mediante itinerarios de servidor que se resuelve dinámicamente y se agregan al contexto del mensaje una vez un mensaje basado en itinerario recibido.</span><span class="sxs-lookup"><span data-stu-id="0cfba-131">It adds support for policy centralization for itinerary-based routing using server-side itineraries that are dynamically resolved and added to the message context after a message is received.</span></span> <span data-ttu-id="0cfba-132">La administración de itinerarios en una ubicación central permite el procesamiento de mensajes de los clientes que están completamente sin tener en cuenta cómo se enrutan sus solicitudes.</span><span class="sxs-lookup"><span data-stu-id="0cfba-132">Managing itineraries in a central location enables the processing of messages from clients that are completely unaware of how their requests are being routed.</span></span>  
  
    -   <span data-ttu-id="0cfba-133">Utiliza una versión mejorada de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y marco de proveedores de adaptador, que permite una resolución dinámica de los puntos de conexión y los requisitos de transformación; esto desacopla eficazmente el consumidor de los servicios.</span><span class="sxs-lookup"><span data-stu-id="0cfba-133">It uses an enhanced version of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework, which enables dynamic resolution of endpoints and transformation requirements; this effectively decouples the consumer from the services.</span></span>  
  
-   <span data-ttu-id="0cfba-134">**Conexión de sistemas.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-134">**Connecting systems.**</span></span> <span data-ttu-id="0cfba-135">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfba-135">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="0cfba-136">Proporciona componentes de canalización que normalizan los espacios de nombres de mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="0cfba-136">It provides pipeline components that normalize XML message namespaces.</span></span>  
  
    -   <span data-ttu-id="0cfba-137">Se integra con JMS a través del adaptador de WebSphere MQ para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-137">It integrates with JMS through the WebSphere MQ adapter for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="0cfba-138">Facilita los patrones de intercambio de mensajes que permiten la agregación de servicios dinámicos, enrutamiento de mensajes, validación de mensajes y transformación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0cfba-138">It facilitates message exchange patterns that enable dynamic service aggregation, message routing, message validation, and message transformation.</span></span>  
  
    -   <span data-ttu-id="0cfba-139">Admite la detección de punto de conexión de servicio de registro y la integración con el repositorio mediante UDDI 3.0.</span><span class="sxs-lookup"><span data-stu-id="0cfba-139">It supports service endpoint discovery from registry and repository integration using UDDI 3.0.</span></span>  
  
    -   <span data-ttu-id="0cfba-140">Admite el enrutamiento de mensajes a través de adaptadores de línea de negocio (LOB) con el adaptador de BizTalk de WCF-Custom para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-140">It supports message routing through line-of-business (LOB) adapters by using the WCF-Custom BizTalk Adapter for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="0cfba-141">**Administración y supervisión.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-141">**Management and monitoring.**</span></span> <span data-ttu-id="0cfba-142">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfba-142">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="0cfba-143">Proporciona herramientas y el marco de administración de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0cfba-143">It provides exception management framework and tools.</span></span>  
  
    -   <span data-ttu-id="0cfba-144">Facilita la reparación de mensajes y reenvío mediante el portal de administración, como una aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0cfba-144">It facilitates message repair and resubmission using a management portal, shipped as a sample application.</span></span> <span data-ttu-id="0cfba-145">Esta aplicación Web también admite las notificaciones de correo electrónico personalizable cuando se produce un error específico.</span><span class="sxs-lookup"><span data-stu-id="0cfba-145">This Web application also supports customizable e-mail notifications when a specific error occurs.</span></span>  
  
    -   <span data-ttu-id="0cfba-146">Permite la publicación, la administración y la integración de punto de conexión y el registro de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-146">It allows BizTalk Server endpoint and registry integration, management, and publication.</span></span>  
  
    -   <span data-ttu-id="0cfba-147">Proporciona un repositorio centralizado de itinerarios con control de versiones de servidor.</span><span class="sxs-lookup"><span data-stu-id="0cfba-147">It provides a centralized repository of versioned server-side itineraries.</span></span>  
  
    -   <span data-ttu-id="0cfba-148">Admite informes y análisis de aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfba-148">It supports reporting and analytics for BizTalk Server applications.</span></span>  
  
    -   <span data-ttu-id="0cfba-149">Incluye componentes de supervisión de la actividad de negocio para realizar el seguimiento de ejecución del servicio itinerarios, incluidos la hora de inicio, hora de finalización y la secuencia de mediación de servicio.</span><span class="sxs-lookup"><span data-stu-id="0cfba-149">It includes Business Activity Monitoring components to track itinerary service execution, including start time, end time, and service mediation sequence.</span></span>  
  
-   <span data-ttu-id="0cfba-150">**Gobierno de SOA.**</span><span class="sxs-lookup"><span data-stu-id="0cfba-150">**SOA governance.**</span></span> <span data-ttu-id="0cfba-151">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfba-151">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="0cfba-152">Se integra con soluciones de regulación de SOA de terceros, incluidos los agentes de administración integrada de BizTalk Server de AmberPoint y Software de SOA.</span><span class="sxs-lookup"><span data-stu-id="0cfba-152">It integrates with third-party SOA governance solutions, including embedded management agents for BizTalk Server from AmberPoint and SOA Software.</span></span>  

> [!TIP]
> <span data-ttu-id="0cfba-153">[Descripción de BizTalk Server](../core/understanding-biztalk-server.md) contiene más detalles sobre el motor de mensajería y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0cfba-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md) provides more details on the messaging engine, and more.</span></span>

## <a name="get-some-help"></a><span data-ttu-id="0cfba-154">Obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="0cfba-154">Get some help</span></span>
<span data-ttu-id="0cfba-155">Obtener ayuda y ayudar a otras personas en la [Kit de herramientas de BizTalk ESB foros](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="0cfba-155">Get some help, and help others at the [BizTalk ESB Toolkit forums](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0cfba-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0cfba-156">Next steps</span></span>
[<span data-ttu-id="0cfba-157">Contenido del Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0cfba-157">Contents of the BizTalk ESB Toolkit</span></span>](contents-of-the-biztalk-esb-toolkit.md)  

---
title: Información general sobre el Kit de herramientas ESB en BizTalk Server | Microsoft Docs
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
ms.openlocfilehash: 404e93739d45cbca0235990dc7d2014bf38e0a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008789"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a><span data-ttu-id="1005c-103">¿Qué es el Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1005c-103">What is the BizTalk ESB Toolkit</span></span>

## <a name="overview"></a><span data-ttu-id="1005c-104">Información general</span><span class="sxs-lookup"><span data-stu-id="1005c-104">Overview</span></span>
<span data-ttu-id="1005c-105">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía las capacidades de BizTalk Server para admitir una arquitectura de mensajería ligeramente acoplada.</span><span class="sxs-lookup"><span data-stu-id="1005c-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the capabilities of BizTalk Server to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="1005c-106">La mayoría de los desarrolladores están familiarizados con los paradigmas de desarrollo orientado a código, procedimientos u orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="1005c-106">Most developers are familiar with code-oriented, procedural, or object-oriented development paradigms.</span></span> <span data-ttu-id="1005c-107">Sin embargo, al empezar a desarrollar soluciones de BizTalk, los desarrolladores tienden a pasar por alto las capacidades orientadas a mensajes de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1005c-107">However, when starting to develop BizTalk solutions, developers tend to overlook the message-oriented capabilities of BizTalk Server.</span></span>  
  
 <span data-ttu-id="1005c-108">BizTalk Server incluye un mecanismo eficaz de publicación/suscripción que funciona creando y rellenando las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="1005c-108">BizTalk Server includes a powerful publish/subscribe mechanism that works by creating and filling subscriptions.</span></span> <span data-ttu-id="1005c-109">Cuando llega un mensaje nuevo en la base de datos de cuadro de mensaje de BizTalk, un agente de mensaje identifica los suscriptores y envía el mensaje a los puntos de conexión que tienen suscripciones.</span><span class="sxs-lookup"><span data-stu-id="1005c-109">When a new message arrives in the BizTalk Message Box database, a message agent identifies subscribers and sends the message to any endpoints that have subscriptions.</span></span> <span data-ttu-id="1005c-110">Las suscripciones se pueden crear de varias maneras, como enlazar una orquestación a un puerto de recepción, tener una recepción correlacionada espera un mensaje, o crear un puerto de envío con una condición de filtro que coincide con una propiedad del mensaje (por ejemplo, el tipo, la recepción punto o el valor de una propiedad enrutable).</span><span class="sxs-lookup"><span data-stu-id="1005c-110">Subscriptions can be created in several ways, including binding an orchestration to a receive port, having a correlated receive waiting for a message, or creating a send port with a filter condition that matches a property of the message (such as the type, the receive point, or the value of a routable property).</span></span>  
  
 <span data-ttu-id="1005c-111">Al proporcionar este enfoque eficaz y escalable, BizTalk Server permite a los desarrolladores crear una serie de los subprocesos discretos, definir los tipos de mensajes que desencadenan su invocación y no preocuparse acerca de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="1005c-111">By providing this efficient and scalable approach, BizTalk Server enables developers to create a series of discrete sub-processes, define the types of messages that trigger their invocation, and not worry about the sequence.</span></span> <span data-ttu-id="1005c-112">Un proceso iniciado por la llegada de un mensaje realice su procesamiento en el mensaje; Después de procesar el mensaje, puede entregar este u otro mensaje a la base de datos de cuadro de mensaje, que, a su vez, puede activar uno o varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="1005c-112">A process initiated by the arrival of a message performs its processing on the message; after it processes the message, it can deliver this or another message to the Message Box database, which, in turn, may activate one or more sub-processes.</span></span>  
  
 <span data-ttu-id="1005c-113">Microsoft proporciona los bloques de creación clave que son necesarios para crear infraestructuras de completa orientada a servicios, incluidos Windows Server, BizTalk Server y el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1005c-113">Microsoft provides key building blocks that are required for building comprehensive Service-Oriented Infrastructures, including Windows Server, the .NET Framework, and BizTalk Server.</span></span> <span data-ttu-id="1005c-114">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se basa en el servidor BizTalk Server porque proporciona la base para los servicios ESB más comunes, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1005c-114">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is based on BizTalk Server because it provides the basis for the most common ESB services, including the following:</span></span>  
  
-   <span data-ttu-id="1005c-115">Enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="1005c-115">Message routing</span></span>  
  
-   <span data-ttu-id="1005c-116">Validación de mensajes</span><span class="sxs-lookup"><span data-stu-id="1005c-116">Message validation</span></span>  
  
-   <span data-ttu-id="1005c-117">Transformación de mensajes</span><span class="sxs-lookup"><span data-stu-id="1005c-117">Message transformation</span></span>  
  
-   <span data-ttu-id="1005c-118">Marco extensible para la conectividad</span><span class="sxs-lookup"><span data-stu-id="1005c-118">Extensible adapter framework for connectivity</span></span>  
  
-   <span data-ttu-id="1005c-119">Orquestación de servicios</span><span class="sxs-lookup"><span data-stu-id="1005c-119">Service orchestration</span></span>  
  
-   <span data-ttu-id="1005c-120">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="1005c-120">Business rules engine</span></span>  
  
-   <span data-ttu-id="1005c-121">La actividad económica</span><span class="sxs-lookup"><span data-stu-id="1005c-121">Business activity monitoring</span></span>  
  
-   <span data-ttu-id="1005c-122">Y servicios Web WS-\* integración (adaptador de WCF)</span><span class="sxs-lookup"><span data-stu-id="1005c-122">Web service and WS-\* integration (WCF adapter)</span></span>  

## <a name="core-capabilities"></a><span data-ttu-id="1005c-123">Capacidades principales</span><span class="sxs-lookup"><span data-stu-id="1005c-123">Core capabilities</span></span>  
 <span data-ttu-id="1005c-124">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] amplía la funcionalidad de BizTalk Server para proporcionar una gama de nuevas capacidades sobre la creación de aplicaciones robustas, conectadas y orientada a servicios.</span><span class="sxs-lookup"><span data-stu-id="1005c-124">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications.</span></span> <span data-ttu-id="1005c-125">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] trata los componentes de BizTalk Server como unidades de trabajo que se pueden conectar, según sea necesario formar débilmente acoplados soluciones.</span><span class="sxs-lookup"><span data-stu-id="1005c-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] treats BizTalk Server components as individual units of work that can be connected, as desired, to form loosely coupled solutions.</span></span> <span data-ttu-id="1005c-126">Los siguientes son algunas de las capacidades básicas que la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona para mejorar las capacidades de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="1005c-126">The following are some of the core capabilities that the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides to enhance the capabilities of BizTalk Server:</span></span>  
  
- <span data-ttu-id="1005c-127">**Por mediación de directivas.**</span><span class="sxs-lookup"><span data-stu-id="1005c-127">**Policy driven mediation.**</span></span> <span data-ttu-id="1005c-128">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1005c-128">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  - <span data-ttu-id="1005c-129">Proporciona enrutamiento basado en itinerarios que admite la composición de servicio ligero en el momento de publicación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1005c-129">It provides itinerary-based routing that supports lightweight service composition at the time of message publication.</span></span> <span data-ttu-id="1005c-130">Este enfoque permite la detección dinámica de extremos de servicio y los requisitos de mediación para enrutar el mensaje mediante un registro del servicio o la directiva de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="1005c-130">This approach allows dynamic discovery of service endpoints and mediation requirements for message routing using a service registry or the business rules policy.</span></span>  
  
  - <span data-ttu-id="1005c-131">Agrega compatibilidad para centralizar la directiva de enrutamiento mediante itinerarios del lado servidor que se resuelven dinámicamente y se agregan al contexto del mensaje después de un mensaje basado en itinerarios se recibe.</span><span class="sxs-lookup"><span data-stu-id="1005c-131">It adds support for policy centralization for itinerary-based routing using server-side itineraries that are dynamically resolved and added to the message context after a message is received.</span></span> <span data-ttu-id="1005c-132">Administración de itinerarios en una ubicación central permite el procesamiento de mensajes de los clientes que desconocen por completo de cómo se enrutan las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="1005c-132">Managing itineraries in a central location enables the processing of messages from clients that are completely unaware of how their requests are being routed.</span></span>  
  
  - <span data-ttu-id="1005c-133">Usa una versión mejorada de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] resolución y el marco de proveedores de adaptador, lo que permite la resolución dinámica de los puntos de conexión y requisitos de transformación; esto desacopla eficazmente el consumidor de los servicios.</span><span class="sxs-lookup"><span data-stu-id="1005c-133">It uses an enhanced version of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework, which enables dynamic resolution of endpoints and transformation requirements; this effectively decouples the consumer from the services.</span></span>  
  
- <span data-ttu-id="1005c-134">**Conexión de sistemas.**</span><span class="sxs-lookup"><span data-stu-id="1005c-134">**Connecting systems.**</span></span> <span data-ttu-id="1005c-135">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1005c-135">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="1005c-136">Proporciona componentes de canalización que normalizan los espacios de nombres de mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="1005c-136">It provides pipeline components that normalize XML message namespaces.</span></span>  
  
  -   <span data-ttu-id="1005c-137">Se integra con JMS a través del adaptador de WebSphere MQ para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1005c-137">It integrates with JMS through the WebSphere MQ adapter for BizTalk Server.</span></span>  
  
  -   <span data-ttu-id="1005c-138">Facilita que los patrones de intercambio de mensajes que permiten la agregación de servicio dinámico, el enrutamiento de mensajes, validación de mensajes y transformación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1005c-138">It facilitates message exchange patterns that enable dynamic service aggregation, message routing, message validation, and message transformation.</span></span>  
  
  -   <span data-ttu-id="1005c-139">Admite la detección de punto de conexión del servicio de registro y la integración de repositorio con UDDI 3.0.</span><span class="sxs-lookup"><span data-stu-id="1005c-139">It supports service endpoint discovery from registry and repository integration using UDDI 3.0.</span></span>  
  
  -   <span data-ttu-id="1005c-140">Admite el enrutamiento de mensajes a través de adaptadores de línea de negocio (LOB) mediante el adaptador de BizTalk de WCF-Custom para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1005c-140">It supports message routing through line-of-business (LOB) adapters by using the WCF-Custom BizTalk Adapter for BizTalk Server.</span></span>  
  
- <span data-ttu-id="1005c-141">**Administración y supervisión.**</span><span class="sxs-lookup"><span data-stu-id="1005c-141">**Management and monitoring.**</span></span> <span data-ttu-id="1005c-142">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1005c-142">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="1005c-143">Proporciona herramientas y el marco de administración de excepciones.</span><span class="sxs-lookup"><span data-stu-id="1005c-143">It provides exception management framework and tools.</span></span>  
  
  -   <span data-ttu-id="1005c-144">Facilita la reparación de mensajes y volver a enviar mediante el portal de administración, se incluye como una aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1005c-144">It facilitates message repair and resubmission using a management portal, shipped as a sample application.</span></span> <span data-ttu-id="1005c-145">Esta aplicación Web también es compatible con notificaciones de correo electrónico personalizable cuando se produce un error específico.</span><span class="sxs-lookup"><span data-stu-id="1005c-145">This Web application also supports customizable e-mail notifications when a specific error occurs.</span></span>  
  
  -   <span data-ttu-id="1005c-146">Permite la publicación, administración e integración de punto de conexión y del registro de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1005c-146">It allows BizTalk Server endpoint and registry integration, management, and publication.</span></span>  
  
  -   <span data-ttu-id="1005c-147">Proporciona un repositorio centralizado de itinerarios de lado servidor con control de versiones.</span><span class="sxs-lookup"><span data-stu-id="1005c-147">It provides a centralized repository of versioned server-side itineraries.</span></span>  
  
  -   <span data-ttu-id="1005c-148">Admite informes y análisis para aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1005c-148">It supports reporting and analytics for BizTalk Server applications.</span></span>  
  
  -   <span data-ttu-id="1005c-149">Incluye componentes de la actividad económica para realizar un seguimiento de ejecución de servicio de itinerarios, incluida la hora de inicio, hora de finalización y la secuencia de mediación de servicio.</span><span class="sxs-lookup"><span data-stu-id="1005c-149">It includes Business Activity Monitoring components to track itinerary service execution, including start time, end time, and service mediation sequence.</span></span>  
  
- <span data-ttu-id="1005c-150">**Gobierno de SOA.**</span><span class="sxs-lookup"><span data-stu-id="1005c-150">**SOA governance.**</span></span> <span data-ttu-id="1005c-151">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1005c-151">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="1005c-152">Se integra con las soluciones de gobierno de SOA de terceros, incluidos a los agentes de administración integrada de servidor de BizTalk de AmberPoint y el Software de SOA.</span><span class="sxs-lookup"><span data-stu-id="1005c-152">It integrates with third-party SOA governance solutions, including embedded management agents for BizTalk Server from AmberPoint and SOA Software.</span></span>  

> [!TIP]
> <span data-ttu-id="1005c-153">[Descripción de BizTalk Server](../core/understanding-biztalk-server.md) proporciona más detalles sobre el motor de mensajería y mucho más.</span><span class="sxs-lookup"><span data-stu-id="1005c-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md) provides more details on the messaging engine, and more.</span></span>

## <a name="get-some-help"></a><span data-ttu-id="1005c-154">Obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="1005c-154">Get some help</span></span>
<span data-ttu-id="1005c-155">Obtener ayuda y ayudar a otros usuarios en el [foros de BizTalk ESB Toolkit](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="1005c-155">Get some help, and help others at the [BizTalk ESB Toolkit forums](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1005c-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1005c-156">Next steps</span></span>
[<span data-ttu-id="1005c-157">Contenido del kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="1005c-157">Contents of the BizTalk ESB Toolkit</span></span>](contents-of-the-biztalk-esb-toolkit.md)  

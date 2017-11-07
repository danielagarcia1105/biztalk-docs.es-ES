---
title: Arquitectura de JD Edwards OneWorld | Documentos de Microsoft
description: "Describe los servicios de entrada en tiempo de diseño y tiempo de ejecución y eventos de salida en tiempo de diseño y tiempo de ejecución en el adaptador de JD Edwards OneWorld en BizTalk"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f866e5d72e392136d19c155785aaf6b71db2ce3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="architecture-of-jd-edwards-oneworld"></a><span data-ttu-id="b7f8f-103">Arquitectura de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="b7f8f-103">Architecture of JD Edwards OneWorld</span></span>
<span data-ttu-id="b7f8f-104">Microsoft BizTalk Adapter para JD Edwards OneWorld proporciona acceso a las funciones de negocio de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-104">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="b7f8f-105">JD Edwards OneWorld se comunica entre los equipos cliente y servidor usando una arquitectura de mensajería patentada llamada JDENet.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-105">JD Edwards OneWorld communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="b7f8f-106">JDENet se implementa mediante las clases de conector de JD Edwards OneWorld que se encuentran en los archivos JAR, Connector.jar y Kernel.jar.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-106">JDENet is implemented by the JD Edwards OneWorld connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="b7f8f-107">La comunicación se implementa con TCP/IP como protocolo de transporte, con un puerto predeterminado 6009 o 6010.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="b7f8f-108">Para obtener una descripción de dónde se establece este valor, consulte [agregar los artefactos a la administración de BizTalk Server](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span><span class="sxs-lookup"><span data-stu-id="b7f8f-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="b7f8f-109">**Arquitectura para el adaptador de BizTalk para JD Edwards OneWorld**</span><span class="sxs-lookup"><span data-stu-id="b7f8f-109">**Architecture for BizTalk Adapter for JD Edwards OneWorld**</span></span>  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 <span data-ttu-id="b7f8f-110">Las llamadas a las funciones de negocio de JD Edwards OneWorld necesitan dos mensajes:</span><span class="sxs-lookup"><span data-stu-id="b7f8f-110">Calls to JD Edwards OneWorld business functions require two messages:</span></span>  
  
-   <span data-ttu-id="b7f8f-111">El primer mensaje responde con la ubicación del servidor que procesa la función de negocio.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-111">The first message responds with the location of the server that processes the business function.</span></span> <span data-ttu-id="b7f8f-112">Esto se logra mediante la realización de una búsqueda en un conjunto de tablas denominadas *asignación de configuración de objeto (OCM)*.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-112">This is accomplished by performing a lookup in a set of tables called *object configuration mapping (OCM)*.</span></span>  
  
-   <span data-ttu-id="b7f8f-113">El segundo mensaje envía un búfer de mensajes formateados que contienen los argumentos que se deben pasar a JD Edwards OneWorld o desde éste al servidor adecuado, y espera una respuesta.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-113">The second message sends a formatted message buffer containing the arguments to pass to or from JD Edwards OneWorld to the appropriate server, and waits for a reply.</span></span> <span data-ttu-id="b7f8f-114">Los búferes están formateados según las typedefs de las estructuras C++ subyacentes.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-114">The buffers are formatted according to the typedefs of the underlying C++ structs.</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="b7f8f-115">Servicios de entrada en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="b7f8f-115">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="b7f8f-116">En tiempo de diseño, se crea el puerto, se selecciona el adaptador y se proporciona información de credenciales para conectar con el servidor JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-116">At design time, you create your port, select the adapter, and provide credential information to connect to the target JD Edwards OneWorld server.</span></span> <span data-ttu-id="b7f8f-117">El entorno de desarrollo de Visual Studio llama al marco del adaptador para solicitar información en tiempo de diseño para este puerto.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-117">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="b7f8f-118">BizTalk Adapter para JD Edwards OneWorld usa Browsingagent para este puerto.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-118">BizTalk Adapter for JD Edwards OneWorld uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="b7f8f-119">En tiempo de diseño, BizTalk Server solicita información realizando llamadas al adaptador.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-119">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="b7f8f-120">Browsingagent convierte la solicitud en código nativo de JD Edwards OneWorld y, a continuación, transmite las solicitudes a JD Edwards OneWorld mediante la conexión de API ThinNet (establecida en Connector.jar y Kernel.jar).</span><span class="sxs-lookup"><span data-stu-id="b7f8f-120">The Browsingagent converts the request into native JD Edwards OneWorld code and then transmits the requests to JD Edwards OneWorld through the ThinNet API connection (established in the Connector and Kernel.jars).</span></span>  
  
-   <span data-ttu-id="b7f8f-121">Una función empresarial personalizada se instala a través de la instalación de BTSREL: expone las funciones de negocio principales.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-121">A custom business function is installed through the BTSREL installation: it exposes the master business functions.</span></span>  
  
-   <span data-ttu-id="b7f8f-122">Inicialmente se devuelve una lista de módulos de JD Edwards OneWorld y se transporta a Visual Studio, donde llena el asistente para adaptador.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-122">A list of modules in JD Edwards OneWorld is initially returned and transported to Visual Studio, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="b7f8f-123">Puede expandir la jerarquía para mostrar el nombre de biblioteca y el nombre de módulo.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-123">You can expand the hierarchy to display the library name and module name.</span></span>  
  
-   <span data-ttu-id="b7f8f-124">Cuando seleccione un módulo específico, verá esquemas para todas las funciones del módulo.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-124">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="b7f8f-125">El adaptador obtiene la información necesaria de JD Edwards OneWorld, y browsingagent crea los esquemas.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-125">The adapter obtains the required information from JD Edwards OneWorld, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="b7f8f-126">Los esquemas se agregan a la orquestación del proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-126">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="b7f8f-127">Servicios de entrada en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b7f8f-127">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="b7f8f-128">BizTalk Server llama a BizTalk Adapter para JD Edwards OneWorld para enviar un mensaje en un puerto específico.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-128">BizTalk Server calls the BizTalk Adapter for JD Edwards OneWorld to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="b7f8f-129">El agente de tiempo de ejecución convierte el XML en código JD Edwards nativo.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-129">The run-time agent converts the XML into native JD Edwards code.</span></span>  
  
-   <span data-ttu-id="b7f8f-130">El agente de tiempo de ejecución envía la solicitud a través de ThinNet al sistema de negocio JD Edwards especificado en las propiedades de transporte del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-130">The run-time agent submits the request through the ThinNet to the JD Edwards enterprise system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="b7f8f-131">La función de negocio principal se ejecuta en el sistema JD Edwards, que luego genera un documento de respuesta que indica el éxito o error, así como los parámetros de datos devueltos por la función de negocio.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-131">The master business function is executed on the JD Edwards system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="b7f8f-132">El mensaje enviado a JD Edwards OneWorld es una arquitectura de un solo mensaje y una sola respuesta.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-132">The message sent to JD Edwards OneWorld is a single message, single reply architecture.</span></span> <span data-ttu-id="b7f8f-133">No se puede procesar varios mensajes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-133">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="b7f8f-134">El documento de respuesta se devuelve a través de ThinNet, se convierte en XML y se vuelve a transmitir a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-134">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="b7f8f-135">Eventos de salida en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="b7f8f-135">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="b7f8f-136">Ninguna creación sistemática de metadatos de eventos está disponible.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-136">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="b7f8f-137">Debe proporcionarse a Visual Studio un facsímil del documento del evento de modo que pueda generarse un esquema e incorporarse al proyecto junto con el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-137">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="b7f8f-138">Eventos de salida en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b7f8f-138">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="b7f8f-139">Se establece un mecanismo de transporte de archivos en el servidor de negocio JD Edwards para transportar el documento XML resultante, desencadenado por la finalización del evento, al directorio de destino en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-139">A file transport mechanism is established in the JD Edwards enterprise server to transport the resulting XML document, triggered by the event completion, to the target directory on that server.</span></span>  
  
-   <span data-ttu-id="b7f8f-140">El equipo de BizTalk Server tiene una unidad asignada al directorio en el servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-140">The BizTalk Server computer has a mapped drive to the directory on the enterprise server.</span></span>  
  
-   <span data-ttu-id="b7f8f-141">Las propiedades de transporte del puerto de recepción se configuran para la unidad asignada.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-141">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="b7f8f-142">El puerto de recepción recibe los mensajes publicados en el directorio por el servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-142">The receive port receives messages posted to directory by the enterprise server.</span></span>  
  
-   <span data-ttu-id="b7f8f-143">La identificación de espacio de nombres de destino asegura que se enruten los mensajes correctos al puerto de recepción configurado.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-143">The target namespace identification ensures that the correct messages are routed to the configured receive port.</span></span>  
  
-   <span data-ttu-id="b7f8f-144">El puerto de recepción envía el documento XML a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b7f8f-144">The receive port submits the XML document to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f8f-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7f8f-145">See Also</span></span>  
 <span data-ttu-id="b7f8f-146">[Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="b7f8f-146">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="b7f8f-147">Planificación y arquitectura</span><span class="sxs-lookup"><span data-stu-id="b7f8f-147">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)
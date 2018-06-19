---
title: Arquitectura de BizTalk Adapter para JD Edwards EnterpriseOne | Documentos de Microsoft
description: Describe los servicios de entrada en tiempo de diseño y tiempo de ejecución y eventos de salida en tiempo de diseño y tiempo de ejecución en el adaptador de JD Edwards EnterpriseOne en BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b495ee9a34cf464bd5cc11caed53c5df54948a49
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013763"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="9b2c8-103">Arquitectura del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="9b2c8-103">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="9b2c8-104">El Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne proporciona acceso a las funciones empresariales de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="9b2c8-105">JD Edwards EnterpriseOne se comunica entre equipos cliente y servidor usando una arquitectura de mensajería propia denominada JDENet.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-105">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="9b2c8-106">JDENet se implementa mediante las clases de conector de JD Edwards EnterpriseOne que se encuentran en los archivos JAR, Connector.jar y Kernel.jar.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-106">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="9b2c8-107">La comunicación se implementa con TCP/IP como protocolo de transporte, con un puerto predeterminado 6009 o 6010.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="9b2c8-108">Para obtener una descripción de dónde se establece este valor, consulte [agregar los artefactos a la administración de BizTalk Server](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span><span class="sxs-lookup"><span data-stu-id="9b2c8-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="9b2c8-109">En la siguiente ilustración se muestra la arquitectura del Adaptador de BizTalk para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-109">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="9b2c8-110">Servicios de entrada en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9b2c8-110">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="9b2c8-111">En tiempo de diseño, cree un puerto, seleccione un adaptador y proporcione información de credencial para conectar con el servidor JD Edwards EnterpriseOne de destino.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-111">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="9b2c8-112">El entorno de desarrollo de Visual Studio llama al marco del adaptador para solicitar información en tiempo de diseño para este puerto.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-112">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="9b2c8-113">El adaptador usa el Browsingagent para este puerto.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-113">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="9b2c8-114">En tiempo de diseño, BizTalk Server solicita información realizando llamadas al adaptador.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-114">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="9b2c8-115">El Browsingagent convierte la solicitud en código nativo de JD Edwards EnterpriseOne y transmite las solicitudes a JD Edwards EnterpriseOne a través de la conexión ThinNet API (establecida en Connector.jar y Kernel.jar).</span><span class="sxs-lookup"><span data-stu-id="9b2c8-115">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="9b2c8-116">Una lista de módulos de JD Edwards EnterpriseOne se devuelve inicialmente y transporta al entorno de desarrollo de Visual Studio, donde rellena el Asistente para adaptador.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-116">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="9b2c8-117">Puede expandir la jerarquía mostrando el nombre de la biblioteca y, a continuación, el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-117">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="9b2c8-118">Cuando seleccione un módulo específico, verá esquemas para todas las funciones del módulo.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-118">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="9b2c8-119">El adaptador recibe la información necesaria de JD Edwards EnterpriseOne, y el browsingagent crea los esquemas.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-119">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="9b2c8-120">Los esquemas se agregan a la orquestación del proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-120">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="9b2c8-121">Servicios de entrada en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9b2c8-121">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="9b2c8-122">BizTalk Server llama al adaptador para enviar un mensaje en un puerto específico.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-122">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="9b2c8-123">El agente de tiempo de ejecución convierte XML en código JDE nativo.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-123">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="9b2c8-124">El agente de tiempo de ejecución envía la solicitud a través de ThinNet al sistema JD Edwards EnterpriseOne especificado en las propiedades de transporte del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-124">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="9b2c8-125">La función empresarial principal se ejecuta en el sistema JD Edwards EnterpriseOne, que a continuación genera un documento de respuesta que indica éxito o fracaso, así como parámetros de datos que devuelve la función empresarial.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-125">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="9b2c8-126">El mensaje enviado a JD Edwards EnterpriseOne es una arquitectura de un único mensaje, una única respuesta.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-126">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="9b2c8-127">No se puede procesar varios mensajes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-127">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="9b2c8-128">El documento de respuesta se devuelve a través de ThinNet, se convierte en XML y se vuelve a transmitir a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-128">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="9b2c8-129">Eventos de salida en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9b2c8-129">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="9b2c8-130">Ninguna creación sistemática de metadatos de eventos está disponible.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-130">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="9b2c8-131">Debe proporcionarse a Visual Studio un facsímil del documento del evento de modo que pueda generarse un esquema e incorporarse al proyecto junto con el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-131">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="9b2c8-132">Eventos de salida en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9b2c8-132">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="9b2c8-133">Se establece un mecanismo de transporte de archivo en el servidor JD Edwards EnterpriseOne para transportar el documento XML resultante, activado por la finalización del evento, al directorio de destino en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-133">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="9b2c8-134">El equipo de BizTalk Server tiene una unidad asignada al directorio en el servidor EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-134">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="9b2c8-135">Las propiedades de transporte del puerto de recepción se configuran para la unidad asignada.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-135">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="9b2c8-136">El puerto de recepción recibe mensajes, que se registran en un directorio por el servidor EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-136">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="9b2c8-137">La identificación del espacio de nombres de destino asegura que se enruten los mensajes correctos al puerto de recepción configurado</span><span class="sxs-lookup"><span data-stu-id="9b2c8-137">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="9b2c8-138">El puerto de recepción envía el documento XML en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9b2c8-138">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="9b2c8-139">Otros recursos útiles</span><span class="sxs-lookup"><span data-stu-id="9b2c8-139">More good stuff</span></span>
[<span data-ttu-id="9b2c8-140">Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="9b2c8-140">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="9b2c8-141">Crear los artefactos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9b2c8-141">Create the application artifacts</span></span>](../core/developing-applications2.md)  
[<span data-ttu-id="9b2c8-142">Importar su JD Edwards EnterpriseOne aplicación</span><span class="sxs-lookup"><span data-stu-id="9b2c8-142">Import your JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="9b2c8-143">Uso del control de excepciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9b2c8-143">Use BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)  
[<span data-ttu-id="9b2c8-144">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="9b2c8-144">Troubleshoot</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)  

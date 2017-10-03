---
title: Desarrollar adaptadores personalizados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c13aba7e378d67523ec755837ac65b26989730a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-adapters"></a><span data-ttu-id="0a881-102">Desarrollar adaptadores personalizados</span><span class="sxs-lookup"><span data-stu-id="0a881-102">Developing Custom Adapters</span></span>
<span data-ttu-id="0a881-103">Para intercambiar mensajes con sistemas externos, aplicaciones y entidades, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el concepto de un adaptador.</span><span class="sxs-lookup"><span data-stu-id="0a881-103">To exchange messages with external systems, applications, and entities, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the concept of an adapter.</span></span> <span data-ttu-id="0a881-104">Los adaptadores son COM o [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] componentes que transfieren mensajes desde y hacia el final de negocios.</span><span class="sxs-lookup"><span data-stu-id="0a881-104">Adapters are COM or [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] components that transfer messages to and from business end.</span></span> <span data-ttu-id="0a881-105">puntos (por ejemplo, sistemas de archivos, bases de datos y aplicaciones empresariales personalizadas) mediante el uso de varios protocolos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="0a881-105">points (such as file systems, databases, and custom business applications) by using various communication protocols.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a881-106">proporciona adaptadores nativos compatibles con varios protocolos.</span><span class="sxs-lookup"><span data-stu-id="0a881-106"> provides native adapters that support various protocols.</span></span> <span data-ttu-id="0a881-107">Estos incluyen:</span><span class="sxs-lookup"><span data-stu-id="0a881-107">These include:</span></span>  
  
-   <span data-ttu-id="0a881-108">Un adaptador de archivo que admite el envío y la recepción de mensajes desde una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="0a881-108">A File adapter that supports sending and receiving messages from a File location</span></span>  
  
-   <span data-ttu-id="0a881-109">Adaptadores para protocolos EDI, FTP, HTTP, MSMQ, SMTP, POP3 y SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a881-109">Adapters for EDI, FTP, HTTP, MSMQ, SMTP, POP3, and SOAP protocols</span></span>  
  
-   <span data-ttu-id="0a881-110">Un adaptador para[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a881-110">An adapter for [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span></span>  
  
 <span data-ttu-id="0a881-111">En algunos casos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que necesite transportar mensajes a una aplicación personalizada específica o usar un protocolo para el que no existe un adaptador nativo.</span><span class="sxs-lookup"><span data-stu-id="0a881-111">In some cases [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may need to transport messages to a specific custom application or use a protocol for which a native adapter does not exist.</span></span> <span data-ttu-id="0a881-112">Las compañías de terceros han escrito adaptadores compatibles con otros protocolos.</span><span class="sxs-lookup"><span data-stu-id="0a881-112">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="0a881-113">Antes de decidirse a escribir un adaptador personalizado, puede que desee saber si ya hay un adaptador para el protocolo.</span><span class="sxs-lookup"><span data-stu-id="0a881-113">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="0a881-114">Para obtener una lista de adaptadores y proveedores asociados, vea [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140).</span><span class="sxs-lookup"><span data-stu-id="0a881-114">For a list of adapters and associated vendors see [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140).</span></span> <span data-ttu-id="0a881-115">Si no consigue encontrar un adaptador compatible para satisfacer los requisitos de comunicación, puede desarrollar un adaptador personalizado propio.</span><span class="sxs-lookup"><span data-stu-id="0a881-115">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  
  
 <span data-ttu-id="0a881-116">La escritura de un adaptador personalizado puede resultar todo un desafío.</span><span class="sxs-lookup"><span data-stu-id="0a881-116">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="0a881-117">Para simplificar este proceso, Microsoft ha desarrollado una base denominada el marco de trabajo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="0a881-117">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="0a881-118">Puede usar este marco de trabajo como base para el desarrollo junto con el código de origen del adaptador de ejemplo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="0a881-118">You can use this framework as a basis for your development along with sample adapter source code in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="0a881-119">Los temas de esta sección incluyen sugerencias y recomendaciones para el desarrollo de adaptadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="0a881-119">The topics in this section present custom adapter development tips and recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a881-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a881-120">In This Section</span></span>  
  
-   [<span data-ttu-id="0a881-121">¿Qué es el marco de trabajo?</span><span class="sxs-lookup"><span data-stu-id="0a881-121">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)  
  
-   [<span data-ttu-id="0a881-122">Cómo BizTalk Server crea una instancia de un adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-122">How BizTalk Server Instantiates an Adapter</span></span>](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [<span data-ttu-id="0a881-123">Lotes de mensajes</span><span class="sxs-lookup"><span data-stu-id="0a881-123">Message Batches</span></span>](../core/message-batches.md)  
  
-   [<span data-ttu-id="0a881-124">Lotes de mensajes transaccionales</span><span class="sxs-lookup"><span data-stu-id="0a881-124">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)  
  
-   [<span data-ttu-id="0a881-125">Desarrollar un adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="0a881-125">Developing a Receive Adapter</span></span>](../core/developing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="0a881-126">Desarrollar un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="0a881-126">Developing a Send Adapter</span></span>](../core/developing-a-send-adapter.md)  
  
-   [<span data-ttu-id="0a881-127">Crear instancias de adaptadores aislados</span><span class="sxs-lookup"><span data-stu-id="0a881-127">Instantiating Isolated Adapters</span></span>](../core/instantiating-isolated-adapters.md)  
  
-   [<span data-ttu-id="0a881-128">Problemas de diseño del adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-128">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)  
  
-   [<span data-ttu-id="0a881-129">Cómo controlan los mensajes de gran tamaño en adaptadores</span><span class="sxs-lookup"><span data-stu-id="0a881-129">How Adapters Handle Large Messages</span></span>](../core/how-adapters-handle-large-messages.md)  
  
-   [<span data-ttu-id="0a881-130">Cómo controlar errores de los adaptadores</span><span class="sxs-lookup"><span data-stu-id="0a881-130">How to Handle Adapter Failures</span></span>](../core/how-to-handle-adapter-failures.md)  
  
-   [<span data-ttu-id="0a881-131">Cómo finalizar un adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-131">How to Terminate an Adapter</span></span>](../core/how-to-terminate-an-adapter.md)  
  
-   [<span data-ttu-id="0a881-132">Cómo diseñar un adaptador de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0a881-132">How to Design a Performant Adapter</span></span>](../core/how-to-design-a-performant-adapter.md)  
  
-   [<span data-ttu-id="0a881-133">Cómo implementar un adaptador personalizado</span><span class="sxs-lookup"><span data-stu-id="0a881-133">How to Deploy a Custom Adapter</span></span>](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [<span data-ttu-id="0a881-134">Cómo probar y depurar un adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-134">How to Test and Debug an Adapter</span></span>](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [<span data-ttu-id="0a881-135">Cómo agregar metadatos de adaptador a un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0a881-135">How to Add Adapter Metadata to a BizTalk Project</span></span>](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [<span data-ttu-id="0a881-136">Problemas de localización del adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-136">Adapter Localization Issues</span></span>](../core/adapter-localization-issues.md)  
  
-   [<span data-ttu-id="0a881-137">Sugerencias para diseñar un adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-137">Tips for Designing Your Adapter</span></span>](../core/tips-for-designing-your-adapter.md)  
  
-   [<span data-ttu-id="0a881-138">Configuración de tiempo de diseño de adaptador</span><span class="sxs-lookup"><span data-stu-id="0a881-138">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a881-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a881-139">See Also</span></span>  
 [<span data-ttu-id="0a881-140">Desarrollar componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="0a881-140">Developing Custom Components</span></span>](../core/developing-custom-components.md)
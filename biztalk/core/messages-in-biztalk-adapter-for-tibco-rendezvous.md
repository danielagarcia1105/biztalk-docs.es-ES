---
title: Mensajes en el adaptador de BizTalk para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- TIBCO Rendezvous
- messages
- message passing
- messages, passing
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc1eadbefdeb5c59df9a1b999ffdd3e530587a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="544f7-102">Mensajes en el adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="544f7-102">Messages in BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="544f7-103">El Adaptador de BizTalk para TIBCO Rendezvous proporciona conectividad bidireccional entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="544f7-103">BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="544f7-104">Este adaptador utiliza tanto la API TIBCO Rendezvous como la API del marco de trabajo de adaptadores BizTalk para proporcionar una elevada integración.</span><span class="sxs-lookup"><span data-stu-id="544f7-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
## <a name="about-tibco-rendezvous"></a><span data-ttu-id="544f7-105">Acerca de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="544f7-105">About TIBCO Rendezvous</span></span>  
 <span data-ttu-id="544f7-106">TIBCO Rendezvous es un producto de software que proporciona un bus de mensaje para la integración de aplicaciones empresariales(EAI).</span><span class="sxs-lookup"><span data-stu-id="544f7-106">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="544f7-107">TIBCO proporciona API de mensajería en C, C++, Java, Visual Basic y de Microsoft .NET Framework recibir fuentes de datos en hojas de cálculo de Microsoft Office Excel y otras aplicaciones de su elección.</span><span class="sxs-lookup"><span data-stu-id="544f7-107">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and for the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span> <span data-ttu-id="544f7-108">Para obtener más información, consulte [conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="544f7-108">For more information, see [TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md).</span></span>  
  
### <a name="message-passing"></a><span data-ttu-id="544f7-109">Pasar mensajes</span><span class="sxs-lookup"><span data-stu-id="544f7-109">Message Passing</span></span>  
 <span data-ttu-id="544f7-110">El concepto básico de pasar mensajes es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="544f7-110">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="544f7-111">Un mensaje tiene un único asunto formado por elementos separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="544f7-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="544f7-112">Se envía un mensaje a un único daemon de Rendezvous (aunque podría transmitirse a otros daemons).</span><span class="sxs-lookup"><span data-stu-id="544f7-112">A message is sent to a single Rendezvous daemon, although it might eventually be broadcast onto other daemons.</span></span>  
  
-   <span data-ttu-id="544f7-113">Un agente de escucha anuncia sus asuntos de interés a un daemon (con una función básica de comodín).</span><span class="sxs-lookup"><span data-stu-id="544f7-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility).</span></span> <span data-ttu-id="544f7-114">Los mensajes con asuntos coincidentes se le entregan si los dos daemons están conectados entre sí o son el mismo daemon.</span><span class="sxs-lookup"><span data-stu-id="544f7-114">Messages that have matching subjects are delivered to it if the two daemons are connected to each other, or are indeed the same daemon.</span></span>  
  
 <span data-ttu-id="544f7-115">Una significativa funcionalidad "Empresarial" se agrega si se desea, con la posibilidad de usar las opciones Tolerancia a errores/Fiable o Certificado, todas implementadas a través de mensajes subyacentes básicos.</span><span class="sxs-lookup"><span data-stu-id="544f7-115">Significant "Enterprise" functionality is layered onto this if desired--with Fault Tolerance/Reliable or Certified options possible--all implemented through the underlying basic messages.</span></span>  
  
 <span data-ttu-id="544f7-116">Los propios mensajes pueden verse como campos nombre-valor o número-valor escritos (los dos mecanismos de identificación de un mensaje pueden mezclarse y coincidir con determinadas restricciones).</span><span class="sxs-lookup"><span data-stu-id="544f7-116">The messages themselves can be viewed as typed name-value fields or number-value fields (the two identification mechanisms in a message can mix and match with certain restrictions).</span></span> <span data-ttu-id="544f7-117">Un mensaje en sí puede contener submensajes, que a su vez pueden contener submensajes.</span><span class="sxs-lookup"><span data-stu-id="544f7-117">A message itself can contain sub-messages, which can contain sub-messages.</span></span>  
  
 <span data-ttu-id="544f7-118">Los nombres de asunto se componen de uno o varios elementos separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="544f7-118">Subject names consist of one or more elements separated by dot characters (periods).</span></span> <span data-ttu-id="544f7-119">Los elementos implementan una jerarquía de nombres de asunto que refleja la estructura de la información en un sistema de aplicación.</span><span class="sxs-lookup"><span data-stu-id="544f7-119">The elements implement a subject name hierarchy that reflects the structure of information in an application system.</span></span> <span data-ttu-id="544f7-120">Las siguientes cadenas son ejemplos de nombres de asunto válidos:</span><span class="sxs-lookup"><span data-stu-id="544f7-120">The following strings are examples of valid subject names:</span></span>  
  
-   <span data-ttu-id="544f7-121">RUN.HOME</span><span class="sxs-lookup"><span data-stu-id="544f7-121">RUN.HOME</span></span>  
  
-   <span data-ttu-id="544f7-122">RUN.for.Elected_Office</span><span class="sxs-lookup"><span data-stu-id="544f7-122">RUN.for.Elected_Office</span></span>  
  
 <span data-ttu-id="544f7-123">El Adaptador de BizTalk para TIBCO Rendezvous usa el SDK de TIBCO Rendezvous para publicar mensajes en asuntos de TIBCO Rendezvous y registrarse para eventos de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="544f7-123">BizTalk Adapter for TIBCO Rendezvous uses the TIBCO Rendezvous SDK to publish messages to TIBCO Rendezvous subjects and to register for TIBCO Rendezvous events.</span></span> <span data-ttu-id="544f7-124">Las clases relacionadas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se hospedan en un equipo con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="544f7-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related classes are hosted in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="544f7-125">Se inicia un proceso independiente (agente de tiempo de ejecución) y actúa como programa Rendezvous; se usan las funciones remotas de .NET Framework para intercambiar mensajes entre los dos.</span><span class="sxs-lookup"><span data-stu-id="544f7-125">A separate process (run-time agent) is started and acts as the Rendezvous program, and .NET Framework remoting is used to exchange messages between the two.</span></span>  
  
-   <span data-ttu-id="544f7-126">Los mensajes en el nivel de información, de advertencia y de error se envían al registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="544f7-126">Info-Level, Warning-Level, and Error-level messages are sent to the Windows event log.</span></span>  
  
-   <span data-ttu-id="544f7-127">Todos los niveles, incluidos los mensajes en el nivel de depuración, se envían al Registro de seguimiento de Windows.</span><span class="sxs-lookup"><span data-stu-id="544f7-127">All levels, including Debug-level messages, are sent to the Windows Tracing Log.</span></span>  
  
#### <a name="transmitter"></a><span data-ttu-id="544f7-128">Transmisor</span><span class="sxs-lookup"><span data-stu-id="544f7-128">Transmitter</span></span>  
 <span data-ttu-id="544f7-129">El Adaptador de BizTalk para TIBCO Rendezvous inicia un agente de tiempo de ejecución por cada puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="544f7-129">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per send port.</span></span> <span data-ttu-id="544f7-130">La API de .NET Framework de TIBCO Rendezvous solo permite establecer la codificación de caracteres en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="544f7-130">The TIBCO Rendezvous .NET Framework API only allows setting character encoding at a global scope.</span></span> <span data-ttu-id="544f7-131">Por lo tanto, una de las opciones de configuración de puerto es un número de página de códigos.</span><span class="sxs-lookup"><span data-stu-id="544f7-131">Therefore, one of the port configuration options is a code page number.</span></span> <span data-ttu-id="544f7-132">Al comenzar un proceso diferente para cada página de código, el adaptador puede proporcionar una mejor compatibilidad con la globalización.</span><span class="sxs-lookup"><span data-stu-id="544f7-132">By starting a different process for each code page, the adapter can provide better support for globalization.</span></span>  
  
#### <a name="receiver"></a><span data-ttu-id="544f7-133">Receptor</span><span class="sxs-lookup"><span data-stu-id="544f7-133">Receiver</span></span>  
 <span data-ttu-id="544f7-134">El Adaptador de BizTalk para TIBCO Rendezvous inicia un agente de tiempo de ejecución por cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="544f7-134">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per receive location.</span></span>  
  
#### <a name="transactions"></a><span data-ttu-id="544f7-135">Transactions</span><span class="sxs-lookup"><span data-stu-id="544f7-135">Transactions</span></span>  
 <span data-ttu-id="544f7-136">El producto TIBCO Rendezvous no es transaccional.</span><span class="sxs-lookup"><span data-stu-id="544f7-136">The TIBCO Rendezvous product is not transactional.</span></span> <span data-ttu-id="544f7-137">Es necesario un producto independiente, TIBCO Rendezvous TX.</span><span class="sxs-lookup"><span data-stu-id="544f7-137">A separate product, TIBCO Rendezvous TX, is required.</span></span> <span data-ttu-id="544f7-138">El Adaptador de BizTalk para TIBCO Rendezvous no admite transacciones en esta versión.</span><span class="sxs-lookup"><span data-stu-id="544f7-138">BizTalk Adapter for TIBCO Rendezvous does not support transactions in this release.</span></span>  
  
#### <a name="security"></a><span data-ttu-id="544f7-139">Seguridad</span><span class="sxs-lookup"><span data-stu-id="544f7-139">Security</span></span>  
 <span data-ttu-id="544f7-140">TIBCO Rendezvous solo admite la autenticación entre los programas y daemons de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="544f7-140">TIBCO Rendezvous only supports authentication between TIBCO Rendezvous programs and daemons.</span></span> <span data-ttu-id="544f7-141">No realiza la autorización o el cifrado.</span><span class="sxs-lookup"><span data-stu-id="544f7-141">It does not perform authorization or encryption.</span></span> <span data-ttu-id="544f7-142">Es necesario un producto independiente, TIBCO Rendezvous DataSecurity.</span><span class="sxs-lookup"><span data-stu-id="544f7-142">A separate product, TIBCO Rendezvous DataSecurity, is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544f7-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="544f7-143">See Also</span></span>  
 <span data-ttu-id="544f7-144">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="544f7-144">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="544f7-145">Introducción</span><span class="sxs-lookup"><span data-stu-id="544f7-145">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)
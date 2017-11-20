---
title: "Acelerador de BizTalk para SWIFT en tiempo de ejecución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312a91d403d125fe6d245b92bf83da57d1031fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-accelerator-for-swift-runtime"></a><span data-ttu-id="17eea-102">Acelerador de BizTalk para SWIFT en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="17eea-102">BizTalk Accelerator for SWIFT Runtime</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="17eea-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona la funcionalidad de dos formas: materiales de desarrollo y los componentes de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="17eea-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides functionality in two forms: development materials and runtime components.</span></span> <span data-ttu-id="17eea-104">Los materiales de desarrollo incluyen esquemas XSD, reglas de validación y las directivas y código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17eea-104">Development materials include XSD schemas, validation rules and policies, and sample code.</span></span> <span data-ttu-id="17eea-105">Los componentes en tiempo de ejecución incluyen el Desensamblador SWIFT personalizado, el ensamblador SWIFT personalizado, la reparación de mensajes y nuevo envío orquestación (MrsrRepair.odx) y la orquestación de conciliación de respuesta de FIN (FrrMain.odx).</span><span class="sxs-lookup"><span data-stu-id="17eea-105">Runtime components include the custom SWIFT disassembler, the custom SWIFT assembler, the Message Repair and New Submission orchestration (MrsrRepair.odx), and the FIN Response Reconciliation orchestration (FrrMain.odx).</span></span> <span data-ttu-id="17eea-106">Para obtener más información sobre la reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span><span class="sxs-lookup"><span data-stu-id="17eea-106">For more information on Message Repair and New Submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span> <span data-ttu-id="17eea-107">Para obtener más información sobre FRR, consulte [FINÉS respuesta conciliación](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span><span class="sxs-lookup"><span data-stu-id="17eea-107">For more information on FRR, see [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="17eea-108">En la siguiente ilustración muestra la arquitectura de alto nivel de sistema de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17eea-108">The following figure shows the high-level system architecture of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  
  
 <span data-ttu-id="17eea-109">La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y una aplicación back-end, y cómo se utiliza A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en MRSR de sitio de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="17eea-109">The following figure illustrates how messages flow between A4SWIFT and a back-end application, and how A4SWIFT uses [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms in MRSR site for Message Repair and New Submission.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  
  
 <span data-ttu-id="17eea-110">La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="17eea-110">The following figure illustrates how messages flow between A4SWIFT and the SWIFT Network.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  
  
 <span data-ttu-id="17eea-111">Puede definir todos los componentes de A4SWIFT como implementaciones específicas de vertical de [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] componentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17eea-111">You can define all A4SWIFT components as vertical-specific implementations of [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] application components.</span></span> <span data-ttu-id="17eea-112">Aceleradores de BizTalk proporcionan funciones de desarrollo y tiempo de ejecución para acelerar el desarrollo de aplicaciones de BizTalk específicos verticales sobre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17eea-112">BizTalk accelerators provide development and runtime functionality to accelerate vertical-specific BizTalk application development on top of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="17eea-113">Por consiguiente, cumplir todos los componentes de A4SWIFT (desarrollo o en tiempo de ejecución) y ajustará, la [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] arquitectura de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17eea-113">Therefore, all A4SWIFT components (development or runtime) abide by, and fit into, the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] application architecture.</span></span> <span data-ttu-id="17eea-114">A4SWIFT instala los componentes de tiempo de ejecución en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución como componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="17eea-114">A4SWIFT installs runtime components into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime as custom components.</span></span> <span data-ttu-id="17eea-115">Tras el desarrollo materiales se compilan e implementan, A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución usarlos para proporcionar funcionalidad de mensajería y la automatización de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="17eea-115">After development materials are compiled and deployed, A4SWIFT and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime use them to provide SWIFT messaging and automation functionality.</span></span>  
  
 <span data-ttu-id="17eea-116">En la siguiente ilustración se muestra la topología de aplicaciones de alto nivel para [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17eea-116">The following figure shows the high-level application topology for [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  
  
 <span data-ttu-id="17eea-117">El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación utiliza la base de datos de cuadro de mensajes y el modelo del publicador y el suscriptor que rige el flujo de mensajes dentro y fuera de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="17eea-117">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model uses the MessageBox database and the publisher-subscriber pattern that governs message flow into and out of the MessageBox database.</span></span> <span data-ttu-id="17eea-118">Para obtener más información acerca del diseño de arquitectura y aplicación de BizTalk, consulte [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="17eea-118">For more information about BizTalk architecture and application design, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="17eea-119">Hereda el modelo de aplicaciones de A4SWIFT el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación y al que se agregan componentes de SWIFT específicos para facilitar las soluciones basadas en SWIFT en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17eea-119">The A4SWIFT application model inherits the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model and adds to it SWIFT-specific components to facilitate SWIFT-related solutions on [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="17eea-120">En la lista siguiente se describe estos componentes específicos de A4SWIFT:</span><span class="sxs-lookup"><span data-stu-id="17eea-120">The following list describes these A4SWIFT-specific components:</span></span>  
  
-   <span data-ttu-id="17eea-121">**Componentes de tiempo de ejecución.**</span><span class="sxs-lookup"><span data-stu-id="17eea-121">**Runtime components.**</span></span> <span data-ttu-id="17eea-122">SWIFT desensamblador en la canalización de recepción, el ensamblador SWIFT en la canalización de envío, la orquestación de reparación de mensajes y nuevo envío y la orquestación de conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="17eea-122">SWIFT disassembler in the receive pipeline, SWIFT assembler in the send pipeline, Message Repair and New Submission orchestration, and FIN Response Reconciliation orchestration.</span></span>  
  
-   <span data-ttu-id="17eea-123">**Materiales de desarrollo.**</span><span class="sxs-lookup"><span data-stu-id="17eea-123">**Development materials.**</span></span> <span data-ttu-id="17eea-124">Esquemas SWIFT, reglas, orquestaciones y proyectos de ejemplo que desea incluir en soluciones de cliente y se implementan en el tiempo de ejecución para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="17eea-124">SWIFT schemas, rules, orchestrations, and sample projects to be included in customer solutions and deployed onto the runtime for execution.</span></span>  
  
 <span data-ttu-id="17eea-125">Esta sección describe el tiempo de ejecución de A4SWIFT en detalle.</span><span class="sxs-lookup"><span data-stu-id="17eea-125">This section describes the A4SWIFT runtime in detail.</span></span>  
  
 <span data-ttu-id="17eea-126">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="17eea-126">This section contains:</span></span>  
  
-   [<span data-ttu-id="17eea-127">Desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="17eea-127">SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  
  
-   [<span data-ttu-id="17eea-128">Ensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="17eea-128">SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  
  
-   [<span data-ttu-id="17eea-129">Enviando mensajes a través de ubicaciones de recepción y formularios de InfoPath</span><span class="sxs-lookup"><span data-stu-id="17eea-129">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  
  
-   [<span data-ttu-id="17eea-130">Motor de validación de mensajes</span><span class="sxs-lookup"><span data-stu-id="17eea-130">Message Validation Engine</span></span>](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
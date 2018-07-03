---
title: Acelerador de BizTalk para SWIFT en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc0e7a7cb00e16263e537e24abcc144e5c7d0a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966125"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a><span data-ttu-id="1f2df-102">Acelerador de BizTalk para SWIFT en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1f2df-102">BizTalk Accelerator for SWIFT Runtime</span></span>
<span data-ttu-id="1f2df-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona la funcionalidad de dos formas: materiales de desarrollo y los componentes de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f2df-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides functionality in two forms: development materials and runtime components.</span></span> <span data-ttu-id="1f2df-104">Materiales de desarrollo incluyen esquemas XSD, las reglas de validación y las directivas y código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f2df-104">Development materials include XSD schemas, validation rules and policies, and sample code.</span></span> <span data-ttu-id="1f2df-105">Componentes de tiempo de ejecución incluyen el Desensamblador SWIFT personalizado, el ensamblador de SWIFT personalizado, la reparación de mensajes y nuevo envío orquestación (MrsrRepair.odx) y la orquestación de conciliación de respuestas de FIN (FrrMain.odx).</span><span class="sxs-lookup"><span data-stu-id="1f2df-105">Runtime components include the custom SWIFT disassembler, the custom SWIFT assembler, the Message Repair and New Submission orchestration (MrsrRepair.odx), and the FIN Response Reconciliation orchestration (FrrMain.odx).</span></span> <span data-ttu-id="1f2df-106">Para obtener más información sobre la reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span><span class="sxs-lookup"><span data-stu-id="1f2df-106">For more information on Message Repair and New Submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span> <span data-ttu-id="1f2df-107">Para obtener más información sobre FRR, consulte [conciliación de respuestas de FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span><span class="sxs-lookup"><span data-stu-id="1f2df-107">For more information on FRR, see [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span></span>  

 <span data-ttu-id="1f2df-108">En la siguiente ilustración muestra la arquitectura de alto nivel del sistema de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2df-108">The following figure shows the high-level system architecture of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  

 <span data-ttu-id="1f2df-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span><span class="sxs-lookup"><span data-stu-id="1f2df-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span></span>  

 <span data-ttu-id="1f2df-110">La figura siguiente ilustra cómo fluyen los mensajes entre A4SWIFT y una aplicación de back-end y el uso de A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en MRSR de sitio de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="1f2df-110">The following figure illustrates how messages flow between A4SWIFT and a back-end application, and how A4SWIFT uses [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms in MRSR site for Message Repair and New Submission.</span></span>  

 <span data-ttu-id="1f2df-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span><span class="sxs-lookup"><span data-stu-id="1f2df-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span></span>  

 <span data-ttu-id="1f2df-112">La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1f2df-112">The following figure illustrates how messages flow between A4SWIFT and the SWIFT Network.</span></span>  

 <span data-ttu-id="1f2df-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span><span class="sxs-lookup"><span data-stu-id="1f2df-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span></span>  

 <span data-ttu-id="1f2df-114">Puede definir todos los componentes de A4SWIFT como implementaciones específicas de vertical de los componentes de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1f2df-114">You can define all A4SWIFT components as vertical-specific implementations of BizTalk Server application components.</span></span> <span data-ttu-id="1f2df-115">Aceleradores de BizTalk proporcionan una funcionalidad en tiempo de ejecución y desarrollo para acelerar el desarrollo de aplicaciones de BizTalk específicos verticales en la parte superior de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2df-115">BizTalk accelerators provide development and runtime functionality to accelerate vertical-specific BizTalk application development on top of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1f2df-116">Por lo tanto, todos los componentes de A4SWIFT (desarrollo o en tiempo de ejecución) acatar y caben en la arquitectura de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1f2df-116">Therefore, all A4SWIFT components (development or runtime) abide by, and fit into, the BizTalk Server application architecture.</span></span> <span data-ttu-id="1f2df-117">A4SWIFT instala componentes en tiempo de ejecución en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución como componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="1f2df-117">A4SWIFT installs runtime components into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime as custom components.</span></span> <span data-ttu-id="1f2df-118">Tras el desarrollo materiales se compilan e implementan, A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución usarlos para proporcionar funcionalidad de mensajería y la automatización de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1f2df-118">After development materials are compiled and deployed, A4SWIFT and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime use them to provide SWIFT messaging and automation functionality.</span></span>  

 <span data-ttu-id="1f2df-119">La siguiente ilustración muestra la topología de alto nivel de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1f2df-119">The following figure shows the high-level application topology for BizTalk Server.</span></span>  

 <span data-ttu-id="1f2df-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span><span class="sxs-lookup"><span data-stu-id="1f2df-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span></span>  

 <span data-ttu-id="1f2df-121">El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación utiliza la base de datos de cuadro de mensajes y el patrón de publicación-suscripción que rige el flujo de mensajes dentro y fuera de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1f2df-121">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model uses the MessageBox database and the publisher-subscriber pattern that governs message flow into and out of the MessageBox database.</span></span> <span data-ttu-id="1f2df-122">Para obtener más información sobre el diseño de arquitectura y la aplicación de BizTalk, consulte la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1f2df-122">For more information about BizTalk architecture and application design, see BizTalk Server Help.</span></span>  

 <span data-ttu-id="1f2df-123">El modelo de aplicación de A4SWIFT hereda el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación y le agrega componentes específicos de SWIFT para facilitar la soluciones relacionadas con SWIFT en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2df-123">The A4SWIFT application model inherits the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model and adds to it SWIFT-specific components to facilitate SWIFT-related solutions on [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1f2df-124">En la lista siguiente se describe estos componentes de A4SWIFT específicos:</span><span class="sxs-lookup"><span data-stu-id="1f2df-124">The following list describes these A4SWIFT-specific components:</span></span>  

- <span data-ttu-id="1f2df-125">**Componentes en tiempo de ejecución.**</span><span class="sxs-lookup"><span data-stu-id="1f2df-125">**Runtime components.**</span></span> <span data-ttu-id="1f2df-126">Desensamblador de SWIFT en la canalización de recepción, el ensamblador de SWIFT en la canalización de envío, la reparación de mensajes y nuevo envío de orquestación y la orquestación de conciliación de respuestas de FIN.</span><span class="sxs-lookup"><span data-stu-id="1f2df-126">SWIFT disassembler in the receive pipeline, SWIFT assembler in the send pipeline, Message Repair and New Submission orchestration, and FIN Response Reconciliation orchestration.</span></span>  

- <span data-ttu-id="1f2df-127">**Materiales de desarrollo.**</span><span class="sxs-lookup"><span data-stu-id="1f2df-127">**Development materials.**</span></span> <span data-ttu-id="1f2df-128">Esquemas de SWIFT, reglas, las orquestaciones y los proyectos de ejemplo se incluyen en las soluciones de clientes e implemente en el tiempo de ejecución para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f2df-128">SWIFT schemas, rules, orchestrations, and sample projects to be included in customer solutions and deployed onto the runtime for execution.</span></span>  

  <span data-ttu-id="1f2df-129">En esta sección se describe el tiempo de ejecución de A4SWIFT en detalle.</span><span class="sxs-lookup"><span data-stu-id="1f2df-129">This section describes the A4SWIFT runtime in detail.</span></span>  

  <span data-ttu-id="1f2df-130">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="1f2df-130">This section contains:</span></span>  

- [<span data-ttu-id="1f2df-131">Desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="1f2df-131">SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [<span data-ttu-id="1f2df-132">Ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="1f2df-132">SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [<span data-ttu-id="1f2df-133">Envío de mensajes a través de ubicaciones de recepción y formularios de InfoPath</span><span class="sxs-lookup"><span data-stu-id="1f2df-133">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [<span data-ttu-id="1f2df-134">Motor de validación de mensajes</span><span class="sxs-lookup"><span data-stu-id="1f2df-134">Message Validation Engine</span></span>](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)

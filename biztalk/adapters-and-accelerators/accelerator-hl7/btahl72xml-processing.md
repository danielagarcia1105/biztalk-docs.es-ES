---
title: Procesamiento de BTAHL72XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86697884c28d71fa9fb91c8b276293f7d36a588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72xml-processing"></a><span data-ttu-id="e62e4-102">Procesamiento de BTAHL72XML</span><span class="sxs-lookup"><span data-stu-id="e62e4-102">BTAHL72XML Processing</span></span>
<span data-ttu-id="e62e4-103">Los componentes siguientes en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) procesar mensajes (codificación XML) de HL7 2. XML:</span><span class="sxs-lookup"><span data-stu-id="e62e4-103">The following components in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.XML (XML-encoded) messages:</span></span>  
  
-   <span data-ttu-id="e62e4-104">Las canalizaciones y las bibliotecas principales: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineCommon.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="e62e4-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
-   <span data-ttu-id="e62e4-105">Bibliotecas de ensamblador y desensamblador: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlAsm.dll y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL72XmlDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="e62e4-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlDAsm.dll</span></span>  
  
-   <span data-ttu-id="e62e4-106">Adaptador de envío de la biblioteca de validación de confirmación (ACK) utilizada para la MLLP bidireccional: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="e62e4-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="xml-message-modes"></a><span data-ttu-id="e62e4-107">Modos de mensaje de XML</span><span class="sxs-lookup"><span data-stu-id="e62e4-107">XML Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-108">admite los siguientes modos de mensaje para los mensajes de 2. XML:</span><span class="sxs-lookup"><span data-stu-id="e62e4-108"> supports the following message modes for 2.XML messages:</span></span>  
  
-   <span data-ttu-id="e62e4-109">Modo de publicador y el suscriptor (publicación-suscripción)</span><span class="sxs-lookup"><span data-stu-id="e62e4-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
     <span data-ttu-id="e62e4-110">El publicador se difunde a una entidad de suscriptores, como declarativas o un no solicitados update.</span><span class="sxs-lookup"><span data-stu-id="e62e4-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e62e4-111">y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporcionar flexibilidad de este modo, ya que puede administrar las suscripciones y las entidades después de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="e62e4-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
-   <span data-ttu-id="e62e4-112">Modo de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="e62e4-112">Request-response mode</span></span>  
  
     <span data-ttu-id="e62e4-113">Intercambio de mensajes un interrogative o consulta en la que da como resultado una solicitud específica de una entidad específica en un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e62e4-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="xml-validation"></a><span data-ttu-id="e62e4-114">Validación de XML</span><span class="sxs-lookup"><span data-stu-id="e62e4-114">XML Validation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-115">proporciona las siguientes de validación de 2. los mensajes XML:</span><span class="sxs-lookup"><span data-stu-id="e62e4-115"> provides the following validation of 2.XML messages:</span></span>  
  
-   <span data-ttu-id="e62e4-116">Lector XML</span><span class="sxs-lookup"><span data-stu-id="e62e4-116">XML reader</span></span>  
  
-   <span data-ttu-id="e62e4-117">Representación esquemática</span><span class="sxs-lookup"><span data-stu-id="e62e4-117">Schematic</span></span>  
  
     <span data-ttu-id="e62e4-118">Habilitar o deshabilitar la validación de esquema por la entidad.</span><span class="sxs-lookup"><span data-stu-id="e62e4-118">You enable or disable schematic validation by the party.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-119">utiliza los esquemas XML de 2. HL7 directamente para este procesamiento, según lo determinado por el campo de encabezado de la estructura de los mensajes MSH9.3 y el campo de Id. de versión MSH12 (2.3.1, 2.4 o 2.5).</span><span class="sxs-lookup"><span data-stu-id="e62e4-119"> uses the HL7 2.XML schemas directly for this processing, as determined by the MSH9.3 message-structure header field and the MSH12 Version ID field (2.3.1, 2.4, or 2.5).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-120">usa las capacidades de procesamiento de XML estándares en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e62e4-120"> uses the standard XML processing capabilities in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e62e4-121">Segmento de Z</span><span class="sxs-lookup"><span data-stu-id="e62e4-121">Z segment</span></span>  
  
     [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-122">valida que ningún segmento declarado se incluye en un segmento de Z no declarado.</span><span class="sxs-lookup"><span data-stu-id="e62e4-122"> validates that no declared segments are included in an undeclared Z segment.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="e62e4-123">Generación de confirmación</span><span class="sxs-lookup"><span data-stu-id="e62e4-123">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e62e4-124">admite los siguientes tipos de confirmaciones (ACK) para los mensajes de 2. XML.</span><span class="sxs-lookup"><span data-stu-id="e62e4-124"> supports the following types of acknowledgments (ACKs) for 2.XML messages.</span></span> <span data-ttu-id="e62e4-125">El tipo de error de HL7 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se utiliza el tipo de error (alternativo):</span><span class="sxs-lookup"><span data-stu-id="e62e4-125">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="e62e4-126">Confirmaciones originales HL7</span><span class="sxs-lookup"><span data-stu-id="e62e4-126">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="e62e4-127">HL7 mejorado confirmaciones</span><span class="sxs-lookup"><span data-stu-id="e62e4-127">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="e62e4-128">Acepte la confirmación y aplicación acepte</span><span class="sxs-lookup"><span data-stu-id="e62e4-128">Commit Accept and Application Accept</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62e4-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e62e4-129">See Also</span></span>  
 <span data-ttu-id="e62e4-130">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="e62e4-130">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="e62e4-131">Uso de esquemas XML de HL7 2.</span><span class="sxs-lookup"><span data-stu-id="e62e4-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
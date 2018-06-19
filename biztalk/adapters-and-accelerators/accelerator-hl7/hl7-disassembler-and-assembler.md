---
title: HL7 Desensamblador y ensamblador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204932"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="dadcd-102">HL7 Desensamblador y ensamblador</span><span class="sxs-lookup"><span data-stu-id="dadcd-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="dadcd-103">El Desensamblador de HL7 y de ensamblador proporcionan compatibilidad para mensajes con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="dadcd-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="dadcd-104">Puesto que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes de forma nativa en formato XML, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa el Desensamblador de HL7 y de ensamblador para realizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] un motor de integración de HL7.</span><span class="sxs-lookup"><span data-stu-id="dadcd-104">Since [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="dadcd-105">Desensamblador de HL7</span><span class="sxs-lookup"><span data-stu-id="dadcd-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="dadcd-106">El Desensamblador de HL7 analiza los mensajes entrantes con codificación HL7 en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dadcd-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="dadcd-107">Realiza la validación del encabezado del mensaje y una validación básica del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="dadcd-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="dadcd-108">Determina el esquema que usa para analizar el mensaje HL7 (vea [determinación del esquema en el HL7 2.X Desensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determina la entidad de origen para el mensaje y lleva a cabo una validación adicional del cuerpo (si habilitado para el entidad).</span><span class="sxs-lookup"><span data-stu-id="dadcd-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="dadcd-109">Ensamblador de HL7</span><span class="sxs-lookup"><span data-stu-id="dadcd-109">HL7 Assembler</span></span>  
 <span data-ttu-id="dadcd-110">El ensamblador de HL7 serializa los segmentos XML en un mensaje saliente de HL7.</span><span class="sxs-lookup"><span data-stu-id="dadcd-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="dadcd-111">Determina el esquema que utiliza para serializar el mensaje HL7 (vea [determinación del esquema en el HL7 2.X ensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determina la entidad de destino para el mensaje y realiza la validación del cuerpo (si está habilitado para la entidad).</span><span class="sxs-lookup"><span data-stu-id="dadcd-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="dadcd-112">El ensamblador puede serializar los mensajes de confirmación (ACK) siguientes:</span><span class="sxs-lookup"><span data-stu-id="dadcd-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="dadcd-113">Estático</span><span class="sxs-lookup"><span data-stu-id="dadcd-113">Static</span></span>  
  
-   <span data-ttu-id="dadcd-114">Modo original</span><span class="sxs-lookup"><span data-stu-id="dadcd-114">Original mode</span></span>  
  
-   <span data-ttu-id="dadcd-115">Modo mejorado</span><span class="sxs-lookup"><span data-stu-id="dadcd-115">Enhanced mode</span></span>  
  
 <span data-ttu-id="dadcd-116">El ensamblador de HL7 también tiene la capacidad de enrutar los mensajes de confirmación diferidos.</span><span class="sxs-lookup"><span data-stu-id="dadcd-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dadcd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dadcd-117">See Also</span></span>  
 <span data-ttu-id="dadcd-118">[Procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="dadcd-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="dadcd-119">Acelerador de BizTalk para HL7 componentes</span><span class="sxs-lookup"><span data-stu-id="dadcd-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
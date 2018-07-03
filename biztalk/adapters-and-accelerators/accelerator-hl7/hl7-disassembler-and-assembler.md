---
title: HL7 Desensamblador y ensamblador | Microsoft Docs
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
ms.openlocfilehash: d603e74defeac983b1287f16c7f562b706b8c54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994997"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="33f0c-102">HL7 Desensamblador y ensamblador</span><span class="sxs-lookup"><span data-stu-id="33f0c-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="33f0c-103">El Desensamblador HL7 y ensamblador proporcionan compatibilidad para mensajes con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="33f0c-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="33f0c-104">Desde Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesa los mensajes de forma nativa en formato XML, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) utiliza el Desensamblador HL7 y ensamblador para realizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] un motor de integración de HL7.</span><span class="sxs-lookup"><span data-stu-id="33f0c-104">Since Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="33f0c-105">Desensamblador HL7</span><span class="sxs-lookup"><span data-stu-id="33f0c-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="33f0c-106">El Desensamblador HL7 analiza los mensajes entrantes con codificación HL7 en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="33f0c-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="33f0c-107">Realiza la validación del encabezado del mensaje y la validación básica del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="33f0c-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="33f0c-108">Lo determina el esquema que usa para analizar el mensaje de HL7 (vea [determinación del esquema en el HL7 2.X Desensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determina la entidad de origen para el mensaje y lleva a cabo una validación adicional del cuerpo (si habilitada para el la entidad).</span><span class="sxs-lookup"><span data-stu-id="33f0c-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="33f0c-109">Ensamblador de HL7</span><span class="sxs-lookup"><span data-stu-id="33f0c-109">HL7 Assembler</span></span>  
 <span data-ttu-id="33f0c-110">El ensamblador HL7 serializa los segmentos XML en un mensaje saliente de HL7.</span><span class="sxs-lookup"><span data-stu-id="33f0c-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="33f0c-111">Determina el esquema que usa para serializar el mensaje de HL7 (consulte [determinación del esquema en el HL7 2.X ensamblador](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determina la entidad de destino para el mensaje y realiza la validación del cuerpo (si está habilitado para la entidad).</span><span class="sxs-lookup"><span data-stu-id="33f0c-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="33f0c-112">El ensamblador puede serializar los mensajes de confirmación (ACK) siguiente:</span><span class="sxs-lookup"><span data-stu-id="33f0c-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="33f0c-113">Estático</span><span class="sxs-lookup"><span data-stu-id="33f0c-113">Static</span></span>  
  
- <span data-ttu-id="33f0c-114">Modo original</span><span class="sxs-lookup"><span data-stu-id="33f0c-114">Original mode</span></span>  
  
- <span data-ttu-id="33f0c-115">Modo mejorado</span><span class="sxs-lookup"><span data-stu-id="33f0c-115">Enhanced mode</span></span>  
  
  <span data-ttu-id="33f0c-116">El ensamblador HL7 también tiene la capacidad para enrutar los mensajes de confirmación diferidos.</span><span class="sxs-lookup"><span data-stu-id="33f0c-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f0c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="33f0c-117">See Also</span></span>  
 <span data-ttu-id="33f0c-118">[Procesamiento de archivos planos BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="33f0c-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="33f0c-119">Acelerador de BizTalk para componentes de HL7</span><span class="sxs-lookup"><span data-stu-id="33f0c-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
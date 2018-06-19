---
title: Desensamblador XML y ensamblador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206652"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="2b962-102">Ensamblador y desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="2b962-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="2b962-103">El desensamblador XML y el ensamblador de asegurarse de que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) no solo es compatible con mensajes con codificación HL7, pero también admite mensajes XML entrantes o salientes.</span><span class="sxs-lookup"><span data-stu-id="2b962-103">The XML disassembler and assembler ensure that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="2b962-104">Desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="2b962-104">XML Disassembler</span></span>  
 <span data-ttu-id="2b962-105">El desensamblador XML analiza mensajes XML entrantes en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2b962-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="2b962-106">A medida que analiza los mensajes, el Desensamblador realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b962-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="2b962-107">Identificadores de secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="2b962-107">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="2b962-108">Controla las comprobaciones de propiedades obligatorias y opcionales</span><span class="sxs-lookup"><span data-stu-id="2b962-108">Handles checks of required/optional properties</span></span>  
  
-   <span data-ttu-id="2b962-109">Identificadores declarados segmentos Z</span><span class="sxs-lookup"><span data-stu-id="2b962-109">Handles declared Z segments</span></span>  
  
 <span data-ttu-id="2b962-110">A medida que analiza los mensajes, el Desensamblador realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b962-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
-   <span data-ttu-id="2b962-111">Validación sintáctica</span><span class="sxs-lookup"><span data-stu-id="2b962-111">Syntactic validation</span></span>  
  
-   <span data-ttu-id="2b962-112">Validación del esquema (si está habilitado)</span><span class="sxs-lookup"><span data-stu-id="2b962-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="2b962-113">ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="2b962-113">XML Assembler</span></span>  
 <span data-ttu-id="2b962-114">El ensamblador XML serializa los segmentos XML en un mensaje XML saliente.</span><span class="sxs-lookup"><span data-stu-id="2b962-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="2b962-115">El ensamblador XML admite y crea el siguiente reconocimiento de mensajes (ACK):</span><span class="sxs-lookup"><span data-stu-id="2b962-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="2b962-116">Estático</span><span class="sxs-lookup"><span data-stu-id="2b962-116">Static</span></span>  
  
-   <span data-ttu-id="2b962-117">Modo original</span><span class="sxs-lookup"><span data-stu-id="2b962-117">Original mode</span></span>  
  
-   <span data-ttu-id="2b962-118">Modo mejorado</span><span class="sxs-lookup"><span data-stu-id="2b962-118">Enhanced mode</span></span>  
  
 <span data-ttu-id="2b962-119">El ensamblador XML también tiene la capacidad para enrutar los mensajes de confirmación diferidos.</span><span class="sxs-lookup"><span data-stu-id="2b962-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b962-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b962-120">See Also</span></span>  
 <span data-ttu-id="2b962-121">[Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="2b962-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="2b962-122">Acelerador de BizTalk para HL7 componentes</span><span class="sxs-lookup"><span data-stu-id="2b962-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
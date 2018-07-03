---
title: Desensamblador XML y ensamblador | Microsoft Docs
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
ms.openlocfilehash: 3d8dfaf91d9b0d3d058c4d3e31cd67c652235eff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983045"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="e8dd2-102">Ensamblador y desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="e8dd2-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="e8dd2-103">El desensamblador XML y el ensamblador de asegurarse de que el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) no solo es compatible con los mensajes codificados en HL7, pero también admite mensajes XML entrantes o salientes.</span><span class="sxs-lookup"><span data-stu-id="e8dd2-103">The XML disassembler and assembler ensure that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="e8dd2-104">Desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="e8dd2-104">XML Disassembler</span></span>  
 <span data-ttu-id="e8dd2-105">El desensamblador XML analiza los mensajes XML entrantes en segmentos XML para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e8dd2-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="e8dd2-106">A medida que analiza los mensajes, el Desensamblador realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e8dd2-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
- <span data-ttu-id="e8dd2-107">Identificadores de secuencias de escape</span><span class="sxs-lookup"><span data-stu-id="e8dd2-107">Handles escape sequences</span></span>  
  
- <span data-ttu-id="e8dd2-108">Controla las comprobaciones de propiedades obligatorias y opcionales</span><span class="sxs-lookup"><span data-stu-id="e8dd2-108">Handles checks of required/optional properties</span></span>  
  
- <span data-ttu-id="e8dd2-109">Identificadores declarados segmentos de Z</span><span class="sxs-lookup"><span data-stu-id="e8dd2-109">Handles declared Z segments</span></span>  
  
  <span data-ttu-id="e8dd2-110">A medida que analiza los mensajes, el Desensamblador realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8dd2-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
- <span data-ttu-id="e8dd2-111">Validación sintáctica</span><span class="sxs-lookup"><span data-stu-id="e8dd2-111">Syntactic validation</span></span>  
  
- <span data-ttu-id="e8dd2-112">Validación del esquema (si está habilitado)</span><span class="sxs-lookup"><span data-stu-id="e8dd2-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="e8dd2-113">ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="e8dd2-113">XML Assembler</span></span>  
 <span data-ttu-id="e8dd2-114">El ensamblador XML serializa los segmentos XML en un mensaje XML saliente.</span><span class="sxs-lookup"><span data-stu-id="e8dd2-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="e8dd2-115">El ensamblador XML admite y crea la siguiente confirmación de mensajes (ACK):</span><span class="sxs-lookup"><span data-stu-id="e8dd2-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="e8dd2-116">Estático</span><span class="sxs-lookup"><span data-stu-id="e8dd2-116">Static</span></span>  
  
- <span data-ttu-id="e8dd2-117">Modo original</span><span class="sxs-lookup"><span data-stu-id="e8dd2-117">Original mode</span></span>  
  
- <span data-ttu-id="e8dd2-118">Modo mejorado</span><span class="sxs-lookup"><span data-stu-id="e8dd2-118">Enhanced mode</span></span>  
  
  <span data-ttu-id="e8dd2-119">El ensamblador XML también tiene la capacidad para enrutar los mensajes de confirmación diferidos.</span><span class="sxs-lookup"><span data-stu-id="e8dd2-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8dd2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8dd2-120">See Also</span></span>  
 <span data-ttu-id="e8dd2-121">[Procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="e8dd2-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="e8dd2-122">Acelerador de BizTalk para componentes de HL7</span><span class="sxs-lookup"><span data-stu-id="e8dd2-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
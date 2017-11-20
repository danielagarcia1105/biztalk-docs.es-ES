---
title: Flujo de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow
- BTAHL7, message flow
ms.assetid: 976d230f-942b-4c80-b03d-0b991a713ebe
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318f4fe89e230aecfa53ddda1861cae2a56b717f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-flow"></a><span data-ttu-id="83a0d-102">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="83a0d-102">Message Flow</span></span>
<span data-ttu-id="83a0d-103">Las secciones siguientes describen cómo fluyen los mensajes de estado de atención a través de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) y cómo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] funciona el enrutamiento de mensajería.</span><span class="sxs-lookup"><span data-stu-id="83a0d-103">The following sections describe how health care messages flow through [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]), and how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] messaging routing works.</span></span> <span data-ttu-id="83a0d-104">A través de esta ruta, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ofrece una funcionalidad mejorada para la validación de datos, de reemplazo de encabezado del mensaje y confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="83a0d-104">Through this routing, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] offers enhanced functionality for data validation, message-header override, and acknowledgments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83a0d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="83a0d-105">In This Section</span></span>  
  
-   [<span data-ttu-id="83a0d-106">Cómo fluyen los mensajes a través de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="83a0d-106">How Messages Flow through BTAHL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-messages-flow-through-btahl7.md)  
  
-   [<span data-ttu-id="83a0d-107">¿Cómo BTAHL7 enruta los mensajes</span><span class="sxs-lookup"><span data-stu-id="83a0d-107">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)  
  
-   [<span data-ttu-id="83a0d-108">Validación del mensaje</span><span class="sxs-lookup"><span data-stu-id="83a0d-108">Message Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)  
  
-   [<span data-ttu-id="83a0d-109">Invalidación de MSH</span><span class="sxs-lookup"><span data-stu-id="83a0d-109">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)  
  
-   [<span data-ttu-id="83a0d-110">Confirmaciones</span><span class="sxs-lookup"><span data-stu-id="83a0d-110">Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)
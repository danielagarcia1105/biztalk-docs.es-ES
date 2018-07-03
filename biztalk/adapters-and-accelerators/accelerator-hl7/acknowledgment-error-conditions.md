---
title: Las condiciones de Error de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26bc0524e76521fcb673c6d5d3dc70f43cb12798
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970261"
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="e3059-102">Condiciones de Error de confirmación</span><span class="sxs-lookup"><span data-stu-id="e3059-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="e3059-103">Las condiciones siguientes se producen un error irrecuperable de condición al Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) es la confirmación de procesamiento de mensajes (ACK):</span><span class="sxs-lookup"><span data-stu-id="e3059-103">The following conditions will result in a fatal error condition when Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="e3059-104">Faltan campos obligatorios en MSH9</span><span class="sxs-lookup"><span data-stu-id="e3059-104">Missing required fields in MSH9</span></span>  
  
- <span data-ttu-id="e3059-105">Faltan campos obligatorios en MSH12</span><span class="sxs-lookup"><span data-stu-id="e3059-105">Missing required fields in MSH12</span></span>  
  
  <span data-ttu-id="e3059-106">Las condiciones siguientes producen una condición de error no grave.</span><span class="sxs-lookup"><span data-stu-id="e3059-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="e3059-107">En esta situación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera la confirmación, pero también se suspende la confirmación:</span><span class="sxs-lookup"><span data-stu-id="e3059-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
- <span data-ttu-id="e3059-108">Falta un campo obligatorio en MSH11</span><span class="sxs-lookup"><span data-stu-id="e3059-108">Missing a required field in MSH11</span></span>  
  
- <span data-ttu-id="e3059-109">Falta un valor MSH10</span><span class="sxs-lookup"><span data-stu-id="e3059-109">Missing a MSH10 value</span></span>  
  
- <span data-ttu-id="e3059-110">Errores de tipo de enumeración para los campos opcionales en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="e3059-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3059-111">Errores de tipo de enumeración se encuentran en el encabezado al 15 de MSH está establecido en AL o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación ACK con el estado **MSA_1 = CR**.</span><span class="sxs-lookup"><span data-stu-id="e3059-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3059-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3059-112">See Also</span></span>  
 <span data-ttu-id="e3059-113">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="e3059-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="e3059-114">[Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="e3059-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="e3059-115">[Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="e3059-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="e3059-116">Configurar un puerto de envío para recibir confirmaciones</span><span class="sxs-lookup"><span data-stu-id="e3059-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)
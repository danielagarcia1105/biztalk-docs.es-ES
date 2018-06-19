---
title: Condiciones de Error de confirmación | Documentos de Microsoft
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
ms.openlocfilehash: 15b481f4cdb60822841021f7f708a6caea021b8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204588"
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="a3cd2-102">Condiciones de Error de confirmación</span><span class="sxs-lookup"><span data-stu-id="a3cd2-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="a3cd2-103">Las siguientes condiciones se producen un error irrecuperable condición cuando [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) es la confirmación de procesamiento de mensajes (ACK):</span><span class="sxs-lookup"><span data-stu-id="a3cd2-103">The following conditions will result in a fatal error condition when [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="a3cd2-104">Faltan campos obligatorios en MSH9</span><span class="sxs-lookup"><span data-stu-id="a3cd2-104">Missing required fields in MSH9</span></span>  
  
-   <span data-ttu-id="a3cd2-105">Faltan campos obligatorios en MSH12</span><span class="sxs-lookup"><span data-stu-id="a3cd2-105">Missing required fields in MSH12</span></span>  
  
 <span data-ttu-id="a3cd2-106">Las condiciones siguientes producen una condición de error no irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="a3cd2-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="a3cd2-107">En esta situación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera la confirmación, pero también se suspende la confirmación:</span><span class="sxs-lookup"><span data-stu-id="a3cd2-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
-   <span data-ttu-id="a3cd2-108">Falta un campo necesario en MSH11</span><span class="sxs-lookup"><span data-stu-id="a3cd2-108">Missing a required field in MSH11</span></span>  
  
-   <span data-ttu-id="a3cd2-109">Falta un valor de MSH10</span><span class="sxs-lookup"><span data-stu-id="a3cd2-109">Missing a MSH10 value</span></span>  
  
-   <span data-ttu-id="a3cd2-110">Errores de tipo de enumeración para los campos opcionales en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="a3cd2-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3cd2-111">Si hay errores de tipo de enumeración se encuentran en el encabezado cuando MSH 15 se establece AL o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación ACK con el estado **MSA_1 = CR**.</span><span class="sxs-lookup"><span data-stu-id="a3cd2-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cd2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3cd2-112">See Also</span></span>  
 <span data-ttu-id="a3cd2-113">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="a3cd2-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="a3cd2-114">[Tipos de esquema de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="a3cd2-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="a3cd2-115">[Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="a3cd2-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="a3cd2-116">Cómo configurar un puerto de envío para recibir mensajes de confirmación</span><span class="sxs-lookup"><span data-stu-id="a3cd2-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)
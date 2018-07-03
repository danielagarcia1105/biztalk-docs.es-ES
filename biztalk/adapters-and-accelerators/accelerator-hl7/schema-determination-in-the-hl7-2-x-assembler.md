---
title: Determinación del esquema en el ensamblador HL7 2.X | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 962f9576032ec8b42542111502c2b6d6698f98d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983653"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a><span data-ttu-id="020bb-102">Determinación del esquema en el ensamblador HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="020bb-102">Schema Determination in the HL7 2.X Assembler</span></span>
<span data-ttu-id="020bb-103">Cuando un mensaje fluye al serializador, el serializador en el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) usa MSH5 (entidad de destino) del mensaje para determinar las operaciones que se realizará en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="020bb-103">When a message flows to the serializer, the serializer in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses MSH5 (destination party) of the message to determine the operations to be performed on the message.</span></span> <span data-ttu-id="020bb-104">Estas operaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="020bb-104">Such operations include:</span></span>  
  
- <span data-ttu-id="020bb-105">Si se debe realizar la validación de XML de segmentos de cuerpo</span><span class="sxs-lookup"><span data-stu-id="020bb-105">Whether to perform XML validation for body segments</span></span>  
  
- <span data-ttu-id="020bb-106">Si se debe validar los tipos de datos personalizados para los segmentos de cuerpo</span><span class="sxs-lookup"><span data-stu-id="020bb-106">Whether to validate custom data types for body segments</span></span>  
  
- <span data-ttu-id="020bb-107">Si desea permitir delimitadores en el cuerpo de la derecha</span><span class="sxs-lookup"><span data-stu-id="020bb-107">Whether to allow trailing delimiters in the body</span></span>  
  
- <span data-ttu-id="020bb-108">Qué espacio de nombres de destino de esquema usará el serializador</span><span class="sxs-lookup"><span data-stu-id="020bb-108">Which schema target namespace the serializer will use</span></span>  
  
- <span data-ttu-id="020bb-109">Si el serializador se debe asignar el encabezado</span><span class="sxs-lookup"><span data-stu-id="020bb-109">Whether the serializer needs to map the header</span></span>  
  
  <span data-ttu-id="020bb-110">Para determinar el esquema, el serializador realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="020bb-110">To determine the schema, the serializer does the following:</span></span>  
  
- <span data-ttu-id="020bb-111">Establece el espacio de nombres de destino (**TargetNS**) en el mismo valor que el espacio de nombres configurado para la entidad de destino</span><span class="sxs-lookup"><span data-stu-id="020bb-111">Sets the target namespace (**TargetNS**) to the same value as the namespace configured for the destination party</span></span>  
  
- <span data-ttu-id="020bb-112">Extrae **Rootnode** desde el **BTS. MessageType** propiedad promocionada</span><span class="sxs-lookup"><span data-stu-id="020bb-112">Extracts **Rootnode** from the **BTS.MessageType** promoted property</span></span>  
  
  <span data-ttu-id="020bb-113">El **doctype** se convierte en **TargetNS + "#" + Rootnode**.</span><span class="sxs-lookup"><span data-stu-id="020bb-113">The **doctype** becomes **TargetNS + "#" + Rootnode**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020bb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="020bb-114">See Also</span></span>  
 <span data-ttu-id="020bb-115">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="020bb-115">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="020bb-116">Procesamiento de archivos planos BTAHL72X</span><span class="sxs-lookup"><span data-stu-id="020bb-116">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
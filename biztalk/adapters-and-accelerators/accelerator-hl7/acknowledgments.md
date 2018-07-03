---
title: Confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46dedd4f2173fd4a3ad36c272963334b4ce66a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969789"
---
# <a name="acknowledgments"></a><span data-ttu-id="64d73-102">Confirmaciones</span><span class="sxs-lookup"><span data-stu-id="64d73-102">Acknowledgments</span></span>
<span data-ttu-id="64d73-103">Configurar confirmaciones HL7 en el nivel de entidad mediante el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) configuración del explorador.</span><span class="sxs-lookup"><span data-stu-id="64d73-103">You configure HL7 acknowledgments at the party level using Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Configuration Explorer.</span></span> <span data-ttu-id="64d73-104">Las confirmaciones se aplican a las entidades que envían mensajes de HL7 a través de una ubicación de recepción (posiblemente el adaptador MLLP) y el HL7 2.X canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="64d73-104">Acknowledgments apply to parties that are sending HL7 messages through a receive location (possibly the MLLP adapter) and the HL7 2.X receive pipeline.</span></span> <span data-ttu-id="64d73-105">Cuando completa un mensaje de análisis y la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede crear un mensaje de confirmación que contiene el resultado (éxito o error), el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="64d73-105">When a message completes parsing and validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can create an acknowledgment message that contains the result (success or error) of the validation process.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="64d73-106"> puede devolver mensajes de confirmación de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="64d73-106"> can return acknowledgment messages in one of two ways.</span></span> <span data-ttu-id="64d73-107">Si la entidad remitente original enviado el mensaje original a través de un bidireccional recibir la configuración del puerto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve el mensaje de confirmación a través de esa ubicación original del puerto.</span><span class="sxs-lookup"><span data-stu-id="64d73-107">If the original sending party submitted the original message through a two-way receive port configuration, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns the acknowledgment message through that original port location.</span></span> <span data-ttu-id="64d73-108">Si el puerto envío original enviado el mensaje original a través de un sentido puerto de recepción [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje de confirmación en la base de datos de cuadro de mensajes y se distribuye con el modelo de suscripción.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d73-108">If the original sending port submitted the original message through a one-way receive port, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] submits the acknowledgment message into the MessageBox database and routes it using the subscription model.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span></span> <span data-ttu-id="64d73-109">realiza la asociación de entidad para recibir el mensaje procesar automáticamente en función del valor dentro del campo de aplicación de envío del mensaje HL7 (MSH 3.1).</span><span class="sxs-lookup"><span data-stu-id="64d73-109">performs party association for receive message processing automatically based on the value within the sending application field of the HL7 message (MSH 3.1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d73-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="64d73-110">See Also</span></span>  
 [<span data-ttu-id="64d73-111">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="64d73-111">Message Flow</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)
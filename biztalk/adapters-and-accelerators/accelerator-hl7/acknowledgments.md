---
title: Confirmaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c519ec4649ee1fbcfbc51edb7e3e8fe6ba6b5871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments"></a><span data-ttu-id="768b7-102">Confirmaciones</span><span class="sxs-lookup"><span data-stu-id="768b7-102">Acknowledgments</span></span>
<span data-ttu-id="768b7-103">Configurar confirmaciones HL7 en el nivel entidad con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) el Explorador de configuración.</span><span class="sxs-lookup"><span data-stu-id="768b7-103">You configure HL7 acknowledgments at the party level using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Configuration Explorer.</span></span> <span data-ttu-id="768b7-104">Confirmaciones que se aplican a las partes que están enviando mensajes HL7 a través de una ubicación de recepción (posiblemente el adaptador MLLP) y el HL7 2.X canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="768b7-104">Acknowledgments apply to parties that are sending HL7 messages through a receive location (possibly the MLLP adapter) and the HL7 2.X receive pipeline.</span></span> <span data-ttu-id="768b7-105">Cuando un mensaje completa el análisis y la validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede crear un mensaje de confirmación que contiene el resultado (éxito o error) del proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="768b7-105">When a message completes parsing and validation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can create an acknowledgment message that contains the result (success or error) of the validation process.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="768b7-106">puede devolver mensajes de confirmación de una de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="768b7-106"> can return acknowledgment messages in one of two ways.</span></span> <span data-ttu-id="768b7-107">Si la entidad remitente original enviado el mensaje original a través de dos sentidos recibe la configuración del puerto, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] devuelve el mensaje de confirmación a través de esa ubicación de puerto original.</span><span class="sxs-lookup"><span data-stu-id="768b7-107">If the original sending party submitted the original message through a two-way receive port configuration, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] returns the acknowledgment message through that original port location.</span></span> <span data-ttu-id="768b7-108">Si el puerto envío original enviado el mensaje original a través de un sentido puerto de recepción [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje de confirmación en la base de datos de cuadro de mensajes y los enruta mediante el modelo de suscripción.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span><span class="sxs-lookup"><span data-stu-id="768b7-108">If the original sending port submitted the original message through a one-way receive port, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] submits the acknowledgment message into the MessageBox database and routes it using the subscription model.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]</span></span> <span data-ttu-id="768b7-109">realiza la asociación de la entidad para recibir el mensaje procesar automáticamente según el valor del campo de aplicación remitente del mensaje HL7 (MSH 3.1).</span><span class="sxs-lookup"><span data-stu-id="768b7-109">performs party association for receive message processing automatically based on the value within the sending application field of the HL7 message (MSH 3.1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="768b7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="768b7-110">See Also</span></span>  
 [<span data-ttu-id="768b7-111">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="768b7-111">Message Flow</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)
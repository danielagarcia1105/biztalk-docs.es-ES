---
title: Tipos de esquema de mensaje de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a556155e364fe56b66f7938fd49036b47085aeac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967475"
---
# <a name="ack-message-schema-types"></a><span data-ttu-id="17876-102">Tipos de esquema de mensaje de confirmación</span><span class="sxs-lookup"><span data-stu-id="17876-102">ACK Message Schema Types</span></span>
<span data-ttu-id="17876-103">Esquemas de mensaje de confirmación tienen dos formas:</span><span class="sxs-lookup"><span data-stu-id="17876-103">Acknowledgment message schemas come in two forms:</span></span>  

- <span data-ttu-id="17876-104">**General confirmación (ACK)**.</span><span class="sxs-lookup"><span data-stu-id="17876-104">**General acknowledgment (ACK)**.</span></span> <span data-ttu-id="17876-105">Puede usar una confirmación (ACK) general donde la aplicación no define un mensaje de confirmación de nivel de aplicación de línea de negocio especiales o donde se produjo un error que impide el procesamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17876-105">You can use a general acknowledgment (ACK) where the application does not define a special line-of-business application level acknowledgment message or where an error occurred that precludes application processing.</span></span> <span data-ttu-id="17876-106">También puede usarlo para aceptar las confirmaciones de nivel.</span><span class="sxs-lookup"><span data-stu-id="17876-106">You can also use it for accept level acknowledgments.</span></span> <span data-ttu-id="17876-107">La tabla siguiente muestra la estructura del mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="17876-107">The following table lists the ACK message structure.</span></span>  


  | <span data-ttu-id="17876-108">Confirmación ^ varía ^ ACK</span><span class="sxs-lookup"><span data-stu-id="17876-108">ACK^varies^ACK</span></span> | <span data-ttu-id="17876-109">Confirmación general</span><span class="sxs-lookup"><span data-stu-id="17876-109">General acknowledgment</span></span> | <span data-ttu-id="17876-110">Capítulo</span><span class="sxs-lookup"><span data-stu-id="17876-110">Chapter</span></span> |
  |----------------|------------------------|---------|
  |      <span data-ttu-id="17876-111">MSH</span><span class="sxs-lookup"><span data-stu-id="17876-111">MSH</span></span>       |     <span data-ttu-id="17876-112">Encabezado de mensaje</span><span class="sxs-lookup"><span data-stu-id="17876-112">Message Header</span></span>     |    <span data-ttu-id="17876-113">2</span><span class="sxs-lookup"><span data-stu-id="17876-113">2</span></span>    |
  |      <span data-ttu-id="17876-114">MSA</span><span class="sxs-lookup"><span data-stu-id="17876-114">MSA</span></span>       | <span data-ttu-id="17876-115">Confirmación de mensajes</span><span class="sxs-lookup"><span data-stu-id="17876-115">Message Acknowledgment</span></span> |    <span data-ttu-id="17876-116">2</span><span class="sxs-lookup"><span data-stu-id="17876-116">2</span></span>    |
  |    <span data-ttu-id="17876-117">[ERROR]</span><span class="sxs-lookup"><span data-stu-id="17876-117">[ ERR ]</span></span>     |         <span data-ttu-id="17876-118">Error</span><span class="sxs-lookup"><span data-stu-id="17876-118">Error</span></span>          |    <span data-ttu-id="17876-119">2</span><span class="sxs-lookup"><span data-stu-id="17876-119">2</span></span>    |


- <span data-ttu-id="17876-120">**Retrasa la confirmación (MCF)**.</span><span class="sxs-lookup"><span data-stu-id="17876-120">**Delayed acknowledgment (MCF)**.</span></span> <span data-ttu-id="17876-121">Este mensaje existe únicamente por compatibilidad con versiones anteriores con HL7 versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="17876-121">This message exists only for backward compatibility with HL7 Version 2.1.</span></span> <span data-ttu-id="17876-122">Usarlo como parte del protocolo que se crea un formulario genérico de una confirmación de nivel de aplicación asincrónica, el mensaje MCF.</span><span class="sxs-lookup"><span data-stu-id="17876-122">You use it as part of the protocol that creates a generic form of an asynchronous application level acknowledgment, the MCF message.</span></span> <span data-ttu-id="17876-123">La tabla siguiente muestra la estructura del mensaje MCF.</span><span class="sxs-lookup"><span data-stu-id="17876-123">The following table lists the MCF message structure.</span></span>  

  |<span data-ttu-id="17876-124">MCF ^ varía ^ ACK</span><span class="sxs-lookup"><span data-stu-id="17876-124">MCF^varies^ACK</span></span>|<span data-ttu-id="17876-125">Confirmación diferida</span><span class="sxs-lookup"><span data-stu-id="17876-125">Delayed Acknowledgment</span></span>|<span data-ttu-id="17876-126">Capítulo</span><span class="sxs-lookup"><span data-stu-id="17876-126">Chapter</span></span>|  
  |--------------------|----------------------------|-------------|  
  |<span data-ttu-id="17876-127">MSH</span><span class="sxs-lookup"><span data-stu-id="17876-127">MSH</span></span>|<span data-ttu-id="17876-128">Encabezado de mensaje</span><span class="sxs-lookup"><span data-stu-id="17876-128">Message Header</span></span>|<span data-ttu-id="17876-129">2</span><span class="sxs-lookup"><span data-stu-id="17876-129">2</span></span>|  
  |<span data-ttu-id="17876-130">MSA</span><span class="sxs-lookup"><span data-stu-id="17876-130">MSA</span></span>|<span data-ttu-id="17876-131">Confirmación de mensajes</span><span class="sxs-lookup"><span data-stu-id="17876-131">Message Acknowledgment</span></span>|<span data-ttu-id="17876-132">2</span><span class="sxs-lookup"><span data-stu-id="17876-132">2</span></span>|  
  |<span data-ttu-id="17876-133">[ERROR]</span><span class="sxs-lookup"><span data-stu-id="17876-133">[ ERR ]</span></span>|<span data-ttu-id="17876-134">Error</span><span class="sxs-lookup"><span data-stu-id="17876-134">Error</span></span>|<span data-ttu-id="17876-135">2</span><span class="sxs-lookup"><span data-stu-id="17876-135">2</span></span>|  

  <span data-ttu-id="17876-136">Los mensajes de confirmación tienen la MSH9 campo establecido como **ACK ^\<**<em>eventos de desencadenador</em>**\>^ ACK** o **MCF ^\<**  <em>eventos de desencadenador</em>**\>^ ACK**.</span><span class="sxs-lookup"><span data-stu-id="17876-136">Acknowledgment messages have the MSH9 field set as either **ACK^\<**<em>trigger event</em>**\>^ACK** or **MCF^\<**<em>trigger event</em>**\>^ACK**.</span></span> <span data-ttu-id="17876-137">Como resultado, el primer componente de MSH9 es suficiente para determinar el esquema de confirmación.</span><span class="sxs-lookup"><span data-stu-id="17876-137">As a result, the first component of MSH9 is sufficient to determine the ACK schema.</span></span> <span data-ttu-id="17876-138">El documento de nombre que el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) utilizan canalizaciones siempre contiene HL7 como el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="17876-138">The document name that the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) pipeline uses always contains HL7 as the namespace.</span></span> <span data-ttu-id="17876-139">El nombre de tipo es el contenido del campo MSH9_1, que es la confirmación o MCF.</span><span class="sxs-lookup"><span data-stu-id="17876-139">The type name is the contents of the MSH9_1 field, which is ACK or MCF.</span></span> <span data-ttu-id="17876-140">Como resultado, como se muestra en el ejemplo anterior, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] canalización buscará un esquema con los nombres de HL7. Confirmación o HL7. MCF, dependiendo del valor del campo MSH9_1.</span><span class="sxs-lookup"><span data-stu-id="17876-140">As a result, as in the example above, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pipeline looks for a schema with the names HL7.ACK or HL7.MCF, depending on the value of the MSH9_1 field.</span></span> <span data-ttu-id="17876-141">El esquema para el cuerpo del mensaje es el mismo para todos los mensajes de la versión 2.X.</span><span class="sxs-lookup"><span data-stu-id="17876-141">The schema for the message body is the same for all 2.X version messages.</span></span>  

> [!NOTE]
>  <span data-ttu-id="17876-142">En un lote en / batch escenario ACK, el contenido del encabezado de confirmación es como sigue:</span><span class="sxs-lookup"><span data-stu-id="17876-142">In a batch in/batch out ACK scenario, the contents of the ACK header is as follows:</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="17876-143"> establece MSH1, 2, 8 y 15 y lo configurará en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="17876-143"> sets MSH1, 2, 8 and 15 to what you configure in the user interface.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="17876-144"> establece MSH7 a la hora del sistema.</span><span class="sxs-lookup"><span data-stu-id="17876-144"> sets MSH7 to the system time.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="17876-145"> MSH9 se establece en confirmación.</span><span class="sxs-lookup"><span data-stu-id="17876-145"> sets MSH9 to ACK.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="17876-146"> establece MSH12 2.4 o 2.5.</span><span class="sxs-lookup"><span data-stu-id="17876-146"> sets MSH12 to 2.4 or 2.5.</span></span>  

## <a name="see-also"></a><span data-ttu-id="17876-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="17876-147">See Also</span></span>  
 <span data-ttu-id="17876-148">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="17876-148">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="17876-149">[Segmento de confirmación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="17876-149">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 <span data-ttu-id="17876-150">[Configurar un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="17876-150">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="17876-151">Condiciones de error de confirmación</span><span class="sxs-lookup"><span data-stu-id="17876-151">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)
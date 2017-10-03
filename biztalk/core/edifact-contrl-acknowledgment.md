---
title: "Confirmación CONTRL de EDIFACT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baaca02ac076c79be004ed7b3d2c0f4fffce6ff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-contrl-acknowledgment"></a><span data-ttu-id="05371-102">Confirmación CONTRL de EDIFACT</span><span class="sxs-lookup"><span data-stu-id="05371-102">EDIFACT CONTRL Acknowledgment</span></span>
<span data-ttu-id="05371-103">La confirmación CONTRL (ACK) sirve de confirmación técnica y funcional para los mensajes con codificación EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="05371-103">The CONTRL acknowledgment (ACK) serves as both technical and functional acknowledgment for EDIFACT-encoded messages.</span></span> <span data-ttu-id="05371-104">Como confirmación técnica, el mensaje CONTRL indica la recepción de un intercambio.</span><span class="sxs-lookup"><span data-stu-id="05371-104">As a technical acknowledgment, the CONTRL message indicates receipt of an interchange.</span></span> <span data-ttu-id="05371-105">Como confirmación funcional, el mensaje CONTRL indica la aceptación o el rechazo del intercambio, el grupo o el mensaje recibido, con una lista de los errores o la funcionalidad no admitida.</span><span class="sxs-lookup"><span data-stu-id="05371-105">As a functional acknowledgment, the CONTRL message indicates acceptance or rejection of the received interchange, group, or message, with a list of errors or unsupported functionality.</span></span>  
  
 <span data-ttu-id="05371-106">El mensaje CONTRL completo sirve de confirmación funcional.</span><span class="sxs-lookup"><span data-stu-id="05371-106">The full CONTRL message serves as the functional ACK.</span></span> <span data-ttu-id="05371-107">Las secciones de la confirmación funcional vuelven a utilizarse para la confirmación técnica.</span><span class="sxs-lookup"><span data-stu-id="05371-107">Sections of the functional ACK are reused for the technical ACK.</span></span> <span data-ttu-id="05371-108">Si ha seleccionado las confirmaciones técnicas y funcionales en las propiedades de entidad para una entidad de envío o en las propiedades globales, BizTalk Server generará dos mensajes CONTRL: una ACK CONTRL técnica y una ACK. CONTRL funcionales</span><span class="sxs-lookup"><span data-stu-id="05371-108">If you have selected both technical and functional ACKs in the party properties for a sending party or in global properties, BizTalk Server will generate two CONTRL messages: a technical CONTRL ACK and a functional CONTRL ACK.</span></span>  
  
 <span data-ttu-id="05371-109">El ACK CONTRL se ajusta a la EFACT_\<número de versión > _CONTRL.xsd esquema.</span><span class="sxs-lookup"><span data-stu-id="05371-109">The CONTRL ACK conforms to the EFACT_\<Version number>_CONTRL.xsd schema.</span></span>  
  
## <a name="technical-acknowledgement"></a><span data-ttu-id="05371-110">Confirmación técnica</span><span class="sxs-lookup"><span data-stu-id="05371-110">Technical Acknowledgement</span></span>  
 <span data-ttu-id="05371-111">Una confirmación técnica implica que el destinatario del mensaje:</span><span class="sxs-lookup"><span data-stu-id="05371-111">A technical ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="05371-112">ha recibido el intercambio del asunto;</span><span class="sxs-lookup"><span data-stu-id="05371-112">has received the subject interchange;</span></span>  
  
-   <span data-ttu-id="05371-113">confirma que las partes del intercambio de asunto que se han comprobado para asegurarse de que los elementos de datos copiados en el segmento UCI del informe son sintácticamente correctos;</span><span class="sxs-lookup"><span data-stu-id="05371-113">acknowledges the parts of the subject interchange that have been checked in order to ensure that the data elements copied into the reporting UCI segment are syntactically correct;</span></span>  
  
-   <span data-ttu-id="05371-114">ha aceptado la responsabilidad de notificar al remitente de la confirmación o el rechazo de otras partes del intercambio de asunto;</span><span class="sxs-lookup"><span data-stu-id="05371-114">has accepted responsibility for notifying the sender of acknowledgement or rejection of the other parts of the subject interchange;</span></span>  
  
-   <span data-ttu-id="05371-115">y ha tomado precauciones razonables para asegurarse de que se le notifica de ello al remitente.</span><span class="sxs-lookup"><span data-stu-id="05371-115">and has taken reasonable precautions in order to ensure that the sender is so notified.</span></span>  
  
## <a name="functional-acknowledgement"></a><span data-ttu-id="05371-116">Confirmación funcional</span><span class="sxs-lookup"><span data-stu-id="05371-116">Functional Acknowledgement</span></span>  
 <span data-ttu-id="05371-117">Una confirmación funcional implica que el destinatario del intercambio:</span><span class="sxs-lookup"><span data-stu-id="05371-117">A functional ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="05371-118">ha recibido los niveles a los que se hace referencia del intercambio confirmado;</span><span class="sxs-lookup"><span data-stu-id="05371-118">has received the referenced levels(s) of the interchange acknowledged;</span></span>  
  
-   <span data-ttu-id="05371-119">ha comprobado que no hay ningún error sintáctico grave en el nivel al que se hace referencia confirmado que evita un procesamiento posterior del intercambio;</span><span class="sxs-lookup"><span data-stu-id="05371-119">has checked that there are no fatal syntactic errors in the acknowledged referenced level that prevents further processing of the interchange;</span></span>  
  
-   <span data-ttu-id="05371-120">ha comprobado que las partes confirmadas de los segmentos de servicio son sintácticamente correctas (si no se informa de ningún error);</span><span class="sxs-lookup"><span data-stu-id="05371-120">has checked that all acknowledged parts of service segments are semantically correct (if no errors are reported);</span></span>  
  
-   <span data-ttu-id="05371-121">cumplirá con las acciones solicitadas en los niveles a los que se hace referencia confirmados de los segmentos de servicio;</span><span class="sxs-lookup"><span data-stu-id="05371-121">will comply with the actions requested in the acknowledged referenced-levels of the service segments;</span></span>  
  
-   <span data-ttu-id="05371-122">ha aceptado la responsabilidad de notificar al remitente por otros medios de que el envío de un mensaje de CONTRL si se detecta con posterioridad algún error sintáctico o semántico tal y como se ha descrito anteriormente, o no puede procesarse la parte por algún otro motivo después de que la parte se haya confirmado en un mensaje de CONTRL enviado;</span><span class="sxs-lookup"><span data-stu-id="05371-122">has accepted responsibility for notifying the sender by other means than sending a CONTRL message if any syntactic or semantic errors as described above, are later detected in the relevant part, or the part cannot be processed for some other reason after the part has been acknowledged in a submitted CONTRL message;</span></span>  
  
-   <span data-ttu-id="05371-123">y ha tomado precauciones razonables para asegurarse de se han detectado dichos errores y de que se le notifica de ello al remitente.</span><span class="sxs-lookup"><span data-stu-id="05371-123">and has taken reasonable precautions in order to ensure that such errors are detected and that the sender is notified.</span></span>  
  
 <span data-ttu-id="05371-124">El rechazo implica que el destinatario del intercambio:</span><span class="sxs-lookup"><span data-stu-id="05371-124">Rejection implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="05371-125">no puede confirmar el intercambio de asunto o las partes relevantes por los motivos indicados en el mensaje de CONTRL;</span><span class="sxs-lookup"><span data-stu-id="05371-125">cannot acknowledge the subject interchange, or the relevant parts of it, for reasons indicated in the CONTRL message;</span></span>  
  
-   <span data-ttu-id="05371-126">y no emprenderá ninguna acción adicional sobre la información empresarial contenida en la parte rechazada del intercambio de asunto.</span><span class="sxs-lookup"><span data-stu-id="05371-126">and will not take any further action on business information contained in the rejected part of the subject interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05371-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="05371-127">In This Section</span></span>  
  
-   [<span data-ttu-id="05371-128">Mensaje de CONTRL de EDIFACT como confirmación técnica</span><span class="sxs-lookup"><span data-stu-id="05371-128">EDIFACT CONTRL Message as Technical Acknowledgment</span></span>](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [<span data-ttu-id="05371-129">Mensaje de CONTRL de EDIFACT como confirmación funcional</span><span class="sxs-lookup"><span data-stu-id="05371-129">EDIFACT CONTRL Message as Functional Acknowledgment</span></span>](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a><span data-ttu-id="05371-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="05371-130">See Also</span></span>  
 [<span data-ttu-id="05371-131">Estructura de confirmación EDI</span><span class="sxs-lookup"><span data-stu-id="05371-131">EDI Acknowledgment Structure</span></span>](../core/edi-acknowledgment-structure.md)
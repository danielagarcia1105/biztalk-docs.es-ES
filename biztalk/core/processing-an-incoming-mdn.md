---
title: Procesamiento de MDN entrante | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-an-incoming-mdn"></a><span data-ttu-id="710b3-102">Procesar MDN entrantes</span><span class="sxs-lookup"><span data-stu-id="710b3-102">Processing an Incoming MDN</span></span>
<span data-ttu-id="710b3-103">Las canalizaciones de recepción AS2 (AS2EDIReceive y AS2Receive) procesan un MDN entrante según las propiedades del acuerdo para la entidad como un receptor de mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="710b3-103">The AS2 receive pipelines (AS2EDIReceive and AS2Receive) process an incoming MDN based upon the agreement properties for the party as an AS2 message receiver.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="710b3-104"> correlaciona automáticamente el MDN al mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="710b3-104"> automatically correlates the MDN to the outgoing AS2 message.</span></span>  
  
 <span data-ttu-id="710b3-105">Los pasos que cada canalización realiza son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="710b3-105">The steps each pipeline performs are as follows:</span></span>  
  
-   <span data-ttu-id="710b3-106">Determina la entidad remitente mediante la correspondencia de AS2-de valor en el encabezado de AS2 del mensaje con el valor para AS2-de lista en la **identificadores** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="710b3-106">Determines the sending party by matching the AS2-From value in the AS2 header of the message with the value for AS2-From list in the **Identifiers** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="710b3-107">Si no se encuentra ninguna coincidencia, la canalización anula el procesamiento y genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="710b3-107">If a match is not found, the pipeline aborts processing and raises an exception.</span></span>  
  
-   <span data-ttu-id="710b3-108">Promociona las siguientes propiedades de AS2 en el contexto:</span><span class="sxs-lookup"><span data-stu-id="710b3-108">Promotes the following AS2 properties to the context:</span></span>  
  
    -   <span data-ttu-id="710b3-109">IsAS2FailedMessage</span><span class="sxs-lookup"><span data-stu-id="710b3-109">IsAS2FailedMessage</span></span>  
  
    -   <span data-ttu-id="710b3-110">DispositionType</span><span class="sxs-lookup"><span data-stu-id="710b3-110">DispositionType</span></span>  
  
    -   <span data-ttu-id="710b3-111">GenerateAsynchronous200OKOnly</span><span class="sxs-lookup"><span data-stu-id="710b3-111">GenerateAsynchronous200OKOnly</span></span>  
  
    -   <span data-ttu-id="710b3-112">IsAS2MdnResponseMessage</span><span class="sxs-lookup"><span data-stu-id="710b3-112">IsAS2MdnResponseMessage</span></span>  
  
    -   <span data-ttu-id="710b3-113">IsAS2MessageSigned</span><span class="sxs-lookup"><span data-stu-id="710b3-113">IsAS2MessageSigned</span></span>  
  
    -   <span data-ttu-id="710b3-114">OriginalMessageId</span><span class="sxs-lookup"><span data-stu-id="710b3-114">OriginalMessageId</span></span>  
  
    -   <span data-ttu-id="710b3-115">ReceivedContentMic</span><span class="sxs-lookup"><span data-stu-id="710b3-115">ReceivedContentMic</span></span>  
  
    -   <span data-ttu-id="710b3-116">DispositionMode</span><span class="sxs-lookup"><span data-stu-id="710b3-116">DispositionMode</span></span>  
  
    -   <span data-ttu-id="710b3-117">MessageId</span><span class="sxs-lookup"><span data-stu-id="710b3-117">MessageId</span></span>  
  
-   <span data-ttu-id="710b3-118">Establece la propiedad InboundHttpHeaders en todos los encabezados HTTP del mensaje y la promociona al contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="710b3-118">Sets the InboundHttpHeaders property to all the HTTP headers of the message, and promotes it to the context of the message.</span></span>  
  
-   <span data-ttu-id="710b3-119">Realiza una copia del MDN (en formato de "cable") y almacena la copia en la base de datos sin repudio (en la tabla EdiMessageContent de la base de datos BizTalkDTADb), si esta opción está habilitada en las propiedades del acuerdo AS2 unidireccional.</span><span class="sxs-lookup"><span data-stu-id="710b3-119">Makes a copy of the MDN (in wire format), and stores the copy in the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database), if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="710b3-120">Realiza el procesamiento de MIME, incluida la comprobación de la firma si el MDN está firmado.</span><span class="sxs-lookup"><span data-stu-id="710b3-120">Performs MIME processing, including verifying the signature if the MDN was signed.</span></span>  
  
-   <span data-ttu-id="710b3-121">Compara la MIC (comprobación de integridad del mensaje) en el MDN con la MIC en el almacén de datos que la canalización AS2Send calculó al mandar el mensaje original (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="710b3-121">Compares the MIC (Message Integrity Check) in the MDN with the MIC in the data store that was computed by the AS2Send pipeline when it sent out the original message (if applicable).</span></span> <span data-ttu-id="710b3-122">Para obtener más información, consulte [mensajes MDN](../core/mdn-messages.md).</span><span class="sxs-lookup"><span data-stu-id="710b3-122">For more information, see [MDN Messages](../core/mdn-messages.md).</span></span>  
  
-   <span data-ttu-id="710b3-123">Realiza entradas de correlación en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="710b3-123">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="710b3-124">Elimina el MDN, a menos que la **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad se establece en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la  **Propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="710b3-124">Deletes the MDN, unless the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="710b3-125">Si el **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad se establece en el **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo**  cuadro de diálogo, la canalización de recepción enruta el MDN en su formato correspondiente a través del descodificador AS2 como un mensaje de paso y lo coloca en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="710b3-125">If the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box, the receive pipeline routes the MDN in wire format through the AS2 Decoder as a passthrough message and drops it into the MessageBox.</span></span> <span data-ttu-id="710b3-126">El MDN en formato de “cable” contiene todos los encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="710b3-126">The MDN in wire format contains all HTTP headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="710b3-127">Puede configurar un puerto de envío para suscribirse a un MDN recibido que se ha colocado en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="710b3-127">You can set up a send port to subscribe to a received MDN that has been dropped into the MessageBox.</span></span> <span data-ttu-id="710b3-128">Para suscribirse al MDN recibido, establezca el filtro del puerto de envío en `IsAS2MdnResponseMessage==True`.</span><span class="sxs-lookup"><span data-stu-id="710b3-128">To subscribe to the received MDN, set the send port filter to `IsAS2MdnResponseMessage==True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="710b3-129">Si usa la canalización AS2EdiReceive para procesar un MDN recibido, no podrá enrutar el MDN en el cuadro de mensajes estableciendo la **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad en el **MDN de remitente Configuración de** página de la ficha de acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="710b3-129">If you use the AS2EdiReceive pipeline to process a received MDN, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="710b3-130">Al tratar de hacerlo, se producirá un error de EDI, ya que el MDN se pasará al descodificador EDI, que no puede procesar un MDN.</span><span class="sxs-lookup"><span data-stu-id="710b3-130">Trying to do so will result in an EDI error because the MDN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="710b3-131">Si el MDN no se envía al cuadro de mensajes, el descodificador AS2 consumirá el MDN, de modo que no se pasará al descodificador EDI.</span><span class="sxs-lookup"><span data-stu-id="710b3-131">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
## <a name="message-integrity-check"></a><span data-ttu-id="710b3-132">Comprobación de integridad del mensaje</span><span class="sxs-lookup"><span data-stu-id="710b3-132">Message Integrity Check</span></span>  
 <span data-ttu-id="710b3-133">La comprobación de integridad del mensaje (MIC) se usa para comprobar si un MDN correlaciona con el mensaje original enviado.</span><span class="sxs-lookup"><span data-stu-id="710b3-133">The Message Integrity Check (MIC) is used to verify that an MDN correlates to the original sent message.</span></span> <span data-ttu-id="710b3-134">La canalización de envío AS2Send calcula la MIC desde la carga del mensaje cuando genera el mensaje AS2 original y la guarda en la MIC en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="710b3-134">The AS2Send send pipeline calculates the MIC from the message payload when it generates the original AS2 message, and stores the MIC in the data store.</span></span> <span data-ttu-id="710b3-135">Cuando es necesario un MDN, el destinatario del mensaje original genera una MIC y la agrega al MDN.</span><span class="sxs-lookup"><span data-stu-id="710b3-135">When an MDN is required, the recipient of the original message generates an MIC and adds it to the MDN.</span></span> <span data-ttu-id="710b3-136">Cuando la canalización de recepción AS2MdnReceive recibe el MDN, si se ha solicitado un MDN firmado, lo compara la MIC en el MDN con la MIC en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="710b3-136">When the AS2MdnReceive receive pipeline receives the MDN, if a signed MDN was requested, it compares the MIC in the MDN with the MIC in the data store.</span></span>  
  
 <span data-ttu-id="710b3-137">Si no coinciden, significa que se ha producido un error durante la transmisión o recepción del mensaje por parte de la entidad receptora.</span><span class="sxs-lookup"><span data-stu-id="710b3-137">A mismatch between the MIC in the MDN and the MIC in the data store indicates that there was an error during transmission or receipt of the message by the receiving party.</span></span> <span data-ttu-id="710b3-138">Los valores notificados en este error son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="710b3-138">The values reported in such a failure are the following:</span></span>  
  
-   <span data-ttu-id="710b3-139">AS2DispositionType: Error</span><span class="sxs-lookup"><span data-stu-id="710b3-139">AS2DispositionType: Failed</span></span>  
  
-   <span data-ttu-id="710b3-140">AS2DispositionModifierExtensionType: Error</span><span class="sxs-lookup"><span data-stu-id="710b3-140">AS2DispositionModifierExtensionType: Error</span></span>  
  
-   <span data-ttu-id="710b3-141">AS2DispositionModifierExtensionDescription: Error en la comprobación de integridad</span><span class="sxs-lookup"><span data-stu-id="710b3-141">AS2DispositionModifierExtensionDescription: Integrity Check Failed</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710b3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="710b3-142">See Also</span></span>  
 <span data-ttu-id="710b3-143">[Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="710b3-143">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="710b3-144">Mensajes MDN</span><span class="sxs-lookup"><span data-stu-id="710b3-144">MDN Messages</span></span>](../core/mdn-messages.md)
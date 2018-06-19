---
title: Generar un mensaje AS2 saliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246548"
---
# <a name="generating-an-outgoing-as2-message"></a><span data-ttu-id="7a8fe-102">Generar un mensaje AS2 saliente</span><span class="sxs-lookup"><span data-stu-id="7a8fe-102">Generating an Outgoing AS2 Message</span></span>
<span data-ttu-id="7a8fe-103">Las canalizaciones de envío AS2EDISend y AS2Send generan un mensaje saliente como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-103">The AS2EDISend and AS2Send send pipelines generate an outbound message as follows.</span></span> <span data-ttu-id="7a8fe-104">Cada canalización utiliza las propiedades en la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo para generar el mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-104">Each pipeline uses the properties in the one-way agreement tab of the **Agreement Properties** dialog box to generate the outgoing AS2 message.</span></span>  
  
## <a name="agreement-destination-and-messageid-determination"></a><span data-ttu-id="7a8fe-105">Determinación del acuerdo, el destino y el identificador de mensaje</span><span class="sxs-lookup"><span data-stu-id="7a8fe-105">Agreement, Destination, and MessageID Determination</span></span>  
 <span data-ttu-id="7a8fe-106">Las canalizaciones de envío de AS2 determinan el acuerdo y el destino que van a usarse en el envío del mensaje AS2 de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="7a8fe-106">The AS2 send pipelines determine the agreement and destination to be used in sending an AS2 message as follows:</span></span>  
  
-   <span data-ttu-id="7a8fe-107">Para determinar qué acuerdo se debe usar en el procesamiento de un mensaje saliente, el codificador AS2 intenta hacer coincidir las propiedades AS2-To del mensaje y la AS2Identity del perfil de negocio de una entidad, o el puerto de envío de suscripción al mensaje con un puerto de envío asociado al acuerdo.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-107">To determine the agreement to use in processing an outgoing message, the AS2 encoder attempts to match the AS2-To properties in the message and the AS2Identity for a party’s business profile, or the send port subscribing to the message with a send port associated with the agreement.</span></span> <span data-ttu-id="7a8fe-108">Para obtener más información acerca de este proceso, consulte [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fe-108">For more information on this process, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="7a8fe-109">Para determinar el destino del mensaje, la canalización de envío de un puerto de envío dinámico usa la propiedad OutboundTransportLocation, que debe estar escrita o promocionada al contexto mediante una aplicación de servidor para que funcione el puerto de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-109">To determine the destination of the message, the send pipeline in a dynamic send port uses the OutboundTransportLocation property, which must be written or promoted to the context by a backend application for the dynamic send port to work.</span></span> <span data-ttu-id="7a8fe-110">La canalización de envío de una canalización de envío estático determinará el destino a partir de la propiedad AS2-From de las propiedades del acuerdo AS2 y de las identidades de las propiedades del perfil de negocio.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-110">The send pipeline in a static send pipeline will determine the destination from the AS2-From property in the AS2 agreement properties and the identities of the business profile properties.</span></span>  
  
-   <span data-ttu-id="7a8fe-111">El codificador AS2 debe establecer el encabezado MessageId de un mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-111">The AS2 Encoder needs to set the MessageId header of an outgoing AS2 message.</span></span> <span data-ttu-id="7a8fe-112">La canalización de envío determina el identificador de mensaje a partir de la propiedad de contexto `EdiIntAS.MessageId` o la propiedad de contexto `HTTP.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-112">The send pipeline determines the MessageId from either the `EdiIntAS.MessageId` context property or the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="7a8fe-113">Si ambas propiedades de contexto están establecidas, el codificador usa el valor de la propiedad de contexto `HTTP.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-113">If both of those context properties are set, the encoder uses the value from the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="7a8fe-114">Si ninguna está establecida, la canalización de envío genera de forma automática un valor para MessageID.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-114">If neither of them is set, the send pipeline autogenerates a value for MessageID.</span></span>  
  
## <a name="outgoing-message-processing"></a><span data-ttu-id="7a8fe-115">Procesamiento de mensajes salientes</span><span class="sxs-lookup"><span data-stu-id="7a8fe-115">Outgoing Message Processing</span></span>  
 <span data-ttu-id="7a8fe-116">Los pasos que usa una canalización de envío de AS2 en el procesamiento de un mensaje saliente de AS2 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a8fe-116">The steps that the AS2 send pipelines use in processing an outgoing AS2 message are as follows:</span></span>  
  
-   <span data-ttu-id="7a8fe-117">Realiza una copia del mensaje en formato nativo y almacena la copia en la base de datos sin repudio, si la recepción sin repudio de mensajes AS2 está habilitada en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-117">Makes a copy of the message in native format, and stores the copy in the non-repudiation database, if non-repudiation of AS2 messages is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="7a8fe-118">El codificador AS2 genera los encabezados HTTP (y AS2) en la propiedad de contexto `HTTP.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-118">The AS2 Encoder builds the HTTP (and AS2) headers into the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="7a8fe-119">Para obtener más información acerca de este proceso, consulte [envíos de procesamiento de un mensaje EDI saliente a través de AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fe-119">For more information on this process, see [Send-Side Processing of an Outgoing EDI Message over AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="7a8fe-120">Escribe `HTTP.UserHttpHeaders` en el contexto.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-120">Writes `HTTP.UserHttpHeaders` to the context.</span></span>  
  
-   <span data-ttu-id="7a8fe-121">Comprime el mensaje saliente, si esta opción está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-121">Compresses the outgoing message, if enabled.</span></span>  
  
-   <span data-ttu-id="7a8fe-122">Realiza un procesamiento MIME, incluido el cifrado del mensaje (si se habilita en el **debe cifrarse el mensaje** propiedad de acuerdo) y aplicar una firma digital (si habilitada en el **de mensajes debe estar firmado**propiedades de acuerdo).</span><span class="sxs-lookup"><span data-stu-id="7a8fe-122">Performs MIME processing, including encrypting the message (if enabled in the **Message should be encrypted** agreement property) and applying a digital signature (if enabled in the **Message should be signed** agreement properties).</span></span> <span data-ttu-id="7a8fe-123">La canalización AS2Send usa SHA1 o MD5 para aplicar la firma, en función de la configuración del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-123">The AS2Send pipeline uses either SHA1 or MD5 to apply the signature, based upon agreement settings.</span></span>  
  
-   <span data-ttu-id="7a8fe-124">Crea un encabezado MIME Content-Disposition que contiene el valor especificado, si está activada la transmisión del nombre de archivo en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-124">Creates a Content-Disposition MIME header containing the specified value, if transmit file name is enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="7a8fe-125">Realiza una copia del mensaje cifrado (en su formato correspondiente) y almacena la copia en la base de datos sin repudio, si se habilita en el **NRR habilitado para mensajes AS2 salientes codificados** en la propiedad de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-125">Makes a copy of the encrypted message (in wire format), and stores the copy in the non-repudiation database, if enabled in the **NRR enabled for outbound encoded AS2 messages** in the agreement property.</span></span>  
  
-   <span data-ttu-id="7a8fe-126">Si se requiere un MDN, calcula el valor MIC y lo guarda en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-126">If an MDN is required, computes the MIC value and stores it in the data store.</span></span>  
  
-   <span data-ttu-id="7a8fe-127">Entrega el mensaje al adaptador de HTTP, que escribe los encabezados de la propiedad de contexto UserHTTPHeaders en el mensaje AS2 saliente.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-127">Delivers the message to the HTTP adapter, which writes the headers from the UserHTTPHeaders context property into the outgoing AS2 message.</span></span>  
  
-   <span data-ttu-id="7a8fe-128">Si se requiere la mensajería de confianza, reenvía el mensaje hasta que se reciba un MDN.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-128">If reliable messaging is required, resends the message until an MDN is received.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8fe-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a8fe-129">See Also</span></span>  
 <span data-ttu-id="7a8fe-130">[Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="7a8fe-130">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="7a8fe-131">AS2 Componentes de envío</span><span class="sxs-lookup"><span data-stu-id="7a8fe-131">AS2 Send Components</span></span>](../core/as2-send-components.md)
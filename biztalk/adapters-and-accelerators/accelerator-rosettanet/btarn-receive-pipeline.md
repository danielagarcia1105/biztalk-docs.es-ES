---
title: Canalización de recepción de BTARN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31b841048f79f460ec3c8098d63eec5cf348b6a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991925"
---
# <a name="btarn-receive-pipeline"></a><span data-ttu-id="65546-102">Canalización de recepción de BTARN</span><span class="sxs-lookup"><span data-stu-id="65546-102">BTARN Receive Pipeline</span></span>
<span data-ttu-id="65546-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] realiza la recepción de mensajes de RosettaNet Implementation Framework (RNIF) con la canalización RNIFReceive (RNIFReceive.btp).</span><span class="sxs-lookup"><span data-stu-id="65546-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] performs RosettaNet Implementation Framework (RNIF) message reception with the RNIFReceive pipeline (RNIFReceive.btp).</span></span> <span data-ttu-id="65546-104">La canalización de recepción incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="65546-104">The receive pipeline includes the following components:</span></span>  
  
-   <span data-ttu-id="65546-105">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="65546-105">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="65546-106">RNMimeDecoder (preprocesador y descodificador MIME)</span><span class="sxs-lookup"><span data-stu-id="65546-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="65546-107">RNDAsm (desensamblador XML)</span><span class="sxs-lookup"><span data-stu-id="65546-107">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="65546-108">RNPartyRes (componente de resolución de entidades)</span><span class="sxs-lookup"><span data-stu-id="65546-108">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="65546-109">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="65546-109">MessageUpdater</span></span>  
  
## <a name="receivemessagenonrepudiate"></a><span data-ttu-id="65546-110">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="65546-110">ReceiveMessageNonRepudiate</span></span>  
 <span data-ttu-id="65546-111">Este componente almacena el mensaje recibido en la tabla MessageStorageIn.</span><span class="sxs-lookup"><span data-stu-id="65546-111">This component stores the received message in the MessageStorageIn table.</span></span> <span data-ttu-id="65546-112">Este componente realiza el procesamiento de rechazo requerido por los estándares RNIF.</span><span class="sxs-lookup"><span data-stu-id="65546-112">This component performs the non-repudiation processing required by the RNIF standards.</span></span>  
  
## <a name="rnmimedecoder"></a><span data-ttu-id="65546-113">RNMimeDecoder</span><span class="sxs-lookup"><span data-stu-id="65546-113">RNMimeDecoder</span></span>  
 <span data-ttu-id="65546-114">Este componente se basa en el nativo BizTalk Server preprocesador y descodificador MIME.</span><span class="sxs-lookup"><span data-stu-id="65546-114">This component is based on the native BizTalk Server MIME Preprocessor/Decoder.</span></span> <span data-ttu-id="65546-115">RNMimeDecoder agrega la siguiente funcionalidad para el procesamiento de RNIF:</span><span class="sxs-lookup"><span data-stu-id="65546-115">RNMimeDecoder adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="65546-116">Para RNIF 2.01, descifra el contenido del servicio y los datos adjuntos, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="65546-116">For RNIF 2.01, decrypts the service content and attachments, if they are present.</span></span>  
  
- <span data-ttu-id="65546-117">Para RNIF 1.1, controla el encabezado de 8 bytes y el encabezado de firma separada al final de la carga.</span><span class="sxs-lookup"><span data-stu-id="65546-117">For RNIF 1.1, handles the 8-byte header and the detached signature header at the end of the payload.</span></span>  
  
  <span data-ttu-id="65546-118">Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocesador y descodificador, vea "Componente de canalización de descodificador MIME/SMIME" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65546-118">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocessor/decoder, see "MIME/SMIME Decoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rndasm"></a><span data-ttu-id="65546-119">RNDAsm</span><span class="sxs-lookup"><span data-stu-id="65546-119">RNDAsm</span></span>  
 <span data-ttu-id="65546-120">Este componente se basa en el XML desensamblador nativo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65546-120">This component is based on the native BizTalk Server XML Disassembler.</span></span> <span data-ttu-id="65546-121">RNDAsm agrega la siguiente funcionalidad para el procesamiento de RNIF:</span><span class="sxs-lookup"><span data-stu-id="65546-121">RNDAsm adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="65546-122">Si un documento entrante tiene un encabezado de tipo de documento, este componente genera un espacio de nombres de él y mueve todos los nodos del documento entrante a ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="65546-122">If an incoming document has a DOCTYPE header, this component generates a namespace from it and moves all nodes in the incoming document to that namespace.</span></span>  
  
- <span data-ttu-id="65546-123">Realiza la correlación de mensajes para determinar si un mensaje entrante es un duplicado y genera un mensaje de error si el mensaje es un duplicado.</span><span class="sxs-lookup"><span data-stu-id="65546-123">Performs message correlation to determine whether an incoming message is a duplicate, and generates an error message if the message is a duplicate.</span></span>  
  
- <span data-ttu-id="65546-124">Almacena los datos adjuntos como partes adicionales del mensaje.</span><span class="sxs-lookup"><span data-stu-id="65546-124">Stores attachments as additional parts of the message.</span></span>  
  
- <span data-ttu-id="65546-125">Promociona las propiedades de mensaje.</span><span class="sxs-lookup"><span data-stu-id="65546-125">Promotes message properties.</span></span>  
  
  <span data-ttu-id="65546-126">Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Desensamblador, vea "Componente de canalización de desensamblador XML" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65546-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Disassembler, see "XML Disassembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rnpartyres"></a><span data-ttu-id="65546-127">RNPartyRes</span><span class="sxs-lookup"><span data-stu-id="65546-127">RNPartyRes</span></span>  
 <span data-ttu-id="65546-128">Este componente se basa en el componente de resolución de entidades de BizTalk Server nativo.</span><span class="sxs-lookup"><span data-stu-id="65546-128">This component is based on the native BizTalk Server Party Resolution component.</span></span> <span data-ttu-id="65546-129">RNPartyRes agrega la siguiente funcionalidad para el procesamiento de RNIF:</span><span class="sxs-lookup"><span data-stu-id="65546-129">RNPartyRes adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="65546-130">Si el mensaje entrante está firmado a una entidad de BizTalk se asigna el certificado del remitente.</span><span class="sxs-lookup"><span data-stu-id="65546-130">Maps the sender certificate if the incoming message is signed to a BizTalk party.</span></span> <span data-ttu-id="65546-131">Si el mensaje entrante no está firmado, y permite el acuerdo de socio comercial, este componente recupera la entidad remitente desde el encabezado de entrega para RNIF 2.01 o el encabezado de servicio para RNIF 1.1.</span><span class="sxs-lookup"><span data-stu-id="65546-131">If the incoming message is not signed, and the trading partner agreement allows for it, this component retrieves the sender party from the Delivery header for RNIF 2.01 or the Service header for RNIF 1.1.</span></span>  
  
- <span data-ttu-id="65546-132">Valida que el remitente existe y que el remitente tiene un acuerdo entre socios comerciales con la organización principal.</span><span class="sxs-lookup"><span data-stu-id="65546-132">Validates that the sender exists and that the sender has a trading partner agreement with the home organization.</span></span>  
  
  <span data-ttu-id="65546-133">Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componente de resolución de entidad, vea "Componente de canalización de resolución de entidad" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="65546-133">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] party resolution component, see "Party Resolution Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="messageupdater"></a><span data-ttu-id="65546-134">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="65546-134">MessageUpdater</span></span>  
 <span data-ttu-id="65546-135">Este componente agrega la siguiente funcionalidad para el procesamiento de RNIF:</span><span class="sxs-lookup"><span data-stu-id="65546-135">This component adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="65546-136">Actualiza la tabla MessageStorageIn con detalles sobre el código PIP, versión de PIP, entidad de origen, entidad de destino e Id. de seguimiento de mensaje del mensaje de conexión que se almacenó el componente ReceiveMessageNonRepudiate.</span><span class="sxs-lookup"><span data-stu-id="65546-136">Updates the MessageStorageIn table with details about the PIP Code, PIP Version, Source Party, Destination Party, and Message Tracking ID of the wire message that was stored by the ReceiveMessageNonRepudiate component.</span></span>  
  
-   <span data-ttu-id="65546-137">Si PIP no requiere sin repudio, marca el registro para su eliminación, establecer `ToBePurged = True`.</span><span class="sxs-lookup"><span data-stu-id="65546-137">If the PIP does not require non-repudiation, marks the record for deletion, setting `ToBePurged = True`.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="65546-138">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="65546-138">Message Flow</span></span>  
 <span data-ttu-id="65546-139">El flujo de mensajes a través de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibir canalización es como sigue:</span><span class="sxs-lookup"><span data-stu-id="65546-139">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline is as follows:</span></span>  
  
1. <span data-ttu-id="65546-140">El adaptador de HTTP recibe un objeto de RNIF 1.1 o un mensaje de RNIF 2.01 empresarial a través de HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="65546-140">The HTTP adapter receives an RNIF 1.1 object or an RNIF 2.01 business message through HTTP POST.</span></span>  
  
2. <span data-ttu-id="65546-141">Si el adaptador recibe correctamente el mensaje, el adaptador extrae los mensajes de objeto o empresarial de RosettaNet y lo enruta a la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="65546-141">If the adapter successfully receives the message, the adapter extracts the RosettaNet object or business message, and routes it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="65546-142">Si el objeto o business mensaje está firmado, el preprocesador y descodificador de MIME quita la firma.</span><span class="sxs-lookup"><span data-stu-id="65546-142">If the object or business message is signed, the MIME Preprocessor/Decoder removes the signature.</span></span>  
  
4. <span data-ttu-id="65546-143">Si la firma es válida, el Desensamblador lee el preámbulo.</span><span class="sxs-lookup"><span data-stu-id="65546-143">If the signature is valid, the disassembler reads the preamble.</span></span>  
  
5. <span data-ttu-id="65546-144">Si el mensaje es un mensaje de acción, y no rechazo es necesario (el **sin repudio del origen y del contenido** configuración de las opciones de configuración de proceso es `True`), el descodificador calcula y se conserva el resumen.</span><span class="sxs-lookup"><span data-stu-id="65546-144">If the message is an action message, and non-repudiation is required (the **Non-Repudiation of Origin and Content** setting in the process configuration settings is `True`), the Decoder calculates and persists the digest.</span></span>  
  
6. <span data-ttu-id="65546-145">El Desensamblador valida el preámbulo (con las directrices de mensaje (MSG) y el esquema de preámbulo en las variables globales).</span><span class="sxs-lookup"><span data-stu-id="65546-145">The disassembler validates the preamble (with message (MSG) guidelines and the preamble schema in the global variables).</span></span>  
  
7. <span data-ttu-id="65546-146">RNIF 2.01, el Desensamblador lee el encabezado de entrega y valida el encabezado mediante las instrucciones del mensaje y el esquema de encabezado de entrega en las variables globales.</span><span class="sxs-lookup"><span data-stu-id="65546-146">For RNIF 2.01, the disassembler reads the delivery header, and validates the header using the MSG guidelines and the delivery header schema in the global variables.</span></span>  
  
8. <span data-ttu-id="65546-147">Para RNIF 2.01, el Desensamblador extrae la información del partner en el encabezado de entrega y examina la firma para comprobar que pertenece al socio comercial.</span><span class="sxs-lookup"><span data-stu-id="65546-147">For RNIF 2.01, the disassembler extracts the partner information from the delivery header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
9. <span data-ttu-id="65546-148">Para RNIF 2.01, si la carga se cifra, el decodificador descifra el contenedor de carga.</span><span class="sxs-lookup"><span data-stu-id="65546-148">For RNIF 2.01, if the payload is encrypted, the decoder decrypts the payload container.</span></span>  
  
10. <span data-ttu-id="65546-149">El Desensamblador lee el encabezado de servicio y valida el encabezado mediante las instrucciones del mensaje y el esquema de encabezado de servicio en las variables globales.</span><span class="sxs-lookup"><span data-stu-id="65546-149">The disassembler reads the service header, and validates the header using the MSG guidelines and the service header schema in the global variables.</span></span>  
  
11. <span data-ttu-id="65546-150">Para RNIF 1.1, el Desensamblador extrae la información del partner de la cabecera de servicio y examina la firma para comprobar que pertenece al socio comercial.</span><span class="sxs-lookup"><span data-stu-id="65546-150">For RNIF 1.1, the disassembler extracts the partner information from the service header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
12. <span data-ttu-id="65546-151">El Desensamblador comprueba si el socio está autorizado para el PIP.</span><span class="sxs-lookup"><span data-stu-id="65546-151">The disassembler checks whether the partner is authorized for the PIP.</span></span> <span data-ttu-id="65546-152">Si no, el Desensamblador se responda un HTTP POST con un mensaje de estado HTTP 403, si es necesario y generar un error.</span><span class="sxs-lookup"><span data-stu-id="65546-152">If not, the disassembler will reply an HTTP POST with an HTTP 403 status message, if necessary, and post an error.</span></span>  
  
13. <span data-ttu-id="65546-153">Si el mensaje es un mensaje de acción con signo y **sin repudio del origen y del contenido** está establecido en `True`, el componente ReceiveMessageNonRepudiate conserva el mensaje original en la tabla MessageStorageIn.</span><span class="sxs-lookup"><span data-stu-id="65546-153">If the message is a signed action message and **Non-Repudiation of Origin and Content** is set to `True`, the ReceiveMessageNonRepudiate component persists the original message in the MessageStorageIn table.</span></span>  
  
14. <span data-ttu-id="65546-154">Si el mensaje es un mensaje de señal con signo y **sin repudio necesario** está establecido en `True`, el componente ReceiveMessageNonRepudiate conserva el mensaje de señal en la tabla MessageStorageIn.</span><span class="sxs-lookup"><span data-stu-id="65546-154">If the message is a signed signal message and **Non-Repudiation Required** is set to `True`, the ReceiveMessageNonRepudiate component persists the signal message in the MessageStorageIn table.</span></span>  
  
15. <span data-ttu-id="65546-155">Si el mensaje se almacena en la tabla MessageStorageIn para sin repudio, el MessageUpdater actualiza la tabla MessageStorageIn con propiedades de la configuración del proceso del mensaje.</span><span class="sxs-lookup"><span data-stu-id="65546-155">If the message was persisted in the MessageStorageIn table for non-repudiation, the MessageUpdater updates the MessageStorageIn table with properties of the process configuration of the message.</span></span>  
  
16. <span data-ttu-id="65546-156">Si el mensaje es un mensaje de acción que es un duplicado de un mensaje de acción procesados previamente, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] registrará un error.</span><span class="sxs-lookup"><span data-stu-id="65546-156">If the message is an action message that is a duplicate of a previously processed action message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will post an error.</span></span>  
  
17. <span data-ttu-id="65546-157">Para RNIF 2.01, el descodificador descifrará la carga si se cifra el mensaje de acción y no hay una coincidencia entre la sincronización HTTP y los requisitos de sincronización PIP.</span><span class="sxs-lookup"><span data-stu-id="65546-157">For RNIF 2.01, the decoder will decrypt the payload if the action message is encrypted and there is a match between the HTTP synchronicity and PIP synchronicity requirements.</span></span>  
  
18. <span data-ttu-id="65546-158">El Desensamblador lee el contenido del servicio y lo valida con las instrucciones del mensaje y el esquema.</span><span class="sxs-lookup"><span data-stu-id="65546-158">The disassembler reads the service content, and validates it using the MSG guidelines and the schema.</span></span>  
  
19. <span data-ttu-id="65546-159">Para RNIF 2.01, el Desensamblador comprueba que el manifiesto es válido y el identificador de contenido está presente.</span><span class="sxs-lookup"><span data-stu-id="65546-159">For RNIF 2.01, the disassembler verifies that the manifest is valid and the content ID is present.</span></span>  
  
20. <span data-ttu-id="65546-160">Para RNIF 2.01, el Desensamblador leerá los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="65546-160">For RNIF 2.01, the disassembler will read any attachments.</span></span>  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="65546-161"> enruta los encabezados de RosettaNet, contenido del servicio y los datos adjuntos en el proceso público.</span><span class="sxs-lookup"><span data-stu-id="65546-161"> routes the RosettaNet headers, service content, and attachments to the public process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65546-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="65546-162">See Also</span></span>  
 [<span data-ttu-id="65546-163">Procesamiento de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="65546-163">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)
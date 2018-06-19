---
title: Canalización de envío de BTARN | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler
- send pipelines, message flow
- DOCTYPE headers
- MIME/SMIME Encoder
- send pipelines, BTARN
- BTARN, send pipelines
- XML Preprocessor
- messages, message flow
ms.assetid: 88562132-0ea4-4b5a-9445-b69f6c84e5ea
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f566b37cc43f8aca2f0a36143d10d809c008d5cd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007525"
---
# <a name="btarn-send-pipeline"></a><span data-ttu-id="69180-102">Canalización de envío BTARN</span><span class="sxs-lookup"><span data-stu-id="69180-102">BTARN Send Pipeline</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="69180-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepara un mensaje de RosettaNet Implementation Framework (RNIF) para su transmisión en la canalización de RNIFSend (RNIFSend.btp).</span><span class="sxs-lookup"><span data-stu-id="69180-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepares a RosettaNet Implementation Framework (RNIF) message for transmission in the RNIFSend pipeline (RNIFSend.btp).</span></span> <span data-ttu-id="69180-104">La canalización de envío incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69180-104">The send pipeline includes the following:</span></span>  
  
-   <span data-ttu-id="69180-105">XML de preprocesador</span><span class="sxs-lookup"><span data-stu-id="69180-105">XML preprocessor</span></span>  
  
-   <span data-ttu-id="69180-106">Ensamblador de XML</span><span class="sxs-lookup"><span data-stu-id="69180-106">XML assembler</span></span>  
  
-   <span data-ttu-id="69180-107">Codificador de Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME)</span><span class="sxs-lookup"><span data-stu-id="69180-107">Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME) encoder</span></span>  
  
## <a name="xml-preprocessor"></a><span data-ttu-id="69180-108">Preprocesador XML</span><span class="sxs-lookup"><span data-stu-id="69180-108">XML Preprocessor</span></span>  
 <span data-ttu-id="69180-109">El preprocesador XML agrega un encabezado de tipo de documento al mensaje.</span><span class="sxs-lookup"><span data-stu-id="69180-109">The XML preprocessor adds a DOCTYPE header to the message.</span></span> <span data-ttu-id="69180-110">El encabezado identifica el esquema de definición (DTD) de tipo de documento asociado con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="69180-110">The header identifies the document type definition (DTD) schema associated with the message.</span></span> <span data-ttu-id="69180-111">La especificación de RNIF requiere la presencia de un encabezado de tipo de documento para la transmisión de RNIF.</span><span class="sxs-lookup"><span data-stu-id="69180-111">The RNIF specification requires the presence of a DOCTYPE header for RNIF transmission.</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="69180-112">ensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="69180-112">XML Assembler</span></span>  
 <span data-ttu-id="69180-113">El ensamblador XML se basa en el ensamblador de XML de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69180-113">The XML assembler is based on the BizTalk Server XML assembler.</span></span> <span data-ttu-id="69180-114">Transfiere las propiedades del contexto del mensaje en sobres y documentos.</span><span class="sxs-lookup"><span data-stu-id="69180-114">It transfers properties from the message context back into envelopes and documents.</span></span> <span data-ttu-id="69180-115">Ensambla el mensaje de sus elementos XML y los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="69180-115">It assembles the message from its XML parts and attachments.</span></span> <span data-ttu-id="69180-116">No realiza validación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="69180-116">It does not perform message validation.</span></span>  
  
 <span data-ttu-id="69180-117">Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblador XML, vea "Componente de canalización de ensamblador XML" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69180-117">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML assembler, see "XML Assembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="mimesmime-encoder"></a><span data-ttu-id="69180-118">codificador de MIME/SMIME</span><span class="sxs-lookup"><span data-stu-id="69180-118">MIME/SMIME Encoder</span></span>  
 <span data-ttu-id="69180-119">El codificador MIME/SMIME se basa en el codificador MIME/SMIME de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69180-119">The MIME/SMIME encoder is based on the BizTalk Server MIME/SMIME Encoder.</span></span> <span data-ttu-id="69180-120">Dependiendo de la configuración del protocolo de acuerdo de socio comercial y la configuración del codificador MIME/SMIME de BizTalk Server, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] codificador realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69180-120">Depending on the protocol settings in the trading partner agreement, and the settings of the BizTalk Server MIME/SMIME Encoder, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] encoder performs the following:</span></span>  
  
-   <span data-ttu-id="69180-121">Agrega un encabezado binario de 8 bytes para el mensaje, según sea necesario para los mensajes de RNIF 1.1.</span><span class="sxs-lookup"><span data-stu-id="69180-121">Adds an 8-byte binary header to the message, as required for RNIF 1.1 messages.</span></span>  
  
-   <span data-ttu-id="69180-122">Codifica las partes del mensaje y calcula el resumen.</span><span class="sxs-lookup"><span data-stu-id="69180-122">Encodes the message parts, and calculates the digest.</span></span>  
  
-   <span data-ttu-id="69180-123">Cifra la carga (contenido del servicio y los datos adjuntos) o el contenedor de carga (contenido del servicio más cab más datos adjuntos).</span><span class="sxs-lookup"><span data-stu-id="69180-123">Encrypts the payload (service content plus attachments), or the payload container (service content plus service header plus attachments).</span></span> <span data-ttu-id="69180-124">Si ha configurado la **codificar todos los puertos** en el **protocolo** ficha del acuerdo de socio comercial a `False`, el codificador cifrará solo la carga.</span><span class="sxs-lookup"><span data-stu-id="69180-124">If you have set the **Encode all ports** setting on the **Protocol** tab of the trading partner agreement to `False`, the encoder will encrypt only the payload.</span></span> <span data-ttu-id="69180-125">Si ha configurado la **codificar todos los puertos** si se establece en `True`, el codificador cifrará el contenedor de carga.</span><span class="sxs-lookup"><span data-stu-id="69180-125">If you have set the **Encode all ports** setting to `True`, the encoder will encrypt the payload container.</span></span>  
  
 <span data-ttu-id="69180-126">Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] codificador MIME/SMIME, vea "Componente de canalización de codificador MIME/SMIME" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="69180-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MIME/SMIME Encoder, see "MIME/SMIME Encoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="69180-127">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="69180-127">Message Flow</span></span>  
 <span data-ttu-id="69180-128">El flujo de mensajes a través de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización es como sigue:</span><span class="sxs-lookup"><span data-stu-id="69180-128">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="69180-129">Si ha configurado la **codificar todas las partes** configuración del acuerdo de socio comercial a `True`, el codificador MIME/SMIME codificará todas las partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="69180-129">If you have set the **Encode all parts** setting of the trading partner agreement to `True`, the MIME/SMIME encoder will encode all message parts.</span></span> <span data-ttu-id="69180-130">Utilizará el método de codificación que se establece el `Encoding` propiedad del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="69180-130">It will use the encoding method set in the `Encoding` property of the agreement.</span></span>  
  
2.  <span data-ttu-id="69180-131">Para RNIF 2.01, si el mensaje es un mensaje de acción y no hay un archivo adjunto, el codificador hará lo siguiente para cada archivo adjunto:</span><span class="sxs-lookup"><span data-stu-id="69180-131">For RNIF 2.01, if the message is an action message and there is an attachment, the encoder will do the following for each attachment:</span></span>  
  
    1.  <span data-ttu-id="69180-132">Si los datos adjuntos están binario, lo codificará el codificador.</span><span class="sxs-lookup"><span data-stu-id="69180-132">If the attachment is binary, the encoder will encode it.</span></span>  
  
    2.  <span data-ttu-id="69180-133">El codificador generará un identificador de contenido de los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="69180-133">The encoder will generate a content ID for the attachment.</span></span>  
  
    3.  <span data-ttu-id="69180-134">El codificador creará una parte MIME para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="69180-134">The encoder will create a MIME part for the attachment.</span></span>  
  
3.  <span data-ttu-id="69180-135">Para RNIF 2.01, la canalización cifrará partes del mensaje y generar el mensaje RNIF según la configuración de **se necesita confidencialidad persistente** (como se establece en los valores de configuración de proceso):</span><span class="sxs-lookup"><span data-stu-id="69180-135">For RNIF 2.01, the pipeline will encrypt message parts and build the RNIF message depending on the setting of **Is Persistent Confidentiality Required** (as set in the process configuration settings):</span></span>  
  
    1.  <span data-ttu-id="69180-136">Si ha configurado **se necesita confidencialidad persistente** a **carga**, el codificador cifrará el contenido del servicio y los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="69180-136">If you have set **Is Persistent Confidentiality Required** to **Payload**, the encoder will encrypt the service content and the attachments.</span></span> <span data-ttu-id="69180-137">El ensamblador, a continuación, agregará el encabezado de servicio, el encabezado de entrega y el preámbulo para construir el mensaje RNIF final.</span><span class="sxs-lookup"><span data-stu-id="69180-137">The assembler will then add the service header, delivery header, and preamble to construct the final RNIF message.</span></span>  
  
    2.  <span data-ttu-id="69180-138">Si ha configurado **se necesita confidencialidad persistente** a **contenedor de carga**, el codificador cifrará el encabezado de servicio, el contenido del servicio y los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="69180-138">If you have set **Is Persistent Confidentiality Required** to **Payload Container**, the encoder will encrypt the service header, service content, and the attachments.</span></span> <span data-ttu-id="69180-139">El ensamblador, a continuación, agregará el encabezado de entrega y el preámbulo para construir el mensaje RNIF final.</span><span class="sxs-lookup"><span data-stu-id="69180-139">The assembler will then add the delivery header and preamble to construct the final RNIF message.</span></span>  
  
    3.  <span data-ttu-id="69180-140">Si ha configurado **se necesita confidencialidad persistente** a **ninguno**, el ensamblador agregará el preámbulo, encabezado de servicio y encabezado de entrega para el contenido del servicio y los datos adjuntos (sin cifrado) para construir el mensaje RNIF final.</span><span class="sxs-lookup"><span data-stu-id="69180-140">If you have set **Is Persistent Confidentiality Required** to **None**, the assembler will add the service header, delivery header, and preamble to the service content and the attachments (without encryption) to construct the final RNIF message.</span></span>  
  
4.  <span data-ttu-id="69180-141">Para RNIF 1.1, el ensamblador construirá el mensaje RNIF final sin cifrado.</span><span class="sxs-lookup"><span data-stu-id="69180-141">For RNIF 1.1, the assembler will construct the final RNIF message without encryption.</span></span>  
  
5.  <span data-ttu-id="69180-142">El codificador firmará el mensaje en el caso siguiente:</span><span class="sxs-lookup"><span data-stu-id="69180-142">The encoder will sign the message in the following case:</span></span>  
  
    1.  <span data-ttu-id="69180-143">El mensaje es un mensaje de señal y la **sin repudio necesario** propiedad (en los valores de configuración de proceso) es `True`.</span><span class="sxs-lookup"><span data-stu-id="69180-143">The message is a signal message, and the **Non-Repudiation Required** property (in the process configuration settings) is `True`.</span></span>  
  
    2.  <span data-ttu-id="69180-144">El mensaje es un mensaje de acción y el **sin repudio del origen y del contenido** propiedad (en los valores de configuración de proceso) es `True`.</span><span class="sxs-lookup"><span data-stu-id="69180-144">The message is an action message, and the **Non-Repudiation of Origin and Content** property (in the process configuration settings) is `True`.</span></span>  
  
6.  <span data-ttu-id="69180-145">Para RNIF 2.01, el codificador calcular el resumen en la primera parte del cuerpo del mensaje MIME y conservar el resumen.</span><span class="sxs-lookup"><span data-stu-id="69180-145">For RNIF 2.01, the encoder will calculate the digest on the first body part of the MIME message, and persist the digest.</span></span> <span data-ttu-id="69180-146">Calculará la síntesis utilizando el método definido en el `Digest` propiedad de método en el acuerdo de socio comercial (SHA-1 o MD5).</span><span class="sxs-lookup"><span data-stu-id="69180-146">It will calculate the digest using the method set in the `Digest` method property in the trading partner agreement (SHA-1 or MD5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69180-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="69180-147">See Also</span></span>  
 [<span data-ttu-id="69180-148">Procesamiento de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="69180-148">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)
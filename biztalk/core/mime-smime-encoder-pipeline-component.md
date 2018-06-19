---
title: Componente de canalización de codificador de MIME-SMIME | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c6a79052d3294420c46bff2a1ce3c0ed869e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263068"
---
# <a name="mime-smime-encoder-pipeline-component"></a><span data-ttu-id="c2e87-102">Componente de canalización de codificador de MIME-SMIME</span><span class="sxs-lookup"><span data-stu-id="c2e87-102">MIME-SMIME Encoder Pipeline Component</span></span>
<span data-ttu-id="c2e87-103">El componente de codificador de MIME/SMIME puede colocarse en la fase de codificación de una canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="c2e87-103">The MIME/SMIME Encoder component can be placed into the Encode stage of a send pipeline.</span></span> <span data-ttu-id="c2e87-104">Admite codificación de 7 bits, 8 bits, binaria, quoted-printable, base64 y UUEncode.</span><span class="sxs-lookup"><span data-stu-id="c2e87-104">It supports 7bit, 8bit, binary, quoted-printable, base64, and UUencode encoding.</span></span> <span data-ttu-id="c2e87-105">Los cambios del juego de caracteres de datos localizados no afectan a la codificación.</span><span class="sxs-lookup"><span data-stu-id="c2e87-105">Localized data character set changes do not affect the encoding.</span></span>  
  
 <span data-ttu-id="c2e87-106">Este componente puede utilizarse bien para codificación MIME o bien para firmar o cifrar un mensaje saliente con certificados de cifrado y de firma.</span><span class="sxs-lookup"><span data-stu-id="c2e87-106">This component can be used to either MIME encode, sign or encrypt an outgoing message with encryption and signing certificates.</span></span>  
  
 <span data-ttu-id="c2e87-107">Si existe un componente de codificación en la canalización de envío que está configurado para firmar mensajes y el grupo de BizTalk que incluye el host en el que se ejecuta la canalización no está configurado con un certificado de firma, el mensaje saliente se suspenderá (con el error apropiado) en la cola de suspensión del host en el que se ejecuta la canalización.</span><span class="sxs-lookup"><span data-stu-id="c2e87-107">If there is an encoding component in the send pipeline that is configured to sign messages, and the BizTalk group that includes the host running the pipeline is not configured with a signing certificate, the outgoing message will be suspended (with the appropriate error) to the suspended queue of the host that is running the pipeline.</span></span> <span data-ttu-id="c2e87-108">Si no se puede encontrar el certificado de firma en el almacén de certificados personales del usuario actual en el que se está ejecutando el servicio, el mensaje se suspenderá en la cola de suspensión del host en el que se ejecuta la canalización.</span><span class="sxs-lookup"><span data-stu-id="c2e87-108">If the signing certificate cannot be found in the personal certificate store of the current user under which the service is running, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="c2e87-109">Si existe un componente de codificación en la canalización de salida configurado para cifrar los mensajes salientes y no se puede encontrar el certificado en el almacén de certificados, el mensaje se suspenderá en la cola de suspensión del host en el que se ejecuta la canalización.</span><span class="sxs-lookup"><span data-stu-id="c2e87-109">If there is an encoding component in the outbound pipeline configured to encrypt outbound messages, and the certificate cannot be found in the certificate store, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="c2e87-110">Para llevar a cabo cifrado de respuesta en un puerto de solicitud-respuesta que está recibiendo mensajes firmados y cifrados, debe agregarse a la canalización un componente de canalización personalizado antes del componente de canalización de codificador de MIME/SMIME.</span><span class="sxs-lookup"><span data-stu-id="c2e87-110">To perform response encryption on a request-response port that is receiving signed and encrypted messages, a custom pipeline component must be added to the pipeline before the MIME/SMIME Encoder pipeline component.</span></span> <span data-ttu-id="c2e87-111">Este componente de canalización personalizado debe identificar la huella digital correspondiente al certificado de cifrado y establézcalo en la **BTS. EncryptionCert** propiedad en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2e87-111">This custom pipeline component must identify the thumbprint corresponding to the encryption certificate and set it to the **BTS.EncryptionCert** property on the message context.</span></span> <span data-ttu-id="c2e87-112">Para obtener más información acerca de las propiedades de contexto de mensaje, consulte [cómo modificar propiedades de grupo](../core/how-to-modify-group-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c2e87-112">For more information about message context properties, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
 <span data-ttu-id="c2e87-113">Para obtener información acerca de cómo configurar el componente de canalización de codificador de MIME/SMIME, vea [cómo configurar el componente de canalización de codificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="c2e87-113">For information about configuring the MIME/SMIME Encoder pipeline component, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="c2e87-114">Para obtener más información sobre la compatibilidad de BizTalk Server para cifrado, firma y el uso de certificados, consulte [seguridad para enviar y recibir mensajes](../core/security-for-sending-and-receiving-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c2e87-114">For more information about BizTalk Server support for encryption, signing, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e87-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2e87-115">See Also</span></span>  
 <span data-ttu-id="c2e87-116">[Componentes de canalización](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c2e87-116">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="c2e87-117">[Propiedades y esquema de propiedades de MIME-SMIME](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c2e87-117">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="c2e87-118">MIME (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="c2e87-118">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)
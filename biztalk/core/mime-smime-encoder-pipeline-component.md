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
# <a name="mime-smime-encoder-pipeline-component"></a>Componente de canalización de codificador de MIME-SMIME
El componente de codificador de MIME/SMIME puede colocarse en la fase de codificación de una canalización de envío. Admite codificación de 7 bits, 8 bits, binaria, quoted-printable, base64 y UUEncode. Los cambios del juego de caracteres de datos localizados no afectan a la codificación.  
  
 Este componente puede utilizarse bien para codificación MIME o bien para firmar o cifrar un mensaje saliente con certificados de cifrado y de firma.  
  
 Si existe un componente de codificación en la canalización de envío que está configurado para firmar mensajes y el grupo de BizTalk que incluye el host en el que se ejecuta la canalización no está configurado con un certificado de firma, el mensaje saliente se suspenderá (con el error apropiado) en la cola de suspensión del host en el que se ejecuta la canalización. Si no se puede encontrar el certificado de firma en el almacén de certificados personales del usuario actual en el que se está ejecutando el servicio, el mensaje se suspenderá en la cola de suspensión del host en el que se ejecuta la canalización.  
  
 Si existe un componente de codificación en la canalización de salida configurado para cifrar los mensajes salientes y no se puede encontrar el certificado en el almacén de certificados, el mensaje se suspenderá en la cola de suspensión del host en el que se ejecuta la canalización.  
  
 Para llevar a cabo cifrado de respuesta en un puerto de solicitud-respuesta que está recibiendo mensajes firmados y cifrados, debe agregarse a la canalización un componente de canalización personalizado antes del componente de canalización de codificador de MIME/SMIME. Este componente de canalización personalizado debe identificar la huella digital correspondiente al certificado de cifrado y establézcalo en la **BTS. EncryptionCert** propiedad en el contexto del mensaje. Para obtener más información acerca de las propiedades de contexto de mensaje, consulte [cómo modificar propiedades de grupo](../core/how-to-modify-group-properties.md).  
  
 Para obtener información acerca de cómo configurar el componente de canalización de codificador de MIME/SMIME, vea [cómo configurar el componente de canalización de codificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md). Para obtener más información sobre la compatibilidad de BizTalk Server para cifrado, firma y el uso de certificados, consulte [seguridad para enviar y recibir mensajes](../core/security-for-sending-and-receiving-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Componentes de canalización](../core/pipeline-components.md)   
 [Propiedades y esquema de propiedades de MIME-SMIME](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (ejemplo de BizTalk Server)](../core/mime-biztalk-server-sample.md)
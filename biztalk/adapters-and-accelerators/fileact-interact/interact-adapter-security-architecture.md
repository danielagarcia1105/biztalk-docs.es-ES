---
title: Arquitectura de seguridad del adaptador de interactuar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4924b8c-1fda-4a0c-b9be-8f2ccba38013
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb4234c72ad1d44fd1ca157ae031a73e2dbbd9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971853"
---
# <a name="interact-adapter-security-architecture"></a>Arquitectura de seguridad adaptador interAct
Seguridad para la transmisión del mensaje y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes en el vínculo de SWIFTNet (SNL) y la puerta de enlace SWIFTAlliance (SAG). SWIFT recomienda que los servicios diseñados para que interactuar aplicar una firma "end-to-end", es decir, los mensajes firmar la solicitud y respuesta.  
  
 Las operaciones criptográficas se implementan mediante el módulo de seguridad de SWIFTNet vínculo. Este módulo permite la firma y cifrado mediante claves PKI. La naturaleza y la extensión de las operaciones criptográficas se especifican como parte de las estructuras de datos de solicitud y respuesta Control pasado a la API.  
  
 SWIFTNet admite el inicio de sesión/cifrar del RequestPayload o ResponsePayload. También se puede firmar el RequestHeader o ResponseHeader.  
  
## <a name="signingencrypting-requests-and-responses"></a>Respuestas y solicitudes de firma y cifrado  
 Las reglas para aplicar las operaciones criptográficas en SWIFTNet interactuar solicitar elementos son los siguientes:  
  
- RequestControl: está destinado a SWIFTNet solo. SWIFTNet ofrece un RequestDescriptor para el servicio de respuesta (y algunos elementos también al solicitante). Por lo tanto, ningún proceso de cliente para la operación criptográfica de proceso de servidor puede realizarse en ella.  
  
- RequestE2EControl: este elemento contiene información para asegurarse de mensajería de confianza-to-end. No puede realizarse ninguna operación criptográfica en él.  
  
- RequestHeader: se usa por SWIFTNet y transmitir sin ninguna variación en el servicio de respuesta. Por lo tanto, esto solo se puede firmar.  
  
- RequestPayload: las operaciones criptográficas se pueden realizar en esto.  
  
- Elementos de cifrado: estos se relacionan con las operaciones criptográficas activadas anteriormente en esta solicitud. Puede realizarse ninguna operación criptográfica en estos.  
  
  Las reglas para aplicar funciones de cifrado en las respuestas de SWIFTNet interactuar son:  
  
- ResponseControl: está destinado a SWIFTNet solo. SWIFTNet ofrece un ResponseDescriptor al solicitante. Por lo tanto, ningún proceso de servidor para la operación criptográfica de proceso de cliente, puede realizarse en ella.  
  
- ResponseE2EControl: este elemento contiene información para asegurarse de mensajería de confianza-to-end. No puede realizarse ninguna operación criptográfica en él.  
  
- ResponseHeader: se puede firmar este elemento (se transfiere sin cambios al solicitante).  
  
- ResponsePayload: se puede cifrar o firmar.  
  
- Elementos de cifrado: estos se relacionan con las operaciones criptográficas activadas anteriormente en esta solicitud. Puede realizarse ninguna operación criptográfica en estos.  
  
## <a name="receiving-requests-with-cryptography"></a>Recibir solicitudes de criptografía  
 Un proceso de servidor puede recibir las solicitudes que se sometieron a las operaciones criptográficas por el solicitante. La solicitud entrante contiene toda la información pertinente para habilitar las operaciones criptográficas inversas. La información de CryptoInternal es tal que la función de descifrado y comprobación ahora funcionará eficazmente.  
  
 El proceso de servidor tendrá que activar los contextos de seguridad de DN de descifrado que se debe tener lugar  
  
 La solicitud, a continuación, se va a modificar las operaciones criptográficas inversas (comprobar, descifrar) de manera que la solicitud original estará disponible sin modificaciones al proceso del servidor, como se envió originalmente el proceso de cliente para el cifrado operaciones. Para la respuesta, realiza un procesamiento similar. Es importante darse cuenta de que la comprobación de una firma no solo comprobará lo que se firmó no se ha modificado, pero que se autenticará si el firmante es auténtico. Esto requiere que el SignDN utiliza un certificado válido. Un certificado válido es un certificado no ha sido revocado (una búsqueda en la lista de revocación de certificados, mantiene de forma centralizada en SWIFTNet).  
  
## <a name="activation"></a>Activación  
 Vínculo SWIFTNet pueden operar de comprobación y el descifrado en el modo automático para todas las solicitudes entrantes y entrante las respuestas. Esto significa que el vínculo de SWIFTNet procesará automáticamente (comprobar y descifrar) la criptografía última block de todos los entrantes (servidor) de solicitudes o respuestas entrantes (cliente). Los requisitos previos son que el contexto de seguridad necesario para el descifrado (si se ha solicitado el descifrado) está abierto y que se inicializó en el modo automático (esta opción para el modo automático se realiza en el Sw:InitRequest o Sw:HandleInitResponse, por vínculo SWIFTNet establecer el CryptoMode en "Automático" o mejor todavía "avanzada" para interactuar. (Use siempre "Avanzadas" para el adaptador interactuar, ya que esto permite que la aplicación cliente o servidor recuperar el formulario cifrado inesperado en el lado remoto, o desde un certificado expirado.  
  
 Vínculo de SWIFTNet funciona firma y cifrado automáticamente en una solicitud de salida (o una respuesta saliente) si se inicializa el campo RequestCrypto (ResponseCrypto) en "TRUE" en el RequestControl (ResponseControl) de la solicitud (respuesta).  
  
 En ese caso SWIFTNet vínculo procesa el último bloque de criptografía. Los requisitos previos son los que se abre el contexto de seguridad necesario para la firma (si se ha solicitado la firma), que está presente en la solicitud con la indicación en la firma y cifrado necesario y que el bloque cifrado el RequestCrypto (ResponseCrypto) marca se establece en "TRUE" en el RequestControl (ResponseControl). Esto se realiza siempre, independientemente de la CryptoMode utilizada en la inicialización del cliente o servidor.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura de adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio empresarial](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador de interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar adaptador Store y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Entrega confiable de extremo a otro adaptador de interactuar](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [No rechazo del adaptador de InterAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
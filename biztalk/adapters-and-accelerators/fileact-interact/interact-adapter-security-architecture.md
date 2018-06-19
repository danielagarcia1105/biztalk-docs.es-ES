---
title: Arquitectura de seguridad del adaptador de interactuar | Documentos de Microsoft
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
ms.openlocfilehash: de0eee57daec102507a9e502e3146e1cfcdec723
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225364"
---
# <a name="interact-adapter-security-architecture"></a>Arquitectura de seguridad del adaptador de interactuar
Seguridad para la transmisión de un mensaje y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes en vínculo SWIFTNet (SNL) y la puerta de enlace de SWIFTAlliance (SAG). SWIFT recomienda que los servicios diseñados para que interactuar aplicar una firma de "end-to-end", es decir, los mensajes firmar la solicitud y respuesta.  
  
 Las operaciones criptográficas se implementan mediante el módulo de seguridad de vínculo de SWIFTNet. Este módulo permite la firma y cifrado mediante claves PKI. La naturaleza y el alcance de operaciones de cifrado se especifican como parte de las estructuras de datos de solicitud y respuesta Control pasado a la API.  
  
 SWIFTNet es compatible con el inicio de sesión/encrypt del RequestPayload o ResponsePayload. También se puede firmar el RequestHeader o ResponseHeader.  
  
## <a name="signingencrypting-requests-and-responses"></a>Firmar o cifrar las solicitudes y respuestas  
 Las reglas para aplicar las operaciones criptográficas en interactuar solicitar SWIFTNet elementos son los siguientes:  
  
-   RequestControl: esto está destinado a SWIFTNet solo. SWIFTNet ofrece un RequestDescriptor para el servicio de respuesta (y algunos elementos también al solicitante). Por lo tanto, no hay ningún proceso de cliente para la operación de cifrado de proceso de servidor puede realizarse en ella.  
  
-   RequestE2EControl: este elemento contiene información para asegurarse de que la mensajería de confianza-to-end. No hay ninguna operación criptográfica puede realizarse en ella.  
  
-   RequestHeader: se está utilizando SWIFTNet y se pueden transmitir sin cambios en el servicio de respuesta. Por lo tanto, esto solo se puede firmar.  
  
-   RequestPayload: ninguna operación criptográfica puede realizarse en el objeto.  
  
-   Elementos de cifrado: estos se relacionan con las operaciones criptográficas activadas previamente en esta solicitud. Puede realizarse ninguna operación criptográfica de estos.  
  
 Las reglas para aplicar funciones de cifrado en las respuestas SWIFTNet interactuar son:  
  
-   ResponseControl: esto está destinado a SWIFTNet solo. SWIFTNet ofrece un ResponseDescriptor al solicitante. Por lo tanto, no hay ningún proceso de servidor para la operación criptográfica de proceso de cliente, puede realizarse en ella.  
  
-   ResponseE2EControl: este elemento contiene información para asegurarse de que la mensajería de confianza-to-end. No hay ninguna operación criptográfica puede realizarse en ella.  
  
-   ResponseHeader: se puede firmar este elemento (se transfiere sin cambios al solicitante).  
  
-   ResponsePayload: es posible cifrar y/o firmado.  
  
-   Elementos de cifrado: estos se relacionan con las operaciones criptográficas activadas previamente en esta solicitud. Puede realizarse ninguna operación criptográfica de estos.  
  
## <a name="receiving-requests-with-cryptography"></a>Recibir las solicitudes con criptografía  
 Un proceso de servidor puede recibir las solicitudes que se han sometido a las operaciones criptográficas por el solicitante. La solicitud entrante contiene toda la información pertinente para habilitar las operaciones criptográficas inversas. La información de CryptoInternal es tal que la función de descifrado y comprobación ahora funcionará eficazmente.  
  
 El proceso de servidor tendrá que activar los contextos de seguridad de DN para las necesidades de descifrado que se realicen  
  
 La solicitud, a continuación, se va a modificar las operaciones criptográficas inversas (comprobar, descifrar) de forma que la solicitud original estará disponible sin modificaciones al proceso del servidor, tal y como se entregó originalmente por el proceso de cliente para el cifrado operaciones. Para la respuesta, procesamiento similar tiene lugar. Es importante tener en cuenta que la comprobación de una firma no solo comprueba lo que se firmó no se han modificado, pero que se autenticarán si firmante es auténtico. Esto requiere que el SignDN utiliza un certificado válido. Un certificado válido es un certificado no ha sido revocado (una búsqueda en la lista de revocación de certificados, mantiene de forma centralizada en SWIFTNet).  
  
## <a name="activation"></a>Activación  
 Vínculo SWIFTNet pueden funcionar comprobación y el descifrado en el modo automático para todas las solicitudes entrantes y entrante respuestas. Esto significa que el vínculo de SWIFTNet procesará automáticamente (comprobar y descifrar) la clave criptográfica último bloque de todas las solicitudes (servidor) o respuestas entrantes (cliente). Los requisitos previos son que el contexto de seguridad necesario para el descifrado (si se solicita el descifrado) está abierto y que se ha inicializado SWIFTNet vínculo en el modo automático (esta opción para el modo automático se realiza en el Sw:InitRequest o Sw:HandleInitResponse, por establecer el CryptoMode en "Automático" o mejor aún "avanzadas" para interactuar. (Siempre usaremos "Opciones avanzadas" para el adaptador interactuar, ya que esto permite que la aplicación cliente o servidor recuperar el formulario cifrado inesperado en el lado remoto, o desde un certificado expirado.  
  
 Vínculo de SWIFTNet funciona firma y cifrado automáticamente en una solicitud de salida (o una respuesta saliente) si el campo RequestCrypto (ResponseCrypto) se inicializa en "TRUE" en la RequestControl (ResponseControl) de la solicitud (respuesta).  
  
 En ese caso SWIFTNet vínculo procesa el último bloque de cifrado. Los requisitos previos son que se abre el contexto de seguridad necesario para la firma (si se solicita la firma), que el bloque de cifrado está presente en la solicitud con la indicación en la firma y cifrado obligatorio y que la RequestCrypto (ResponseCrypto) marca se establece en "TRUE" en la RequestControl (ResponseControl). Esto se realiza siempre, independientemente de la CryptoMode utilizada en la inicialización del cliente o servidor.  
  
## <a name="see-also"></a>Vea también  
 [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [Componentes de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Interactuar mensajes del adaptador para el intercambio de negocios](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [Aplicación de cliente de adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [Aplicación de servidor del adaptador interAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [Interactuar el adaptador de almacenamiento y reenvío](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [Interactuar entrega confiable de adaptador-to-End](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [Estado del adaptador de interactuar de supervisión](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [Interactuar sin repudio de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)
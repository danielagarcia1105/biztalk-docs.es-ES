---
title: "Estándar RNIF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNIF, message definitions
- RNIF, messaging framework patterns
- messages, message definitions
- RNIF, standards
- messages, messaging framework patterns
ms.assetid: d39a9683-1ef5-462b-9472-4e30fe873f7d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6b29d8c9c770893fd78769b86266ce33e31a336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-standard"></a>Estándar RNIF
El estándar del marco de implementación de RosettaNet (RNIF) define cómo transportan los sistemas un mensaje de RosettaNet. El estándar RNIF es un estándar sólido de transferencia, enrutamiento, empaquetado y seguridad. Todos los sistemas de mensajería de RosettaNet deben ser compatibles con el estándar RNIF para obtener la certificación de RosettaNet.  
  
 El estándar define la estructura del mensaje, la necesidad de confirmaciones, la codificación de extensiones multipropósito de correo Internet (MIME) y la firma digital. El estándar principal incluye los requisitos de autenticación, autorización, cifrado y sin repudio. El estándar RNIF se basa en estándares HTTP, MIME y XML. El estándar RNIF no especifica una plataforma o una aplicación de activación.  
  
 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]implementa dos versiones de RNIF: especificación de RNIF v02.00.01 y especificación de RNIF v1.1. RNIF 2.01 agrega funciones no incluidas en RNIF 1.1, incluido el cifrado, los datos adjuntos y las transacciones sincrónicas. RNIF 2.0 no es compatible con RNIF 1.1.  
  
## <a name="messaging-framework-patterns"></a>Patrones del marco de mensajería  
 En la siguiente tabla se muestra la compatibilidad de RNIF con patrones del marco de mensajería y el intercambio de mensajes sincrónico. Un mensaje de acción única es aquel que no implica una respuesta, mientras que un mensaje de doble acción incluye una solicitud y una respuesta.  
  
|Framework|Patrón|Sincrónico/<br />Asincrónico|  
|---------------|-------------|---------------------------------|  
|RNIF 1.1|Notification|Asincrónico|  
|RNIF 1.1|Transacción|Asincrónico|  
|RNIF 2.0|Doble acción|Sincrónico|  
|RNIF 2.0|Doble acción|Asincrónico|  
|RNIF 2.0|Acción única|Sincrónico|  
|RNIF 2.0|Acción única|Asincrónico|  
  
## <a name="message-definitions"></a>Definiciones de mensaje  
 RNIF 1.1 y RNIF 2.01 definen los mensajes de RosettaNet de manera diferente. Entre estas diferencias se incluye el modo de controlar los datos adjuntos, la envoltura de extensiones seguras multipropósito al correo de Internet (SMIME), el encabezado de entrega y el empaquetado MIME. RNIF 2.01 incluye expresamente datos adjuntos; RNIF 2.01 agrega un encabezado de entrega, mientras que RNIF 1.1 no lo hace.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no admite la *recomendaciones técnicas para RNIF 1.1* fabricado por la organización RosettaNet (una para la compatibilidad con datos adjuntos y otra para las respuestas sincrónicas).  
  
 Los sistemas utilizan las partes de los mensajes RNIF 1.1 y RNIF 2.01 dedicadas a la identificación de la entidad, al enrutamiento y a la identificación de nivel de servicio. Antes de leer y responder a un cuerpo de contenido de servicio, que es el contenido principal del mensaje, cada entidad debe rellenar o interpretar correctamente los valores del encabezado.  
  
 La ilustración siguiente describe las definiciones de mensaje de RNIF 1.1 y RNIF 2.01.  
  
 ![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-rnif-message-definitions.gif "RN3_RNIF_Message_Definitions")  
  
 En el mensaje de RNIF 1.1, el número de versión indica la versión RNIF. La longitud del contenido es la longitud del mensaje de servicio de RosettaNet. El mensaje del servicio, que incluye el preámbulo, la cabecera del servicio y el contenido del servicio, es una entidad MIME de varias partes o relacionada. La longitud de la firma se expresa en bytes. Si la firma existe, será una firma Public-Key Cryptography Standards (PKCS) #7 en el campo de mensaje de servicio.  
  
 RNIF 2.01 incluye un contenedor independiente del protocolo de transferencia que empaqueta la carga empresarial, los componentes del encabezado y otros elementos que se intercambiarán los sistemas en el paquete. Un mensaje empresarial de RosettaNet (como se define para RNIF 2.01) contiene un preámbulo, un encabezado de entrega, un encabezado de servicio y contenido del servicio. Los sistemas deben validar todos los elementos con respecto al esquema del tipo de documento que los contiene, según las reglas estándares de validación de la gramática de la definición de tipo de documento (DTD) de RosettaNet. El contenido de un servicio puede ser un mensaje de acción o de señal. Si el contenido de un servicio es un mensaje de acción, el mensaje puede incluir uno o varios datos adjuntos.  
  
 Un mensaje empresarial de RosettaNet es una entidad MIME de varias partes o relacionada. Como se muestra en la ilustración anterior, los encabezados y el contenido del servicio se empaquetan juntos mediante una construcción de varias partes o relacionada de MIME, que es similar al esquema de empaquetado de RNIF 1.1. Opcionalmente, los sistemas pueden firmar digitalmente un mensaje empresarial de RosettaNet. En RNIF 1.1, se usaría el formato de Objeto de RosettaNet (RNO) para esta finalidad. RNIF 2.0 elimina el formato RNO y, en su lugar, utiliza el estándar de codificación S/MIME.  
  
 Un sistema puede cifrar la carga RNIF 2.01 o el contenedor de carga. Para ello, debe agrupar los elementos que desea cifrar en una entidad MIME de varias partes o relacionada y, después, cifrarlos. A continuación, empaquete el objeto S/MIME resultante como una única parte en el mensaje empresarial de RosettaNet.  
  
 Un mensaje de señal siempre debe ser una instancia del mensaje definido por RosettaNet. Para los mensajes de acción, la especificación RNIF 2.01 ofrece la opción de enviar los mensajes de acción empresariales en un formato definido de terceros. El encabezado de servicio de RNIF 2.01 incluye campos adicionales para este fin, como un campo que identifica el "cuerpo estándar" y un campo que identifica la versión de la especificación a la que se ajusta el mensaje de acción.  
  
 Solo los mensajes de acción (también conocidos como contenido empresarial) pueden tener un origen distinto a RosettaNet. Los sistemas deben intercambiar estos mensajes en un PIP definido por RosettaNet. RosettaNet debe autorizar estos mensajes mediante la identificación explícita del mensaje de acción de terceros aprobado en la especificación de PIP. Además, los socios comerciales deben aceptar en su acuerdo de socios comerciales el intercambio de contenido comercial de otro fabricante. El contrato debe incluir la información de enlace de carga PIP, que identifica el contenido empresarial de terceros que usaría como un reemplazo para un mensaje de acción determinado en un PIP.  
  
## <a name="see-also"></a>Vea también  
 [RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [PIP de RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)
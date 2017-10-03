---
title: "Componente de canalización de descodificador de MIME-SMIME | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d85fe099cb876156410ba86c5f204a154dfbac36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mime-smime-decoder-pipeline-component"></a>Componente de canalización de descodificador de MIME-SMIME
El componente de descodificador de MIME/SMIME proporciona funcionalidad de descodificación MIME para los mensajes. Este componente de canalización puede situarse en la fase de decodificación de una canalización de recepción, y admite decodificación de 7bits, 8bits, binaria, quoted-printable, UUEncode y base64. Los cambios del juego de caracteres de datos localizados no afectarán a la descodificación.  
  
 El componente de descodificador de MIME/SMIME puede descifrar y validar con firma un mensaje entrante. Los certificados de descifrado se utilizan desde el almacén de certificados personales del usuario actual bajo el que se está ejecutando el servicio. Los certificados de validación con firma se utilizan desde el almacén de libretas de direcciones del equipo local o desde el propio mensaje.  
  
 Con el descifrado correcto de un mensaje, el componente de canalización del descodificador de MIME/SMIME asocia la huella digital del certificado de descifrado que se utiliza para descifrar el mensaje como un predicado del mensaje. Esto supone que cualquier servicio (orquestación o puerto de envío) que se esté suscribiendo a ese mensaje debe asociarse a un host que sea el propietario de la clave. Las asociaciones entre hosts y claves pueden completarse en la consola de administración de BizTalk como una propiedad del host. Para obtener más información acerca de cómo configurar el host en la consola de administración de BizTalk, consulte [cómo modificar propiedades de Host](../core/how-to-modify-host-properties.md).  
  
 El componente de canalización del descodificador de MIME/SMIME es el único componente de canalización de recepción predeterminado que controla los mensajes de varias partes, incluso los mensajes MIME/SMIME de varias partes. El componente de canalización analiza el mensaje y crea un mensaje de varias partes de BizTalk equivalente. Un mensaje de varias partes de BizTalk tiene una parte única denominada cuerpo. Los demás componentes de la canalización, como el desensamblador XML, solo procesan la parte del cuerpo del mensaje de BizTalk. Además el MessageType que corresponde a la parte del cuerpo de BizTalk se utiliza para enrutar el mensaje a los suscriptores.  
  
 El componente de canalización del descodificador de MIME/SMIME evalúa las siguientes condiciones para identificar la BodyPart de BizTalk que corresponde a un mensaje MIME de varias partes. El orden de la evaluación de condiciones es el siguiente:  
  
1.  La primera parte MIME/SMIME que tiene el encabezado de la descripción de contenido definido como "cuerpo" (no distingue mayúsculas de minúsculas).  
  
2.  La primera parte MIME/SMIME que tiene el encabezado del tipo de contenido definido como "texto/xml" (no distingue mayúsculas de minúsculas).  
  
3.  La primera parte MIME/SMIME que tiene el encabezado del tipo de contenido definido como "texto/" (no distingue mayúsculas de minúsculas).  
  
4.  La primera parte MIME/SMIME.  
  
> [!NOTE]
>  El orden de las partes en el mensaje de salida de BizTalk es el mismo que el orden de las partes MIME/SMIME en el mensaje MIME/SMIME.  
  
> [!NOTE]
>  Si una orquestación suscribe o consume el mensaje de varias partes de BizTalk, el número de partes en el mensaje tiene que coincidir con el número de partes en el mensaje que activa la orquestación.  
  
 Para obtener información acerca de cómo configurar el componente de canalización de descodificador de MIME/SMIME, vea [cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md). Para obtener más información sobre la compatibilidad de BizTalk Server para el descifrado, validación de inicio de sesión y el uso de certificados, consulte [seguridad para enviar y recibir mensajes](../core/security-for-sending-and-receiving-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Componentes de canalización](../core/pipeline-components.md)   
 [Propiedades y esquema de propiedades de MIME-SMIME](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (ejemplo de BizTalk Server)](../core/mime-biztalk-server-sample.md)
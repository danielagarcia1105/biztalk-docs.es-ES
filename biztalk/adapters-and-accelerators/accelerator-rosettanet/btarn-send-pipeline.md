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
# <a name="btarn-send-pipeline"></a>Canalización de envío BTARN
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepara un mensaje de RosettaNet Implementation Framework (RNIF) para su transmisión en la canalización de RNIFSend (RNIFSend.btp). La canalización de envío incluye lo siguiente:  
  
-   XML de preprocesador  
  
-   Ensamblador de XML  
  
-   Codificador de Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME)  
  
## <a name="xml-preprocessor"></a>Preprocesador XML  
 El preprocesador XML agrega un encabezado de tipo de documento al mensaje. El encabezado identifica el esquema de definición (DTD) de tipo de documento asociado con el mensaje. La especificación de RNIF requiere la presencia de un encabezado de tipo de documento para la transmisión de RNIF.  
  
## <a name="xml-assembler"></a>ensamblador XML.  
 El ensamblador XML se basa en el ensamblador de XML de BizTalk Server. Transfiere las propiedades del contexto del mensaje en sobres y documentos. Ensambla el mensaje de sus elementos XML y los datos adjuntos. No realiza validación del mensaje.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblador XML, vea "Componente de canalización de ensamblador XML" en la Ayuda de BizTalk Server.  
  
## <a name="mimesmime-encoder"></a>codificador de MIME/SMIME  
 El codificador MIME/SMIME se basa en el codificador MIME/SMIME de BizTalk Server. Dependiendo de la configuración del protocolo de acuerdo de socio comercial y la configuración del codificador MIME/SMIME de BizTalk Server, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] codificador realiza lo siguiente:  
  
-   Agrega un encabezado binario de 8 bytes para el mensaje, según sea necesario para los mensajes de RNIF 1.1.  
  
-   Codifica las partes del mensaje y calcula el resumen.  
  
-   Cifra la carga (contenido del servicio y los datos adjuntos) o el contenedor de carga (contenido del servicio más cab más datos adjuntos). Si ha configurado la **codificar todos los puertos** en el **protocolo** ficha del acuerdo de socio comercial a `False`, el codificador cifrará solo la carga. Si ha configurado la **codificar todos los puertos** si se establece en `True`, el codificador cifrará el contenedor de carga.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] codificador MIME/SMIME, vea "Componente de canalización de codificador MIME/SMIME" en la Ayuda de BizTalk Server.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización es como sigue:  
  
1.  Si ha configurado la **codificar todas las partes** configuración del acuerdo de socio comercial a `True`, el codificador MIME/SMIME codificará todas las partes del mensaje. Utilizará el método de codificación que se establece el `Encoding` propiedad del acuerdo.  
  
2.  Para RNIF 2.01, si el mensaje es un mensaje de acción y no hay un archivo adjunto, el codificador hará lo siguiente para cada archivo adjunto:  
  
    1.  Si los datos adjuntos están binario, lo codificará el codificador.  
  
    2.  El codificador generará un identificador de contenido de los datos adjuntos.  
  
    3.  El codificador creará una parte MIME para los datos adjuntos.  
  
3.  Para RNIF 2.01, la canalización cifrará partes del mensaje y generar el mensaje RNIF según la configuración de **se necesita confidencialidad persistente** (como se establece en los valores de configuración de proceso):  
  
    1.  Si ha configurado **se necesita confidencialidad persistente** a **carga**, el codificador cifrará el contenido del servicio y los datos adjuntos. El ensamblador, a continuación, agregará el encabezado de servicio, el encabezado de entrega y el preámbulo para construir el mensaje RNIF final.  
  
    2.  Si ha configurado **se necesita confidencialidad persistente** a **contenedor de carga**, el codificador cifrará el encabezado de servicio, el contenido del servicio y los datos adjuntos. El ensamblador, a continuación, agregará el encabezado de entrega y el preámbulo para construir el mensaje RNIF final.  
  
    3.  Si ha configurado **se necesita confidencialidad persistente** a **ninguno**, el ensamblador agregará el preámbulo, encabezado de servicio y encabezado de entrega para el contenido del servicio y los datos adjuntos (sin cifrado) para construir el mensaje RNIF final.  
  
4.  Para RNIF 1.1, el ensamblador construirá el mensaje RNIF final sin cifrado.  
  
5.  El codificador firmará el mensaje en el caso siguiente:  
  
    1.  El mensaje es un mensaje de señal y la **sin repudio necesario** propiedad (en los valores de configuración de proceso) es `True`.  
  
    2.  El mensaje es un mensaje de acción y el **sin repudio del origen y del contenido** propiedad (en los valores de configuración de proceso) es `True`.  
  
6.  Para RNIF 2.01, el codificador calcular el resumen en la primera parte del cuerpo del mensaje MIME y conservar el resumen. Calculará la síntesis utilizando el método definido en el `Digest` propiedad de método en el acuerdo de socio comercial (SHA-1 o MD5).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)
---
title: Canalización de envío de BTARN | Microsoft Docs
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
ms.openlocfilehash: 0791ab4714e1e8a9de847a60d17d14e38f095ecf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011637"
---
# <a name="btarn-send-pipeline"></a>Canalización de envío BTARN
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepara un mensaje de RosettaNet Implementation Framework (RNIF) para su transmisión en la canalización RNIFSend (RNIFSend.btp). La canalización de envío incluye lo siguiente:  
  
-   XML de preprocesador  
  
-   Ensamblador de XML  
  
-   Codificador de Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME)  
  
## <a name="xml-preprocessor"></a>Preprocesador XML  
 El preprocesador XML agrega un encabezado de tipo de documento al mensaje. El encabezado identifica el esquema de definición (DTD) de tipo de documento asociado al mensaje. La especificación de RNIF requiere la presencia de un encabezado de tipo de documento para la transmisión de RNIF.  
  
## <a name="xml-assembler"></a>ensamblador XML.  
 El ensamblador XML se basa en el ensamblador de XML de BizTalk Server. Transfiere las propiedades del contexto del mensaje en sobres y documentos. Ensambla el mensaje de sus elementos XML y los datos adjuntos. No lleva a cabo la validación de mensajes.  
  
 Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblador XML, vea "Componente de canalización de ensamblador XML" en la Ayuda de BizTalk Server.  
  
## <a name="mimesmime-encoder"></a>codificador de MIME/SMIME  
 El codificador MIME/SMIME se basa en el codificador MIME/SMIME de BizTalk Server. Dependiendo de la configuración del protocolo de acuerdo de socio comercial y la configuración del codificador MIME/SMIME de BizTalk Server, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] codificador realiza lo siguiente:  
  
- Agrega un encabezado binario de 8 bytes para el mensaje, según sea necesario para los mensajes de RNIF 1.1.  
  
- Codifica las partes del mensaje y calcula el resumen.  
  
- Cifra la carga (contenido del servicio y los datos adjuntos) o el contenedor de carga (contenido del servicio más encabezado de servicio más datos adjuntos). Si ha establecido la **codificar todos los puertos** en el **protocolo** ficha del acuerdo de socio comercial a `False`, el codificador va a cifrar sólo la carga. Si ha establecido la **codificar todos los puertos** si se establece en `True`, el codificador cifrará el contenedor de carga.  
  
  Para obtener más información acerca de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] codificador MIME/SMIME, vea "Componente de canalización de codificador MIME/SMIME" en la Ayuda de BizTalk Server.  
  
## <a name="message-flow"></a>Flujo de mensajes  
 El flujo de mensajes a través de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización es como sigue:  
  
1.  Si ha establecido la **codificar todas las partes** configuración del acuerdo de socio comercial a `True`, el codificador MIME/SMIME codificarán todas las partes del mensaje. Usará el método de codificación establecido el `Encoding` propiedad del acuerdo.  
  
2.  Para RNIF 2.01, si el mensaje es un mensaje de acción y no hay datos adjuntos, el codificador hará lo siguiente para cada archivo adjunto:  
  
    1.  Si los datos adjuntos están binario, el codificador se codificará.  
  
    2.  El codificador generará un identificador de contenido de los datos adjuntos.  
  
    3.  El codificador creará una parte MIME para los datos adjuntos.  
  
3.  Para RNIF 2.01, la canalización se cifrar partes del mensaje y generar el mensaje RNIF según la configuración de **se necesita confidencialidad persistente** (como se establece en la configuración del proceso):  
  
    1.  Si ha establecido **se necesita confidencialidad persistente** a **carga**, el codificador va a cifrar el contenido del servicio y los datos adjuntos. El ensamblador, a continuación, agregará el encabezado de servicio, encabezado de entrega y preámbulo para construir el mensaje RNIF final.  
  
    2.  Si ha establecido **se necesita confidencialidad persistente** a **contenedor de carga**, el codificador cifrará el encabezado de servicio, el contenido del servicio y los datos adjuntos. El ensamblador, a continuación, agregará el encabezado de entrega y el preámbulo para construir el mensaje RNIF final.  
  
    3.  Si ha establecido **se necesita confidencialidad persistente** a **ninguno**, el ensamblador agregará el preámbulo, encabezado de servicio y encabezado de entrega para el contenido del servicio y los datos adjuntos (sin cifrado) para construir el mensaje RNIF final.  
  
4.  Para RNIF 1.1, el ensamblador construirá el mensaje RNIF final sin cifrado.  
  
5.  El codificador firmará el mensaje en el caso siguiente:  
  
    1.  El mensaje es un mensaje de señal y la **sin repudio necesario** propiedad (en la configuración del proceso) es `True`.  
  
    2.  El mensaje es un mensaje de acción y el **sin repudio del origen y del contenido** propiedad (en la configuración del proceso) es `True`.  
  
6.  Para RNIF 2.01, el codificador calcular el resumen en la primera parte del cuerpo del mensaje MIME y conservar el resumen. Calculará la síntesis utilizando el método definido en el `Digest` propiedad method en el acuerdo entre socios comerciales (SHA-1 o MD5).  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)
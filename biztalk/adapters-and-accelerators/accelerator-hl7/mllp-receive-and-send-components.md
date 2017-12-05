---
title: "Componentes de envío y recepción de MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135b98c04531aa6200f3b79c5b6d5153bf299a7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mllp-receive-and-send-components"></a>Componentes de envío y recepción de MLLP
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) todos los admite [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tipos de adaptador nativo, incluidos el archivo, HTTP, SQL y FTP. Para HL7 mensaje codificado en recibir y enviar, sin embargo, se suele usa el adaptador MLLP. Este adaptador es un adaptador de socket de TCP/IP que usa el protocolo de nivel inferior (MLLP) mínimo. Este protocolo proporciona integración de aplicaciones sanitaria de soporte técnico y end-to-end de mensajes bidireccionales.  
  
 Puede configurar el MLLP como un adaptador bidireccional o un adaptador unidireccional del adaptador de recepción. Puede configurar el adaptador de envío MLLP como adaptador de envío de una petición-respuesta bidireccional, un envío unidireccional adaptador configurado para recibir confirmaciones (ACK) en la misma conexión de socket o una unidireccional del adaptador que no devuelve ningún mensaje de envío. Cuando se usa el bidireccional adaptador MLLP de envío de petición-respuesta, puede configurar el puerto de recepción para devolver mensajes de confirmación o mensajes de respuesta. Para obtener ejemplos de MLLP enviarán y adaptadores de recepción, consulte [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).  
  
 Los mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe o envía en un adaptador MLLP requiere los siguientes contenedores:  
  
-   \<SB\> caracteres de bloque de inicio  
  
-   \<EB\> caracteres de bloque final  
  
-   \<CR\> bytes de devolver del carro (opcional)  
  
 Adaptadores MLLP proporcionan control de errores de falta \<SB\> o \<EB\> contenedores, las conexiones interrumpidas o tiempos de espera. Con un adaptador MLLP, puede configurar una limitación en el número de conexiones. Puede usar una gran variedad de confirmaciones con un adaptador MLLP.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Acelerador de BizTalk para componentes de HL7](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
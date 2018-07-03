---
title: Componentes de envío y recepción de MLLP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eebc51d23c66fb9dd7047f29982fbcc05a8215f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971805"
---
# <a name="mllp-receive-and-send-components"></a>Componentes de envío y recepción de MLLP
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) es compatible con todos los Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tipos de adaptador nativo, incluidos el archivo, HTTP, FTP y SQL. Para HL7 mensaje codificado en recibir y enviar, sin embargo, se suele usa el adaptador de MLLP. Este adaptador es un adaptador de socket de TCP/IP que usa el protocolo de capa inferior (MLLP) mínimos. Este protocolo proporciona integración de mensajes bidireccionales-to-end y de soporte técnico principal aplicación sanitaria.  
  
 Puede configurar el MLLP como un adaptador bidireccional o un adaptador unidireccional del adaptador de recepción. Puede configurar el adaptador de envío MLLP como adaptador de envío de una petición-respuesta bidireccional, configurado para recibir la confirmación (ACK) en la misma conexión de socket de adaptador de envío unidireccional o adaptador que no devuelve ningún mensaje de envío unidireccional. Al usar bidireccional de petición-respuesta del adaptador MLLP de envío, puede configurar el puerto de recepción para devolver mensajes de confirmación o mensajes de respuesta. Para obtener ejemplos de MLLP enviarán y adaptadores de recepción, vea [Tutorial de interrogación](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).  
  
 Los mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe o envía en un adaptador MLLP requiere los siguientes contenedores:  
  
- \<SB\> carácter de inicio de bloque  
  
- \<EB\> caracteres de bloque final  
  
- \<CR\> bytes de devolver del carro (opcional)  
  
  Los adaptadores MLLP proporcionan control de errores de falta \<SB\> o \<EB\> contenedores, las conexiones interrumpidas o tiempos de espera. Con un adaptador MLLP, puede configurar una limitación del número de conexiones. Puede usar una gran variedad de confirmaciones con un adaptador MLLP.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [Acelerador de BizTalk para componentes de HL7](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
---
title: Confirmación CONTRL de EDIFACT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8489f89714871f23fec329b44cafb4180f91c874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996901"
---
# <a name="edifact-contrl-acknowledgment"></a>Confirmación CONTRL de EDIFACT
La confirmación CONTRL (ACK) sirve de confirmación técnica y funcional para los mensajes con codificación EDIFACT. Como confirmación técnica, el mensaje CONTRL indica la recepción de un intercambio. Como confirmación funcional, el mensaje CONTRL indica la aceptación o el rechazo del intercambio, el grupo o el mensaje recibido, con una lista de los errores o la funcionalidad no admitida.  
  
 El mensaje CONTRL completo sirve de confirmación funcional. Las secciones de la confirmación funcional vuelven a utilizarse para la confirmación técnica. Si ha seleccionado las confirmaciones técnicas y funcionales en las propiedades de entidad para una entidad de envío o en las propiedades globales, BizTalk Server generará dos mensajes CONTRL: una ACK CONTRL técnica y un ACK. CONTRL funcionales  
  
 El ACK CONTRL se ajusta a la EFACT_\<número de versión\>esquema _CONTRL.xsd.  
  
## <a name="technical-acknowledgement"></a>Confirmación técnica  
 Una confirmación técnica implica que el destinatario del mensaje:  
  
-   ha recibido el intercambio del asunto;  
  
-   confirma que las partes del intercambio de asunto que se han comprobado para asegurarse de que los elementos de datos copiados en el segmento UCI del informe son sintácticamente correctos;  
  
-   ha aceptado la responsabilidad de notificar al remitente de la confirmación o el rechazo de otras partes del intercambio de asunto;  
  
-   y ha tomado precauciones razonables para asegurarse de que se le notifica de ello al remitente.  
  
## <a name="functional-acknowledgement"></a>Confirmación funcional  
 Una confirmación funcional implica que el destinatario del intercambio:  
  
- ha recibido los niveles a los que se hace referencia del intercambio confirmado;  
  
- ha comprobado que no hay ningún error sintáctico grave en el nivel al que se hace referencia confirmado que evita un procesamiento posterior del intercambio;  
  
- ha comprobado que las partes confirmadas de los segmentos de servicio son sintácticamente correctas (si no se informa de ningún error);  
  
- cumplirá con las acciones solicitadas en los niveles a los que se hace referencia confirmados de los segmentos de servicio;  
  
- ha aceptado la responsabilidad de notificar al remitente por otros medios de que el envío de un mensaje de CONTRL si se detecta con posterioridad algún error sintáctico o semántico tal y como se ha descrito anteriormente, o no puede procesarse la parte por algún otro motivo después de que la parte se haya confirmado en un mensaje de CONTRL enviado;  
  
- y ha tomado precauciones razonables para asegurarse de se han detectado dichos errores y de que se le notifica de ello al remitente.  
  
  El rechazo implica que el destinatario del intercambio:  
  
- no puede confirmar el intercambio de asunto o las partes relevantes por los motivos indicados en el mensaje de CONTRL;  
  
- y no emprenderá ninguna acción adicional sobre la información empresarial contenida en la parte rechazada del intercambio de asunto.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Mensaje CONTRL de EDIFACT como confirmación técnica](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [Mensaje CONTRL de EDIFACT como confirmación funcional](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a>Vea también  
 [Estructura de confirmación EDI](../core/edi-acknowledgment-structure.md)
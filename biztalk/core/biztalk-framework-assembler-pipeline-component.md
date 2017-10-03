---
title: "Componente de canalización de ensamblador de BizTalk Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777e3d98ade5b4e0c54744cea6d37b1e43717e66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-assembler-pipeline-component"></a>Componente de canalización de ensamblador de BizTalk Framework
BizTalk Framework es un enfoque para hacer una entrega garantizada exactamente una vez utilizando protocolos de transporte mediante conexión como HTTP o SMTP. Este marco de trabajo existe desde 1998 y puede considerarse un precursor de las iniciativas de estándares pendientes basadas en servicios Web, específicamente WSReliable. Por lo general, el problema de la entrega de datos garantizada exactamente una vez ha sido el dominio de tecnologías como Message Queue Server (también conocida como MSMQ). Sin embargo, estas tecnologías suelen requerir software común en los dos extremos de un flujo de datos y tampoco hacen nada para resolver la utilización de protocolos de transporte abiertos basados en redes públicas, por ejemplo, datos que fluyen entre empresas a través de Internet.  
  
 Obviamente, BizTalk Framework implementa algunos de los mismos mecanismos presentes en intentos previos de resolver el problema de la entrega de datos garantizada exactamente una vez. Un buen ejemplo de otras soluciones al problema es el intercambio electrónico de datos (EDI), en el que los documentos de confirmación funcional del estándar 997 y los números de control de ANSI X12 forman la base de la garantía de que los datos se reciban solo una vez, y de que se notifique al remitente cualquier problema en el extremo receptor.  
  
 BizTalk Framework asume que, por distintos que sean los sistemas de intercambio de datos, ambos entienden los requisitos del protocolo de BizTalk Framework respecto de:  
  
-   Utilizar un formato de sobre previsible en el que ajustar las transmisiones.  
  
-   Etiquetar todas las transmisiones de salida con un identificador único global.  
  
-   Devolver siempre al remitente una confirmación de recepción que incluya el identificador único global, incluso de datos que ya se hayan recibido, confirmado y procesado.  
  
-   Algunos medios por los que el remitente pueda repetir las transmisiones, bien hasta que llegue una notificación del receptor o bien pase un período de tiempo más allá del cual la transmisión ya no sea válida.  
  
 El componente de canalización de ensamblador de BizTalk Framework es el responsable de serializar el sobre y los contenidos de BizTalk Framework en el mensaje antes de la transmisión y repetición del envío en caso de que no llegue una notificación en el período de tiempo asignado. También es responsable de recibir y procesar las notificaciones y de eliminar la instancia de mensaje. (Una copia de la instancia de mensaje del mensaje enviado se mantiene en la base de datos de cuadro de mensajes hasta que BizTalk recibe una notificación de recepción del destinatario. Una vez recibida, el motor de mensajería elimina la instancia de mensaje).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de ensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)   
 [Componentes de canalización](../core/pipeline-components.md)
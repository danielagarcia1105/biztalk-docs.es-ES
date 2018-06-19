---
title: Tipos y eventos de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9880da0ca5fea84c5a2b3d6e9f3a43ace41970
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205956"
---
# <a name="message-types-and-events"></a>Eventos y los tipos de mensaje
El estándar HL7 agrupan mensajes relacionados con un agrupamiento de eventos reales juntos como *tipo de mensaje* ADT. Estos mensajes implican los eventos de desencadenador, como administración de pacientes. Versión 2.4 del estándar HL7 define más de 100 tipos de mensajes, cada uno de los cuales el HL7 organización le ha asignado un código de tipo de mensaje de tres caracteres únicos. Tal y como han evolucionado versiones del estándar HL7, la organización de HL7 ha agregado nuevos tipos de mensajes para proporcionar nuevas capacidades.  
  
 Todos los tipos de mensaje contienen eventos de mensaje, también denominados *eventos*. Se puede considerar un evento como un único tipo de mensaje agrupado dentro de un tipo de mensaje determinado. Por ejemplo, la notificación de administración/visita (evento de mensaje A01) y la descarga/End visite (evento de mensaje A03) son mensajes únicos contenidos por el tipo de mensaje de administración de paciente (ADT). La organización de HL7 asignó a cada evento de mensaje de un código de evento único de tres caracteres.  
  
 Tipo de solo mensaje puede contener un evento de mensaje determinado. Tipos de mensaje pueden contener varios eventos de mensaje. Sin embargo, la estructura de un evento de mensaje determinado puede variar entre las versiones del estándar HL7.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [Desencadenar eventos y mensajes](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md)   
 [Mensajería HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
---
title: Problemas conocidos con confirmaciones EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02ef54ed8786f8ead12e16fad880040dbcadc8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-acknowledgments"></a>Problemas conocidos de confirmaciones EDI
Este tema describe los problemas conocidos con las confirmaciones EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a>AK102 en una confirmación 997 puede ser negativo.  
 El elemento de datos AK102 (número de grupo de control) en una confirmación 997 de X12 puede ser un valor negativo. Una confirmación con un elemento de datos AK102 negativo pasará la validación realizada por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], aunque un número de control de grupo negativo no es significativo.  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a>Una recepción CONTRL puede informar de un estado aceptado cuando parte del mensaje se ha rechazado.  
 Una recepción CONTRL (confirmación técnica de EDIFACT) informa de un estado “Rechazado” sólo cuando el mensaje EDIFACT entrante es un duplicado o hay errores en el sobre (por ejemplo, existe un problema con el juego de caracteres). EDIFACT no informa de un estado de intercambio “Aceptado con errores” en la confirmación técnica CONTRL, como hace X12 en el campo TA104 de una confirmación TA1. Si se acepta parte del mensaje EDIFACT, la confirmación técnica CONTRL informará de un estado “Aceptado”. En algunos escenarios, se rechazará parte del mensaje, pero la confirmación CONTRL seguirá informando de un estado “Aceptado”. En tales escenarios, el elemento UCI5 puede informar del error.  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a>Las confirmaciones X12 mostrarán el estado Aceptado para un intercambio conservado (suspender intercambio en caso de error) cuando se produce un error en un encabezado o un finalizador de grupo.  
 Si la entrada procesamiento por lotes de opción para un mensaje está establecido en "Conservar intercambio: suspender intercambio en caso de error" y un campo en el encabezado de grupo o finalizador de X12 no es válida, se notificará el estado como aceptado en TA1 y 997 confirmaciones. El informe de estado de EDI y los detalles del conjunto de transacciones también mostrarán un estado Aceptado. Esto ocurre aunque se suspenda el intercambio y un error en el Visor de eventos indicará que se ha suspendido el intercambio.  
  
 La confirmación TA1 mostrará un estado Aceptado porque está destinada a verificar la corrección del encabezado ISA y el finalizador IEA, pero no la corrección del encabezado GS y el finalizador GE. No obstante, la confirmación 997 también mostrará un estado Aceptado.  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a>Si los grupos de un intercambio tienen el mismo nombre, el informe de estado mostrará dos veces tantas confirmaciones como haya.  
 Si el servidor BizTalk Server procesa un intercambio EDI con varios grupos que tienen el mismo nombre, el informe Intercambio EDI y estado de confirmación correlacionado enumerará dos veces tantas confirmaciones funcionales como se prevean. Por ejemplo, si dos grupos de un intercambio tienen el mismo nombre, el informe de estado enumerará cuatro confirmaciones, en lugar de dos.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos del procesamiento de EDI](../core/known-issues-with-edi-processing.md)   
 [Enviar una confirmación EDI](../core/sending-an-edi-acknowledgment.md)   
 [Procesamiento de confirmaciones recibidas](../core/processing-a-received-acknowledgment.md)   
 [Configurar confirmaciones EDI](../core/configuring-edi-acknowledgments.md)
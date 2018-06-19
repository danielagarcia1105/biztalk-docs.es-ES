---
title: Problemas conocidos de procesamiento por lotes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47246662c5945f8ef09040ec7a8aa49326f59db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204500"
---
# <a name="batching-known-issues"></a>Problemas conocidos de procesamiento por lotes
Esta sección contiene información útil que puede ayudar a evitar errores de procesamiento por lotes.  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a>Segmento de finalizador de campos (FT y BTS) se aceptan incluso si son cadenas de lote  
 HL7 especifica los campos en segmentos FT y BTS de manera diferente en las distintas versiones de HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]define todos los campos como tipo de datos de cadena para evitar la incoherencia.  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>Tipo de datos de una confirmación para un mensaje por lotes  
 En un mensaje de confirmación (ACK) generado en respuesta a un mensaje por lotes, si se desactiva la fragmentación de la entidad de origen y, a continuación, el MSH10 campo (Id. de control de mensajes) será un GUID en lugar de cualquier otro tipo de datos del campo MSH10 en el mensaje de lote.  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a>Explorador de configuración de BTAHL7 y crear lote orquestaciones no son bidireccionales sincronizado  
 Es posible que no se puede ver el estado actual de la programación de control de lote incluso si presiona F5 en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración y podría tener que comprobar ambos [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] herramienta Explorador de configuración y el mantenimiento y seguimiento de actividad (HAT) para el actual estado de la programación de control de lote.  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a>Dos errores de análisis cuando registran los mensajes en lote en / lote Out escenario contiene errores de validación  
 Cuando el primer mensaje en el lote en / escenario de lote Out (varios mensajes por lotes sin encabezados de lote) contiene errores de validación, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registra dos errores en el registro de eventos. El primer error pertenece al primer mensaje en el lote y el segundo error pertenece al resto de los mensajes.  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a>Suscripción mediante el BTS. Propiedad MessageType para el lote en / no se admite el escenario de lote Out con fragmentación deshabilitada  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no admite el uso de suscripción el **BTS. MessageType** propiedad para el lote en / lote escenario con fragmentación deshabilitada como un intercambio que puede constar de varios tipos de mensaje.  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a>Todo el lote suspendido después de un mensaje erróneo en el lote en / escenario de lote  
 Si un mensaje con errores de analizador irrecuperable (por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no analiza MSH 9 o esquema de MSH 12 ni un cuerpo para el mensaje no se pudo cargar) se encuentra en un lote fragmentado en / lote Out escenario, los datos después de que se suspende el mensaje erróneo incluso if el se ha habilitado la compatibilidad de intercambio recuperable.  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a>Lote de mensajes de confirmación se enrutan a la entidad de origen del primer mensaje en el lote en / escenario de lote  
 En procesar por lotes en / lote espera el lote de escenario de confirmaciones se enrutan basándose en la información de entidad de origen del primer mensaje, porque esta funcionalidad se supone que para el origen de lotes de todos los mensajes de entrada y de entidades de destino son los mismos.  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a>Lote de mensajes de confirmación no se enrutan a la entidad de origen cuando bidireccional de recepción se usa el puerto en el lote en / escenario de lote  
 En el caso de solicitudes y respuestas el lote ACK o NACK no se enrutan a la entidad de origen para el escenario BIBO de puerto de recepción.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)
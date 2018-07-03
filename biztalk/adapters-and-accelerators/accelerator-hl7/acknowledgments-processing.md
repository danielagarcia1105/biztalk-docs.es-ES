---
title: Procesamiento de confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969469"
---
# <a name="acknowledgments-processing"></a>Procesamiento de confirmaciones
La especificación de HL7 admite intercambio de mensajes en dos formatos:  
  
- Actualización no solicitado y su confirmación (ACK)  
  
- Consulta y su respuesta  
  
  En respuesta a un mensaje desde una aplicación iniciadora, la aplicación responde responde con un mensaje que incluye datos o una indicación de error. La aplicación iniciadora puede recibir un estado de rechazo de la aplicación de servicio de respuesta que indica que la aplicación de servicio de respuesta no ha recibido el mensaje correctamente. En ambos casos, el proceso de intercambio de mensajes implica dos entidades, las aplicaciones de iniciadores y responde. Cada uno es un remitente y receptor de mensajes. La aplicación iniciadora envía primero y, a continuación, recibe, mientras que el sistema responde recibe y, a continuación, se envía.  
  
## <a name="unsolicited-updates"></a>Actualizaciones no solicitadas  
 Cuando una aplicación de línea de negocio (LOB) publica un mensaje, o inicia a una transferencia de información cuando se produce un evento de desencadenador, se produce una actualización no solicitada. Por ejemplo, cuando los resultados de laboratorio para un paciente están disponibles, puede haber una necesidad de enviar los resultados de laboratorio a otros sistemas. Estas actualizaciones son actualizaciones no solicitadas a la que responde una confirmación.  
  
## <a name="queries"></a>Consultas  
 En el caso de una consulta, una aplicación que requiere información envía una consulta a otra aplicación y la aplicación receptora responde a la consulta. Por ejemplo, una aplicación de farmacia puede enviar un mensaje de solicitud que contiene el número de identificación del paciente en el sistema de entrada de pedido (CPOE) y recibir una respuesta que contiene los datos necesarios para permitir el procesamiento del pedido. Esta transacción solicitante es una consulta y es diferente de una actualización no solicitada. La información que fluye entre las dos aplicaciones se encuentra en la respuesta. La propia respuesta no requiere una confirmación con un cuarto mensaje. Sin embargo, puede modificar esto en algunos entornos responde con una confirmación. Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responde con una confirmación si está configurado así. Para obtener un ejemplo de un intercambio de la consulta/respuesta, consulte [Tutorial de interrogación](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Validación de mensajes](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [Modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [Modelo de procesos de ACK](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)
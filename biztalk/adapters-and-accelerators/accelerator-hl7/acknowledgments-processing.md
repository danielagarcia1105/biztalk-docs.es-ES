---
title: Procesamiento de confirmaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b726eb4698eaa9887703d7df01dc0f6cadf5eefc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-processing"></a>Procesamiento de confirmaciones
La especificación de HL7 admite intercambio de mensajes en dos formatos:  
  
-   Actualización no solicitado y su confirmación (ACK)  
  
-   Consulta y su respuesta  
  
 En respuesta a un mensaje desde una aplicación de inicia, la aplicación responde responde con un mensaje que incluye datos o una indicación de error. La aplicación iniciadora puede recibir un estado de rechazo de la aplicación de servicio de respuesta que indica que la aplicación de servicio de respuesta no ha recibido el mensaje correctamente. En ambos casos, el proceso de intercambio de mensajes implica dos entidades, las aplicaciones de inicia y de que responda. Cada uno de ellos es un remitente y receptor de mensajes. La aplicación iniciadora envía primero y, a continuación, recibe, mientras que el sistema responde recibe y, a continuación, se envía.  
  
## <a name="unsolicited-updates"></a>Actualizaciones no solicitadas  
 Se produce una actualización no solicitada cuando una aplicación de línea de negocio (LOB) publica un mensaje o inicia a una transferencia de información cuando se produce un evento de desencadenador. Por ejemplo, cuando los resultados de laboratorio para un paciente están disponibles, puede haber una necesidad para enviar los resultados de laboratorio a otros sistemas. Estas actualizaciones son actualizaciones no solicitadas a los que responde una confirmación.  
  
## <a name="queries"></a>Consultas  
 En el caso de una consulta, una aplicación que requiere información envía una consulta a otra aplicación y la aplicación receptora responde a la consulta. Por ejemplo, una aplicación farmacia puede enviar un mensaje de solicitud que contiene el número de identificación del paciente en el sistema de entrada de pedido (CPOE) y recibir una respuesta que contiene los datos necesarios para permitir el procesamiento del pedido. Esta transacción solicitante es una consulta y es diferente de una actualización no solicitada. La información que circula entre las dos aplicaciones se encuentra en la respuesta. La propia respuesta no requiere una confirmación con un mensaje cuarto. Sin embargo, puede modificar esto en algunos entornos para responder con una confirmación. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responde con una confirmación si se encuentran configurados. Para obtener un ejemplo de un cambio de la consulta/respuesta, consulte [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Validación de mensajes](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [Modos de mensaje de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [Modelo de proceso de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)
---
title: "Error de configuración. Puerto de envío MDN sincrónico solicitado en HTTP unidireccional | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd38eb3-321f-4738-b35e-390f4f54673e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0a240593aa21b102c401a2a6886ea24baa42c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-synchronous-mdn-requested-on-one-way-http-send-port"></a>Error de configuración. MDN sincrónico solicitado en puerto de envío HTTP unidireccional
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error de configuración. MDN sincrónico solicitado en puerto de envío HTTP unidireccional.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo recibir un MDN sincrónico después de enviar un mensaje AS2 porque el puerto de envío HTTP que envió el mensaje AS2 era un puerto unidireccional. Es necesario un puerto de envío de petición-respuesta bidireccional para procesar un MDN sincrónico devuelto en respuesta a un mensaje AS2 enviado por el puerto. En este caso, el MDN debe devolverse sincrónicamente porque en la configuración para la entidad como receptora de mensaje AS2, la propiedad Solicitar MDN está activada y la propiedad Solicitar MDN asíncrono está desactivada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el puerto de envío que envía el mensaje AS2 para que sea un puerto de envío de petición-respuesta estático, en lugar de un puerto de envío unidireccional. Defina la canalización de recepción del puerto de envío de petición-respuesta para que sea AS2EdiReceive para un intercambio EDI o bien AS2Receive para un intercambio no perteneciente a EDI.
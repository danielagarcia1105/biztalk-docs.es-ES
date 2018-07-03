---
title: Error de configuración. Puerto de recepción MDN sincrónico solicitado en HTTP unidireccional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d0d6e78830c06c11c4c6f54789ba522cfaf366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004733"
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a>Error de configuración. MDN sincrónico solicitado en puerto de recepción HTTP unidireccional
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |       Error de configuración. MDN sincrónico solicitado en puerto de envío HTTP unidireccional.        |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo devolver un MDN sincrónico después de recibir un mensaje AS2 porque el puerto de recepción HTTP que procesó el mensaje AS2 entrante era un puerto unidireccional. Es necesario un puerto de recepción de solicitud-respuesta bidireccional para devolver un MDN sincrónico en respuesta a un mensaje AS2 entrante. En este caso, el MDN debe devolverse sincrónicamente porque el mensaje AS2 incluye el encabezado Disposition-Notification-To o, en la configuración para la entidad como remitente del mensaje AS2, la propiedad Invalidar propiedades de mensajes entrantes está activada, la propiedad Generar MDN está activada y la propiedad Transmitir MDN de forma asíncrona está desactivada.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el puerto de recepción que recibe el mensaje AS2 para que sea un puerto de recepción de solicitud-respuesta, en lugar de un puerto de recepción unidireccional. Defina la canalización de envío de la ubicación de recepción de solicitud-respuesta para que sea AS2EdiSend para un intercambio EDI o bien AS2Send para un intercambio no perteneciente a EDI.
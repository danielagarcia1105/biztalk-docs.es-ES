---
title: Trabajar con errores de mensaje suscripciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a29c6e00ee56c6869b9d9326d045a2ad8fb5fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-failed-message-subscriptions"></a>Trabajar con suscripciones de mensajes con errores
Cuando el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] procesos Desensamblador (analiza y valida) un mensaje, promociona propiedades para ese mensaje. Estas propiedades promocionadas proporcionan información sobre la corrección y validez del mensaje, así como información relacionada con el lote si A4SWIFT recibe el mensaje como parte de un lote de entrada. Para obtener una lista completa de estas propiedades, vea [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
 A diferencia de nativo desensambladores de BizTalk, el Desensamblador de A4SWIFT no suspende un mensaje al procesar produce errores. En su lugar, publica el mensaje error a la base de datos de cuadro de mensajes tal como haría con un mensaje válido. Como resultado, los mensajes con errores pueden realizar detalles del error en la base de datos de cuadro de mensajes. Puede recuperar el mensaje de la base de datos de cuadro de mensajes, administrar y reparar el mensaje e incluso volver a enviar el mensaje en la base de datos de cuadro de mensajes. No puede realizar la mayoría de estas tareas si el mensaje fue realmente *suspendido*.  
  
 Puede identificar un mensaje que ha publicado A4SWIFT para la base de datos de cuadro de mensajes como errores o serán erróneos por sus propiedades promocionadas. Al procesar un mensaje de error, el Desensamblador SWIFT rellena y promueve el **A4SWIFT_Failed** propiedad y uno o más de las demás propiedades siguientes, antes de publicar el mensaje en la base de datos de cuadro de mensajes:  
  
-   **A4SWIFT_ParseErrors** indica el número de errores (por ejemplo, datos mal formados) detectados durante el proceso de análisis.  
  
-   **A4SWIFT_XmlValidationErrors** indica el número de errores de validación de XML (por ejemplo, los datos no válidos o tipo incorrecto con respecto a los esquemas) detectado durante el procesamiento.  
  
-   **A4SWIFT_BreValidationErrors** indica el número de errores de validación de motor de reglas de negocios (BRE) (por ejemplo, los datos que infringen una regla de red SWIFT) detectado durante el procesamiento.  
  
-   **A4SWIFT_Failed** es **true** cuando el recuento de cualquiera de las propiedades anteriores es mayor que cero, o **false** cuando el recuento es igual a cero.  
  
 Estas propiedades forman parte de la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Espacio de nombres Solutions.A4SWIFT.Property. Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
 Para detectar o recuperar mensajes con errores, se necesita para crear expresiones de filtro (suscripciones) para puertos de envío o recepción de una orquestación formas que incluyen algunas de las propiedades enumeradas anteriormente, como **AND** cláusulas de la expresión.  
  
 Por ejemplo, para suscribirse a todos los mensajes error, agregue la siguiente cláusula (como un **AND** cláusula si hay otras cláusulas):  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**  
  
 Para suscribirse a mensajes con errores de análisis solo, sume las cláusulas siguientes:  
  
 **Y** [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**,**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors == 0,**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors == 0;  
  
 Por el contrario, para puertos de envío u orquestaciones diseñadas para controlar sólo los mensajes válidos, incluir "**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **false**"como una cláusula en sus expresiones de filtro.  
  
> [!NOTE]
>  Si se superponen las suscripciones, A4SWIFT cumplirán todas las suscripciones. Es decir, si más de un servicio (puerto de envío u orquestación) tiene un mensaje determinado que cumple las expresiones de filtro, todos los servicios de este tipo recibe el mismo mensaje. Por ejemplo, si un puerto de envío se suscribe a todos los mensajes error y una orquestación se suscribe a solo los mensajes con errores de análisis, las suscripciones se atenderá cuando A4SWIFT encuentra errores de análisis al procesar un mensaje. No olvide eliminar superposiciones no deseadas en las suscripciones a través de servicios.  
  
> [!NOTE]
>  Si A4SWIFT recibe y procesa un mensaje y publica ese mensaje en la base de datos de cuadro de mensajes, pero el mensaje no satisface cualquier suscripción, A4SWIFT suspenderá el mensaje con un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] error que indica una falta de suscriptores. Por ejemplo, si tiene un servicio que se suscribe a todos los mensajes "A4SWIFT_Failed == false", pero no hay servicios suscriben a mensajes donde "A4SWIFT_Failed == true", a continuación, los mensajes que generan errores de análisis o validación realmente se suspende debido a una falta de suscriptores. Este escenario permite realmente imitar tradicional suspensión de mensajes con errores. No olvide suscribirse a todos los mensajes que no desea que se ha suspendido. Vea [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda para obtener más información acerca de las suscripciones de base de datos de cuadro de mensajes, puertos de envío, orquestaciones y expresiones de filtro.  
  
 Esta sección contiene:  
  
-   [Mensajes de error y ErrorCollection objetos](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)
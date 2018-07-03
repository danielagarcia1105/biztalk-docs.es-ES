---
title: Trabajar con error del mensaje suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4cedf2d47c0bbe8e812795ad428a987d4c2014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014221"
---
# <a name="working-with-failed-message-subscriptions"></a>Trabajar con suscripciones de mensajes con errores
Cuando Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] procesos Desensamblador (analiza y valida) un mensaje, promociona las propiedades de ese mensaje. Estas propiedades promocionadas proporcionan información sobre la corrección y la validez del mensaje, así como información relacionada con el lote si A4SWIFT recibió el mensaje como parte de un lote de entrada. Para obtener una lista completa de estas propiedades, vea [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
 A diferencia de desensambladores nativo de BizTalk, el Desensamblador de A4SWIFT no suspender un mensaje cuando genera errores o errores de procesamiento. En su lugar, publica el mensaje con errores en la base de datos de cuadro de mensajes tal como lo haría con un mensaje válido. Como resultado, los mensajes con errores pueden llevar a los detalles del error en la base de datos de cuadro de mensajes. Puede recuperar el mensaje de la base de datos de cuadro de mensajes, administrar y reparar el mensaje e incluso volver a enviar el mensaje nuevo en la base de datos de cuadro de mensajes. No sería capaz de realizar la mayoría de estas tareas si el mensaje fue realmente *suspendido*.  
  
 Puede identificar un mensaje que ha publicado A4SWIFT para la base de datos de cuadro de mensajes como erróneo o con errores por sus propiedades promocionadas. Al procesar un mensaje con errores, el Desensamblador de SWIFT rellena y promueve el **A4SWIFT_Failed** propiedad y uno o más de las demás propiedades siguientes, antes de publicar el mensaje en la base de datos de cuadro de mensajes:  
  
- **A4SWIFT_ParseErrors** indica el número de errores (por ejemplo, los datos con formato incorrecto) detectados durante el procesamiento de análisis.  
  
- **A4SWIFT_XmlValidationErrors** indica el número de errores de validación de XML (por ejemplo, los datos no válidos o un tipo incorrecto en relación con el esquema) detectado durante el procesamiento.  
  
- **A4SWIFT_BreValidationErrors** indica el número de errores de validación de motor de reglas de negocios (BRE) (por ejemplo, los datos que infringen una regla de red SWIFT) detectado durante el procesamiento.  
  
- **A4SWIFT_Failed** es **true** cuando el recuento de cualquiera de las propiedades anteriores es mayor que cero, o **false** cuando el recuento es igual a cero.  
  
  Estas propiedades forman parte de Microsoft. Espacio de nombres Solutions.A4SWIFT.Property. Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
  Para detectar o recuperar los mensajes con errores, deberá crear las expresiones de filtro (suscripciones) para puertos de envío o recepción de formas que incluyen algunas de las propiedades enumeradas anteriormente, una orquestación como **AND** cláusulas de la expresión.  
  
  Por ejemplo, para suscribirse a todos los mensajes con errores, agregue la siguiente cláusula (como un **AND** cláusula si hay otras cláusulas):  
  
  Microsoft. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**  
  
  Para suscribirse a mensajes con errores de análisis solo, sume las cláusulas siguientes:  
  
  **Y** Microsoft. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**,**AND**Microsoft. Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors == 0,**AND**Microsoft. Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors == 0;  
  
  A la inversa, para puertos de envío u orquestaciones que se ha diseñado para controlar los mensajes válidos sólo, incluya "**AND**Microsoft. Solutions.A4SWIFT.Property.A4SWIFT_Failed == **false**"como una cláusula en sus expresiones de filtro.  
  
> [!NOTE]
>  Si se superponen las suscripciones, A4SWIFT, cumplirá con todas las suscripciones. Es decir, si más de un servicio (puerto de envío u orquestación) tiene las expresiones de filtro rellenando un mensaje determinado, todos estos servicios recibirán el mismo mensaje. Por ejemplo, si un puerto de envío se suscribe a todos los mensajes con errores y una orquestación se suscribe a solo los mensajes con errores de análisis, ambas suscripciones se cumplirse cuando A4SWIFT encuentra errores de análisis al procesar un mensaje. No olvide eliminar superposiciones no deseados en las suscripciones a través de servicios.  
> 
> [!NOTE]
>  Si recibe y procesa un mensaje de A4SWIFT y publica ese mensaje en la base de datos de cuadro de mensajes, pero el mensaje no cumple ninguna suscripción, A4SWIFT suspenderá el mensaje con un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] error que indica una falta de suscriptores. Por ejemplo, si tiene un servicio que se suscribe a todos los mensajes "A4SWIFT_Failed == false", pero no hay servicios suscripción a mensajes donde "A4SWIFT_Failed == true", los mensajes que se producirá un error de análisis o validación de hecho se suspende debido a la falta de suscriptores. Este escenario realmente permite imitar tradicional suspensión de mensajes con errores. No olvide suscribirse a todos los mensajes que no desea que se ha suspendido. Consulte la Ayuda de BizTalk Server para obtener más información acerca de las suscripciones de base de datos de cuadro de mensajes, puertos de envío, orquestaciones y las expresiones de filtro.  
  
 Esta sección contiene:  
  
-   [Mensajes de error y objetos ErrorCollection](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)
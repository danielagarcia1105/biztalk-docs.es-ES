---
title: "Cómo enruta los mensajes BTAHL7 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- routing, about routing
- routing, messages
- messages, routing
- BTAHL7, message routing
ms.assetid: 555696c7-6023-44eb-b13d-cf7527bbc92f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61dd223a014ae8ea7de35d8d73f1a7cf7ef35449
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-btahl7-routes-messages"></a>¿Cómo BTAHL7 enruta los mensajes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) aprovecha el capacidades de procesamiento de mensajes [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], pero también se extiende en varias formas que son específicas de los requisitos de mensajería de HL7.  

## <a name="routing-overview"></a>Introducción al enrutamiento

HL7 recibe mensajes desde un sistema de línea de negocio (LOB) y puede recibirlos mediante el adaptador MLLP. El sistema de LOB se conecta al adaptador MLLP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a través de un puerto TCP y, a continuación, envía los mensajes para el adaptador MLLP.

En  **[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores**, la MLLP HL7 recepción esperas de adaptador de transporte para el sistema LOB remoto para conectarse a MLLP. Una vez que se conecta el sistema LOB remoto, el sistema de LOB envía los mensajes con MLLP a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Concretamente: 

1. El sistema LOB remoto se conecta al adaptador MLLP en la variable local [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] con un puerto TCP 
2. La BTA4HL7 ubicación de recepción con adaptador MLLP acepta la conexión 
3. El sistema LOB remoto envía mensajes de uno o más 
4. El sistema LOB remoto se desconecta

En  **[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y versiones más recientes**, se inicia la conexión al sistema de LOB por el adaptador MLLP y, a continuación, reciban los mensajes de inserciones de sistema LOB para la MLLP. En otras palabras, espera a que el sistema LOB remoto para la conexión antes de enviar messagings MLLP. Concretamente: 

1. La variable local [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se conecta al sistema LOB remoto utilizando un puerto TCP 
2. La BTA4HL7 ubicación de recepción con MLLP adaptador inicia la conexión 
3. El sistema LOB remoto envía mensajes de uno o más 
4. El sistema LOB remoto se desconecta 

Para mantener la compatibilidad, puede usar el comportamiento predeterminado original en el sistema LOB remoto inicia las conexiones. Esta opción es configurable en el MLLP propiedades de la ubicación de recepción. 
 
Una vez que se recibe el mensaje HL7, a continuación, se envía a un HL7 canalización de recepción. En esta canalización, el Desensamblador HL7 analizará el mensaje y validará el mensaje según la configuración de definición y validación de esquema adecuado. En este momento, se genera un mensaje de confirmación puede ser de HL7 (éxito o error), según la validez del mensaje y la configuración de confirmación pertinentes. Desde aquí, enviará a la canalización de la instancia de mensaje y la confirmación opcional para la base de datos de cuadro de mensajes para el procesamiento adicional y enrutamiento.  
  
 Una vez que una instancia de mensaje llega en la base de datos de cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] comprueba suscripciones basadas en filtro y enruta el mensaje a uno o varios puertos de envío (posiblemente puertos MLLP) a través de una canalización de envío HL7. La canalización de envío puede validar las instancias de mensaje según la configuración de definición y validación de esquema adecuado. Además de la validación, es posible invalidar ciertos valores de campo en el segmento de MSH del mensaje saliente. Esta capacidad de invalidación es especialmente útil si varios puertos han suscrito a un mensaje y cada aplicación receptora tiene expectativas únicas dentro de los valores de segmento de MSH.  
  
 Por supuesto, todas las demás [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enviar y recibir puerto funcionalidades estarán disponibles para los mensajes HL7, junto con algunas funcionalidades que pueden ser exclusivos para el tipo de puerto seleccionado, como los parámetros de puerto de envío MLLP. Un ejemplo de lo relevante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] capacidades sería la capacidad de aplicar una asignación de transformación a un mensaje saliente.  
  
## <a name="how-routing-works"></a>Cómo funciona el enrutamiento

El [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] rutas HL7 mensaje instancias según las suscripciones que administra la base de datos de cuadro de mensajes. Estas suscripciones utilizar filtros que definen para cada puerto de envío. Filtros de ejemplo podrían incluir enrutamiento basado en tipo de mensaje de Id. o HL7 de puerto de recepción (ADT ^ A03, por ejemplo) y/o el envío de la aplicación (valor MSH3.1).  
  
 Además de configurar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suscripciones, debe configurar algunas opciones específicas de HL7 mensajería que afectarán a instancias de mensajes HL7 como [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta. Esta configuración adicional permite aplicar reglas de validación de HL7 únicas, la generación automática de las confirmaciones y la capacidad de invalidar valores de MSH. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]se aplica esta configuración en el nivel de entidad. Debe definir las partes en el Explorador de BizTalk y realizar la configuración de HL7 relacionada dentro de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] el Explorador de configuración.  
  
 Para aplicar la única configuración de mensajería de HL7 (por ejemplo, validación o las invalidaciones de MSH) a varios puertos de envío que se suscriben a un mensaje, debe crear asociaciones entre entidades y puertos de envío. Configurar las asociaciones de puerto de envío de entidad como propiedades de la entidad en el Explorador de BizTalk.  
  
 Si no se necesita para HL7 de enrutar mensajes a varios puertos de envío o aplicar la configuración de procesamiento de HL7 único a varios puertos de envío, puede eliminar el paso de asociar usuarios a los puertos de envío. En este caso, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] asocia la entidad con su configuración de mensajería HL7 a través del campo de aplicación receptora del mensaje HL7 (MSH 3.1). Esta situación es más probable que se produzca en un interrogative HL7 (solicitud-respuesta) intercambio de mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)
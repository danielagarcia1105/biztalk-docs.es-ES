---
title: Cómo los mensajes en Btahl7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- routing, about routing
- routing, messages
- messages, routing
- BTAHL7, message routing
ms.assetid: 555696c7-6023-44eb-b13d-cf7527bbc92f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c64cd0620dacf835d3765510ea74c2a8cc80c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999293"
---
# <a name="how-btahl7-routes-messages"></a>Cómo los mensajes en Btahl7
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) aprovecha las capacidades de Microsoft de procesamiento de mensajes [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], pero también se extiende en varias formas que son específicas de los requisitos de mensajería de HL7.  

## <a name="routing-overview"></a>Introducción al enrutamiento

HL7 recibe mensajes desde un sistema de línea de negocio (LOB) y puede recibirlos mediante el adaptador de MLLP. El sistema de LOB se conecta al adaptador MLLP en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a través de un puerto TCP y, a continuación, envía mensajes al adaptador de MLLP.

En  **[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores**, el HL7 MLLP recibir esperas del adaptador de transporte para el sistema LOB remoto para conectarse a MLLP. Una vez que se conecta el sistema LOB remoto, el sistema de LOB envía los mensajes mediante MLLP a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Concretamente: 

1. El sistema LOB remoto se conecta al adaptador de MLLP local [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] con un puerto TCP 
2. El BTA4HL7 ubicación de recepción con el adaptador de MLLP acepta la conexión 
3. El sistema LOB remoto proporciona uno o más mensajes 
4. Desconecta el sistema LOB remoto

En  **[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y las versiones más recientes**, se inicia la conexión al sistema de LOB mediante el adaptador de MLLP y, a continuación, reciben los mensajes de inserciones del sistema LOB para el MLLP. En otras palabras, el sistema LOB remoto espera para la conexión antes de enviar messagings MLLP. Concretamente: 

1. Local [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se conecta al sistema de LOB remoto usa un puerto TCP 
2. El BTA4HL7 ubicación de recepción con MLLP adaptador inicia la conexión 
3. El sistema LOB remoto proporciona uno o más mensajes 
4. Desconecta el sistema LOB remoto 

Para mantener la compatibilidad, puede usar el comportamiento predeterminado original donde el sistema LOB remoto inicia las conexiones. Esta opción es configurable en lo MLLP propiedades de la ubicación de recepción. 
 
Una vez que se recibe el mensaje de HL7, a continuación, se envía a un HL7 canalización de recepción. Dentro de esta canalización, el Desensamblador HL7 analizará el mensaje y validará el mensaje según la configuración de definición y la validación de esquema adecuado. En este momento, se genera un mensaje de confirmación puede ser de HL7 (éxito o error), según la validez del mensaje y la configuración de la confirmación pertinente. Desde aquí, la canalización enviará la instancia de mensaje y la confirmación opcional para la base de datos de cuadro de mensajes para el procesamiento adicional y enrutamiento.  
  
 Una vez que llega a una instancia de mensaje de la base de datos de cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] comprueba las suscripciones basadas en filtro y enruta el mensaje a uno o más puertos de envío (posiblemente puertos MLLP) a través de una canalización de envío de HL7. La canalización de envío puede validar las instancias de mensaje según la configuración de definición y la validación de esquema adecuado. Además de la validación, es posible invalidar determinados valores de campo en el segmento de MSH del mensaje saliente. Esta capacidad de invalidación es especialmente útil si varios puertos han suscrito a un mensaje y cada aplicación receptora tiene expectativas únicas dentro de los valores de segmento de MSH.  
  
 Por supuesto, todas las demás [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de envío y puerto de recepción capacidades estarán disponibles para los mensajes de HL7, junto con algunas funcionalidades que pueden ser únicos para el tipo de puerto seleccionado, como los parámetros de puerto de envío MLLP. Un ejemplo de la correspondiente [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] capacidades sería la capacidad de aplicar una asignación de transformación a un mensaje saliente.  
  
## <a name="how-routing-works"></a>Cómo funciona el enrutamiento

El [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] rutas HL7 instancias según las suscripciones que administra la base de datos del mensaje. Estas suscripciones utilizar filtros que defina para cada puerto de envío. Filtros de ejemplo podrían incluir el enrutamiento basado en el tipo de mensaje de identificador o HL7 puerto de recepción (ADT ^ A03, por ejemplo) o el envío de aplicación (valor MSH3.1).  
  
 Además de configurar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suscripciones, deberá configurar algunas opciones de mensajería de HL7 específicas que afectan a las instancias de mensajes de HL7 como [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta. Esta configuración adicional le permite aplicar reglas de validación de HL7 únicas, la generación automática de las confirmaciones y la capacidad de invalidar los valores de MSH. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] se aplica esta configuración en el nivel de entidad. Debe definir las partes en el Explorador de BizTalk y realizar la configuración de HL7 relacionada dentro de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Explorador de configuración.  
  
 Para aplicar la única configuración de mensajería de HL7 (por ejemplo, validación o las invalidaciones de MSH) a varios puertos de envío que se suscriben a un mensaje, deberá crear asociaciones entre entidades y puertos de envío. Configurar las asociaciones de puerto de envío de entidad como propiedades de entidad en el Explorador de BizTalk.  
  
 Si no necesita HL7 de enrutar mensajes a varios puertos de envío, o aplicar la configuración de procesamiento de HL7 único a varios puertos de envío, puede eliminar el paso de asociar entidades a puertos de envío. En este caso, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] asocia la entidad con su configuración de mensajería de HL7 a través del campo de aplicación receptora del mensaje de HL7 (MSH 3.1). Esta situación es más probable que se produzca en un interrogative HL7 (solicitud/respuesta) intercambio de mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Validación de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)
---
title: Qué agrega el Acelerador de BizTalk para HL7 a BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, documents
- BTAHL7, batching
- messages, acknowledgements
- messages, auditing
- Configuration Explorer
- BTAHL7, message validation
- BTAHL7, Configuration Explorer
- messages, processing
- BTAHL7, BizTalk Server
- BTAHL7, message processing
- auditing, messages
- BTAHL7, auditing
- validating, messages
- acknowledgements, messages
- BTAHL7, logging
- BizTalk Server, BTAHL7
- messages, validating
- logging
- BTAHL7, acknowledgements
- errors, logging
ms.assetid: 862e9f26-588a-4e91-8ebc-f53aab6f46c2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ab7cd2d5abe126cc246be678c192c037ee48c90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980061"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>Qué agrega el Acelerador de BizTalk para HL7 a BizTalk Server
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se basa un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sistema de integración en un sistema de integración de atención médica. Agrega una funcionalidad que requieren atención médica.  
  
 Instalar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] en la parte superior de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] agrega funcionalidad al núcleo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor. Agrega a las características, herramientas y utilidades que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona. También agrega interfaces de programación de aplicaciones (API) a lo que el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona SDK.  
  
## <a name="btahl72x-message-processing"></a>Procesamiento de mensajes BTAHL72X  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Agrega un número de características y herramientas que permiten al sistema procesar los mensajes de HL7 de forma nativa, sin necesidad de personalización. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] incluye todas las especificaciones de documentos, aplicaciones y componentes que necesita para desarrollar e implementar para procesar las transacciones completa gama de HL7 específicos. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] admite [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X esquemas de archivo sin formato. La siguiente [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes realizan [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X el procesamiento de mensajes:  
  
- HL7 Desensamblador y ensamblador que permiten al sistema de analizar y serializar los mensajes de HL7 de forma nativa. El Desensamblador y ensamblador forman parte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización, que realiza una serie de pasos de procesamiento en los mensajes, incluida la conversión a o desde XML, descodificar o codificar y validación de mensajes.  
  
- Un adaptador de protocolo de nivel inferior mínimo (MLLP) que permite al sistema recibir o enviar mensajes de HL7, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] transporta normalmente mediante el protocolo MLLP. El adaptador de MLLP garantiza que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pueden interoperar con aplicaciones de mensajes basadas en HL7.  
  
- Esquemas de mensaje HL7 que permiten al sistema recibir mensajes con codificación HL7.  
  
## <a name="btahl72xml-message-processing"></a>Procesamiento de mensajes de BTAHL72XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Agrega un número de características y herramientas que permiten al sistema para procesar los mensajes XML. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Convierte los mensajes de HL7 en formato XML con el fin de habilitar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], que utiliza internamente, el XML para realizar operaciones en los mensajes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza la conversión a XML sólo para HL7 V2. Los mensajes de X, ya que se encuentran en forma nativa de archivo sin formato. No lleva a cabo la conversión para los mensajes XML 2., que están en formato XML. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] analiza y valida estos mensajes sin conversión.  
  
 Los esquemas de mensaje XML admitidos son el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML los esquemas generados por la organización de HL7 para la versión 2 de HL7. Versión XML y el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X esquemas que se usan para HL7 V2. Versión de X mensajes (en formato de archivo sin formato). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] incluye las especificaciones de documentos, aplicaciones y componentes que necesita para desarrollar e implementar para procesar toda la gama de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML transacciones. La siguiente [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes realizan [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML procesamiento de mensajes:  
  
- Desensamblador XML y ensamblador que permiten al sistema analizar y serializar los mensajes XML que corresponden a los mensajes de HL7. El desensamblador XML y ensamblador incluyen mejoras más allá de la funcionalidad de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML Desensamblador y ensamblador, incluida la validación automática confirmación y el mensaje.  
  
- Esquemas XML de HL7 compatible que permiten al sistema recibir mensajes de HL7 (ambos V2. X y V2. Mensajes XML). El sistema convierte V2. X mensajes en mensajes XML (V2. Los mensajes XML ya están en XML) y, a continuación, los envía a otro sistema que sea compatible con XML. De forma similar, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede recibir mensajes XML y, a continuación, convertirlos en HL7 para enviar. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] transforma los datos de HL7 específicos desde o a otro formato mediante el uso de las especificaciones de documentos basada en XML, junto con el analizador de HL7, mapas y otras [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas que llamen los esquemas y asignaciones. Por ejemplo, podría recibir un intercambio en formato estándar de HL7 V2.0 o versión 2.5 y transformar los datos en otro formato que puede usar una aplicación médica existente.  
  
## <a name="validation"></a>Validación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza la validación de HL7 V2. Los mensajes de X que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no se puede realizar. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza automáticamente una validación sintáctica y esquemática del encabezado de un mensaje de HL7 y automáticamente lleva a cabo alguna validación estructural del cuerpo de un mensaje de HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] realiza la validación de esquema del cuerpo de un mensaje de HL7, si habilita esta característica (consulte [configuración de la validación](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)).  
  
 La validación del cuerpo de un mensaje con codificación de HL7 incluye el esquema, formato de datos, algunos encabezado y los campos del cuerpo y los valores de enumeración. La validación de mensajes XML de 2. incluye la validación con respecto a su esquema, que es la validación de XML estándar. Para obtener más información, consulte [procesamiento de archivos planos BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) y [procesamiento de BTAHL72XML](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md).  
  
## <a name="auto-acknowledgment"></a>Confirmación automática  
 Para garantizar la confiabilidad del sistema de mensajería, es posible que desee requieren confirmaciones (ACK) a HL7 para los mensajes que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera automáticamente en función de los valores de configuración.  
  
 Modo original confirmaciones confirmación la validación del encabezado del mensaje y cuerpo. En el modo mejorado, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera dos tipos de mensajes de confirmación: una confirmación que envía en la validación del encabezado accept y una aplicación de confirmación que envía en la validación del mensaje completo. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera una confirmación diferida por la aplicación de línea de negocio que recibe un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] facilita el procesamiento de confirmación que admiten los transportes de mensajes bidireccional.  
  
## <a name="batching"></a>Procesar por lotes  
 Puede procesar documentos en modo por lotes, lo que evita la sobrecarga de procesamiento. También puede procesar por lotes las respuestas a los procesos por lotes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] permite tres tipos de procesamiento por lotes para HL7 2.X mensajes:  
  
- Entrada de procesamiento por lotes, en el que el sistema recibe los mensajes como un lote y, a continuación, fragmenta en mensajes individuales.  
  
- Procesar por lotes en o por lotes, en el que el sistema recibe y envía mensajes como un lote.  
  
- Creación de procesamiento por lotes, en el que el sistema envía un lote de mensajes que recibe como mensajes individuales.  
  
  > [!NOTE]
  >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no proporciona capacidades de procesamiento por lotes para la versión 2. Mensajes XML.  
  
## <a name="logging"></a>Registro  
 Para mejorar la solución de problemas, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] habilita los informes de errores o advertencias que se señaliza mediante los componentes del sistema. Puede filtrar estos eventos, almacenarlos en cualquiera de los tres almacenes del registro ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de sucesos de WMI, o un [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] almacén del registro), o personalícelos utilizando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK.  
  
## <a name="configuration-explorer"></a>Explorador de configuración  
 Puede configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] partes, lotes, confirmaciones y almacenar en el registro de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración, una herramienta administrativa que se agregan a las herramientas que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona. Esta herramienta también le permite iniciar en el nivel de entidad de procesamiento por lotes. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK le permite personalizar esta configuración mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo resuelve BizTalk Server la necesidad empresarial](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)
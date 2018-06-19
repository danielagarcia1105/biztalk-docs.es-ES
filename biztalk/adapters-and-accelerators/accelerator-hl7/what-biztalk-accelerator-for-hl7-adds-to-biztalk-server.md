---
title: ¿Qué Acelerador de BizTalk para HL7 agrega a BizTalk Server | Documentos de Microsoft
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
ms.openlocfilehash: 7b9e9d1277c5d037a42fd85ca48ec13c8f1893a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209268"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>¿Qué Acelerador de BizTalk para HL7 agrega a BizTalk Server
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sistema de integración en un sistema de integración de atención médica. Agrega la funcionalidad que requieren atención sanitaria organizaciones.  
  
 Instalar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sobre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]agrega funcionalidad al núcleo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor. Agrega a las características, herramientas y utilidades que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona. También agrega interfaces de programación de aplicaciones (API) a lo que el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK proporciona.  
  
## <a name="btahl72x-message-processing"></a>Procesamiento de mensajes de BTAHL72X  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Agrega una serie de características y herramientas que permiten que el sistema para procesar mensajes HL7 de forma nativa, sin necesidad de personalización. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]incluye todas las especificaciones de documentos, aplicaciones y componentes que se necesitan para desarrollar e implementar para procesar las transacciones completa intervalo de HL7 específica. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]admite [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X esquemas de archivo sin formato. El siguiente [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes realizan [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X el procesamiento de mensajes:  
  
-   Desensamblador de HL7 y de ensamblador que permiten al sistema analizar y serializar mensajes HL7 de forma nativa. El Desensamblador y ensamblador forman parte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización, que lleva a cabo una serie de pasos de procesamiento en mensajes, incluida la conversión a o desde XML, descodificación o codificación y validación de mensajes.  
  
-   Un adaptador de protocolo de nivel inferior mínimo (MLLP) que permite al sistema recibir o enviar mensajes basados en HL7, que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] normalmente transporta mediante el protocolo MLLP. El adaptador MLLP garantiza que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pueden interoperar con aplicaciones de mensajes basadas en HL7.  
  
-   Esquemas de mensaje HL7 que permiten al sistema recibir mensajes con codificación HL7.  
  
## <a name="btahl72xml-message-processing"></a>Procesamiento de mensajes de BTAHL72XML  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Agrega una serie de características y herramientas que permiten al sistema para procesar los mensajes XML. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Convierte HL7 mensajes en formato XML para permitir que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], que utiliza XML internamente, para realizar operaciones en los mensajes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]realiza la conversión a XML solo para HL7 V2. Mensajes de X, ya que son de forma nativa en planos, formato de archivo. No lleva a cabo la conversión para los mensajes XML 2., que están en formato XML. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]analiza y valida estos mensajes sin conversión.  
  
 Los esquemas de mensaje XML admitidos son el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]esquemas 2XML generados por la organización de HL7 para el V2 HL7. Versión XML y el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X esquemas que se utiliza para HL7 V2. Versión de X mensajes (en formato de archivo sin formato). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]incluye las especificaciones de documentos, aplicaciones y componentes que se necesitan para desarrollar e implementar para procesar todo el rango de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML transacciones. El siguiente [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes realizan [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML el procesamiento de mensajes:  
  
-   Desensamblador XML y ensamblador que permiten al sistema analizar y serializar los mensajes XML correspondientes a mensajes HL7. El desensamblador XML y ensamblador incluyen mejoras adicionales a la función de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML Desensamblador y ensamblador, incluida la validación de confirmación automática y el mensaje.  
  
-   Esquemas XML de HL7 compatible que permiten al sistema recibir mensajes HL7 (ambos V2. X y V2. Mensajes XML). El sistema convierte V2. X mensajes en mensajes XML (V2. Los mensajes XML ya están en XML) y, a continuación, los envía a otro sistema que sea compatible con XML. De forma similar, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede recibir los mensajes XML y, a continuación, convertirlos en HL7 para enviar. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]transforma los datos de HL7 específica desde o a otro formato mediante el uso de las especificaciones de documentos basada en XML, junto con el analizador de HL7, mapas y otros [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas que llamen los esquemas y asignaciones. Por ejemplo, podría recibir un intercambio estándar HL7 V2.0 en formato de o versión 2.5 y transformar los datos en otro formato que puede usar una aplicación de ejemplo medical existente.  
  
## <a name="validation"></a>Validación  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]realiza la validación de HL7 V2. X de los mensajes que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no se puede realizar. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]realiza automáticamente la validación sintáctica y esquemática del encabezado de un mensaje HL7 y automáticamente realiza alguna validación estructural del cuerpo de un mensaje HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]realiza la validación de esquema del cuerpo de un mensaje HL7, si habilita esta característica (vea [configuración de la validación](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)).  
  
 La validación del cuerpo de un mensaje con codificación HL7 incluye el esquema, formato de datos, algunos encabezado y cuerpo campos y valores de enumeración. La validación de mensajes XML de 2. incluye la validación con respecto a su esquema, que es la validación de XML estándar. Para obtener más información, consulte [procesamiento de archivo sin formato BTAHL72X](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) y [BTAHL72XML procesamiento](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md).  
  
## <a name="auto-acknowledgment"></a>Confirmación automática  
 Para garantizar la confiabilidad del sistema de mensajería, puede que desee requerir que los mensajes de confirmaciones (ACK) para HL7 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera automáticamente basándose en los valores de configuración.  
  
 Confirmaciones de modo original confirmación la validación del encabezado del mensaje y cuerpo. En modo mejorado, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera dos tipos de mensajes de confirmación: una confirmación que envía en la validación del encabezado de aceptación y una aplicación ACK que envía en la validación del mensaje completo. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]genera una confirmación diferida por la aplicación de línea de negocio que recibe un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]facilita la compatibilidad con transportes de mensajes bidireccional de procesamiento de confirmación.  
  
## <a name="batching"></a>Procesar por lotes  
 Puede procesar documentos en modo por lotes, lo que evita la sobrecarga de procesamiento. También puede procesar por lotes las respuestas a los procesos por lotes. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]permite realizar tres tipos de procesamiento por lotes para HL7 2.X mensajes:  
  
-   Entrada de procesamiento por lotes, en el que el sistema recibe los mensajes como un lote y, a continuación, los fragmentos en mensajes individuales.  
  
-   Procesar por lotes en / por lotes, en el que el sistema recibe y envía los mensajes como un lote.  
  
-   Cree el procesamiento por lotes, en el que el sistema envía un lote de mensajes que recibe como mensajes individuales.  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no proporciona capacidades de procesamiento por lotes para V2. Mensajes XML.  
  
## <a name="logging"></a>Registro  
 Para mejorar la solución de problemas, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] permite la creación de informes de errores o advertencias señaladas por componentes del sistema. Puede filtrar estos eventos, almacenarlos en cualquiera de los tres almacenes de registro ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] registro de eventos de WMI, o un [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] almacén del registro), o personalizar mediante la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK.  
  
## <a name="configuration-explorer"></a>Explorador de configuración  
 Puede configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] entidades, lotes, confirmaciones y el registro de almacenar en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración, una herramienta administrativa que se agregan a las herramientas que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona. Esta herramienta también le permite iniciar en el nivel de entidad de procesamiento por lotes. El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK permite personalizar esta configuración mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server resuelve la necesidad empresarial](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)
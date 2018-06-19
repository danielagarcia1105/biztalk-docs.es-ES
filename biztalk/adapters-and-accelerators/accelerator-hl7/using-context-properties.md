---
title: Usar propiedades de contexto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, context properties
- messages, promoted properties
- promoted properties, context properties
- context properties, messages
ms.assetid: 306127a9-df03-4aaf-8dd8-76df51eb193d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a3fad82b8d537fcc017dfed175c5348cc1529d3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006757"
---
# <a name="using-context-properties"></a>Usar propiedades de contexto
El Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) motor de mensajería y sus componentes utilizan internamente las propiedades de contexto. No se recomienda cambiar los valores establecidos por el motor para algunas propiedades de contexto, porque puede afectar a la lógica de ejecución del motor de. Sin embargo, puede cambiar un gran número de propiedades no definidas por el motor. Puede usar las propiedades de contexto para la creación de expresiones de filtro de puertos de envío (para obtener más información, consulte [expresiones de filtro de la configuración de puertos de envío](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)). También puede utilizar las propiedades de contexto en expresiones de filtro de orquestaciones. Las propiedades están disponibles para las expresiones de filtro siempre y cuando un proyecto tiene una referencia a los esquemas de propiedades globales (que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] crea cuando se usa una de las plantillas comunes).  
  
 En la tabla siguiente contiene una lista de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] propiedades de contexto que utiliza el motor de mensajería del mensaje. El motor utiliza muchas de estas propiedades para el enrutamiento. El serializador utiliza las demás para su procesamiento. Estas propiedades tienen el prefijo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].  
  
 Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] propiedades de contexto (los identificados en las expresiones de filtro con un prefijo BTS), consulte "Propiedades de contexto de mensaje" en la Ayuda de BizTalk Server. **BTS. SchemaStrongName** y **BTS. MessageType** son dos propiedades que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor utiliza.  
  
 En la tabla siguiente, el se promueve y no se requiere las columnas tienen los siguientes efectos:  
  
-   Cuando IsPromoted es "N", [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] escribe el valor en el contexto, en lugar de que se va a promocionar.  
  
-   Cuando IsRequired es "N" para tipos booleanos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] escribe el valor solo si es true.  
  
-   Cuando IsRequired es "N" para los tipos de cadena, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] escribe el valor si no está en blanco o si existe un valor predeterminado.  
  
|Nombre de propiedad|Se promueve|Es necesario|Notas|  
|-------------------|-----------------|-----------------|-----------|  
|BatchDateTime|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageType|S|S|El serializador utiliza esta propiedad para distinguir los mensajes únicos y por lotes. El Desensamblador de HL7 establece solo para los mensajes por lotes. La propiedad indica si el mensaje es un único mensaje, un mensaje por lotes entrantes o un mensaje de lotes de salida. Si el serializador no lo encuentra, se supone que el mensaje es un único mensaje.|  
|FHS10|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|FHS3|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|FHS4|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|FHS5|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|FHS6|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|FileDateTime|S|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|Falta LastSegmentDelimiter|N|N|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]promueve esta propiedad cuando procesa un mensaje por lotes.|  
|MessageClass|S|S|Contiene **MessageClass2X** o **MessageClass2Xml** para distinguir entre las dos clases de mensajes.|  
|MSA1|S|S|Se aplica solo a los mensajes de confirmación.|  
|MSH1|N|S|El campo que contiene el separador de campos. El serializador utiliza esta propiedad.|  
|MSH2|N|S|El serializador utiliza esta propiedad. El campo que contiene los caracteres de codificación (separador de componentes, separador de repeticiones, carácter de escape y separador subcomponente).|  
|MSH3_1|S|N|El primer componente del campo de la aplicación de envío.|  
|MSH3_2|S|N|El segundo componente de campo de la aplicación de envío.|  
|MSH3_3|S|N|El tercer componente de campo de la aplicación de envío.|  
|MSH5_1|S|N|El primer componente del campo de la aplicación receptora.|  
|MSH5_2|S|N|El segundo componente de campo de la aplicación receptora.|  
|MSH5_3|S|N|El tercer componente de campo de la aplicación receptora.|  
|ParseError|S|S|Indica que se produjo un error durante el análisis.|  
|SegmentDelimiter2Char|N|N|El carácter que delimita los segmentos.|  
|ToBeBatched|S|N|Cuando se establece en false, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no almacena en búfer el mensaje pueda procesarse por lotes más adelante; en caso contrario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía el mensaje como parte de un lote.|  
|ZPartPresent|S|N|Indica si se encuentra un segmento de Z no declarado.|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Establecimiento de expresiones de filtro en puertos de envío](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)
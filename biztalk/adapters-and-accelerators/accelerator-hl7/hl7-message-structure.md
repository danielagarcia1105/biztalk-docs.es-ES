---
title: HL7 Estructura de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- trigger events
- messages, trigger events
- segments, messages
- messages, message structure
ms.assetid: 4dbef56d-97ae-466d-bc8a-dc96c40896f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a298a21b7df2605cdb8dc181898808c94cf40b33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996957"
---
# <a name="hl7-message-structure"></a>HL7 Estructura de mensajes
Un mensaje de HL7 es una estructura jerárquica asociada a un evento de desencadenador. El estándar HL7 define los eventos de desencadenador como "un evento en el mundo real de sanidad (es) crea la necesidad de los datos fluyan entre los sistemas". Cada evento de desencadenador está asociado a un mensaje abstracto que define el tipo de datos que el mensaje debe admitir el evento de desencadenador. El mensaje abstracto es una colección de segmentos e incluye las reglas de inclusión para dichos segmentos y de repetición. En la tabla siguiente se muestra un ejemplo de un mensaje abstracto asociado al evento de desencadenador A04: registrar paciente.  
  
|Evento de desencadenador|Mensaje abstracto|  
|-------------------|----------------------|  
|ADT ^ A04 ^ ADT_A01|Admisión, descarga y transferencia|  
|MSH|Encabezado de mensaje|  
|EVN|Tipo de evento|  
|PID|Identificación de pacientes|  
|[PD1]|Datos demográficos adicionales|  
|[{ROL}]|Rol|  
|[{VM NK1}]|Siguiente de entidades familiar más / asociadas|  
|PV1|Visite paciente|  
|[PV2]|Visite paciente - información adicional|  
|[{ROL}]|Rol|  
|[{DB1}]|Información de discapacidad|  
|[{OBX}]|Observación o resultado|  
|[{AL1}]|Información de alergias|  
|[{DG1}]|Información de diagnóstico|  
|[DRG]|Grupo relacionado de diagnóstico|  
|[{||  
|PR1|Procedimientos|  
|[{ROL}]|Rol|  
|}]||  
|[{GT1}]|Fianza|  
|[{||  
|IN1|Seguros|  
|ENTRADA [2]|Información adicional de seguros|  
|[{IN3}]|Información adicional seguros - Cert.|  
|[{ROL}]|Rol|  
|}]||  
|[ACC]|Información sobre los accidentes|  
|[UB1]|Información de factura universal|  
|[UB2]|Información de 92 factura universal|  
|[PDA]|Autopsia y la muerte del paciente|  
  
 Los corchetes anteriores "[", "]" indican que un segmento o el grupo de segmentos es opcional, mientras que las llaves "{", "}" indican el segmento o el grupo de segmentos de repetición.  
  
 Un segmento es un grupo de campos de cada uno de los cuales se ajusta a un tipo de datos determinado. Los campos pueden tener una estructura simple o compleja. Están formados por componentes según las reglas definidas en su definición de tipo de datos. Para admitir los tipos de datos más complejos, algunos componentes pueden constar de subcomponentes.  
  
> [!NOTE]
>  El hecho de que usa la codificación de mensajes de HL7 especifican delimitadores limita la capacidad de un desarrollador para introducir nuevas formas de subdividir los datos. No puede haber ningún subcomponente secundarias, puesto que esto requeriría la invención de un nuevo tipo de delimitador.  
  
 Las especificaciones de HL7 primera no definió el mensaje abstracto. El mensaje abstracto es el patrón de segmentos asociada a un evento de desencadenador. De forma similar, los mensajes de HL7 contienen colecciones de segmentos que repita juntos o grupos de segmento. Las especificaciones de HL7 primera no definió los grupos de segmentos. A partir de V2.3.1 y continuar en las versiones posteriores, esto puede cambiar debido a la necesidad de admitir la codificación XML. Por ejemplo, en la tabla de eventos de desencadenador anterior, el nombre de la estructura del mensaje es "ADT_A01". Este es el mismo patrón de segmentos usados para admitir A01 – admitir paciente. Para mayor comodidad, los nombres de las estructuras de mensajes corresponden a la primera (en términos de selección de ubicación en el documento HL7) desencadena el evento que los usa. De forma similar, el grupo de segmentos en la tabla de eventos de desencadenador anterior que comienza por IN1, incluidos entrada 2 IN3 y ROL, se repite como un grupo. Su nombre, empezando por la versión 2.5 es el grupo "Seguros".  
  
 En la versión 2, las reglas de compatibilidad entre versiones admiten la evolución de las interfaces al requerir que las versiones posteriores del estándar no incluyen las estructuras que invalidan las versiones anteriores. Esto requiere que no se quitan de un evento de desencadenador y que no use un evento de desencadenador para un propósito diferente o con un mensaje diferente abstracto que originalmente se diseñó. Para los mensajes abstractos, esto implica que no se puede quitar un segmento de un mensaje, ni puede realizar un segmento obligatorio opcional o una repetición segmento no repetitivo. Si agrega un segmento, debe hacerlo al final de un mensaje o al final de un grupo de repetición dentro de un mensaje.  
  
 Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:  
  
-   Compatibilidad con todos los eventos de desencadenador y estructuras de mensajes a partir de V2.1 y continuando hasta la versión 2.5.  
  
-   Compatibilidad de localización a través de agregar segmentos y adaptar el segmento opcionalmente y repetición.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
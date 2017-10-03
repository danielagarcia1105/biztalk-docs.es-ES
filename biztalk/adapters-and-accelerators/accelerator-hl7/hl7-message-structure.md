---
title: HL7 Estructura de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- trigger events
- messages, trigger events
- segments, messages
- messages, message structure
ms.assetid: 4dbef56d-97ae-466d-bc8a-dc96c40896f6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e705d3c8a72b5ca1072157a227bf6f218035d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-message-structure"></a>HL7 Estructura de los mensajes
Un mensaje de HL7 es una estructura jerárquica asociada a un evento de desencadenador. El estándar HL7 define los eventos de desencadenador como "un evento en el mundo real de atención médica (es) crea la necesidad de los datos fluyan entre los sistemas". Cada evento de desencadenador está asociado a un mensaje abstracto que define el tipo de datos que el mensaje debe admitir el evento de desencadenador. El mensaje abstracto es una colección de segmentos e incluye las reglas de inclusión para dichos segmentos y de repetición. En la tabla siguiente se muestra un ejemplo de un mensaje abstracto asociado al evento de desencadenador A04: registrar paciente.  
  
|Evento de desencadenador|Mensaje abstracta|  
|-------------------|----------------------|  
|ADT ^ A04 ^ ADT_A01|Admisión y descarga, transferencia|  
|MSH|Encabezado de mensaje|  
|EVN|Tipo de evento|  
|PID|Identificación de pacientes|  
|[PD1]|Datos demográficos adicionales|  
|[{ROL}]|Rol|  
|[{NK1}]|Siguiente de entidades familiar más / asociados|  
|PV1|Visite paciente|  
|[PV2]|Visite paciente - información adicional|  
|[{ROL}]|Rol|  
|[{DB1}]|Información de discapacidad|  
|[{OBX}]|Observación o resultado|  
|[{AL1}]|Información de alergia|  
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
|[COM]|Información de accidente|  
|[UB1]|Información de facturación universal|  
|[UB2]|Información de 92 factura universal|  
|[PDA]|Autopsia y la muerte del paciente|  
  
 Los corchetes anteriores "[", "]" indican que un segmento o el grupo de segmentos es opcional, mientras llaves "{", "}" indican el segmento o el grupo de segmentos de repetición.  
  
 Un segmento es un grupo de campos de cada uno de los cuales se ajusta a un tipo de datos determinado. Los campos pueden tener una estructura simple o compleja. Están formados por componentes según las reglas definidas en su definición de tipo de datos. Para admitir los tipos de datos más complejos, algunos componentes pueden constar de subcomponentes.  
  
> [!NOTE]
>  El hecho de que usa la codificación de mensajes de HL7 especificado delimitadores limita la capacidad de un desarrollador para introducir nuevas formas de subdividir los datos. No puede haber ningún subcomponente subcarpetas, ya que esto requeriría invención de un nuevo tipo de delimitador.  
  
 Las especificaciones de HL7 primer no definió el mensaje abstracto. El mensaje abstracto es el patrón de segmentos asociado a un evento de desencadenador. Del mismo modo, los mensajes HL7 contienen colecciones de segmentos que repiten juntos o grupos de segmento. Las especificaciones de HL7 primer no definió grupos de segmentos. A partir de V2.3.1 y continuar en las versiones posteriores, esto cambia debido a la necesidad de admitir la codificación XML. Por ejemplo, en la tabla de eventos de desencadenador anterior, el nombre de la estructura del mensaje es "ADT_A01". Este es el mismo patrón de segmentos que se usa para admitir A01: admitir paciente. Para mayor comodidad, los nombres de las estructuras de mensaje corresponden a la primera (en términos de selección de ubicación dentro del documento HL7) desencadenar eventos que los usa. De igual forma, el grupo de segmentos en la tabla de eventos de desencadenador anterior que comienza por IN1, incluida la entrada de 2 y IN3, ROL, se repite como un grupo. Su nombre, a partir de la versión 2.5 es grupo de "Seguros".  
  
 En la versión 2, las reglas de compatibilidad entre versiones admiten la evolución de interfaces exigiendo que las versiones posteriores del estándar no incluyen las estructuras que invalidan las versiones anteriores. Esto requiere que no se quitan de un evento de desencadenador y que no usa un evento de desencadenador para un propósito diferente o con un mensaje abstracto diferente a lo esperado originalmente. Para los mensajes abstractos, esto implica que no se puede quitar un segmento de un mensaje, ni puede hacer que un segmento obligatorio opcional o una repetición segmento no repetitivo. Si agrega un segmento, debe hacerlo al final de un mensaje o al final de un grupo de repetición dentro de un mensaje.  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:  
  
-   Compatibilidad de todos los eventos de desencadenador y estructuras de mensajes a partir de V2.1 y hasta la versión 2.5.  
  
-   Compatibilidad de localización a través de agregar segmentos y adaptar el segmento opcionalmente y repetición.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
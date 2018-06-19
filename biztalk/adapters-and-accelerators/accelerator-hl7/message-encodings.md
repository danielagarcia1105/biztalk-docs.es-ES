---
title: Codificación de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36063416e1c5d1f30c9cb9c26056299f0b926a50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204796"
---
# <a name="message-encodings"></a>Codificaciones de mensaje
No es suficiente para definir la semántica de mensaje para HL7 sean útiles. Una vez que se ha determinado el contenido del mensaje, el estándar tiene que explicar cómo representar el contenido en una interfaz real. Es decir, debe haber especificado "codificación de mensajes". HL7 versión 2 admite dos formatos de codificación de mensajes, una codificación basado en delimitadores personalizada y una codificación XML.  
  
 HL7 eligió la original basado en delimitadores codificación para reducir el tamaño de mensajes tanto como sea posibles. Por ejemplo, si se compara una estructura de datos en el que los delimitadores separan los elementos a una estructura que cada elemento se coloca en un conjunto fijo de posiciones, la estructura basado en delimitadores es mucho más barata si) mensajes no contienen algunos elementos y b) algunos elementos no llenar todo el espacio permitido. La única sobrecarga en las estructuras basadas en delimitador es los delimitadores por sí mismos.  
  
 La codificación original de HL7 define cinco delimitadores, que cada mensaje se declara dentro del segmento de MSH. Éstas indican:  
  
-   Segmentos  
  
-   Campos  
  
-   Components  
  
-   Subcomponentes  
  
-   Repetición (de un campo, componente o subcomponente)  
  
 Tenga en cuenta que puesto que los delimitadores son un aspecto fundamental de la codificación, debe definirlos en primer lugar. Una de las consecuencias es que no puede haber ningún subdirectorio sub-delimitador. A veces, esta limitación tiene efectos indeseable en el diseño de nuevos tipos de datos.  
  
 En junio de 2003, HL7 publicado HL7 versión 2, la sintaxis de codificación de XML, la versión 1. Este estándar define reglas de codificación alternativas para los mensajes de HL7 versión 2.3.1 y 2.4 y proporciona un mecanismo para determinar las reglas de codificación alternativas para HL7 posteriores versiones 2.X. En esencia, este nuevo estándar define las etiquetas del elemento XML de la versión 2.3.1 y mensajes abstractos V2.4, segmentos, campos y tipos de datos y crea las reglas para definir las etiquetas necesarias para las nuevas estructuras creadas para versiones posteriores de la versión 2 estándares. El proceso de definición de esta norma dio lugar a una serie de mejoras en las versiones 2.4 y 2.5. Esto se deba a que la creación de etiquetas XML ha provocado la necesidad de abordar ciertas ambigüedades enfoque en el estándar subyacente. As a result, se crearon los códigos de estructura de mensaje) bien definido para indicar las variaciones en los mensajes abstractas asociados con los eventos de desencadenador, b) repetir grupos de segmentos con un mensaje abstracto formalmente se identificaron y con nombre y c) localmente tipo de datos definido, CM se reemplazó por tipos más específicos.  
  
 Por ejemplo, el siguiente es un mensaje de confirmación simple utilizando el formato delimitado por la canalización tradicional:  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 Por el contrario, el siguiente es el mismo mensaje que se representa como un documento XML:  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:  
  
-   Compatibilidad de delimitado por canalización y codificación de XML.  
  
-   Compatibilidad de traducción entre XML y la canalización había delimitada codificaciones.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
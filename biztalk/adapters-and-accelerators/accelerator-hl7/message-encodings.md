---
title: Codificación de mensajes | Microsoft Docs
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
ms.openlocfilehash: 013df4d29604e6dd7ce6d2e486612be303cc5898
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007093"
---
# <a name="message-encodings"></a>Codificaciones de mensajes
No es suficiente definir la semántica de mensajes en orden para HL7 sea útil. Una vez determinado el contenido del mensaje, el estándar tiene que explicar cómo representar ese contenido en una interfaz real. Es decir, debe haber especificado "codificación de mensajes". HL7 versión 2 admite dos formas de codificación de mensajes, una codificación basada en delimitador personalizado y una codificación XML.  
  
 HL7 eligió la original basado en delimitadores codificación para reducir el tamaño de mensajes tanto como sea posibles. Por ejemplo, si se compara una estructura de datos en el que los delimitadores separan los elementos a una estructura que coloca cada elemento de un conjunto fijo de posiciones, la estructura de delimitador es mucho más económica si) los mensajes no contienen algunos elementos y (b) otros los elementos no llenar todo el espacio permitido. La única sobrecarga en las estructuras basadas en el delimitador es los delimitadores de ellos mismos.  
  
 La codificación original de HL7 define cinco delimitadores, que cada mensaje se declara dentro del segmento de MSH. Estos errores indican:  
  
- Segmentos  
  
- Campos  
  
- Components  
  
- Subcomponentes  
  
- Repetición (de un campo, el componente o subcomponente)  
  
  Tenga en cuenta que dado que los delimitadores son un aspecto fundamental de la codificación, debe definirlos en primer lugar. Un resultado de esto es que no puede haber ningún sub sub-delimitador. A veces, esta limitación tiene desafortunados efectos en el diseño de nuevos tipos de datos.  
  
  En junio de 2003, HL7 publicado HL7 versión 2, la sintaxis de codificación XML, la versión 1. Este estándar define las reglas de codificación alternativas para los mensajes de HL7 versión 2.3.1 y 2.4 y proporciona un mecanismo para determinar las reglas de codificación alternativas para HL7 posteriores versiones 2.X. En esencia, este nuevo estándar define las etiquetas de elementos XML para la versión 2.3.1 y mensajes abstractos V2.4, segmentos, campos y tipos de datos y crea reglas para definir las etiquetas necesarias para las nuevas estructuras creadas para las versiones posteriores de la versión 2 del estándares. El proceso de definir este estándar dio lugar a una serie de mejoras en las versiones 2.4 y 2.5. Esto se deba a que la creación de etiquetas XML que se llevó a la necesidad de abordar ciertas ambigüedades antiguo en el estándar subyacente. As a result, se crearon los códigos de la estructura de mensaje (a) bien definidos para indicar las variaciones en los mensajes abstractos asociados a los eventos de desencadenador, (b) repetición formalmente los grupos de segmentos con un mensaje abstracto se han identificado y con nombre y c) la localmente tipo de datos definido, CM se ha reemplazado por tipos más específicos.  
  
  Por ejemplo, este es un mensaje de confirmación simple con el formato delimitado por la canalización tradicional:  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 Por el contrario, este es el mismo mensaje que se representa como un documento XML:  
  
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
  
 Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:  
  
-   Soporte técnico de codificación de XML y delimitado por canalización.  
  
-   Soporte de traducción entre XML y canalización delimitados codificaciones.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
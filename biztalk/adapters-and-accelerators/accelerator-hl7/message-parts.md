---
title: Partes del mensaje | Documentos de Microsoft
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
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-parts"></a>Partes de mensaje
Un mensaje HL7 contiene las siguientes partes: segmentos, los campos de datos, componentes y, opcionalmente, subcomponentes. Los mensajes de HL7 tienen la siguiente estructura jerárquica:  
  
 Segment  
  
 Campo de datos  
  
 Componente  
  
 Subcomponente (opcional)  
  
 **Segmentos**  
  
 Un segmento es una agrupación lógica de campos de datos. Segmentos se encuentran en el nivel más alto (profundidad 1) de la jerarquía de mensaje. Cada segmento tiene un nombre que incluye un valor literal de tres caracteres. En la tabla siguiente se muestra ejemplos de nombres de segmento contenidos los tipos de mensaje ADT.  
  
|Código de segmento|Description|  
|------------------|-----------------|  
|MSH|Encabezado de mensaje|  
|EVN|Tipo de evento|  
|PID|Información del paciente|  
  
 Mensajes HL7 tienen un *encabezado del mensaje* y *cuerpo*. Los segmentos de MSH definen el encabezado del mensaje y todos los demás tipos de segmentos forman el cuerpo del mensaje.  
  
 **Campos de datos**  
  
 Un campo de datos es una cadena de caracteres que se producen en profundidad 2 de la jerarquía de mensaje. Tipos de datos definen campos de datos: simples y complejos.  
  
 En el ejemplo siguiente se muestra la estructura del mensaje jerárquica de los segmentos de MSH y EVN que contiene los campos de datos MSH.1 y EVN.1:  
  
 MSH  
  
 MSH.1  
  
 EVN  
  
 EVN.1  
  
 **Componentes y subcomponentes**  
  
 Componentes y subcomponentes más contienen los datos en los campos de datos. Pueden repetir los componentes y subcomponentes dentro del mismo campo.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
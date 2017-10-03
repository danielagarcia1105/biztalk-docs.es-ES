---
title: "Conversión de propiedades de tipos de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-conversion-of-properties"></a>Conversión de tipos de datos de propiedades
Las propiedades de encabezado de los mensajes MQSeries son estructuras de datos contenidas en el propio mensaje. Al enviar y recibir mensajes, el adaptador de MQSeries automáticamente valida y convierte determinados valores de los encabezados de mensaje MQSeries.  
  
 En la tabla siguiente se describen los tipos de datos MQSeries, su validación y su conversión.  
  
|Tipo de datos MQSeries|Validación y conversión|  
|------------------------|-------------------------------|  
|MQLONG|MQSeries realiza la validación. Realiza la conversión a un valor de tipo “entero largo”. Los valores no válidos evitan que el mensaje se coloque en la cola MQSeries.|  
|MQCHAR|Realiza la conversión a una cadena.|  
|MQBYTE|Realiza la conversión a una cadena que contiene los caracteres 0-9, a-f o A-F, que representan el valor hexadecimal del número.|  
  
 Muchas de las propiedades de MQSeries son valores enteros de 32 bits (4 bytes) sin signo. Dado que **uint** no es un Common Language Specification (CLS)-tipo compatible, debe asignar a **objeto** tipos antes de usarlos en métodos. NET.  
  
## <a name="see-also"></a>Vea también  
 [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)   
 [Propiedades relacionadas con BizTalk Server](../core/properties-related-to-biztalk-server.md)   
 [Propiedades de contexto de MQSeries](../core/mqseries-context-properties.md)
---
title: Campo relleno | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56aa8490bd9e72677c9c8eefa73e7f6bd8438dfd
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="field-padding"></a>Relleno de los campos

## <a name="overview"></a>Información general

Los caracteres controladores se utilizan en campos de registros delimitados y posicionales cuando los datos que contiene el campo son más pequeños que el número de caracteres o bytes reservados para el campo. Estos caracteres ocupan la parte del campo que no necesitan los datos, si hay alguno. Caracteres de relleno se especifican en un campo por campo mediante el **carácter controlador** y **tipo de carácter controlador** propiedades de los correspondientes **elemento de campo** y  **Atributo de campo** nodos. Si no se especifica ningún carácter controlador para un campo concreto, se utiliza el carácter controlador predeterminado, el espacio (" "), en ese campo.  
  
## <a name="inbound-instances"></a>Instancias de entrada
 En los mensajes de instancia de entrada, ya sea el registro concreto de tipo posicional o delimitado, el desensamblador de archivos sin formato descarta los caracteres iniciales o finales que se corresponden con el carácter controlador especificado o predeterminado de un campo concreto cuando el mensaje de instancia se traduce al formato XML equivalente. Iniciales o finales del carácter controlador relevante que se descartan dependen de si la **justificación** propiedad de correspondientes **elemento de campo** y **campo Atributo** nodo se establece en **derecha** o **izquierda**, respectivamente.  

## <a name="outbound-instances"></a>Instancias de salida  
 En el caso de los mensajes de instancia de salida, el ensamblador de archivos sin formato insertará el número apropiado de caracteres del carácter controlador especificado o predeterminado en los campos, de modo que la longitud del campo sea correcta. Los caracteres controladores se insertarán antes o después de los caracteres de datos en función de si la **justificación** propiedad de los correspondientes **elemento de campo** y **deatributodecampo** nodo se establece en **derecha** o **izquierda**, respectivamente.  
  
 Cuando el campo que se debe rellenar en un mensaje de instancia de salida está incluido en un registro posicional, el **desplazamiento posicional** y **longitud posicional** propiedades de los correspondientes **campo Elemento** o **atributo de campo** nodo, junto con el número de caracteres de datos que el campo debe contener, determinar si los caracteres controladores son necesarios y, si es así, ¿cuántos. Cuando el campo que se debe rellenar de un mensaje de instancia de salida está incluido en un registro delimitado, solo son caracteres de relleno cuando inserta el valor de la **longitud mínima con carácter controlador** propiedad de los correspondientes  **Elemento de campo** o **atributo de campo** nodo supera el número de caracteres de datos.  

## 
Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
 [Consideraciones de campo](../core/field-considerations.md)   
 [Justificación de los campos](../core/field-justification.md)   
 [Especificación de las posiciones de los campos en los registros posicionales](../core/specification-of-field-positions-within-positional-records.md)  
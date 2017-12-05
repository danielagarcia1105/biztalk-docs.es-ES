---
title: "El Functoid de índice | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Index functoids, about Index functoids
- Index functoids
ms.assetid: 0c8ba427-881c-4b1f-92b9-61992d2a29df
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22881e7694fee872b7820b8b99157ef2cf20170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="index-functoid"></a>Índice (functoid)
El **índice** functoid le permite seleccionar información de un registro específico en una serie de registros. Cada **índice** functoid recopila información de un solo campo.  
  
 Algunos registros suelen aparecer varias veces en un archivo de entrada. Por ejemplo, en un informe meteorológico, el **DailySummary** elemento podría aparecer muchas veces. El **DailySummary** elemento puede incluir atributos para la temperatura, la presión barométrica y la velocidad del viento. El código que se muestra a continuación es un ejemplo de un informe meteorológico.  
  
```  
<ns0:WeatherReport xmlns:ns0="http://IndexFunctoid.WeatherReport">  
    <DailySummary Pressure="80" Windspeed="10" Temperature="20" />  
    <DailySummary Pressure="78" Windspeed="20" Temperature="23" />  
    <DailySummary Pressure="77" Windspeed="16" Temperature="24" />  
</ns0:WeatherReport>  
```  
  
 En el esquema subyacente, el **Max Occurs** propiedad para la **DailySummary** registro se establecería en ilimitado para indicar un periódico o registro de bucle. El Asignador de BizTalk compila este registro como un bucle.  
  
 Imagine que desea recopilar información meteorológica de los dos primeros **DailySummary** registros del informe meteorológico. En el asignador de BizTalk, cada atributo de la **DailySummary** registro del esquema de origen entrante puede estar conectado a un **índice** functoid. A su vez, cada uno de ellos **índice** functoid puede especificar la **DailySummary** grabar desde el que se va a dibujar la información: la primera o la segunda. El **índice** functoids, a continuación, se puede conectar a los campos correspondientes del esquema de destino.  
  
 La siguiente ilustración muestra **índice** functoids utilizados de esta manera.  
  
 ![](../core/media/ebiz-prog-map-index.gif "ebiz_prog_map_index")  
Ejemplo de functoid de índice  
  
 Para obtener la información de resumen diaria para el primer día, Establece la parte superior de tres **índice** functoids tienen sus valores de índice que se establece en 1. Para obtener la información de resumen diaria del segundo día, establezca el mínimo de tres **índice** functoids tienen sus valores de índice establecidos en 2.  
  
 **Índice** functoids usan el **configurar \<Functoid\> Functoid** cuadro de diálogo para establecer sus parámetros de entrada. El primer parámetro de entrada identifica un campo que está dentro de un registro de bucle en el esquema de origen. El segundo parámetro de entrada y los siguientes especifican el registro concreto. Puede especificar múltiples valores de índice para seleccionar un registro de las estructuras de repetición anidadas. El valor de índice de la estructura más interna es el segundo parámetro. El valor de índice de la siguiente estructura más externa sería el tercer parámetro y así sucesivamente. Por ejemplo, suponga que los anteriores **DailySummary** registros estaban dentro de **WeeklyData** registros. Para recuperar el **presión** desde la primera **DailySummary** en el segundo **WeeklyData**, el segundo parámetro debería ser 1 y el tercer parámetro sería 2.  
  
 Tenga en cuenta que este ejemplo se supone la **presión** campo no se repite. Si el campo se repitiera, los índices estarían desactivados — el número comenzaría con el **presión** campo, en lugar de la **Daily Summary**.  
  
> [!NOTE]
>  Aunque un parámetro de entrada de secuencia de índice suele ser una constante, es posible utilizar un vínculo desde un nodo del esquema de origen. Si este vínculo proviene de un registro de bucle que no es primario en relación con el primer parámetro de entrada, el valor de entrada de secuencia de índice proviene de la primera instancia del nodo del mensaje de instancia de entrada.  
  
> [!NOTE]
>  El valor de entrada de secuencia de índice siempre guarda relación con el contexto actual del documento de origen.  
  
> [!IMPORTANT]
>  Un **índice** functoid debe tener como muchos valores de índice como nodos de elemento primario desde el nivel de campo para el primer nivel por debajo del nodo raíz. Por ejemplo, en el mensaje de instancia de informe meteorológico múltiple, se requieren dos valores de índice. En el mensaje de instancia de informe meteorológico simple, únicamente es necesario un valor de índice. Error al configurar el número necesario de valores de índice de un **índice** functoid crea una salida basada en el primer nodo en el mensaje de instancia de origen que coincida con el primer parámetro de entrada de la **índice** functoid.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids de índice a un mapa](../core/how-to-add-index-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de iteración](../core/iteration-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)
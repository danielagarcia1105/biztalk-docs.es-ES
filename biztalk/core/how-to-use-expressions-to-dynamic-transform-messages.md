---
title: "Cómo usar expresiones para transformar dinámica mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a>Cómo usar expresiones para transformar mensajes de forma dinámica
En la orquestación, puede usar expresiones para transformar mensajes de forma dinámica. XLANG expone un método de transformación que se pueda llamar desde una **asignación de mensajes** forma dentro de un **construir mensaje** forma. Este es el mismo método que se llama cuando un **transformar** forma se utiliza, pero permite transformar mediante programación los mensajes mediante la asignación designada en la orquestación. Esto resulta útil en los procesamientos de mensajes de tipo independiente. Por ejemplo, si tiene un proceso empresarial que necesita elegir entre una serie de asignaciones para transformar mensajes entrantes según los parámetros que los mensajes entrantes recibidos proporcionaron, puede conseguirlo mediante el uso del método de transformación en la forma Expresión mientras mantiene intacto su proceso empresarial general.  
  
## <a name="transforming-messages"></a>Transformar mensajes  
 Puede usar el siguiente código de ejemplo para transformar mediante programación los mensajes en el **asignación de mensajes** forma:  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 En este ejemplo, MyMapType se declara como una variable de tipo **System.Type** en la orquestación. MyMapName es el nombre de una asignación ya creada en el proyecto de BizTalk. Si desea hacer referencia a una asignación que se encuentre en un ensamblado de BizTalk diferente, tendrá que hacer referencia a ese ensamblado en el proyecto de BizTalk. MyInputMsg es el mensaje de origen y MyOutputMsg es el mensaje de destino. Si la asignación toma varios mensajes de origen, puede usar el siguiente código de ejemplo para transformar los mensajes:  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  Si tiene varios mensajes de origen, deben estar colocados en orden en la expresión en relación al número de parte del mensaje de entrada que se indica en la asignación.  
  
> [!IMPORTANT]
>  Cuando se transforman mensajes de forma dinámica en la forma Expresión, se recomienda escribir una caché en el código de usuario para almacenar las asignaciones compiladas y, después, usarla en la forma Expresión para recuperar las asignaciones antes de realizar la transformación del mensaje. Si no almacena en caché las asignaciones, existe la posibilidad de que la memoria de Common Language Runtime (CLR) aumente de forma significativa. La asignación dinámica requiere que el motor de tiempo de ejecución de .NET realice comprobaciones de acceso al código que de origen a un objeto de evidencia de .NET se coloque en el montón del objeto grande para cada transformación y a que este objeto no se elimine hasta que la orquestación finalice. Por tanto, cuando se suceden muchos de estos tipos de transformaciones de forma simultánea, puede ver que el uso de memoria aumenta significativamente lo que puede provocar también una excepción de memoria insuficiente.  
  
## <a name="see-also"></a>Vea también  
 [Formas de orquestación](../core/orchestration-shapes.md)   
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)
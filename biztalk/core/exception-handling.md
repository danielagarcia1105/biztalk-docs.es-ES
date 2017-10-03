---
title: Control de excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a9125c-7c7c-4d2a-ae04-c923cd89683c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520f4eb47fb98bf497753a8348031f7c2ab93d29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling"></a>Control de excepciones
El **RuleEngine** clase tiene la propiedad **CompensationHandlerInfo**, que a su vez tiene dos propiedades: **CompensationHandler** y **UserData**. El **CompensationHandler** propiedad es de tipo **RuleEngineCompensationHandler**y el **UserData** propiedad es de tipo **objeto** . La definición de la **RuleEngineCompensationHandler** es como sigue:  
  
```  
public delegate bool RuleEngineCompensationHandler(  
   Exception ex,  
   object userData  
);  
```  
  
 El consumidor del motor de reglas especifica el controlador y los datos de usuario al motor de reglas mediante el **CompensationHandlerInfo** propiedad de la **RuleEngine** clase. El controlador debe tener la misma firma que el **RuleEngineCompensationHandler** delegar. Si se produce una excepción de tiempo de ejecución, el motor llama al controlador, y le pasa la excepción y los datos de usuario predefinidos como parámetros. Si el controlador devuelve `true`, a continuación, el motor de reglas continúa el procesamiento. De lo contrario, el motor de reglas anula el procesamiento y devuelve la excepción original al usuario. Como puede ver, puede utilizar este mecanismo de control de excepciones únicamente si se invoca la directiva mediante el uso de la **RuleEngine.Execute** método.  
  
 Si usas el **Policy.Execute** método para ejecutar una directiva, debe usar un bloque try-catch para detectar las excepciones generadas por el motor de reglas al ejecutar la directiva.  
  
 Si usas el **reglas de llamada** forma para ejecutar una directiva, use la **excepción de filtrado** bloquear para el **ámbito** forma para detectar una excepción producida por el motor de reglas al ejecutar la directiva.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar un bloque de excepción de filtrado](../core/how-to-add-a-catch-exception-block3.md)
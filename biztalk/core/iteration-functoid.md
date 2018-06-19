---
title: El Functoid de iteración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a491b8829f23296e77ba5a89d12985e8ccd32783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261972"
---
# <a name="iteration-functoid"></a>Iteración (functoid)
El **iteración** functoid salidas el índice del registro actual en un bucle de la estructura, empezando por 1 para el primer registro, 2 para el segundo registro y así sucesivamente.  
  
 La siguiente ilustración muestra un **iteración** functoid se combina con un **mayor o igual que** functoid, un **menor o igual a** functoid y un **y**  functoid para crear el equivalente de un **para** bucle.  
  
 ![Mapa que ilustra el uso del functoid de iteración](../core/media/iterationfunctoid.gif "iterationfunctoid")  
Asignación de functoid de iteración  
  
 Se asume que el **mayor o igual que** pruebas de functoid para valores mayores que o igual a 2 y el **menor o igual que** functoid comprueba para valores menor o igual a 4. En ese caso, el **y** functoid devolverá **true** solo para los registros 2, 3 y 4. Por lo tanto, la instancia de salida contendrá registra dos, tres y cuatro de los mensajes de instancia de entrada.  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids de iteración a un mapa](../core/how-to-add-iteration-functoids-to-a-map.md)   
 [Functoids avanzados](../core/advanced-functoids.md)   
 [Functoid de índice](../core/index-functoid.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de número de registros](../core/record-count-functoid.md)
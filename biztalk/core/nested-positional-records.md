---
title: Anidar los registros posicionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 618d5475842a9e5844f289a7ca77e4d9a725b130
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990221"
---
# <a name="nested-positional-records"></a>Registros posicionales anidados
Se permiten registros posicionales anidados si la **Max Occurs** propiedad de los registros secundarios está establecida en un entero positivo. El cálculo automático del campo podrá controlar la nueva profundidad. Sin embargo, existe una modificación en cuanto al modo en que éste se comporta. En concreto, como se pueden usar delimitadores nulos, el cálculo automático de las posiciones de los campos solo funcionará si se cumple una de las siguientes condiciones:  
  
- El nodo seleccionado tiene un nodo primario que está delimitado por infijos.  
  
- El nodo seleccionado tiene una posición inicial especificada.  
  
  Tenga en cuenta que hay una diferencia entre los registros posicionales anidados y los registros posicionales cuyo elemento primario es un contenedor delimitado en el que el delimitador es un valor null. Para que las estructuras sean verdaderamente de tipo posicional anidado, no debe existir ninguna ambigüedad al determinar la longitud. Por ejemplo, un nodo de bucle delimitado puede contener un registro posicional de repetición que aparezca de 0 a N veces. Sin embargo, para que ese nodo de bucle sea en sí mismo posicional y probablemente también para que contenga campos como pares en el registro posicional de repetición, la aparición del registro posicional de repetición debe ser determinista (un entero positivo).  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones acerca de los registros posicionales](../core/positional-record-considerations.md)
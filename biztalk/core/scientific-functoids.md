---
title: "Functoids científicos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b23f65ecede9082ec93041ddab45fa92029851a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scientific-functoids"></a>Functoids científicos

## <a name="overview"></a>Información general
**Científicos** functoids se utilizan para realizar una serie de cálculos trigonométricos, logarítmicos y exponenciales estándar.  
  
 Con la excepción de la **logaritmo en una base especificada** y **X ^ Y** functoids, que toman dos parámetros de entrada, el **científica** todos los functoids toman un único parámetro.  
  
 Las cuatro operaciones trigonométricas **científica** functoids (**arcotangente**, **coseno**, **seno**, y **tangente**) todos utilizan radianes en vez de grados como unidades para sus parámetros de salida o entrada pertinente. El Radián es una unidad de medida de ángulos, hay 2π radianes en un círculo. Así pues:  
  
-   2π radianes equivalen a 360 grados  
  
-   1 Radián = 180/π grados  
  
-   1 grado = π/180 radianes  
  
 Si los mensajes de instancia de entrada o salida utilizan grados como unidad de medida de ángulos, necesitará utilizar un **matemáticos** functoid junto con un trigonométrico **científica** functoid obtener el resultado correcto.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **científica** functoids son: 

* 10^n
* Arco tangente
* Logaritmo en una base de datos especificada
* Logaritmo común
* Coseno
* Función exponencial natural
* Logaritmo natural
* Seno
* Tangente
* X^Y
  
## <a name="see-also"></a>Vea también  
-  [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **Referencia a Functoids científicos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
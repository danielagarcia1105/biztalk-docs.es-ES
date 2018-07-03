---
title: Functoids científicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7a181f200948335aab0ffa2a06d43d38408afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977420"
---
# <a name="scientific-functoids"></a>Functoids científicos

## <a name="overview"></a>Información general
**Científicos** functoids se utilizan para realizar una serie de cálculos trigonométricos, logarítmicos y exponenciales estándar.  

 Con la excepción de la **logaritmo en una base especificada** y **X ^ Y** functoids, que toman dos parámetros de entrada, el **científica** todos los functoids toman un único parámetro.  

 Las cuatro operaciones trigonométricas **científica** functoids (**arco tangente**, **coseno**, **seno**, y **tangente**) todos utilizan radianes en vez de grados como unidades para sus parámetros de salida o entrada correspondiente. Una en radianes es una unidad de medida de ángulos, de forma que hay 2π radianes en un círculo. Así pues:  

- 2π radianes es igual a 360 grados  

- 1 radianes = π/180 grados  

- 1 grado = 180/π radianes  

  Si los mensajes de instancia de entrada o salida utilizan grados como unidad de medida de ángulos, deberá usar un **matemáticos** functoid junto con un trigonométrico **científica** functoid para lograr el resultado correcto.  

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
- [Cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md)   
- **Referencia a Functoids científicos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

---
title: "Cómo agregar Functoids de valor nulo a un mapa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc7d8b0035161b4a2126ace021072ffcd1d17e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a>Cómo agregar functoids de valor nulo a una asignación
El **valor nulo** functoid establece el valor del nodo de destino a **Nil**.  
  
 Para obtener información conceptual acerca de la **valor nulo** functoid, consulte [Functoid de valor nulo](../core/nil-value-functoid.md).  
  
## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a>Agregar el functoid valor nulo a una asignación y configurarlo  
  
1.  Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids. Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2.  Arrastre el **valor nulo** functoid (![functoid valor nulo](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.  
    >
    >  Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3.  El **valor nulo** functoid puede tener cero para un parámetro de entrada. Si no hay ningún parámetro de entrada para el functoid, el nodo de destino se establece en **Nil**. Para establecer el parámetro de entrada para el **valor nulo** functoid, crear un vínculo de entrada, arrastre la salida desde otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.  
  
4.  Para utilizar el parámetro de salida desde el **valor nulo** functoid, crear un vínculo de salida arrastrando el **valor nulo** functoid a un registro o campo del esquema de destino.  
  
    > [!NOTE]
    >  Al igual que con otros functoids, la salida de la **valor nulo** functoid puede utilizarse como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
-  **Referencia de Functoid de valor nulo**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)
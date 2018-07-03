---
title: Cómo agregar Functoids de valor nulo a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8488ea03fb40e1616b98e3ac8a1fc68b18e70e9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011869"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a>Cómo agregar functoids de valor nulo a una asignación
El **valor Nil** functoid establece el valor del nodo de destino a **Nil**.  

 Para obtener información conceptual sobre la **valor Nil** functoid, consulte [Functoid de valor nulo](../core/nil-value-functoid.md).  

## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a>Agregar el functoid valor nulo a una asignación y configurarlo  

1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids. Aparece la lista de functoids avanzados de la categoría seleccionada.  

2. Arrastre el **valor Nil** functoid (![functoid valor nulo](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  

   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
   >
   >  Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  

3. El **valor Nil** functoid puede tener cero a uno de los parámetros de entrada. Si no hay ningún parámetro de entrada para functoid, el nodo de destino se establece en **Nil**. Para establecer el parámetro de entrada para el **valor Nil** functoid, crear un vínculo de entrada arrastrando el resultado de algún otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.  

4. Para utilizar el parámetro de salida desde el **valor nulo** functoid, crear un vínculo de salida arrastrando el **valor nulo** functoid a un registro o campo del esquema de destino.  

   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **valor Nil** functoid puede utilizarse como entrada para otro functoid.  

## <a name="see-also"></a>Vea también  
- **Referencia de Functoid valor nulo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)

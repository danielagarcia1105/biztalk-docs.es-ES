---
title: Cómo agregar Functoids de aserción a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cfeabbbeac860e927854fb79c90d2b1608b9c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015277"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a>Cómo agregar functoids de aserción a una asignación
El **Assert** functoid le permite probar sus suposiciones acerca de las condiciones de la asignación. Por ejemplo, si realiza algunos cálculos para determinar un descuento adicional en las compras de productos, podría imponer que el descuento adicional sea no superior a 100 dólares mediante un functoid lógico (**mayor** o  **Less than**).  

> [!NOTE]
>  El **Assert** functoid solo se activa en las compilaciones de desarrollo o cuando el **generar información de depuración** propiedad en la configuración de compilación del proyecto está establecida en **True**. Cuando se compila la aplicación de BizTalk para la implementación y la **generar información de depuración** propiedad está establecida en **False** (valor predeterminado), se omiten las aserciones.  

 Para obtener información conceptual sobre la **Assert** functoid, consulte [Functoid imponer](../core/assert-functoid.md).  

## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a>Agregar el functoid de aserción a una asignación y configurarlo  

1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids. Aparece la lista de functoids avanzados de la categoría seleccionada.  

2. Arrastre el **Assert** functoid (![functoid de aserción](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  

   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar. 
   >    
   >  Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  

3. El functoid debe tener exactamente tres parámetros de entrada y genera un parámetro de salida. Para establecer el primer parámetro para el **Assert** functoid, crear un vínculo de entrada arrastrando el resultado de algún otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.  

4. Para establecer el segundo parámetro de entrada para el **Assert** functoid, crear un vínculo de entrada por un nodo de campo del esquema de origen a la **Assert** functoid, o inserte una constante.  

5. Para establecer el tercer parámetro de entrada para el **Assert** functoid, crear un vínculo de entrada por un nodo de campo del esquema de origen a la **Assert** functoid, o inserte una constante.  

6. Para utilizar el parámetro de salida desde el **Assert** functoid, crear un vínculo de salida arrastrando el **Assert** functoid a un campo del esquema de destino.  

   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **Assert** functoid puede utilizarse como entrada para otro functoid.  

## <a name="see-also"></a>Vea también  
- **Referencia de Functoid de aserción** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)

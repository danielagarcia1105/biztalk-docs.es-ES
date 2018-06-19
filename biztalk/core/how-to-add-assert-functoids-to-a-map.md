---
title: Cómo agregar Functoids a una asignación de aserción | Documentos de Microsoft
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
ms.openlocfilehash: 553daa0c6e97d09e8284d2369e801c5d2ff8beee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247764"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a>Cómo agregar functoids de aserción a una asignación
El **Assert** functoid le permite probar sus suposiciones acerca de las condiciones de la asignación. Por ejemplo, si realiza cálculos para determinar un descuento adicional sobre las compras de productos, podría imponer que el descuento adicional sea no más de 100 $ mediante un functoid lógico (**Greater Than** o  **Less than**).  
  
> [!NOTE]
>  El **Assert** functoid solo se activa en las compilaciones de desarrollo o cuando la **generar información de depuración** propiedad en la configuración de compilación del proyecto está establecida en **True**. Cuando se compila la aplicación de BizTalk para la implementación y la **generar información de depuración** propiedad está establecida en **False** (valor predeterminado), se omiten las aserciones.  
  
 Para obtener información conceptual acerca de la **Assert** functoid, consulte [Functoid imponer](../core/assert-functoid.md).  
  
## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a>Agregar el functoid imponer a una asignación y configurarlo  
  
1.  Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids. Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2.  Arrastre el **Assert** functoid (![functoid de aserción](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar. 
    >    
    >  Si crea una asignación que usa más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3.  El functoid debe tener exactamente tres parámetros de entrada y genera un parámetro de salida. Para establecer el primer parámetro para el **Assert** functoid, crear un vínculo de entrada, arrastre la salida desde otro **lógicos** functoid o de un campo booleano variable en el mensaje de instancia de entrada.  
  
4.  Para establecer el segundo parámetro de entrada para el **Assert** functoid, cree un vínculo de entrada mediante un nodo de campo del esquema de origen a la **Assert** functoid, o insertar una constante.  
  
5.  Para establecer el tercer parámetro de entrada para el **Assert** functoid, cree un vínculo de entrada mediante un nodo de campo del esquema de origen a la **Assert** functoid, o insertar una constante.  
  
6.  Para utilizar el parámetro de salida desde el **Assert** functoid, crear un vínculo de salida arrastrando el **Assert** functoid a un campo del esquema de destino.  
  
    > [!NOTE]
    >  Al igual que con otros functoids, la salida de la **Assert** functoid puede utilizarse como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
-  **Referencia de Functoid de aserción**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)
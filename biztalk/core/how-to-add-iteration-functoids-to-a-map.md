---
title: "Cómo agregar Functoids de iteración a un mapa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2df7cda082a9a85e54e1dce427d73ea15d8f920
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a>Cómo agregar functoids de iteración a una asignación
El **iteración** functoid salidas el índice del registro actual en un bucle de la estructura, empezando por 1 para el primer registro, 2 para el segundo registro y así sucesivamente.  
  
 Para obtener información conceptual acerca de la **iteración** functoid, consulte [Functoid de iteración](../core/iteration-functoid.md).  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de índice a una asignación y configurarlo  
  
1.  Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.  
  
     Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2.  Arrastre el **índice** functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) en el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.  
  
    > [!NOTE]
    >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3.  Para establecer el bucle parámetro de entrada de registro para el **iteración** functoid, crear un vínculo de entrada arrastrando un registro de bucle del esquema de origen a la **iteración** functoid, o bien arrastrando el  **Iteración** functoid hasta un registro de bucle del esquema de origen.  
  
4.  Para utilizar el parámetro de salida desde el **iteración** functoid, crear un vínculo de salida arrastrando el **iteración** functoid a un campo del esquema de destino o arrastrando un campo en el esquema de destino el **iteración** functoid.  
  
    > [!NOTE]
    >  El tipo de datos del campo correspondiente en el esquema de destino debe ser numérico o convertible a numérico para que coincida con el tipo de datos de salida de la **iteración** functoid.  
  
## <a name="see-also"></a>Vea también  
 [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)
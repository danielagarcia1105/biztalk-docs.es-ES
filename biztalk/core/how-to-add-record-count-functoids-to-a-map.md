---
title: Cómo agregar Functoids de número de registros a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980333"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>Cómo agregar functoids de número de registros a una asignación
El **número de registros** functoid le permite generar un recuento del número de veces que se produce un registro en un mensaje de instancia.  
  
 Para obtener información conceptual sobre la **número de registros** functoid, consulte [Functoid de número de registros](../core/record-count-functoid.md).  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de número de registros a una asignación y configurarlo  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **número de registros** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar en primer lugar la otra página de cuadrícula.  
  
   > [!NOTE]
   >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Para establecer el parámetro de entrada para el **número de registros** functoid, crear un vínculo de entrada arrastrando un registro de bucle del esquema de origen a la **número de registros** functoid, o bien arrastrando el  **Número de registros** functoid a un registro de bucle del esquema de origen.  
  
4. Para utilizar el parámetro de salida desde el **número de registros** functoid, crear un vínculo de salida arrastrando el **número de registros** functoid a un campo del esquema de destino o arrastrando un campo en el destino esquema para el **número de registros** functoid.  
  
   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **número de registros** functoid puede utilizarse como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)
---
title: Cómo agregar Functoids de índice a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b560b1565638c7d82d6f497319387fc5f58755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976189"
---
# <a name="how-to-add-index-functoids-to-a-map"></a>Cómo agregar functoids de índice a una asignación
El **índice** functoid le permite seleccionar la información de un registro específico en una serie de registros de bucle. Cada **índice** functoid selecciona información de un solo campo.  
  
 Para obtener información conceptual sobre la **índice** functoid, consulte [el Functoid de índice](../core/index-functoid.md).  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de índice a una asignación y configurarlo  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **índice** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar en primer lugar la otra página de cuadrícula.  
  
   > [!NOTE]
   >  Si se construye un mapa con más de un functoid juntas, necesitará tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Para establecer el parámetro de entrada del campo para el **índice** functoid, crear un vínculo de entrada arrastrando un campo dentro de un registro de bucle del esquema de origen a la **índice** functoid, o bien arrastrando el **Índice** functoid a un campo del registro de bucle del esquema de origen.  
  
4. Para establecer al menos un parámetro de entrada de índice para el **índice** functoid, realice los pasos siguientes:  
  
   1.  Con el **índice** functoid seleccionado, haga clic en el botón de puntos suspensivos (**...** ) botón asociado a la **parámetros de entrada** propiedad en el **propiedades** ventana.  
  
   2.  En el **configurar Functoid de índice** cuadro de diálogo, haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón.  
  
   3.  En el cuadro de edición, escriba el parámetro de entrada de índice como un valor numérico. Repita según sea necesario si los valores de índice adicionales son necesarios y, a continuación, haga clic en **Aceptar**.  
  
5. Para utilizar el parámetro de salida desde el **índice** functoid, crear un vínculo de salida arrastrando el **índice** functoid a un campo del esquema de destino o arrastrando un campo del esquema de destino para el  **Índice** functoid.  
  
   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **índice** functoid puede utilizarse como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)
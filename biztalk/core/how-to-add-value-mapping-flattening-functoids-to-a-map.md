---
title: Cómo agregar Functoids de (valores sin formato) de la asignación a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81486bedb71d69dde815f2849e0faf5b3b841f08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981293"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a>Cómo agregar functoids de asignación de valores (sin formato) a una asignación
El **asignación de valores (sin formato)** functoid permite aplanar una parte de un mensaje de instancia de entrada convirtiendo varios registros en un único registro. Ésta es una operación común para convertir catálogos de Microsoft Commerce Server.  
  
 Para obtener información conceptual sobre la **asignación de valores (sin formato)** functoid, consulte [Functoid de asignación de (valores sin formato)](../core/value-mapping-flattening-functoid.md).  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de asignación de valores (sin formato) a una asignación y configurarla  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **asignación de valores (sin formato)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
  
   > [!NOTE]
   >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Para establecer el primer parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o a otro functoid hacia su izquierda, que tiene un tipo de datos booleano y que generará un valor de entrada de "true" o "false".  
  
   > [!NOTE]
   >  También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **asignación de valores (sin formato)** functoid.  
  
4. Para establecer el segundo parámetro de entrada para el **asignación de valores (sin formato)** functoid, crear un vínculo de entrada arrastrando el **asignación de valores (sin formato)** functoid a un nodo registro o campo en el origen esquema, o arrastrando un nodo registro o campo del esquema de origen a la **asignación de valores (sin formato)** functoid, o inserte una constante.  
  
   > [!NOTE]
   >  El segundo parámetro de entrada la **asignación de valores (sin formato)** functoid también puede situarse desde la salida de otro functoid hacia su izquierda. Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids correspondientes hasta el otro functoid correspondiente.  
  
5. Para utilizar el parámetro de salida desde el **asignación de valores (sin formato)** functoid, crear un vínculo de salida arrastrando el **asignación de valores (sin formato)** functoid a un registro o campo en el esquema de destino, o bien arrastrar un campo de registro en el esquema de destino para la **asignación de valores (sin formato)** functoid.  
  
   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **asignación de valores (sin formato)** functoid puede utilizarse como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)
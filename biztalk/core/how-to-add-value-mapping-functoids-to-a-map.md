---
title: Cómo agregar Functoids de asignación a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e4ba1b22b7db156717c2f40e91117562e879caa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996261"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a>Cómo agregar functoids de asignación de valores a una asignación
El **Value Mapping** functoid devuelve el valor de su segundo parámetro si el primer parámetro es true. Una utilización común del functoid es cambiar los atributos de un campo a los atributos de un registro.  
  
 Para obtener información conceptual sobre la **Value Mapping** functoid, consulte [el Functoid de asignación de valor](../core/value-mapping-functoid.md).  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de asignación de valores a una asignación y configurarlo  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
  
   > [!NOTE]
   >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Para establecer el primer parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen, o hasta otro functoid para su izquierda, que tiene un tipo de datos booleano y que generará un valor de entrada "true" o "false".  
  
   > [!NOTE]
   >  También puede arrastrar en la dirección opuesta, desplazando el origen del valor booleano para la **Value Mapping** functoid.  
  
4. Para establecer el segundo parámetro de entrada para el **Value Mapping** functoid, crear un vínculo de entrada arrastrando el **Value Mapping** functoid a un nodo registro o campo del esquema de origen, o arrastrando un registro nodo de campo en el esquema de origen o el **Value Mapping** functoid.  
  
   > [!NOTE]
   >  El segundo parámetro de entrada la **Value Mapping** functoid también puede situarse desde la salida de otro functoid hacia su izquierda. Cree los vínculos que representan estos orígenes de entrada arrastrando uno de los functoids importantes hasta el otro functoid importante.  
  
5. Para utilizar el parámetro de salida desde el **Value Mapping** functoid, crear un vínculo de salida arrastrando el **Value Mapping** functoid a un registro o campo del esquema de destino o arrastrando un campo de registro el esquema de destino para la **Value Mapping** functoid.  
  
   > [!NOTE]
   >  Igual que con otros functoids, la salida de la **Value Mapping** functoid puede servir como entrada para otro functoid.  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)
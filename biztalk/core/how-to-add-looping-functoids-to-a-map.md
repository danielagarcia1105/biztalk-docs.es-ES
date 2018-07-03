---
title: Cómo agregar Functoids de bucle a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 659b9b39beea4bf5efed4c6d1553fca173191cc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988765"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>Cómo agregar functoids de bucle a una asignación

## <a name="overview"></a>Información general
El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.  

 Para obtener información conceptual sobre la **bucle** functoid, consulte [Functoid de bucle](../core/looping-functoid.md).  

 Bajo ciertas condiciones, algunos functoids podrían no funcionar según lo esperado cuando se usan en un mapa con una **bucle** functoid. Si un functoid cumple las siguientes condiciones, no producirá los resultados esperados:  

-   El functoid tiene más de un vínculo de entrada.  

-   Dos o más de los vínculos de entrada de functoid están vinculados a campos secundarios de los registros de entrada para el **bucle** functoid, donde los campos secundarios no son del mismo nivel.  

-   El functoid tiene un vínculo de salida que esté vinculado a un campo secundario del registro de salida de la **bucle** functoid.  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>Agregar el functoid de bucle a una asignación y configurarlo  

1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  

    Aparece la lista de functoids avanzados de la categoría seleccionada.  

2. Arrastre el **bucle** functoid del cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  

    ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
   Functoid de bucle  

   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
   > 
   >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  

3. Para establecer los parámetros de entrada para el **bucle** functoid, crear un vínculo de entrada arrastrando un registro o campo del esquema de origen a la **bucle** functoid, o bien arrastrando el **bucle**  functoid a un registro o campo del esquema de origen. Repita según sea necesario para incluir todos los registros de entrada relevantes o campos a la **bucle** functoid.  

4. Para utilizar el parámetro de salida desde el **bucle** functoid, crear un vínculo de salida arrastrando el **bucle** functoid a un registro o campo del esquema de destino o arrastrando un registro o campo en el esquema de destino en el **bucle** functoid.  

   > [!NOTE]
   >  A diferencia de muchos otros functoids, la salida de la **bucle** functoid solo se puede vincular a un elemento del esquema de destino.  

## <a name="see-also"></a>Vea también  
- [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)   
- **Referencia de Functoid de bucle** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

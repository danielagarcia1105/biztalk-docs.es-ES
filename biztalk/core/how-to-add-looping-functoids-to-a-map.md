---
title: Cómo agregar Functoids a una asignación de bucle | Documentos de Microsoft
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
ms.openlocfilehash: faa380b4a92de685ad8dc19c27a98f6578d12dc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248732"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a>Cómo agregar functoids de bucle a una asignación

## <a name="overview"></a>Información general
El **bucle** functoid combina múltiples registros o campos del esquema de origen en un único registro del esquema de destino.  
  
 Para obtener información conceptual acerca de la **bucle** functoid, consulte [Functoid de bucle de](../core/looping-functoid.md).  
  
 Bajo ciertas condiciones, algunos functoids podrían no funcionar según lo esperado cuando se utilizan en un mapa con una **bucle** functoid. Si un functoid cumple las siguientes condiciones, no producirá los resultados esperados:  
  
-   El functoid tiene más de un vínculo de entrada.  
  
-   Dos o más de los vínculos de entrada de functoid están vinculados a campos secundarios de los registros de entrada a la **bucle** functoid, donde los campos secundarios no son del mismo nivel.  
  
-   El functoid tiene un vínculo de salida que está vinculado a un campo de elemento secundario del registro de salida de la **bucle** functoid.  
  
## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a>Agregar el functoid de bucle a una asignación y configurarlo  
  
1.  Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en cuadro de herramientas activa, el **Functoids avanzados** tab para seleccionar esta categoría de functoids.  
  
     Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2.  Arrastre el **bucle** functoid del cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
     ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
Functoid de bucle  
  
    > [!NOTE]
    >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, necesitará mostrar otra página de cuadrícula en primer lugar.  
    > 
    >  Si crea una asignación que utiliza más de un functoid, es necesario tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3.  Para establecer los parámetros de entrada para el **bucle** functoid, crear un vínculo de entrada arrastrando un registro o campo del esquema de origen a la **bucle** functoid, o bien arrastrando el **bucle**  functoid a un registro o campo del esquema de origen. Repita según sea necesario para incluir todos los registros de entrada relevantes o campos a la **bucle** functoid.  
  
4.  Para utilizar el parámetro de salida desde el **bucle** functoid, crear un vínculo de salida arrastrando el **bucle** functoid a un registro o campo del esquema de destino, o arrastrando un registro o campo en el esquema de destino en la **bucle** functoid.  
  
    > [!NOTE]
    >  A diferencia de muchos otros functoids, la salida de la **bucle** functoid solo puede vincularse a un elemento del esquema de destino.  
  
## <a name="see-also"></a>Vea también  
-  [Agregar Functoids avanzados a un mapa](../core/adding-advanced-functoids-to-a-map.md)   
-  **Referencia de Functoid de bucle**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
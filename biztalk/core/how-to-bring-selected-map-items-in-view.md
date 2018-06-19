---
title: Cómo colocar el mapa seleccionado elementos en la vista | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005549"
---
# <a name="how-to-bring-selected-map-items-in-view"></a>Agregación de elementos de asignación seleccionados en la vista
Con las versiones anteriores del Asignador de BizTalk, si un mapa comprendía esquemas grandes, era necesario desplazarse por el panel de esquema de origen, la página de cuadrícula y el panel de esquema de destino para llevar todos los elementos del mapa relevantes a una única vista. El asignador de BizTalk con BizTalk Server le permite llevar todos los elementos del mapa relevantes del functoid/vínculo seleccionado en una única vista desplazando automáticamente la página de cuadrícula. En este tema se proporciona información acerca de cómo realizar esta operación.  
  
 En función de lo que seleccione (un nodo de esquema de origen, un elemento de la vista de relación o un nodo de esquema de destino), el Asignador de BizTalk desplaza automáticamente las vistas de esquema y la vista de relación de modo sincronizado, y muestra la vista de relación global del elemento seleccionado.  
  
> [!NOTE]
>  La característica de desplazamiento automático entra en vigor una vez que el Asignador de BizTalk ha resaltado todos los elementos del mapa relevantes. En otras palabras, primero se resaltan los elementos relacionados con la selección y después el Asignador de BizTalk desplaza automáticamente para llevar a la vista los elementos relacionados.  
  
 El Asignador de BizTalk no mueve realmente los objetos de cuadrícula. Los objetos de cuadrícula vuelven a sus respectivas ubicaciones al quitar o modificar la selección.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Esta operación requiere que se está ejecutando el Asignador de BizTalk.  
  
### <a name="to-bring-the-selected-map-items-in-view"></a>Procedimiento para llevar los elementos del mapa seleccionados a la vista  
  
1.  En la cinta de opciones de la utilidad asignador, haga clic en el icono de desplazamiento automático ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") para desactivarlo.  
  
    > [!NOTE]
    >  El ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icono está desactivado OFF de forma predeterminada.  
  
2.  Haga clic en un functoid o en un vínculo; se resaltarán los elementos del mapa relevantes de la relación.  
  
     En la siguiente ilustración se muestra el vínculo seleccionado en color azul. A su vez, el Asignador de BizTalk resalta en color verde los demás elementos de asignación que son relevantes para la selección. En la ilustración puede ver que todos los elementos de la relación seleccionada, a pesar de estar resaltados, no se encuentran totalmente en la vista actual.  
  
     ![Cuando se vincula automáticamente &#45; desplazamiento está desactivado](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")  
  
3.  Haga clic en el icono de desplazamiento automático ![Auto &#45; icono de desplazamiento](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") para activarlo.  
  
     El Asignador de BizTalk se desplaza automáticamente para llevar todos los elementos relevantes de la selección a la vista actual del mapa.  
  
     ![Ver cuando se cambia el desplazamiento automático en](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")  
  
    > [!NOTE]
    >  Como alternativa, puede presionar CTRL+M o CTRL+U del teclado. Para obtener una lista de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el Asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)
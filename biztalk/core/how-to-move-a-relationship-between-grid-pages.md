---
title: Cómo mover una relación entre las páginas de cuadrícula | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5737adcb9159568bfea7c7cdde9dff8015b19706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255092"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a>Mover una relación entre las páginas de cuadrícula
Las asignaciones grandes incluyen numerosos conjuntos de functoids y vínculos, por lo cual pueden perjudicarle la identificación de los vínculos que unen varios functoids. En tal caso, es posible que desee mover un conjunto similar de functoids y vínculos a una página de cuadrícula diferente para que la asignación resulte más legible. En este tema se proporcionan instrucciones detalladas para realizar la operación.  
  
 Puede mover una relación de una página de cuadrícula a otra, en el mismo mapa solamente, de uno de los modos siguientes:  
  
-   Mediante el **moverse a la página** cuadro de diálogo  
  
-   Usando la función de arrastrar y colocar de los functoids (y vínculos) seleccionados en la cinta  
  
> [!IMPORTANT]
>  Puede mover uno o más functoids y sus vínculos. Al mover una relación, se mantienen las etiquetas, comentarios y los valores constantes (junto con los marcadores de posición correctos) asociados con dicha relación.  
  
> [!IMPORTANT]
>  No se pueden arrastrar y colocar vínculos solamente a otra página de cuadrícula.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a>Procedimiento para mover una relación mediante el cuadro de diálogo Mover a página  
  
1.  En el mapa, seleccione la página de cuadrícula desde la que desea mover una relación.  
  
2.  Haga clic en un functoid o un vínculo en la relación que desea mover y, a continuación, haga clic en **moverse a la página**. Se muestra un mensaje que indica que se van a mover todos los elementos de asignación seleccionados, junto con los vínculos y functoids relacionados. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para deshabilitar el mensaje emergente, en el menú de Visual Studio, vaya a **herramientas**, haga clic en **opciones**, haga clic en **el asignador de BizTalk**, haga clic en **General**, y, a continuación, desactive la **ir a la página** opción. Para obtener más información acerca de opciones generales, consulte [cómo personalizar la configuración General del asignador de BizTalk](../core/how-to-customize-general-settings-in-biztalk-mapper.md).  
  
    > [!TIP]
    >  Como alternativa, puede presionar CTRL + M, CTRL + M para abrir la **moverse a la página** cuadro de diálogo. Para obtener una lista de métodos abreviados del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
     ![Mover la relación seleccionada a una nueva página](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")  
  
3.  En el **moverse a la página** cuadro de diálogo, seleccione la página de cuadrícula de destino al que desea mover la relación y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  También puede crear una nueva página seleccionando  **\*(Agregar nueva página)** y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Como alternativa, puede presionar CTRL+M, CTRL+A para agregar una nueva página de cuadrícula en una asignación. Para obtener una lista de métodos abreviados del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
     ![Seleccione la página de cuadrícula de destino](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")  
  
     El functoid/vínculo seleccionado, junto con los functoids y vínculos relacionados, se mueve a la nueva página de cuadrícula. En la ilustración siguientes se muestra la relación seleccionada (que estaba en la página 3) movida a la página 1.  
  
     ![Relación seleccionada se mueve a una nueva página](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a>Procedimiento para mover una relación mediante arrastrar y colocar  
  
1.  En el mapa, seleccione la página de cuadrícula desde la que desea mover una relación.  
  
2.  Seleccione los functoids (y vínculos) que desee mover a otra página de cuadrícula. Este selecciona recursivamente todos los vínculos que conectan con los functoids de la selección.  
  
3.  Arrastre la selección a la página (en la pestaña de páginas) donde desee mover la relación.  
  
    > [!WARNING]
    >  No suelte el mouse hasta que realice el paso 4.  
  
4.  Cuando la página de cuadrícula de destino pase a estar seleccionada (en la anterior figura, está seleccionada la Página 1), suelte la selección en una celda vacía de la página de cuadrícula. La relación seleccionada se moverá a la nueva página de cuadrícula.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con páginas de cuadrícula](../core/working-with-grid-pages.md)
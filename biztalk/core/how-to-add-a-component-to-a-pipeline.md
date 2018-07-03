---
title: Cómo agregar un componente a una canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b1d37c6fafcec158f63c3728c773c19089658b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991333"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a>Cómo agregar un componente a una canalización
Los componentes se agregan a las canalizaciones arrastrándolos desde el cuadro de herramientas hasta la superficie de diseño.  
  
### <a name="to-add-a-component-to-a-pipeline"></a>Para agregar un componente a una canalización  
  
- En el cuadro de herramientas, arrastre el componente de canalización hasta un **Coloque aquí!** cuadro de la superficie de diseño.  
  
  La siguiente ilustración muestra cómo la superficie de diseño de canalización muestra las canalizaciones. Esta canalización tiene dos fases, la fase de ensamblado y la fase de codificación. El componente de canalización de ensamblador XML se agregó a la fase de ensamblado, pero la fase de codificación todavía está vacía, porque aún muestra **Coloque aquí!** para indicar que un componente de canalización se puede agregar a la fase.  
  
  ![Fases y componentes de una canalización de BizTalk](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
  Muestra fases y componentes de una canalización de BizTalk.  
  
> [!NOTE]
>  Un componente de canalización solo puede colocarse en ubicaciones específicas de la superficie de diseño. El componente de canalización solo puede colocarse en una fase con la que tenga afinidad de fases. Un círculo con una barra diagonal aparece cerca del puntero en los lugares en que no puede colocarse el componente de canalización. En los lugares en que un componente de canalización puede colocarse, se muestra una flecha y aparece resaltada una parte de la superficie de diseño.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md)   
 [Cómo abrir una canalización](../core/how-to-open-a-pipeline.md)   
 [Cómo usar el cuadro de herramientas](../core/how-to-use-the-toolbox.md)   
 [Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md)   
 [Creación de canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md)
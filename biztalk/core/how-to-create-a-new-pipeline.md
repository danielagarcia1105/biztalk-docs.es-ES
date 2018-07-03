---
title: Cómo crear una nueva canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908c0eebecaf005e22194584f9a1d1e7fafa4daf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970237"
---
# <a name="how-to-create-a-new-pipeline"></a>Cómo crear una nueva canalización
Puede agregar una plantilla de canalización al proyecto para crear una nueva canalización.  
  
> [!WARNING]
>  No debería agregar un proyecto que contenga una implementación de un componente de canalización personalizado a una solución que contenga un proyecto que utilice ese componente de canalización. Si lo hace, la próxima vez que vuelva a generar la solución, aparecerá un error que informará de que otro proceso está utilizando el dll de salida.  
  
### <a name="to-create-a-new-pipeline"></a>Para crear una nueva canalización  
  
1. En el Explorador de soluciones, seleccione el proyecto en el que desea crear la canalización.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
3. En el **Agregar nuevo elemento** cuadro de diálogo, seleccione un **canalización de recepción** o **canalización de envío** plantilla haciendo clic en él una vez.  
  
   > [!NOTE]
   >  Si hace doble clic en la plantilla, la canalización se crearán automáticamente con el nombre predeterminado que aparece en el **nombre** campo.  
  
4. En el **nombre** , escriba un nombre para la canalización.  
  
5. Haga clic en **Abrir**.  
  
    La nueva canalización aparecerá en el Explorador de soluciones. La superficie de diseño muestra las fases de canalización y un conjunto predeterminado de componentes.  
  
   Para obtener información acerca de cómo agregar componentes de canalización a la canalización, consulte [cómo agregar un componente a una canalización](../core/how-to-add-a-component-to-a-pipeline.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo abrir una canalización](../core/how-to-open-a-pipeline.md)   
 [Cómo guardar una canalización](../core/how-to-save-a-pipeline.md)   
 [Cómo usar el cuadro de herramientas](../core/how-to-use-the-toolbox.md)   
 [Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md)   
 [Creación de canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md)
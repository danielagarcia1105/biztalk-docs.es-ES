---
title: Cómo usar el cuadro de herramientas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257276"
---
# <a name="how-to-use-the-toolbox"></a>Uso del cuadro de herramientas
Una canalización se crea arrastrando componentes (formas) desde el cuadro de herramientas hasta la superficie de diseño. El Diseñador de canalizaciones ayuda a ensamblar canalizaciones válidas poniendo algunas restricciones en el proceso de creación. Solo puede seleccionar componentes del cuadro de herramientas aplicables al tipo de canalización que está creando. Por ejemplo, una canalización de recepción mostrará descodificadores, desensambladores y validadores como componentes válidos del cuadro de herramientas, mientras que los codificadores y ensambladores estarán deshabilitados (atenuados).  
  
 Además, las fases solo pueden aceptar componentes válidos. Por ejemplo, no puede arrastrar un componente de codificador hasta una fase de ensamblado. Cuando arrastra un componente cerca de una ubicación válida para la acción de colocar, aparece una flecha que indica el punto en el que el componente puede insertarse.  
  
 Si arrastra un componente válido a una fase que está contraída, mantenga el mouse sobre la fase durante unos segundos para expandirla y, a continuación, coloque el componente en la fase.  
  
 Agregar un componente personalizado al cuadro de herramientas en el Diseñador de canalizaciones es parecido al procedimiento estándar en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 **Formas inicio y fin**  
  
 **Iniciar** y **final** formas aparecen como viñetas en todas las canalizaciones. Se muestran en la superficie de diseño únicamente para organización visual. Hay solo una de cada y no pueden ser ni agregadas ni eliminadas. El **iniciar** y **final** formas no aparecen en el cuadro de herramientas.  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a>Para agregar un componente de canalización al cuadro de herramientas.  
  
1.  En el menú **Herramientas** , haga clic en **Elegir elementos del cuadro de herramientas**.  
  
     : "O":  
  
     Haga clic en el cuadro de herramientas y, a continuación, haga clic en **elegir elementos**.  
  
2.  En el **Personalizar cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha.  
  
     En un cuadro de diálogo se muestran los componentes de canalización compatibles. Puede desplazarse por las categorías haciendo clic en las pestañas de la parte superior del cuadro de diálogo.  
  
3.  Seleccione el componente que desea agregar al cuadro de herramientas.  
  
4.  Haga clic en **Aceptar**. El componente aparecerá en el **componentes de canalización de BizTalk** ficha del cuadro de herramientas.  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a>Para quitar un componente de canalización del cuadro de herramientas  
  
-   Abra la **Personalizar cuadro de herramientas** cuadro de diálogo (como en el procedimiento anterior) y desactive el componente que desee quitar.  
  
     Un componente sigue registrado incluso después de haberlo quitado del cuadro de herramientas.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md)   
 [Cómo abrir una canalización](../core/how-to-open-a-pipeline.md)   
 [Cómo desplazarse con el teclado](../core/how-to-navigate-with-the-keyboard.md)   
 [Crear canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md)
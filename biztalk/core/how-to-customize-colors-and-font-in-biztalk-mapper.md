---
title: Cómo personalizar los colores y fuentes en el asignador de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.options.colors
ms.assetid: 494e4d70-8159-4721-9378-85bfc3c3d6f2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d9e3c118afc4ef0ca369be17b36f439c5885e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a>Cómo personalizar colores y fuentes en el Asignador de BizTalk
Puede cambiar los colores asociados con diversos tipos de vínculos y el color de los objetos seleccionados en la vista de cuadrícula. También puede cambiar la fuente utilizada para mostrar los nodos de árbol de esquema. En este tema se proporcionan instrucciones paso a paso para realizar estos cambios.  
  
 También puede optar por personalizar la configuración general del Asignador de BizTalk. Para obtener información sobre cómo elegir la configuración, consulte [cómo personalizar la configuración General del asignador de BizTalk](../core/how-to-customize-general-settings-in-biztalk-mapper.md).  
  
> [!NOTE]
>  Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a>Para cambiar la fuente y los colores usados en el Asignador de BizTalk  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.  
  
2.  En el **opciones** cuadro de diálogo, expanda el **el asignador de BizTalk** nodo y, a continuación, haga clic en **fuentes y colores**.  
  
     ![Seleccionar colores y fuentes](../core/media/colorsfonts-options.gif "ColorsFonts_Options")  
  
3.  Cambie los colores de los diversos tipo de vínculos, advertencias de compilador, primer plano de cuadrícula y fondo de cuadrícula mediante el selector de color asociado a cada propiedad de color.  
  
     Están disponibles las siguientes opciones de color:  
  
    -   **Vínculos de nodos secundarios.** El color usado para dibujar los vínculos de los elementos secundarios del elemento primario contraído.  
  
    -   **Errores del compilador.** El color usado para dibujar el error del compilador.  
  
    -   **Vínculos de compilador.** El color de los vínculos de compilador, que son los vínculos de directivas de compilador. Son vínculos que se crean automáticamente cuando un vínculo se establece desde un campo del árbol del esquema de origen en un campo del árbol del esquema de destino.  
  
    -   **Vínculos atenuados.** El color que se usa para trazar los vínculos que no están seleccionados o resaltados.  
  
    -   **Vínculos elásticos.** El color de los vínculos elásticos, que son vínculos de valor-copia sencillos que se arrastran desde el árbol de esquema de origen al árbol de esquema de destino. Una vez creado el vínculo, su color cambia al definido para vínculos fijos.  
  
    -   **Vínculos generales.** El color que se usa para trazar los vínculos con ambos extremos en la vista, si no hay elementos seleccionados.  
  
    -   **Fondo de cuadrícula.** El color de fondo en las páginas de cuadrícula.  
  
    -   **Líneas de cuadrícula.** El color usado para dibujar las líneas de cuadrícula.  
  
    -   **Vínculos resaltados.** El color usado para resaltar vínculos.  
  
    -   **Vínculos de coincidencia indicativa.** El color que se usa para trazar las coincidencias indicativas.  
  
    -   **Parcialmente vínculos fuera de ámbito.** El color que se para trazar los vínculos que tengan solo un extremo en la vista.  
  
    -   **Color de fuente del nodo de esquema.** El color que se usa para los nodos de árbol de esquema.  
  
    -   **Resultados de la búsqueda.** El color usado para dibujar las coincidencias de búsqueda en el árbol de esquema.  
  
    -   **Objetos de cuadrícula seleccionado.** El color usado para dibujar la selección en la superficie de la cuadrícula.  
  
    -   **Totalmente fuera de ámbito de vínculos.** El color que se usa para trazar vínculos con ambos extremos fuera de la vista.  
  
4.  Haga clic en el botón de puntos suspensivos (**...** ) situado en el extremo derecho de la **fuente del nodo esquema** cuadro de valor de propiedad.  
  
5.  En el **fuente** cuadro de diálogo, cambie la fuente utilizada en las vistas en la ventana de edición principal.  
  
6.  Haga clic en **Aceptar**. La configuración se aplica según la selección.  
  
    > [!IMPORTANT]
    >  Si no desea usar la configuración personalizada, haga clic en **Restaurar valores predeterminados** en el **opciones** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)
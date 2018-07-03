---
title: El asignador de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfa3ac3d03e5f9537284ea4e4371ab5a443d2b42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967533"
---
# <a name="using-biztalk-mapper"></a>Utilizar el Asignador de BizTalk

## <a name="overview"></a>Información general
El Asignador de BizTalk reside en el shell de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Parte de la funcionalidad del Asignador de BizTalk se basan en los elementos de la interfaz de usuario del shell de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Por ejemplo, usa el **archivo**, **editar**, y **vista** menús igual que haría para otros entornos de desarrollo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Información sobre esta funcionalidad común está disponible desde el **ayuda** menú.  
  
 El Asignador de BizTalk se activa cuando agrega una nueva asignación a un proyecto de BizTalk, cuando abre una asignación ya existente (archivo .btm) o cuando vuelve a activar una asignación haciendo clic en la pestaña correspondiente de la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  El Asignador de BizTalk guarda los archivos de asignación con la codificación de caracteres UTF-16.  
>
>  Al agregar un artefacto existente a un proyecto de BizTalk, siempre se establece la acción de compilación en **BtsCompile**. Incluso cuando cambia el nombre de un artefacto existente, su acción de compilación se establece en el valor predeterminado **BtsCompile**. Por lo tanto, mientras agregue o cambie de nombre un artefacto existente, debe establecer la acción de generación adecuadamente, en función de si genera ese artefacto en particular o no.  

## <a name="parts-of-the-biztalk-mapper"></a>Partes del asignador de BizTalk  
 En la siguiente ilustración se muestran las distintas partes del Asignador de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 ![El asignador de BizTalk](../core/media/mapper-views.gif "Mapper_Views")  
  
 La funcionalidad de cada una de las vistas es la siguiente:  
  
- **Cinta de utilidades del asignador de Visual Studio.** El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] asignador proporciona una cinta de utilidades para desplazarse de los comandos relacionados con el asignador. La cinta proporciona información del esquema de origen, un botón de alternancia para la vista de relevancia de los esquemas de origen y destino, un botón de alternancia para mostrar u ocultar los vínculos que estén totalmente fuera del ámbito, un conmutador para activar o desactivar el desplazamiento automático, un botón para aplicar una panorámica de la superficie del Asignador, controles para acercar o alejar y el cuadro de texto de búsqueda. En la siguiente ilustración se muestra la cinta de utilidades que se puede ver en la parte superior de la página de cuadrícula.  
  
   ![Cinta del asignador](../core/media/mapper-ribbon.gif "Mapper_Ribbon")  
  
- **Vista de árbol de esquema de origen.** Esta vista comparte la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con la vista de árbol del esquema de origen y la vista de cuadrícula.  
  
   Como sugiere su nombre, esta vista muestra el esquema que describe los mensajes de instancia que son el origen de la asignación. Los vínculos que definen la asignación abarcan desde la vista de árbol del esquema de origen hasta la vista de cuadrícula y, en última instancia, hasta la vista de árbol del esquema de destino.  
  
   Para obtener más información acerca de cómo se representan los esquemas de BizTalk en una vista de árbol de esquema, vea [representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md).  
  
- **Vista de árbol de esquema de destino.** Esta vista comparte la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con la vista de árbol del esquema de destino y la vista de cuadrícula.  
  
   Como sugiere su nombre, esta vista muestra el esquema que describe los mensajes de instancia que son el destino de la asignación. Los vínculos que definen la asignación llevan a la vista de árbol del esquema de destino desde la vista de cuadrícula y, en última instancia, desde la vista de árbol del esquema de origen.  
  
   Para obtener más información acerca de cómo se representan los esquemas de BizTalk en una vista de árbol de esquema, vea [representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md).  
  
- **Vista de cuadrícula.** Esta vista comparte la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] con la vista de árbol del esquema de origen y la vista de árbol del esquema de destino, con la vista de árbol del esquema de origen a la izquierda y la vista de árbol del esquema de destino a la derecha.  
  
   Como sugiere su nombre, esta vista desempeña un papel fundamental en la definición de asignaciones, puesto que contiene los vínculos y functoids que controlan cómo se transforman los datos de un mensaje de instancia de origen en un mensaje de instancia que se ajuste al esquema de destino.  
  
   La vista de cuadrícula puede tener varias capas, denominadas páginas de cuadrícula, que le permiten organizar asignaciones complejas en subdivisiones lógicas de asignaciones. Las páginas de cuadrícula suelen ocupar más espacio del que puede mostrarse de una vez. Además, existen varias formas efectivas de desplazarse en una página de cuadrícula.  
  
   En esta vista se trabaja activamente para construir la asignación.  
  
- **Ventana Visual Studio del cuadro de herramientas.** Esta vista se utiliza para ver los functoids que están disponibles para utilizarse en asignaciones de BizTalk, y como origen de las operaciones de arrastrar y colocar para situar functoids en una página de cuadrícula.  
  
   Los functoids mostrados en el cuadro de herramientas se organizan según sus categorías. Para obtener más información acerca de los functoids disponibles, consulte [Functoids en asignaciones](../core/functoids-in-maps.md). Consulte también el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
- **Ventana Visual Studio propiedades.** Esta vista (y los cuadros de diálogo asociados) se utiliza para examinar y establecer las propiedades de los vínculos y functoids que cree para definir la asignación.  
  
   Al seleccionar un vínculo o functoid en una página de cuadrícula en la vista de cuadrícula, seleccione un nodo de esquema en las vistas de árbol de esquema de origen o destino, o seleccione una asignación en el **el Explorador de soluciones** ventana; las propiedades correspondientes de ese vínculo, functoid, nodo de esquema o asignación aparecen en la **propiedades** ventana mediante las convenciones estándar de Visual Studio. Por ejemplo, las propiedades se agrupan en categorías y pueden mostrarse según estas categorías o alfabéticamente.  
  
   Para obtener información detallada sobre los distintos conjuntos de propiedades que están disponibles para vínculos, functoids, nodos de esquema o la propia asignación, vea el **referencia de asignación de propiedad** y **referencia de esquema de propiedad**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
- **Ventanas de lista de tareas de Studio y resultados visuales.** Estas vistas se utilizan para examinar los resultados de la validación, compilación y comprobación de las asignaciones de BizTalk de la misma manera que se utilizan cuando se compila el código fuente y se generan otro tipo de proyectos.  
  
  Además de estas vistas, puede interactuar con varios cuadros de diálogo. Generalmente abrirá estos cuadros de diálogo cuando esté editando una propiedad compleja, como los parámetros de entrada de un functoid.  
  
  A menudo utiliza la ventana Explorador de soluciones al mismo tiempo que el Asignador de BizTalk. Por ejemplo, para crear una nueva asignación, haga clic en el proyecto de BizTalk en el **el Explorador de soluciones** ventana, haga clic en **agregar**, haga clic en **Agregar nuevo elemento**y, a continuación, utilice el  **Agregar nuevo elemento** cuadro de diálogo para nombrar y crear una nueva asignación.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Uso de comandos del Asignador de BizTalk](../core/using-biztalk-mapper-commands.md)  
  
-   [Trabajar con páginas de cuadrícula](../core/working-with-grid-pages.md)  
  
-   [Cómo administrar vistas](../core/how-to-manage-views.md)  
  
-   [Cómo personalizar los colores y fuentes en el asignador de BizTalk](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [Cómo expandir y contraer los árboles de esquema](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [Cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [Cómo buscar elementos de asignación](../core/how-to-search-for-map-items.md)  
  
-   [Uso de características mejoradas en el Asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [Visualización de recuadros informativos e información sobre herramientas](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo optimizar la visualización de vínculos](../core/how-to-optimize-the-display-of-links.md)
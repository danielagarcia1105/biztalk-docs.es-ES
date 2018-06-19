---
title: Cómo administrar la vista de árbol de esquema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97fb7a88-e38a-4abb-93bc-a5be1bd091e6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f84ba68cd515c673daaac2e2ca96bb0e2346ecbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254908"
---
# <a name="how-to-manage-the-schema-tree-view"></a>Cómo administrar la vista de árbol de esquema
Tareas de administración con respecto a la vista de árbol de esquema pueden dividirse en cuatro categorías: cambiar el tamaño, cambiar el color de fondo y la fuente, cambiar su uso de los cuadros de diálogo de advertencia y expandir y contraer la estructura del árbol. Este tema proporciona instrucciones paso a paso para esta serie de tareas.  
  
### <a name="to-make-the-schema-tree-view-taller-or-shorter"></a>Para hacer que la vista de árbol de esquema sea más alta o baja  
  
1.  Mueva el puntero del mouse hasta el borde inferior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la que se presenta la vista XSD y la vista de árbol de esquema en paralelo, hasta que el cursor cambie al icono de ajuste de tamaño vertical de ventana estándar.  
  
2.  Haga clic y mantenga presionado el botón primario del mouse y arrastre el borde de la ventana hacia arriba o hacia abajo.  
  
     Ha cambiado el tamaño vertical de la vista de árbol de esquema al ajustar el tamaño vertical de toda la ventana de edición principal.  
  
### <a name="to-make-the-schema-tree-view-wider-or-more-narrow"></a>Para hacer que la vista de árbol de esquema sea más ancha o más estrecha  
  
1.  Mueva el puntero del mouse hasta el divisor de panel en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] la ventana de edición principal, que divide la vista de árbol de esquema de la vista XSD, hasta que el cursor cambie al icono de cambio de tamaño horizontal de ventana estándar.  
  
2.  Haga clic y mantenga presionado el botón primario del mouse y arrastre el borde del panel hacia la izquierda (más estrecho) o hacia la derecha (más ancho).  
  
     Ha cambiado el tamaño horizontal de la vista de árbol de esquema al cambiar la parte de la ventana de edición principal que se dedica a la vista de árbol de esquema con respecto a la vista XSD.  
  
     También puede hacer que la vista de árbol de esquema sea más ancha o estrecha al ajustar el tamaño horizontal de toda la ventana de edición principal.  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-schema-tree-view"></a>Para cambiar el color de fondo o la fuente utilizados por la vista de árbol de esquema  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.  
  
2.  En el **opciones** cuadro de diálogo, haga clic en la carpeta Editor de BizTalk y, si es necesario, expanda el **Mostrar esquema** categoría haciendo clic en el signo más (+) icono.  
  
3.  Cambiar el color de fondo o la fuente mediante el selector de colores de la lista desplegable o **fuente** cuadro de diálogo asociado con el **Color de fondo de árbol de esquema** y **fuente de árbol de esquema**propiedades, respectivamente.  
  
     Acceso a la **fuente** cuadro de diálogo mediante el uso de los puntos suspensivos (**...** ) situado en el extremo derecho de la **fuente de árbol de esquema** cuadro de valor de propiedad.  
  
### <a name="to-change-the-warning-dialogs-used-when-working-in-the-schema-tree-view"></a>Para cambiar los cuadros de diálogo de advertencia utilizados cuando se trabaja en la vista de árbol de esquema  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el menú **Herramientas** , haga clic en **Opciones**.  
  
2.  En el **opciones** cuadro de diálogo, haga clic en el **el Editor de BizTalk** carpeta y si es necesario, expanda el **opciones de edición** sección haciendo clic en el signo más (+) icono.  
  
3.  Defina cualquiera de las siguientes propiedades en **True** o **False** mediante la lista desplegable en el borde derecho del cuadro de valor de propiedad respectiva.  
  
    > [!NOTE]
    >  El valor **True** es el valor predeterminado para las tres opciones del cuadro de diálogo de advertencia.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |**Mostrar destruir el cuadro de diálogo de advertencia de estructura**|Cuando se establece en **True**, muestra un cuadro de diálogo de advertencia antes de que se destruye la estructura del esquema y permite cancelar la operación de destrucción.|  
    |**Mostrar el cuadro de diálogo de advertencia de codificar**|Cuando se establece en **True**, muestra un cuadro de diálogo cuando el nombre del nodo que ha escrito no es válido en XML a menos que codificar, lo que permite cancelar la operación de asignación de nombres, o continuar con la codificación del nombre.|  
    |**Mostrar el cuadro de diálogo de inserción no válida**|Cuando se establece en **True**, muestra un cuadro de diálogo de advertencia para determinados errores de inserción de nodo y ofrece opciones sobre cómo continuar. Los errores posibles de inserción de nodo son:<br /><br /> -Crear duplicados **atributo de campo** nodos con el mismo nombre y el mismo nodo primario.<br />-Crear duplicados **registro** nodos con el mismo nombre y el mismo nodo primario, pero con diferentes tipos subyacentes.|  
  
### <a name="to-completely-expand-all-or-part-of-the-schema-tree"></a>Para expandir completamente una parte o la totalidad de un árbol de esquema  
  
-   Seleccione el nodo en el que desea expandir completamente el árbol de esquema.  
  
     El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).  
  
     En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Expandir nodo de esquema**. Todos los nodos situados por debajo del nodo seleccionado se expandirán completamente. Si el árbol de esquema debajo del nodo seleccionado ya está completamente expandido, el **Expandir nodo de esquema** elemento de menú estará atenuado.  
  
    > [!NOTE]
    >  En un esquema grande y complejo, al hacer clic en **Expandir nodo de esquema** en un nodo que contenga tipos complejos, algunos nodos en el esquema pueden permanecer en el estado contraído. Esto se debe a que el proceso recursivo expande solo el primer caso de un tipo complejo determinado. Deberá expandir manualmente los casos posteriores del mismo tipo. Este comportamiento está diseñado para optimizar el rendimiento a la hora de expandir nodos en esquemas grandes y complejos.  
  
### <a name="to-completely-collapse-all-or-part-of-the-schema-tree"></a>Para contraer completamente una parte o la totalidad de un árbol de esquema  
  
1.  Seleccione el nodo en el que desea contraer completamente el árbol de esquema.  
  
     El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).  
  
2.  En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Contraer nodo de esquema**.  
  
     Todos los nodos situados por debajo del nodo seleccionado se contraerán completamente.  
  
    > [!NOTE]
    >  Si el árbol de esquema debajo del nodo seleccionado ya está contraído, el **Contraer nodo de esquema** elemento de menú estará atenuado.  
  
    > [!NOTE]
    >  Esta operación no recordará la configuración individual de expansión o contracción de los nodos situados por debajo del nodo seleccionado. Es decir, cuando vuelva a expandir un nodo contraído, la configuración individual previa se pierde y debe expandir el árbol de esquema situado por debajo de ese punto nodo por nodo, o bien expandirlo por completo.  
  
### <a name="to-expand-a-node-of-the-schema-tree"></a>Para expandir un nodo del árbol de esquema  
  
-   Haga clic en el icono más (+) que se encuentra junto al nodo que desea expandir.  
  
    > [!NOTE]
    >  El nodo seleccionado se expande. El hecho de que los nodos descendentes se expandan o contraigan dependerá de cómo se contrajo el nodo seleccionado y de la configuración de expansión y contracción previa.  
  
### <a name="to-collapse-a-node-of-the-schema-tree"></a>Para contraer un nodo del árbol de esquema  
  
-   Haga clic en el icono menos (-) que se encuentra junto al nodo que desea contraer.  
  
    > [!NOTE]
    >  El nodo seleccionado se contrae.  
  
    > [!NOTE]
    >  Esta operación recordará la configuración individual de expansión o contracción de los nodos situados por debajo del nodo seleccionado. Es decir, cuando vuelva a expandir mediante el icono más (+) el nodo contraído, la configuración individual previa no se pierde y el árbol de esquema situado por debajo de ese punto recupera su estado previo de expansión o contracción.  
  
## <a name="see-also"></a>Vea también  
 [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)
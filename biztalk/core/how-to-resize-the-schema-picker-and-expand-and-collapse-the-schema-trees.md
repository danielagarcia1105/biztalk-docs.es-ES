---
title: Cómo cambiar el tamaño del selector de esquema y expandir y contraer los árboles de esquema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972be8ca5f412c39e1eb6fa2c81ccd9a21e65a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254820"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a>Cómo cambiar el tamaño del selector de esquema y expandir y contraer los árboles de esquema
Al desarrollar asignaciones de BizTalk, es probable que necesite expandir y contraer los árboles de esquema de origen y de destino para mostrar u ocultar los diversos nodos de esquema. Este tema proporciona instrucciones paso a paso para cambiar el tamaño del selector de esquema y para expandir y contraer el árbol de esquema.  

## <a name="resize-the-schema-picker"></a>Cambiar el tamaño del selector de esquema

Cuando se crea un mapa, agrega un esquema de origen y un esquema de destino. Al agregar o reemplazar un esquema, se abre la ventana del selector de tipos de BizTalk y seleccione el esquema. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de esta ventana de selector de tipos. Esta característica permite ver el nombre completo del esquema.

1. En el mapa, seleccione **Abrir esquema de destino**, o **Abrir esquema de origen**.
2. En el **selector de tipos de BizTalk** ventana, arrastre la esquina inferior derecha esquina para aumentar o disminuir el tamaño de la ventana.
  
## <a name="expand-all-or-part-of-a-schema-tree"></a>Expandir todo o parte de un árbol de esquema  
  
1.  Seleccione el nodo en el que desea expandir completamente el árbol de esquema.  
  
     El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).  
  
2.  En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Expandir nodo de árbol**. Todos los nodos situados por debajo del nodo seleccionado se expandirán completamente.  
  
     Si el árbol de esquema debajo del nodo seleccionado ya está completamente expandido, el **Expandir nodo de árbol** elemento de menú está deshabilitado.  
  
    > [!NOTE]
    >  Como alternativa, puede presionar CTRL+M, E para expandir los nodos del árbol de esquema. Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
    > [!NOTE]
    >  En un esquema grande y complejo, al hacer clic en **Expandir nodo de árbol** en un nodo que contenga tipos complejos, algunos nodos en el esquema pueden permanecer en el estado contraído. Esto se debe a que el proceso recursivo expande solo el primer caso de un tipo complejo determinado. Deberá expandir manualmente los casos posteriores del mismo tipo. Este comportamiento está diseñado para optimizar el rendimiento a la hora de expandir nodos en esquemas grandes y complejos.  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a>Contraer todo o parte de un árbol de esquema  
  
1.  Seleccione el nodo en el que desea contraer completamente el árbol de esquema.  
  
     El nodo seleccionado debe tener junto a él un icono más (+) o menos (-).  
  
2.  En el **BizTalk** menú, o en el menú contextual para ese nodo, haga clic en **Contraer nodo de árbol**.  
  
     Todos los nodos situados por debajo del nodo seleccionado se contraerán completamente.  
  
    > [!NOTE]
    >  Como alternativa, puede presionar CTRL+M, C para contraer los nodos del árbol de esquema. Para obtener una lista de métodos abreviados de teclado, consulte [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
     Si el árbol de esquema debajo del nodo seleccionado ya está contraído, el **Contraer nodo de árbol** elemento de menú está deshabilitado.  
  
 Esta operación no recordará la configuración individual de expansión o contracción de los nodos situados por debajo del nodo seleccionado. Cuando vuelva a expandir un nodo contraído, la configuración previa se pierde y debe expandir el árbol de esquema situado por debajo de ese punto nodo por nodo, o bien expandirlo por completo.  
  
### <a name="expand-a-node"></a>Expanda un nodo
  
-   Haga clic en el icono más (+) que se encuentra junto al nodo que desea expandir.  
  
 Se expande el nodo seleccionado. El hecho de que sus nodos descendentes se expandan o contraigan dependerá de cómo se contrajo el nodo seleccionado y de su configuración de expansión y contracción previa.  
  
### <a name="collapse-a-node"></a>Contraer un nodo
  
-   Haga clic en el icono menos (-) que se encuentra junto al nodo que desea contraer.  
  
 Se contrae el nodo seleccionado.  
  
 Esta operación se recuerde la individual de expansión y contraer la configuración de los nodos situados por debajo del nodo seleccionado. Cuando vuelva a expandir mediante el icono más (+) un nodo contraído, la configuración individual previa no se pierde y el árbol de esquema situado por debajo de ese punto recupera su estado previo.  
  
## <a name="see-also"></a>Vea también  
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)
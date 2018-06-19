---
title: Cómo mover y copiar nodos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254772"
---
# <a name="how-to-move-and-copy-nodes"></a>Cómo mover y copiar nodos
Es probable que en determinadas situaciones desee mover un nodo existente a otra ubicación en el árbol de esquema. Asimismo, puede ahorrar tiempo si copia un nodo existente y luego lo pega en una ubicación diferente en el árbol de esquema. Este tema proporciona instrucciones paso a paso para realizar estas tareas.  
  
> [!NOTE]
>  El Editor de BizTalk es compatible con copiar y pegar nodos solo dentro de los esquemas, no entre los esquemas.  
  
### <a name="to-move-a-node-within-a-schema"></a>Para mover un nodo dentro de un esquema  
  
1.  Si es necesario, expanda el árbol de esquema para mostrar tanto el nodo que está moviendo como la ubicación a la que desea moverlo. Para obtener más información acerca de cómo expandir y contraer la vista de árbol de esquema, consulte [administrar la vista de árbol de esquema](../core/how-to-manage-the-schema-tree-view.md).  
  
2.  Haga clic en el nodo que desea mover y, sin soltar el mouse, arrástrelo a otra ubicación del árbol.  
  
> [!NOTE]
>  Cuando empiece a arrastrar el nodo arriba y abajo en el árbol de esquema, el puntero del mouse cambiará a una flecha arriba, abajo o de elemento secundario. Esta flecha indica la ubicación en la que se colocará el nodo al soltar el botón del mouse, que puede ser antes del nodo, después del nodo o como secundario del nodo.  
  
#### <a name="to-copy-a-node-within-a-schema"></a>Para copiar un nodo dentro de un esquema  
  
1.  Haga clic en el nodo que desea copiar y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en el **registro** nodo o grupo en el que desea insertar el nodo copiado y, a continuación, haga clic en **pegar**.  
  
     La copia del nodo copiado se coloca al final de los nodos secundarios de la **registro** nodo o grupo seleccionado en el paso 2.  
  
> [!NOTE]
>  Únicamente puede usar la funcionalidad de cortar, copiar y pegar dentro de un esquema individual; es decir, no puede copiar nodos de un esquema a otro.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con nodos existentes](../core/working-with-existing-nodes.md)
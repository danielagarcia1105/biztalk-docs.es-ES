---
title: Cómo optimizar la vista de árbol de esquema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeeddd0893b80c1c7b37b2d0ee5f9f6cd68849d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-optimize-the-schema-tree-view"></a>Optimización de la vista del árbol de esquema
Puede usar el **la vista de relevancia** en el asignador de BizTalk para optimizar el origen o árboles de esquema de destino. En este tema se proporcionan instrucciones sobre cómo realizar la operación.  
  
 La vista Relevancia usa coalescencia del mismo nivel para contraer elementos de esquema no pertinentes y proporcionar así una vista más compacta del esquema. Esto reduce más la necesidad de desplazamiento y le ayuda a centrarse en el uso de los esquemas y asignaciones.  
  
 La siguiente ilustración muestra un esquema cuando la vista Relevancia está desactivada. El panel de esquema muestra todos los nodos, independientemente de si forman parte de alguna relación o no.  
  
 ![Esquema cuando la vista de relevancia está desactivada](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")  
  
 Haga clic en el ![cambie a la vista de relevancia](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icono en la cinta de utilidades del asignador para activar la vista de relevancia. Puede cambiar a la vista Relevancia para el esquema de origen y o de destino, o para ambos; para ello, haga clic en los iconos correspondientes a los esquemas de origen y destino.  
  
 Cuando cambia a la vista Relevancia para un esquema:  
  
-   Se contraen todos los elementos de registro que no tienen vínculos ni para ellos ni para sus elementos de campo secundarios.  
  
-   Todos los nodos sucesivos que no tienen ningún vínculo se combinan y se ha reemplazado por la ![fusionado nodos ocultos](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icono. El Asignador de BizTalk busca un mínimo de dos nodos no relevantes sucesivos que se puedan combinar. Puede mover el mouse sobre el icono para ver la lista de nodos combinados. Tenga en cuenta que el recuadro informativo únicamente enumera los nombres de los tres primeros nodos combinados, aunque haya más. Puede ver todos los nodos, haga clic en el ![fusionado nodos ocultos](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icono.  
  
    > [!NOTE]
    >  Para obtener más información sobre el recuadro informativo, consulte [cómo Recuadro informativo de vista y la información sobre herramientas](../core/how-to-view-infotip-and-tooltip.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Esta operación requiere que se está ejecutando el Asignador de BizTalk.  
  
## <a name="to-optimize-the-schema-tree-view"></a>Procedimiento para optimizar la vista de árbol de esquema  
 En la cinta de opciones de la utilidad asignador, activar la vista de relevancia para esquemas de origen o destino haciendo clic en los respectivos ![cambie a la vista de relevancia](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") iconos. La ilustración siguiente muestra el mismo esquema cuando se activa la vista Relevancia. Todos los nodos no pertinentes se sustituyen por los ![fusionado nodos ocultos](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icono para proporcionar una vista más compacta del esquema.  
  
 ![Esquema cuando la vista de relevancia está activada](../core/media/on-schema.gif "On_schema")  
  
 Cuando se expande los nodos combinados en esquemas de origen o destino, el ![fusionado nodos ocultos](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") cambia a ![fusionado nodos se muestra] (../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence") icono.  
  
> [!NOTE]
>  Puede presionar CTRL+M, CTRL+E o CTRL+M, CTRL+C para expandir o contraer los tres nodos en el esquema de origen, respectivamente. De manera similar, puede presionar CTRL+M, CTRL+E o CTRL+M, CTRL+C para expandir o contraer los tres nodos en el esquema de destino, respectivamente. También puede presionar CTRL+M, CTRL+H o CTRL+M, CTRL+D para la fusión de origen o de destino, respectivamente. Para obtener una lista de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)
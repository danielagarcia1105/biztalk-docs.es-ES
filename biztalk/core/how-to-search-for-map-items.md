---
title: Cómo buscar elementos de asignación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.search
ms.assetid: 3dbb089a-6aa8-4921-a82d-81d3a193e933
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61bccfae53a79d8fba6bd0aa5af2c537d98270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-map-items"></a>Cómo buscar elementos de asignación
El Asignador de BizTalk le permite buscar elementos en el esquema de origen, en el de destino y en la superficie de la cuadrícula. Este tema proporciona información acerca de cómo realizar esta operación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
## <a name="to-search-for-items"></a>Procedimiento para buscar elementos  
 Seleccione el esquema donde desea buscar. Si selecciona el esquema de origen, el Asignador de BizTalk busca la coincidencia únicamente en el esquema de origen. Sin embargo, puede seleccionar tanto el esquema de origen como el de destino.  
  
> [!NOTE]
>  Para confirmar la selección, busque la marca delante del esquema o del elemento de esquema.  
  
 ![Búsqueda de elementos de mapa](../core/media/searching-map-items.gif "Searching_map_items")  
  
 En el **búsqueda** en la cinta de utilidades del asignador, escriba el nombre del elemento que va a buscar. Puede buscar una cadena en el nombre de un nodo en el esquema de origen o destino, así como en el nombre, la etiqueta, el comentario, las entradas o los scripts de functoids.  
  
 A medida que escribe la cadena de búsqueda, se resaltan los objetos que cumplen los criterios de búsqueda. Puede desplazarse por los resultados de búsqueda de claves usando la flecha en el teclado o el ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") y ![mover hacia abajo en una lista] (../core/media/move-down-button.gif " Move_down_button") iconos en la cinta de utilidades. Si los resultados de la búsqueda están distribuidos por las tres vistas, los resultados de la búsqueda se recorren en el siguiente orden: esquema de origen, vista de relación y esquema de destino. Después de revisar los resultados de búsqueda, puede cerrar la búsqueda mediante la eliminación de la cadena de búsqueda o haciendo clic en el (![Borrar búsqueda del asignador](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) icono situado junto a la cadena de búsqueda.  
  
> [!NOTE]
>  También puede presionar CTRL+M, CTRL+J o CTRL+M, CTRL+K para realizar el recorrido de los resultados de la búsqueda hacia arriba o hacia abajo, respectivamente. Para obtener una lista de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).  
  
> [!IMPORTANT]
>  Si los resultados de la búsqueda para la vista de relación no están visibles en una única vista de mapa, el Asignador de BizTalk muestra flechas que parpadean en la dirección donde hay resultados adicionales. Por ejemplo, el icono de flecha hacia arriba (![dirección para resultados de búsqueda adicionales](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) indica que no hay resultados de búsqueda adicionales que puedan verse por desplazar hacia arriba. De manera similar, si los resultados de la búsqueda se encuentran en páginas de asignación diferentes, las pestañas de dichas páginas se resaltan en amarillo. Al mover el mouse sobre la página resaltada, la información sobre herramientas muestra el número de coincidencias de búsqueda en esa página. La barra de estado muestra los resultados de la búsqueda.  
  
 ![Mostrar los resultados de búsqueda de la barra de estado](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")  
  
## <a name="see-also"></a>Vea también  
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)
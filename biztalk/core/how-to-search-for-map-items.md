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
ms.locfileid: "22255540"
---
# <a name="how-to-search-for-map-items"></a><span data-ttu-id="2e7c4-102">Cómo buscar elementos de asignación</span><span class="sxs-lookup"><span data-stu-id="2e7c4-102">How to Search for Map Items</span></span>
<span data-ttu-id="2e7c4-103">El Asignador de BizTalk le permite buscar elementos en el esquema de origen, en el de destino y en la superficie de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-103">The BizTalk Mapper enables you to search for items in the source schema, the destination schema, and the grid surface.</span></span> <span data-ttu-id="2e7c4-104">Este tema proporciona información acerca de cómo realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e7c4-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e7c4-105">Prerequisites</span></span>  
 <span data-ttu-id="2e7c4-106">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-search-for-items"></a><span data-ttu-id="2e7c4-107">Procedimiento para buscar elementos</span><span class="sxs-lookup"><span data-stu-id="2e7c4-107">To search for items</span></span>  
 <span data-ttu-id="2e7c4-108">Seleccione el esquema donde desea buscar.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-108">Select the schema where you want to search.</span></span> <span data-ttu-id="2e7c4-109">Si selecciona el esquema de origen, el Asignador de BizTalk busca la coincidencia únicamente en el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-109">If you select source schema, the BizTalk Mapper searches and looks for the match only in the source schema.</span></span> <span data-ttu-id="2e7c4-110">Sin embargo, puede seleccionar tanto el esquema de origen como el de destino.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-110">However, you can select both source and destination schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e7c4-111">Para confirmar la selección, busque la marca delante del esquema o del elemento de esquema.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-111">To confirm selection, look for the mark before the schema or the schema item.</span></span>  
  
 <span data-ttu-id="2e7c4-112">![Búsqueda de elementos de mapa](../core/media/searching-map-items.gif "Searching_map_items")</span><span class="sxs-lookup"><span data-stu-id="2e7c4-112">![Searching for map items](../core/media/searching-map-items.gif "Searching_map_items")</span></span>  
  
 <span data-ttu-id="2e7c4-113">En el **búsqueda** en la cinta de utilidades del asignador, escriba el nombre del elemento que va a buscar.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-113">In the **Search** box on the Mapper utility ribbon, type the name of the item you want to search.</span></span> <span data-ttu-id="2e7c4-114">Puede buscar una cadena en el nombre de un nodo en el esquema de origen o destino, así como en el nombre, la etiqueta, el comentario, las entradas o los scripts de functoids.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-114">You can search for a string in the name of a node in the source or destination schema, as well as in the name, label, comment, inputs, or scripts for functoids.</span></span>  
  
 <span data-ttu-id="2e7c4-115">A medida que escribe la cadena de búsqueda, se resaltan los objetos que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-115">As you enter the search string, the objects that meet the search criteria are highlighted.</span></span> <span data-ttu-id="2e7c4-116">Puede desplazarse por los resultados de búsqueda de claves usando la flecha en el teclado o el ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") y ![mover hacia abajo en una lista] (../core/media/move-down-button.gif " Move_down_button") iconos en la cinta de utilidades.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-116">You can then traverse through the search results either using the arrow keys on the keyboard or the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") and ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") icons on the utility ribbon.</span></span> <span data-ttu-id="2e7c4-117">Si los resultados de la búsqueda están distribuidos por las tres vistas, los resultados de la búsqueda se recorren en el siguiente orden: esquema de origen, vista de relación y esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-117">If the search results are spread across all three views, the search results are traversed in the order of the source schema, relationship view, and the destination schema.</span></span> <span data-ttu-id="2e7c4-118">Después de revisar los resultados de búsqueda, puede cerrar la búsqueda mediante la eliminación de la cadena de búsqueda o haciendo clic en el (![Borrar búsqueda del asignador](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) icono situado junto a la cadena de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-118">After going through the search results, you can close the search either by deleting the search string or by clicking the (![Clear Mapper search](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) icon next to the search string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e7c4-119">También puede presionar CTRL+M, CTRL+J o CTRL+M, CTRL+K para realizar el recorrido de los resultados de la búsqueda hacia arriba o hacia abajo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-119">You can also press CTRL+M, CTRL+J or CTRL+M, CTRL+K to traverse through the search results upwards or downwards, respectively.</span></span> <span data-ttu-id="2e7c4-120">Para obtener una lista de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="2e7c4-120">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e7c4-121">Si los resultados de la búsqueda para la vista de relación no están visibles en una única vista de mapa, el Asignador de BizTalk muestra flechas que parpadean en la dirección donde hay resultados adicionales.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-121">If the search results for the relationship view are not visible in a single map view, the BizTalk Mapper displays blinking arrows in the direction where there are additional hits.</span></span> <span data-ttu-id="2e7c4-122">Por ejemplo, el icono de flecha hacia arriba (![dirección para resultados de búsqueda adicionales](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) indica que no hay resultados de búsqueda adicionales que puedan verse por desplazar hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-122">For example, the top arrow icon (![Direction for additional search results](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) denotes that there are additional search results that can be viewed by scrolling up.</span></span> <span data-ttu-id="2e7c4-123">De manera similar, si los resultados de la búsqueda se encuentran en páginas de asignación diferentes, las pestañas de dichas páginas se resaltan en amarillo.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-123">Similarly, if there are search results in different map pages, the page tabs for those pages are highlighted, in yellow.</span></span> <span data-ttu-id="2e7c4-124">Al mover el mouse sobre la página resaltada, la información sobre herramientas muestra el número de coincidencias de búsqueda en esa página.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-124">On moving the mouse over the highlighted page, the tooltip displays the number of search matches on that page.</span></span> <span data-ttu-id="2e7c4-125">La barra de estado muestra los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e7c4-125">The status bar displays the search results.</span></span>  
  
 <span data-ttu-id="2e7c4-126">![Mostrar los resultados de búsqueda de la barra de estado](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span><span class="sxs-lookup"><span data-stu-id="2e7c4-126">![Status bar displaying the search results](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7c4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e7c4-127">See Also</span></span>  
 [<span data-ttu-id="2e7c4-128">Con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2e7c4-128">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)
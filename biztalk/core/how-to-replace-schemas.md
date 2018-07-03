---
title: Cómo reemplazar esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8aaca705c54866ec6323d7c26a5fe7b731129e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022530"
---
# <a name="how-to-replace-schemas"></a><span data-ttu-id="31312-102">Cómo reemplazar esquemas</span><span class="sxs-lookup"><span data-stu-id="31312-102">How to Replace Schemas</span></span>
<span data-ttu-id="31312-103">Puede que en algún momento desee reemplazar el esquema de origen o el de destino en una asignación existente, como cuando recibe un esquema actualizado de un socio comercial.</span><span class="sxs-lookup"><span data-stu-id="31312-103">There may be times when you want to replace either the source or destination schema in an existing map, such as when you receive an updated schema from a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31312-104">El Asignador de BizTalk intenta mantener todos los vínculos existentes entre el esquema que se conserva y el que se reemplaza.</span><span class="sxs-lookup"><span data-stu-id="31312-104">The BizTalk Mapper attempts to maintain all existing links between the retained schema and the replaced schema.</span></span>  
  
## <a name="replace-a-source-or-destination-schema"></a><span data-ttu-id="31312-105">Reemplazar un esquema de origen o destino</span><span class="sxs-lookup"><span data-stu-id="31312-105">Replace a source or destination schema</span></span>  
  
1. <span data-ttu-id="31312-106">Haga clic en vista de árbol de esquema de origen o destino y, a continuación, seleccione **Reemplazar esquema**.</span><span class="sxs-lookup"><span data-stu-id="31312-106">Right-click either the source or destination schema tree view, and then select **Replace Schema**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="31312-107">Como alternativa, también puede presionar CTRL+M o CTRL+S del teclado.</span><span class="sxs-lookup"><span data-stu-id="31312-107">Alternatively, you can also press CTRL+M, CTRL+S from the keyboard.</span></span> <span data-ttu-id="31312-108">Para obtener una lista completa de métodos abreviados de teclado del asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="31312-108">For a complete list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
2. <span data-ttu-id="31312-109">En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo en el árbol, seleccione el esquema apropiado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31312-109">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node in the tree, select the appropriate schema, and then select **OK**.</span></span>  
  
    <span data-ttu-id="31312-110">![Seleccione el esquema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span><span class="sxs-lookup"><span data-stu-id="31312-110">![Select the Schema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span></span>  

   > [!TIP]
   > <span data-ttu-id="31312-111">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , puede cambiar el tamaño de la ventana del selector de tipo para ver el nombre completo del esquema.</span><span class="sxs-lookup"><span data-stu-id="31312-111">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
      
    <span data-ttu-id="31312-112">Si solo existe una raíz en el esquema de reemplazo, o se ha establecido un nodo de raíz para el esquema de reemplazo mediante la **referencia raíz** propiedad de la **esquema** abre el nodo, el esquema de reemplazo en el panel correspondiente, y no tendrá que realizar el paso 3.</span><span class="sxs-lookup"><span data-stu-id="31312-112">If only a single root exists in the replacement schema, or a root node has been established for the replacement schema using the **Root Reference** property of the **Schema** node, the replacement schema opens in the relevant pane, and you will not need to perform step 3.</span></span>  
  
3. <span data-ttu-id="31312-113">Si existen múltiples nodos raíz del esquema de destino, y no se ha establecido ningún nodo de raíz para el esquema de destino mediante el **referencia raíz** propiedad de la **esquema** nodo, en el **raíz Nodo de \< *origen/destino* \> esquema** cuadro de diálogo, seleccione el nodo raíz apropiado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31312-113">If multiple root nodes exist in the destination schema, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for \<*Source/Target*\> Schema** dialog box, select the appropriate root node, and then select **OK**.</span></span>  
  
    <span data-ttu-id="31312-114">El esquema de reemplazo se abre en el panel correspondiente.</span><span class="sxs-lookup"><span data-stu-id="31312-114">The replacement schema opens in the relevant pane.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="31312-115">Mientras se reemplaza el esquema, si no se encuentran los registros/campos relevantes, pueden perderse algunos vínculos.</span><span class="sxs-lookup"><span data-stu-id="31312-115">While replacing schema, if relevant records/fields are not found, some links may get lost.</span></span> <span data-ttu-id="31312-116">El esquema se sustituirá solo cuando se selecciona **Sí** en el **confirmación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="31312-116">The schema is replaced only when you select **Yes** on the **Confirmation**  dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31312-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="31312-117">See Also</span></span>  
 [<span data-ttu-id="31312-118">Administración de asignaciones en proyectos</span><span class="sxs-lookup"><span data-stu-id="31312-118">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)
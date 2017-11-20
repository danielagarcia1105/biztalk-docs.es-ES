---
title: "Cómo administrar vínculos existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0db213b9-df84-4ebd-a59f-7691774d5031
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e61bc8c7fbf015eba28666c63dbeabf57a39e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-existing-links"></a><span data-ttu-id="97ca7-102">Cómo administrar vínculos existentes</span><span class="sxs-lookup"><span data-stu-id="97ca7-102">How to Manage Existing Links</span></span>
<span data-ttu-id="97ca7-103">A veces puede que necesite cambiar el origen o el destino de un vínculo, asignar o cambiar su nombre o bien eliminar un vínculo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-103">Sometimes you may need to change the source or destination of a link, name or rename a link, or delete a link.</span></span> <span data-ttu-id="97ca7-104">En este tema se proporcionan instrucciones detalladas para llevar a cabo estas operaciones de tipos de vínculo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-104">This topic provides step-by-step instructions for performing these types of link operations.</span></span>  
  
### <a name="to-change-the-source-or-destination-of-a-link"></a><span data-ttu-id="97ca7-105">Para modificar el origen o el destino de un vínculo</span><span class="sxs-lookup"><span data-stu-id="97ca7-105">To change the source or destination of a link</span></span>  
  
1.  <span data-ttu-id="97ca7-106">En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="97ca7-107">Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="97ca7-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="97ca7-108">Arrastre cualquier extremo del vínculo al nuevo nodo de esquema o functoid con el que desea conectarlo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-108">Drag either endpoint of the link to the new schema node or functoid to which you want it to connect it.</span></span>  
  
     <span data-ttu-id="97ca7-109">Cuando arrastre el extremo, el cursor se convertirá en una cruz.</span><span class="sxs-lookup"><span data-stu-id="97ca7-109">As you drag an endpoint, the cursor becomes a crosshair.</span></span> <span data-ttu-id="97ca7-110">Si selecciona un nodo de esquema o functoid (u otro objeto) que no puede aceptar el vínculo, el cursor se convierte en un círculo con una barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="97ca7-110">If you point to a schema node or functoid (or other object) which cannot accept the link, the cursor becomes a circle with a line through it.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="97ca7-111">Si hay dos o más vínculos de entrada conectados con un functoid y redirige uno o más de estos vínculos de entrada a otros nodos del esquema de origen o a otros functoids, el orden de los parámetros de entrada al functoid original puede que no se conserve.</span><span class="sxs-lookup"><span data-stu-id="97ca7-111">If you have two or more input links connected to a functoid and you redirect one or more of those input links to other nodes in the source schema or to other functoids, the order of the input parameters to the original functoid may not be preserved.</span></span> <span data-ttu-id="97ca7-112">Use la **configurar \<Functoid > Functoid** cuadro de diálogo para revisar el orden resultante de los parámetros de entrada y para reordenarlos si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="97ca7-112">Use the **Configure \<Functoid> Functoid** dialog box to review the resulting order of the input parameters and to reorder them if necessary.</span></span> <span data-ttu-id="97ca7-113">Para obtener más información acerca de la reorganización de los parámetros de entrada de un functoid, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="97ca7-113">For more information about reordering the input parameters of a functoid, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span>  
  
### <a name="to-setedit-the-label-of-a-link"></a><span data-ttu-id="97ca7-114">Para configurar o editar la etiqueta de un vínculo</span><span class="sxs-lookup"><span data-stu-id="97ca7-114">To set/edit the label of a link</span></span>  
  
1.  <span data-ttu-id="97ca7-115">En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-115">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="97ca7-116">Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="97ca7-116">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="97ca7-117">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, proporcione un nombre (nuevo) para el vínculo mediante el **etiqueta** propiedad.</span><span class="sxs-lookup"><span data-stu-id="97ca7-117">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a (new) name for the link using the **Label** property.</span></span>  
  
### <a name="to-delete-a-link"></a><span data-ttu-id="97ca7-118">Para eliminar un vínculo</span><span class="sxs-lookup"><span data-stu-id="97ca7-118">To delete a link</span></span>  
  
1.  <span data-ttu-id="97ca7-119">En una página de cuadrícula del Asignador de BizTalk, haga clic en un vínculo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="97ca7-119">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="97ca7-120">Se resaltan los puntos finales de un vínculo seleccionado en la página de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="97ca7-120">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="97ca7-121">En el **editar** menú, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="97ca7-121">On the **Edit** menu, click **Delete**.</span></span>  
  
     <span data-ttu-id="97ca7-122">También puede presionar la tecla SUPR o haga clic en el vínculo y haga clic en **eliminar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="97ca7-122">You can also press the DELETE key or right-click the link and click **Delete** on the shortcut menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97ca7-123">Puede seleccionar de forma masiva varios functoids o vínculos y eliminarlos en una única operación.</span><span class="sxs-lookup"><span data-stu-id="97ca7-123">You can bulk-select multiple link(s) and/or functoid(s) and then delete them in one operation.</span></span> <span data-ttu-id="97ca7-124">Puede deshacer o rehacer la eliminación masiva de vínculos o functoids.</span><span class="sxs-lookup"><span data-stu-id="97ca7-124">You can undo or redo the bulk deletion of link(s) and/or functoid(s).</span></span> <span data-ttu-id="97ca7-125">Para obtener más información acerca de cómo deshacer y rehacer las operaciones, vea [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).</span><span class="sxs-lookup"><span data-stu-id="97ca7-125">For more information about undo and redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ca7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ca7-126">See Also</span></span>  
 [<span data-ttu-id="97ca7-127">Utilizar vínculos para especificar el registro y las asignaciones de campos</span><span class="sxs-lookup"><span data-stu-id="97ca7-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)
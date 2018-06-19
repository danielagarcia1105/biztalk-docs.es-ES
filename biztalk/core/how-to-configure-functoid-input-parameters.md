---
title: Cómo configurar los parámetros de entrada de Functoid | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab04111835e7732aa8384e1d701a15ae8d268378
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969546"
---
# <a name="how-to-configure-functoid-input-parameters"></a><span data-ttu-id="9c4bb-102">Cómo configurar parámetros de entrada de functoid</span><span class="sxs-lookup"><span data-stu-id="9c4bb-102">How to Configure Functoid Input Parameters</span></span>
<span data-ttu-id="9c4bb-103">La configuración correcta de los parámetros de entrada de los functoids en la asignación es uno de los aspectos más importantes, y que más errores potenciales puede ocasionar, al utilizar los functoids.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-103">Properly configuring the input parameters to the functoids in your map is one of the most important, and potentially error-prone, aspects of using functoids.</span></span> <span data-ttu-id="9c4bb-104">Puede configurar los parámetros de entrada de functoid como sigue:</span><span class="sxs-lookup"><span data-stu-id="9c4bb-104">You can configure the functoid input parameters as follows:</span></span>  
  
-   <span data-ttu-id="9c4bb-105">Cree vínculos de entradas visibles al conectar los nodos de esquema y los functoids respectivos (arrastre y suelte el mouse desde el nodo del esquema al functoid).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-105">Create visible input links by connecting schema nodes and respective functoids (drag-and-drop the mouse from schema node to the functoid).</span></span>  
  
-   <span data-ttu-id="9c4bb-106">Edite directamente la lista de parámetros de entrada con el **configurar \<Functoid\> Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-106">Directly edit the list of input parameters using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="9c4bb-107">En este tema se proporcionan instrucciones detalladas para configurar los parámetros de entrada de un functoid mediante estos métodos.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-107">This topic provides step-by-step instructions for configuring the input parameters for a functoid using these methods.</span></span>  
  
 <span data-ttu-id="9c4bb-108">El método de arrastrar para establecer parámetros de entrada de functoid es una manera adecuada de especificar parámetros de entrada que implican especificaciones de XPath en el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-108">The dragging method of establishing functoid input parameters provides a convenient way to specify input parameters that involve XPath specifications into the source schema.</span></span> <span data-ttu-id="9c4bb-109">Para obtener información acerca de cómo crear un esquema de parámetros de entrada de functoid y nodo, consulte [cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-109">For information on creating a schema node and functoid input parameters, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="9c4bb-110">Sin embargo, el **configurar \<Functoid\> Functoid** cuadro de diálogo es el mecanismo definitivo para ver todos los parámetros de entrada a un functoid, para crear y modificar cualquier parámetro constante y de volver a establecer el orden de los parámetros de entrada cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-110">However, the **Configure \<Functoid\> Functoid** dialog box is the definitive mechanism for viewing all the input parameters to a functoid, for creating and modifying any constant parameters, and for re-arranging the order of the input parameters when necessary.</span></span>  
  
 <span data-ttu-id="9c4bb-111">Al configurar los parámetros de entrada para un functoid directamente en la página de cuadrícula (trazando líneas, arrastrando y soltando con el mouse, desde el nodo del esquema de origen y vinculándolo con el functoid), si el número de entradas alcanza el máximo, el cursor cambia a un estado NO.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-111">When you configure the input parameters for a functoid directly on the grid page (by drawing lines, using the mouse drag-and-drop, from the source schema node and linking it to the functoid), if the number of inputs reaches maximum, the cursor changes to a NO state.</span></span> <span data-ttu-id="9c4bb-112">Además, la barra de estado muestra el motivo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-112">Also, the status bar displays the reason.</span></span> <span data-ttu-id="9c4bb-113">La siguiente ilustración muestra un functoid que acepta solo un vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-113">The figure below shows a functoid which accepts only one input link.</span></span>  
  
 <span data-ttu-id="9c4bb-114">![SIN estado para configurar el parámetro de entrada de functoid](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span><span class="sxs-lookup"><span data-stu-id="9c4bb-114">![NO state for configuring functoid input parameter](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span></span>  
  
 <span data-ttu-id="9c4bb-115">Puede configurar los functoids de secuencias de comandos y el bucle de tabla mediante el **configurar \<Functoid\> Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-115">You can configure the Scripting and Table Looping functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="9c4bb-116">Para obtener información sobre cómo configurar los functoids, consulte [cómo configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md) y [cómo configurar el bucle de tabla y el functoid de Extractor de tabla](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-116">For information about how to configure the functoids, see [How to Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) and [How to Configure the Table Looping and Table Extractor Functoids](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c4bb-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c4bb-117">Prerequisites</span></span>  
 <span data-ttu-id="9c4bb-118">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-118">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-is-an-input-parameter"></a><span data-ttu-id="9c4bb-119">¿Qué es un parámetro de entrada?</span><span class="sxs-lookup"><span data-stu-id="9c4bb-119">What is an input parameter?</span></span>  
 <span data-ttu-id="9c4bb-120">Un parámetro de entrada puede ser cualquiera de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4bb-120">An input parameter can be any of the following:</span></span>  
  
-   <span data-ttu-id="9c4bb-121">Un vínculo de un nodo del esquema de origen a un functoid</span><span class="sxs-lookup"><span data-stu-id="9c4bb-121">A link from source schema node to a functoid</span></span>  
  
-   <span data-ttu-id="9c4bb-122">Un vínculo desde un functoid a otro functoid válido</span><span class="sxs-lookup"><span data-stu-id="9c4bb-122">A link from functoid to another valid functoid</span></span>  
  
-   <span data-ttu-id="9c4bb-123">Un valor constante</span><span class="sxs-lookup"><span data-stu-id="9c4bb-123">A constant value</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c4bb-124">Existen algunos functoids, como **fecha**, **tiempo**, **fecha y hora**, y **Nil**, que no necesita ningún parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-124">There are a few functoids, such as **Date**, **Time**, **Date and Time**, and **Nil**, which do not need any input parameters.</span></span>  
  
 <span data-ttu-id="9c4bb-125">La siguiente ilustración muestra un functoid (resaltado en rojo) con dos parámetros de entrada (Input[0] e Input[1]) y un parámetro constante (Input[2]).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-125">The figure below displays a functoid (highlighted in red) with two input parameters (Input[0] and Input[1]) and a constant parameter (Input[2]).</span></span>  
  
 <span data-ttu-id="9c4bb-126">![Mostrar los parámetros de entrada a un functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span><span class="sxs-lookup"><span data-stu-id="9c4bb-126">![Displaying the input parameters to a functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span></span>  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="9c4bb-127">Para abrir configurar \<Functoid\> cuadro de diálogo de Functoid</span><span class="sxs-lookup"><span data-stu-id="9c4bb-127">To open the Configure \<Functoid\> Functoid dialog box</span></span>  
 <span data-ttu-id="9c4bb-128">Puede abrir el **configurar \<Functoid\> Functoid** cuadro de diálogo de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4bb-128">You can open the **Configure \<Functoid\> Functoid** dialog box in one of the following ways:</span></span>  
  
-   <span data-ttu-id="9c4bb-129">En la página de cuadrícula correspondiente, haga clic en el functoid y, a continuación, haga clic en **configurar entradas de Functoid**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-129">In the relevant grid page, right-click the functoid, and then click **Configure Functoid Inputs**.</span></span>  
  
-   <span data-ttu-id="9c4bb-130">Haga doble clic en el functoid para el que desea configurar los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-130">Double-click the functoid for which you want to configure the input parameters.</span></span>  
  
-   <span data-ttu-id="9c4bb-131">Seleccione el functoid y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) en la Visual Studio **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-131">Select the functoid and then click the ellipses (**…**) in the Visual Studio’s **Properties** window.</span></span>  
  
-   <span data-ttu-id="9c4bb-132">Seleccione el functoid y presione ENTRAR del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-132">Select the functoid and then press ENTER from the keyboard.</span></span>  
  
-   <span data-ttu-id="9c4bb-133">Seleccione el functoid y presione CTRL+M, CTRL+I del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-133">Select the functoid and then press CTRL+M, CTRL+I from the keyboard.</span></span> <span data-ttu-id="9c4bb-134">Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-134">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
### <a name="to-insert-constant-input-parameters"></a><span data-ttu-id="9c4bb-135">Para insertar parámetros de entrada constantes</span><span class="sxs-lookup"><span data-stu-id="9c4bb-135">To insert constant input parameters</span></span>  
  
1.  <span data-ttu-id="9c4bb-136">En el **configurar \<Functoid\> Functoid** cuadro de diálogo, seleccione la **entradas de Functoid** ficha.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-136">In the **Configure \<Functoid\> Functoid** dialog box, select the **Functoid Inputs** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-137">El **entradas de Functoid** ficha está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-137">The **Functoid Inputs** tab is selected by default.</span></span>  
  
2.  <span data-ttu-id="9c4bb-138">Haga clic en el ![agregar parámetros de entrada constantes a un functoid](../core/media/add-input-parameters.gif "Add_input_parameters") botón.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-138">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span> <span data-ttu-id="9c4bb-139">Se agrega una nueva fila.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-139">A new row is added.</span></span>  
  
3.  <span data-ttu-id="9c4bb-140">Escriba el valor para el nuevo parámetro de entrada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-140">Type the value for the new input parameter, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-141">Si el botón Agregar no está habilitado, el functoid no acepta o no requiere parámetros de entrada, o puede que ya tenga el máximo número de entradas permitidas.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-141">If the add button is not enabled, the functoid does not accept or require input parameters, or may already have the maximum number of allowed inputs.</span></span>  
  
### <a name="to-edit-existing-constant-input-parameters"></a><span data-ttu-id="9c4bb-142">Para editar parámetros de entrada constantes que ya existen</span><span class="sxs-lookup"><span data-stu-id="9c4bb-142">To edit existing constant input parameters</span></span>  
  
1.  <span data-ttu-id="9c4bb-143">En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en la constante existente de entrada de parámetro que desea editar.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-143">In the **Configure \<Functoid\> Functoid** dialog box, click the existing constant input parameter that you want to edit.</span></span> <span data-ttu-id="9c4bb-144">El valor actual está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-144">The current value is selected.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c4bb-145">Solo puede editar los parámetros de las entradas constantes.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-145">You can edit the parameters of constant inputs only.</span></span> <span data-ttu-id="9c4bb-146">No se pueden editar los parámetros de entrada de todos los demás tipos.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-146">Input parameters of all other types cannot be edited.</span></span> <span data-ttu-id="9c4bb-147">Solo se pueden reorganizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-147">They can only be rearranged or deleted.</span></span>  
  
2.  <span data-ttu-id="9c4bb-148">Haga clic en el ![editar parámetros de entrada constantes](../core/media/edit-input-parameters.gif "Edit_input_parameters") botón.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-148">Click the ![Editing constant input parameters](../core/media/edit-input-parameters.gif "Edit_input_parameters") button.</span></span> <span data-ttu-id="9c4bb-149">Realice los cambios apropiados en el valor constante y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-149">Make the appropriate changes to the constant value, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9c4bb-150">Como alternativa, puede hacer doble clic en el parámetro de entrada constante para modificarlo o presionar F2 del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-150">Alternatively, you can double-click the constant input parameter to edit it, or press F2 from the keyboard.</span></span>  
  
## <a name="to-select-multiple-input-parameters"></a><span data-ttu-id="9c4bb-151">Para seleccionar varios parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="9c4bb-151">To select multiple input parameters</span></span>  
 <span data-ttu-id="9c4bb-152">Para seleccionar varios parámetros de entrada, mantenga presionada la tecla CTRL y haga clic en las filas que desee. A continuación, realice cualquiera de las siguientes operaciones.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-152">You can select multiple input parameters by holding down the CTRL key and clicking the desired rows, and then perform any of the following operations.</span></span> <span data-ttu-id="9c4bb-153">Presione CTRL+A del teclado para seleccionar todas las filas.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-153">You can press CTRL+A from the keyboard to select all the rows.</span></span>  
  
-   <span data-ttu-id="9c4bb-154">Mueva la selección hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-154">Move the selection up/down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-155">Si la selección masiva incluye la fila situada en la parte superior o en la parte inferior entre otras, no es posible mover la selección hacia arriba o hacia abajo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-155">If the bulk selection includes either the top-most or the bottom-most row among the other rows, you cannot move the selection up/down respectively.</span></span>  
  
-   <span data-ttu-id="9c4bb-156">Reorganice la selección.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-156">Rearrange the selection.</span></span>  
  
-   <span data-ttu-id="9c4bb-157">Elimine la selección.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-157">Delete the selection.</span></span>  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a><span data-ttu-id="9c4bb-158">Para cambiar el orden de los parámetros de entrada existentes</span><span class="sxs-lookup"><span data-stu-id="9c4bb-158">To change the order of existing input parameters</span></span>  
  
1.  <span data-ttu-id="9c4bb-159">En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en las existentes de entrada de parámetro que desee mover a una posición diferente en la lista ordenada de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-159">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to move to a different position in the ordered list of input parameters.</span></span>  
  
2.  <span data-ttu-id="9c4bb-160">Haga clic en el ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") botón para mover el parámetro hacia arriba en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-160">Click the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") button to move the parameter up in the parameter list.</span></span> <span data-ttu-id="9c4bb-161">Repita según sea necesario hasta que el parámetro de entrada seleccionado se encuentre en la posición deseada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-161">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="9c4bb-162">Como alternativa, puede presionar la tecla FLECHA ARRIBA del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-162">Alternatively, you can press the UP ARROW key from the keyboard.</span></span> <span data-ttu-id="9c4bb-163">Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-163">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="9c4bb-164">-OR-</span><span class="sxs-lookup"><span data-stu-id="9c4bb-164">-OR-</span></span>  
  
     <span data-ttu-id="9c4bb-165">Haga clic en el ![mover hacia abajo en una lista](../core/media/move-down-button.gif "Move_down_button") botón para mover el parámetro hacia abajo en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-165">Click the ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") button to move the parameter down in the parameter list.</span></span> <span data-ttu-id="9c4bb-166">Repita según sea necesario hasta que el parámetro de entrada seleccionado se encuentre en la posición deseada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-166">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="9c4bb-167">Como alternativa, puede presionar la tecla FLECHA ABAJO del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-167">Alternatively, you can press the DOWN ARROW key from the keyboard.</span></span> <span data-ttu-id="9c4bb-168">Para obtener una lista de teclas de método abreviado de asignador, vea [métodos abreviados de teclado del asignador de BizTalk](../core/biztalk-mapper-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-168">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c4bb-169">Puede reorganizar la secuencia de entradas solo desde el **configurar \<Functoid\> Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-169">You can rearrange the sequence of inputs only from the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="9c4bb-170">Si selecciona la fila superiores o inferiores, la ![se desplazan hacia arriba en la lista](../core/media/move-up-button.gif "Move_up_button") o ![mover hacia abajo en una lista](../core/media/move-down-button.gif "Move_down_button")botones se deshabilitaría, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-170">If you select the top-most or bottom-most row, the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") or ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") buttons would be disabled, respectively.</span></span>  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a><span data-ttu-id="9c4bb-171">Para eliminar un parámetro de entrada eliminando el vínculo de entrada</span><span class="sxs-lookup"><span data-stu-id="9c4bb-171">To delete an input parameter by deleting the input link</span></span>  
  
1.  <span data-ttu-id="9c4bb-172">En la página de cuadrícula correspondiente, haga clic en el vínculo de entrada que corresponda al parámetro de entrada que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-172">In the relevant grid page, click the input link corresponding to the input parameter you want to delete.</span></span>  
  
2.  <span data-ttu-id="9c4bb-173">En el **editar** menú, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-173">On the **Edit** menu, click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-174">Como alternativa, puede presionar la tecla SUPR o haga clic en el vínculo en la página de cuadrícula correspondiente y haga clic en **eliminar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-174">Alternatively, you can press the DELETE key, or right-click the link in the relevant grid page, and click **Delete** from the shortcut menu.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c4bb-175">El vínculo de entrada se elimina silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-175">The input link is deleted silently.</span></span> <span data-ttu-id="9c4bb-176">Siempre puede deshacer la eliminación si no está seguro de ella.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-176">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="9c4bb-177">Para obtener más información acerca de las operaciones de deshacer/rehacer, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-177">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="9c4bb-178">Para eliminar parámetros de entrada existentes en la configuración \<Functoid\> cuadro de diálogo de Functoid</span><span class="sxs-lookup"><span data-stu-id="9c4bb-178">To delete existing input parameters within the Configure \<Functoid\> Functoid dialog box</span></span>  
  
1.  <span data-ttu-id="9c4bb-179">En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en las existentes de entrada de parámetro que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-179">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-180">Puede eliminar cualquier parámetro de entrada mediante esta técnica, incluso los que corresponden a un vínculo de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-180">You can delete any input parameter using this technique, even those that correspond to an input link.</span></span>  
  
2.  <span data-ttu-id="9c4bb-181">Haga clic en el ![eliminar la selección](../core/media/delete-button.gif "Delete_button") botón.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-181">Click the ![Deleting the selection](../core/media/delete-button.gif "Delete_button") button.</span></span> <span data-ttu-id="9c4bb-182">El parámetro de entrada existente seleccionado se elimina de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-182">The selected existing input parameter is deleted from the parameter list.</span></span> <span data-ttu-id="9c4bb-183">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-183">Click **OK**.</span></span>  
  
     <span data-ttu-id="9c4bb-184">También puede seleccionar la fila que desea eliminar y presionar la tecla SUPRIMIR del teclado.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-184">Alternatively, you can select the row you want to delete, and press the DELETE key from the keyboard.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c4bb-185">El parámetro de entrada se elimina silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-185">The input parameter is deleted silently.</span></span> <span data-ttu-id="9c4bb-186">Siempre puede deshacer la eliminación si no está seguro de ella.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-186">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="9c4bb-187">Para obtener más información acerca de las operaciones de deshacer/rehacer, consulte [cómo deshacer o rehacer operaciones de usuario](../core/how-to-undo-or-redo-user-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-187">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c4bb-188">El botón Eliminar no está habilitado cuando no hay parámetros de entrada en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-188">The delete button is not enabled when there are no input parameters in the parameter list.</span></span>  
  
## <a name="to-set-labels-and-comments-for-functoids"></a><span data-ttu-id="9c4bb-189">Procedimiento para establecer etiquetas y comentarios para functoids</span><span class="sxs-lookup"><span data-stu-id="9c4bb-189">To set labels and comments for functoids</span></span>  
 <span data-ttu-id="9c4bb-190">Puede establecer etiquetas y comentarios para functoids mediante el **configurar \<Functoid\> Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-190">You can set labels and comments for functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
1.  <span data-ttu-id="9c4bb-191">En el **configurar \<Functoid\> Functoid** cuadro de diálogo, haga clic en el **etiqueta y comentarios** ficha.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-191">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
2.  <span data-ttu-id="9c4bb-192">Tipo de la **etiqueta** y **comentarios**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c4bb-192">Type the **Label** and **Comments**, and then click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9c4bb-193">Para obtener más información acerca de cómo etiqueta y comentar functoids y/o vínculos, consulte [cómo etiquetar un vínculo](../core/how-to-label-a-link.md) y [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="9c4bb-193">For more information about how to label and comment functoids and/or links, see [How to Label a Link](../core/how-to-label-a-link.md) and [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4bb-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c4bb-194">See Also</span></span>  
 [<span data-ttu-id="9c4bb-195">Editar propiedades de functoid y parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="9c4bb-195">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)
---
title: Agregar y quitar Functoids personalizados del cuadro de herramientas de Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955c526c39a1cbb376a0d83848554bdeb6cc15c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="e7496-102">Adición y eliminación de functoids personalizados del cuadro de herramientas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7496-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="e7496-103">En este tema se describe cómo agregar functoids personalizados y quitarlos del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7496-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="e7496-104">Agregar functoids personalizados a Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7496-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="e7496-105">Los functoids personalizados se deben agregar al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] antes de que se puedan usar en una asignación.</span><span class="sxs-lookup"><span data-stu-id="e7496-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="e7496-106">Utilice el procedimiento siguiente para agregar functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="e7496-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="e7496-107">Para agregar un functoid personalizado</span><span class="sxs-lookup"><span data-stu-id="e7496-107">To add a custom functoid</span></span>  
  
1.  <span data-ttu-id="e7496-108">Agregue el functoid al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7496-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="e7496-109">Mediante el Explorador de Windows, busque el ensamblado que implemente su functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="e7496-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
    2.  <span data-ttu-id="e7496-110">Copie el ensamblado en el \< *carpeta de instalación de BizTalk Server*\>**\Developer Tools\Mapper extensiones** directory.</span><span class="sxs-lookup"><span data-stu-id="e7496-110">Copy the assembly to the \<*BizTalk Server installation folder*\>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="e7496-111">Aquí es donde el Asignador de BizTalk busca functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="e7496-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
    3.  <span data-ttu-id="e7496-112">Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e7496-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    4.  <span data-ttu-id="e7496-113">En el **elementos de cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="e7496-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    5.  <span data-ttu-id="e7496-114">Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7496-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="e7496-115">Este proceso podría tardar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="e7496-115">This process may take a few moments.</span></span>  
  
         <span data-ttu-id="e7496-116">Su functoid personalizado debería aparecer ahora en el cuadro de herramientas en las fichas que coinciden con su categoría.</span><span class="sxs-lookup"><span data-stu-id="e7496-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
     <span data-ttu-id="e7496-117">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="e7496-117">\- OR -</span></span>  
  
    1.  <span data-ttu-id="e7496-118">Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e7496-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="e7496-119">En el **elementos de cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="e7496-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="e7496-120">Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7496-120">Click **Reset**, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e7496-121">Si el functoid personalizado no expone ningún código en línea, asegúrese de que su ensamblado debe ponerse a disposición en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e7496-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
    4.  <span data-ttu-id="e7496-122">En el **archivo** menú, haga clic en **Exit** para cerrar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7496-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    5.  <span data-ttu-id="e7496-123">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e7496-123">Start **Visual Studio Command Prompt**.</span></span>  
  
    6.  <span data-ttu-id="e7496-124">En el símbolo del sistema, escriba **devenv /setup**.</span><span class="sxs-lookup"><span data-stu-id="e7496-124">At the command prompt, type **devenv /setup**.</span></span>  
  
    7.  <span data-ttu-id="e7496-125">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e7496-125">Start **Microsoft Visual Studio**.</span></span>  
  
         <span data-ttu-id="e7496-126">El functoid personalizado debería aparecer en la ficha correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e7496-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2.  <span data-ttu-id="e7496-127">Agregue el ensamblado a la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="e7496-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="e7496-128">Si su ensamblado contiene sólo functoids en línea, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="e7496-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    1.  <span data-ttu-id="e7496-129">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e7496-129">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="e7496-130">Pase a la carpeta que contiene su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7496-130">Switch to the folder containing your assembly.</span></span>  
  
    3.  <span data-ttu-id="e7496-131">En el símbolo del sistema, escriba **gacutil /if < assembly_path >**.</span><span class="sxs-lookup"><span data-stu-id="e7496-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="e7496-132">Por ejemplo, si el nombre del ensamblado es FunctoidLibrary.dll, a continuación, escriba **gacutil /if FunctoidLibrary.dll**.</span><span class="sxs-lookup"><span data-stu-id="e7496-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
    4.  <span data-ttu-id="e7496-133">Cuando haya terminado, escriba **salir**.</span><span class="sxs-lookup"><span data-stu-id="e7496-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="e7496-134">Quitar functoids personalizados de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7496-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="e7496-135">Utilice el procedimiento siguiente para quitar functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="e7496-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="e7496-136">Para quitar un functoid personalizado</span><span class="sxs-lookup"><span data-stu-id="e7496-136">To remove a custom functoid</span></span>  
  
1.  <span data-ttu-id="e7496-137">Quite el functoid del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7496-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="e7496-138">Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="e7496-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="e7496-139">En el **elementos de cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="e7496-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="e7496-140">Busque el functoid personalizado en la lista, seleccione la **quitar** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7496-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e7496-141">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="e7496-141">\- OR -</span></span>  
  
    1.  <span data-ttu-id="e7496-142">Mientras edita una asignación en una [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **cuadro de herramientas** tab para abrir la paleta de cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="e7496-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="e7496-143">Haga clic en el grupo de functoids que contiene su functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="e7496-143">Click the functoid group containing your custom functoid.</span></span>  
  
    3.  <span data-ttu-id="e7496-144">Haga clic en el functoid que desea quitar y, a continuación, haga clic en **eliminar** o presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="e7496-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2.  <span data-ttu-id="e7496-145">Quitar el ensamblado de functoid el **Programador\extensiones** directory.</span><span class="sxs-lookup"><span data-stu-id="e7496-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e7496-146">Si un ensamblado contiene functoids activos, no los quite.</span><span class="sxs-lookup"><span data-stu-id="e7496-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="e7496-147">Si lo hace, se interrumpirán otras asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e7496-147">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="e7496-148">Inicie el Explorador de Windows y vaya a la **Programador\extensiones** directorio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7496-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="e7496-149">Haga clic en el ensamblado que contiene el functoid que ha quitado y, a continuación, haga clic en **eliminar** para quitar el archivo.</span><span class="sxs-lookup"><span data-stu-id="e7496-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3.  <span data-ttu-id="e7496-150">Quitar el ensamblado de functoid de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="e7496-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="e7496-151">Si su ensamblado contiene sólo functoids en línea, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="e7496-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e7496-152">Si un ensamblado contiene functoids activos, no los quite de la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="e7496-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="e7496-153">Si lo hace, se interrumpirán otras asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e7496-153">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="e7496-154">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e7496-154">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="e7496-155">En el símbolo del sistema, escriba **gacutil /u < assembly_display_name >**.</span><span class="sxs-lookup"><span data-stu-id="e7496-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="e7496-156">Por ejemplo, si el nombre del ensamblado es FunctoidLibrary.dll, a continuación, escriba **gacutil /if Functoidlibrary.dll**.</span><span class="sxs-lookup"><span data-stu-id="e7496-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
    3.  <span data-ttu-id="e7496-157">Cuando haya terminado, escriba **salir**.</span><span class="sxs-lookup"><span data-stu-id="e7496-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7496-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7496-158">See Also</span></span>  
 [<span data-ttu-id="e7496-159">Desarrollo de functoids personalizados</span><span class="sxs-lookup"><span data-stu-id="e7496-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)
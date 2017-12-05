---
title: "Anular la implementación de un adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1332e41593ede5f7075ec7f5ede1293d79d65594
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="4b6e1-102">Anular la implementación de un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="4b6e1-102">Undeploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="4b6e1-103">Para anular la implementación de un adaptador desde un equipo, el usuario debe realizar las dos tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b6e1-103">To undeploy an adapter from a computer, the user needs to perform the following two tasks:</span></span>  
  
1.  <span data-ttu-id="4b6e1-104">Desinstalar el ensamblado de adaptador (y cualquier ensamblado dependiente) desde la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="4b6e1-104">Uninstall the adapter assembly (and any dependent assemblies) from the global assembly cache (GAC).</span></span>  
  
2.  <span data-ttu-id="4b6e1-105">Quitar el enlace del adaptador y el elemento de enlace de adaptador en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-105">Remove the adapter binding and adapter binding element in the machine.config file.</span></span>  
  
## <a name="uninstall-an-assembly-from-the-gac"></a><span data-ttu-id="4b6e1-106">Desinstalar un ensamblado de la GAC</span><span class="sxs-lookup"><span data-stu-id="4b6e1-106">Uninstall an Assembly from the GAC</span></span>  
  
#### <a name="use-the-windows-interface"></a><span data-ttu-id="4b6e1-107">Utilice la interfaz de Windows</span><span class="sxs-lookup"><span data-stu-id="4b6e1-107">Use the Windows interface</span></span>  
  
1.  <span data-ttu-id="4b6e1-108">Abra el Explorador de Windows como se indica a continuación: haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **elExploradordeWindows**.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-108">Open Windows Explorer as follows: Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="4b6e1-109">Vaya a la GAC, que se encuentra en % systemdrive%\Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-109">Browse to the GAC, which is located at %systemdrive%\Windows\Assembly.</span></span>  
  
3.  <span data-ttu-id="4b6e1-110">Haga clic en cada archivo de ensamblado que se incluye en la aplicación, haga clic en **desinstalar**y, a continuación, haga clic en **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-110">Right-click each assembly file that is included in your application, click **Uninstall**, and then click **Yes** to confirm.</span></span>  
  
#### <a name="use-the-command-line"></a><span data-ttu-id="4b6e1-111">Usar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="4b6e1-111">Use the command line</span></span>  
  
1.  <span data-ttu-id="4b6e1-112">Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-112">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="4b6e1-113">En el símbolo del sistema, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b6e1-113">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="4b6e1-114">**Gacutil /u** \< *completo**nombre de ensamblado*\></span><span class="sxs-lookup"><span data-stu-id="4b6e1-114">**gacutil /u** \<*fully qualified**assembly name*\></span></span>  
  
     <span data-ttu-id="4b6e1-115">En este comando, el nombre del ensamblado es el nombre del ensamblado que se va a desinstalar de la GAC.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-115">In this command, the assembly name is the name of the assembly to uninstall from the GAC.</span></span>  
  
     <span data-ttu-id="4b6e1-116">En el ejemplo siguiente se quita el ensamblado denominado hello.dll de la GAC.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-116">The following example removes an assembly named hello.dll from the GAC.</span></span>  
  
     `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a><span data-ttu-id="4b6e1-117">Quite el enlace del adaptador desde el archivo Machine.config</span><span class="sxs-lookup"><span data-stu-id="4b6e1-117">Remove the Adapter Binding from the Machine.config File</span></span>  
 <span data-ttu-id="4b6e1-118">Manualmente, puede editar el archivo machine.config para quitar el enlace del adaptador o usar el Editor de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-118">You can manually edit the machine.config file to remove the adapter binding, or use the Service Configuration Editor.</span></span> <span data-ttu-id="4b6e1-119">Esta sección enumeran los pasos.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-119">This section lists both steps.</span></span> 
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="4b6e1-120">Editar manualmente el archivo machine.config</span><span class="sxs-lookup"><span data-stu-id="4b6e1-120">Manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="4b6e1-121">Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-121">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="4b6e1-122">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **el Bloc de notas \<ruta de instalación de Windows\>\Microsoft.NET\Framework\\< versión\>\CONFIG\machine.config**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-122">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b6e1-123">Realizar una copia de seguridad del archivo machine.config antes de realizar cambios para protegerse contra errores de edición.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-123">Make a backup of the machine.config file before you make changes to guard against editing mistakes.</span></span>  
  
2.  <span data-ttu-id="4b6e1-124">Actualice el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-124">Update the machine.config file.</span></span> <span data-ttu-id="4b6e1-125">Busque el elemento bindingExtensions para el adaptador que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-125">Find the bindingExtensions element for the adapter you want to remove.</span></span> <span data-ttu-id="4b6e1-126">Basándose en la otra información que está presente, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4b6e1-126">Based on the other information that is present, do one of the following:</span></span>  
  
    -   <span data-ttu-id="4b6e1-127">Si hay otros bindingExtensions, quite sólo la extensión del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-127">If there are other bindingExtensions, remove only your adapter extension.</span></span>  
  
    -   <span data-ttu-id="4b6e1-128">Si no hay ningún otro bindingExtensions, puede quitar la sección bindingExtensions (incluida la extensión de adaptador).</span><span class="sxs-lookup"><span data-stu-id="4b6e1-128">If there are no other bindingExtensions, you can remove the bindingExtensions section (including your adapter extension).</span></span>  
  
    -   <span data-ttu-id="4b6e1-129">Si no hay ningún otro bindingExtensions o extensiones, puede quitar la sección de extensiones.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-129">If there are no other bindingExtensions or extensions, you can remove the extensions section.</span></span>  
  
    -   <span data-ttu-id="4b6e1-130">Por último, si system.serviceModel contiene solo la extensión de adaptador, puede quitar la sección system.serviceModel todo.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-130">Finally, if system.serviceModel contains only your adapter extension, you can remove the entire system.serviceModel section.</span></span>  
  
3.  <span data-ttu-id="4b6e1-131">Repita el paso 2 para el elemento bindingElementExtensions.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-131">Repeat step 2 for the bindingElementExtensions element.</span></span>  
  
4.  <span data-ttu-id="4b6e1-132">Cierre y guarde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-132">Close and save the machine.config file.</span></span>  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a><span data-ttu-id="4b6e1-133">Use el Editor de configuración de servicio cambia el archivo machine.config</span><span class="sxs-lookup"><span data-stu-id="4b6e1-133">Use the Service Configuration Editor do change the machine.config file</span></span>  
  
1.  <span data-ttu-id="4b6e1-134">Abra el Editor de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-134">Open Service Configuration Editor.</span></span> <span data-ttu-id="4b6e1-135">Vea [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-135">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for more information.</span></span>
  
2.  <span data-ttu-id="4b6e1-136">En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-136">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="4b6e1-137">Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione el elemento de extensiones de enlace.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-137">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
3.  <span data-ttu-id="4b6e1-138">En el panel de detalles del Editor de extensiones de enlace, haga clic en la extensión de enlace que desea eliminar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-138">In the details pane of the Binding Extensions Editor, click the binding extension that you want to delete, and then click **Delete**.</span></span> <span data-ttu-id="4b6e1-139">En la ilustración siguiente, MyAdapterExtension se resalta y se eliminará.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-139">In the following figure, MyAdapterExtension is highlighted and will be deleted.</span></span>  
  
     <span data-ttu-id="4b6e1-140">![Editor de configuración de servicio con extensión agregada. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="4b6e1-140">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
4.  <span data-ttu-id="4b6e1-141">Cierre el editor de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="4b6e1-141">Close the Service Configuration Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6e1-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b6e1-142">See Also</span></span>  
 [<span data-ttu-id="4b6e1-143">Implementar un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="4b6e1-143">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)
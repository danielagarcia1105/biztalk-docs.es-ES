---
title: Implementar un adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacb0599d28a43888422df0d488458f780f30bdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="a7014-102">Implementar un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="a7014-102">Deploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="a7014-103">Para implementar un adaptador, debe instalar al ensamblado de adaptador en la caché global de ensamblados (GAC) y, a continuación, registrar el adaptador en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="a7014-103">To deploy an adapter, you must install the adapter assembly into the global assembly cache (GAC), and then register the adapter in the machine.config file.</span></span>  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a><span data-ttu-id="a7014-104">Instalar al ensamblado de adaptador en la GAC</span><span class="sxs-lookup"><span data-stu-id="a7014-104">Install the Adapter Assembly into the GAC</span></span>  
 <span data-ttu-id="a7014-105">Antes de consumir un adaptador en Visual Studio mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] comandos o en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] utilizando el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] característica, debe instalar el ensamblado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="a7014-105">Before consuming an adapter in Visual Studio using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] command or in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] by using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] feature, you must install the assembly into the GAC.</span></span> <span data-ttu-id="a7014-106">Solo los ensamblados con nombre seguro pueden instalarse en la GAC.</span><span class="sxs-lookup"><span data-stu-id="a7014-106">Only assemblies that are strong-named can be installed into the GAC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7014-107">Para completar este procedimiento, debe ser iniciado sesión con una cuenta que tenga permisos de escritura en la GAC.</span><span class="sxs-lookup"><span data-stu-id="a7014-107">To complete this procedure, you must be logged on with an account that has Write permissions on the GAC.</span></span> <span data-ttu-id="a7014-108">La cuenta de administradores del equipo local tiene estos permisos.</span><span class="sxs-lookup"><span data-stu-id="a7014-108">The Administrators account on the local computer has these permissions.</span></span>  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="a7014-109">Configurar un archivo de clave de ensamblado de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="a7014-109">Configure a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="a7014-110">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], cargue el archivo de proyecto de adaptador que necesita un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a7014-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], load the adapter project file that needs a strong name.</span></span>  
  
2.  <span data-ttu-id="a7014-111">Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7014-111">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3.  <span data-ttu-id="a7014-112">En el símbolo del sistema, desde la carpeta donde desea almacenar el archivo de clave, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a7014-112">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="a7014-113">**sn /k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="a7014-113">**sn /k**  *file_name* **.snk**</span></span>  
  
     <span data-ttu-id="a7014-114">Ejemplo: **sn /k EchoAdapter.snk**</span><span class="sxs-lookup"><span data-stu-id="a7014-114">Example: **sn /k EchoAdapter.snk**</span></span>  
  
     <span data-ttu-id="a7014-115">Un mensaje de confirmación, **escribe en el par de claves** \< *file_name*>**.snk** `,` muestra en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a7014-115">A confirmation message, **Key pair written to** \<*file_name*>**.snk**`,` displays on the command line.</span></span>  
  
4.  <span data-ttu-id="a7014-116">En el Explorador de soluciones de Visual Studio, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7014-116">In Visual Studio Solution Explorer, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a7014-117">En el panel izquierdo, expanda **propiedades comunes**y, a continuación, haga clic en **ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="a7014-117">In the left pane, expand **Common Properties**, and then click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="a7014-118">En el panel derecho, desplácese a la **nombre seguro** cuadro.</span><span class="sxs-lookup"><span data-stu-id="a7014-118">In the right pane, scroll to the **Strong name** box.</span></span>  
  
7.  <span data-ttu-id="a7014-119">En el **nombre seguro** cuadro, haga clic en el campo junto a **archivo de clave de ensamblado**, haga clic en el botón Examinar (**...** ) y, a continuación, busque el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="a7014-119">In the **Strong name** box, click the field next to **Assembly Key File**, click the browse button (**…**), and then browse to the key file.</span></span>  
  
8.  <span data-ttu-id="a7014-120">Haga clic en el archivo de clave, haga clic en **abiertos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7014-120">Click the key file, click **Open**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a7014-121">En el menú de Visual Studio, haga clic en **generar**y, a continuación, elija **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="a7014-121">On the Visual Studio menu, click **Build**, and then choose **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7014-122">Si su ensamblado de adaptador depende de otros ensamblados, asegúrese de que estos ensamblados se firman con un nombre seguro; en caso contrario, obtendrá un error.</span><span class="sxs-lookup"><span data-stu-id="a7014-122">If your adapter assembly depends on any other assemblies, ensure these referenced assemblies are signed with a strong name; otherwise you will get an error.</span></span>  
  
 <span data-ttu-id="a7014-123">Si tiene el código fuente, puede volver a compilar con un nombre seguro tal y como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a7014-123">If you have the source, you can recompile with a strong name as shown previously.</span></span> <span data-ttu-id="a7014-124">Si el ensamblado de referencia pertenece a un tercero y no puede garantizar que se le asignará un nombre seguro, puede desensamblar y, a continuación, volver a ensamblar el ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a7014-124">If the reference assembly belongs to a third-party and you cannot ensure that it will be given a strong name, you can disassemble and then reassemble the assembly with a strong name.</span></span>  
  
 <span data-ttu-id="a7014-125">El ensamblado original se sobrescribirá, por lo que si desea conservar la versión original, asegúrese de realizar una copia de seguridad del mismo antes de continuar con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7014-125">Your original assembly will be overwritten, so if you want to keep the original version, ensure you make a backup copy of it before proceeding with the following steps.</span></span>  
  
 <span data-ttu-id="a7014-126">Utilizar el Desensamblador de lenguaje intermedio de Microsoft (MSIL) para desensamblar el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="a7014-126">Use Microsoft Intermediate Language (MSIL) Disassembler to disassemble the assembly:</span></span>  
  
-   <span data-ttu-id="a7014-127">ILDASM thirdparty.dll /out:thirdparty.il</span><span class="sxs-lookup"><span data-stu-id="a7014-127">ILDASM thirdparty.dll /out:thirdparty.il</span></span>  
  
 <span data-ttu-id="a7014-128">Usar el ensamblador de MSIL para volver a ensamblar el ensamblado con un nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="a7014-128">Use MSIL Assembler to reassemble the assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="a7014-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span><span class="sxs-lookup"><span data-stu-id="a7014-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span></span>  
  
#### <a name="install-an-assembly-in-the-gac"></a><span data-ttu-id="a7014-130">Instalar a un ensamblado en la GAC</span><span class="sxs-lookup"><span data-stu-id="a7014-130">Install an assembly in the GAC</span></span>  
  
1.  <span data-ttu-id="a7014-131">Compruebe que el adaptador se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="a7014-131">Verify that your adapter has been signed.</span></span>  
  
2.  <span data-ttu-id="a7014-132">Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7014-132">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3.  <span data-ttu-id="a7014-133">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a7014-133">Type the following command:</span></span>  
  
     <span data-ttu-id="a7014-134">**Gacutil.exe /if "\<**  *ruta de acceso al archivo .dll del ensamblado* **>"**</span><span class="sxs-lookup"><span data-stu-id="a7014-134">**gacutil.exe /if "\<** *path to the assembly .dll file* **>"**</span></span>  
  
4.  <span data-ttu-id="a7014-135">Se instalará el ensamblado en la GAC, sobrescribiendo cualquier ensamblado existente con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="a7014-135">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
## <a name="register-the-adapter-in-machineconfig"></a><span data-ttu-id="a7014-136">Registrar el adaptador en el archivo Machine.config</span><span class="sxs-lookup"><span data-stu-id="a7014-136">Register the Adapter in Machine.config</span></span>  
 <span data-ttu-id="a7014-137">Un adaptador desarrolladas con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparece como un enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="a7014-137">An adapter developed using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is surfaced as a WCF binding.</span></span>  <span data-ttu-id="a7014-138">Para obtener más información, consulte Microsoft.ServiceModel.Channels.Common.AdapterBinding.</span><span class="sxs-lookup"><span data-stu-id="a7014-138">See Microsoft.ServiceModel.Channels.Common.AdapterBinding for more information.</span></span>  <span data-ttu-id="a7014-139">El enlace del adaptador está registrado con WCF con \<bindingExtensions > dentro de la sección \<sistema. ServiceModel > y el elemento de enlace de transporte de adaptador está registrado con WCF con \<bindingElementExtensions > dentro de la sección \<sistema. ServiceModel >.</span><span class="sxs-lookup"><span data-stu-id="a7014-139">The adapter binding is registered with WCF using \<bindingExtensions> section within \<system.ServiceModel> and the adapter transport binding element is registered with WCF using \<bindingElementExtensions> section within \<system.ServiceModel>.</span></span>  
  
 <span data-ttu-id="a7014-140">Puede editar manualmente el archivo machine.config con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a7014-140">You can manually edit the machine.config file using a text editor.</span></span>  
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="a7014-141">Editar manualmente el archivo machine.config</span><span class="sxs-lookup"><span data-stu-id="a7014-141">Manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="a7014-142">Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="a7014-142">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="a7014-143">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad \<ruta de instalación de Windows > \Microsoft.NET\Framework\\< versión\>\CONFIG\machine.config, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7014-143">To do this, click **Start**, click **Run**, type notepad \<Windows install path>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a7014-144">Actualice el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="a7014-144">Update the machine.config file.</span></span> <span data-ttu-id="a7014-145">Si el archivo no contiene una sección de system.serviceModel, agregue la siguiente sección al final del archivo de configuración, pero antes de que el cierre raíz etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a7014-145">If the file does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7014-146">Reemplace "myAdapterBinding", versión, referencia cultural y otra información específica del ensamblado con la información de su adaptador.</span><span class="sxs-lookup"><span data-stu-id="a7014-146">Replace "myAdapterBinding", version, culture and other assembly-specific information with your adapter's information.</span></span>  
  
    ```  
    \<system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
        </bindingExtensions>      <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
      </extensions>  
    \</system.serviceModel>  
    ```  
  
     - <span data-ttu-id="a7014-147">O BIEN</span><span class="sxs-lookup"><span data-stu-id="a7014-147">OR -</span></span>  
  
     <span data-ttu-id="a7014-148">Si el archivo machine.config contiene una sección de system.serviceModel, determinar qué elementos se encuentran y agregan, reemplazando "MyAdapter" y otra información con la información de su adaptador.</span><span class="sxs-lookup"><span data-stu-id="a7014-148">If your machine.config file contains a system.serviceModel section, determine which elements are missing and add them, replacing "MyAdapter" and other information with your adapter's information.</span></span>  
  
    ```  
    <extensions>  
      <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
      </bindingExtensions>  
          <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
    </extensions>  
    ```  
  
3.  <span data-ttu-id="a7014-149">Cierre y guarde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="a7014-149">Close and save the machine.config file.</span></span>  
  
 <span data-ttu-id="a7014-150">También puede usar el [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para modificar el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="a7014-150">You can also use the [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) to modify the machine.config file.</span></span>
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="a7014-151">Edite el archivo machine.config con el Editor de configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="a7014-151">Edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="a7014-152">Abra la **Editor de configuración de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a7014-152">Open the **Service Configuration Editor**.</span></span> <span data-ttu-id="a7014-153">Vea [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7014-153">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for  more information.</span></span>
  
2.  <span data-ttu-id="a7014-154">En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos.</span><span class="sxs-lookup"><span data-stu-id="a7014-154">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="a7014-155">Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione el elemento de extensiones de enlace.</span><span class="sxs-lookup"><span data-stu-id="a7014-155">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
     <span data-ttu-id="a7014-156">![Editor de configuración de servicio. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span><span class="sxs-lookup"><span data-stu-id="a7014-156">![Service configuration editor.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span></span>  
  
3.  <span data-ttu-id="a7014-157">Cree una nueva extensión de enlace.</span><span class="sxs-lookup"><span data-stu-id="a7014-157">Create a new binding extension.</span></span> <span data-ttu-id="a7014-158">Haga clic en el **New** botón para abrir la extensión **Editor de elementos de configuración** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a7014-158">Click the **New** button to open the Extension **Configuration Element Editor** dialog box.</span></span> <span data-ttu-id="a7014-159">En **nombre de configuración**, escriba un nombre único para las extensiones, por ejemplo *MyAdapterExtension*.</span><span class="sxs-lookup"><span data-stu-id="a7014-159">In **Configuration Name**, enter a unique name for the extensions, for example *MyAdapterExtension*.</span></span>  
  
     <span data-ttu-id="a7014-160">![Editor de elementos de configuración de extensiones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span><span class="sxs-lookup"><span data-stu-id="a7014-160">![Extension configuration element editor](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span></span>  
  
4.  <span data-ttu-id="a7014-161">Haga clic en el **tipo** campo y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el **Explorador de tipos de extensión de enlace** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a7014-161">Click the **Type** field, and then click the ellipsis button (**...**) to open the **Binding Extension Type Browser** dialog box.</span></span>  
  
5.  <span data-ttu-id="a7014-162">Haga clic en el icono de (GAC) de la caché global de ensamblados para obtener una lista de los archivos DLL en la GAC.</span><span class="sxs-lookup"><span data-stu-id="a7014-162">Click the global assembly cache (GAC) icon to list the DLLs in the GAC.</span></span>  
  
6.  <span data-ttu-id="a7014-163">Haga clic en su ensamblado de adaptador.</span><span class="sxs-lookup"><span data-stu-id="a7014-163">Click your adapter assembly.</span></span>  
  
     <span data-ttu-id="a7014-164">![Crear Explorador de tipo de extensión. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span><span class="sxs-lookup"><span data-stu-id="a7014-164">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span></span>  
  
7.  <span data-ttu-id="a7014-165">Haga clic en el **abiertos** para seleccionar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7014-165">Click the **Open** button to select the assembly.</span></span>  
  
8.  <span data-ttu-id="a7014-166">En el **el Explorador de tipos de extensión de enlace** diálogo cuadro, haga clic en el nombre del tipo que implementa el elemento de la colección de enlace.</span><span class="sxs-lookup"><span data-stu-id="a7014-166">In the **Binding Extension Type Browser** dialog box, click the type name that implements the binding collection element.</span></span>  
  
     <span data-ttu-id="a7014-167">![Crear Explorador de tipo de extensión. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span><span class="sxs-lookup"><span data-stu-id="a7014-167">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span></span>  
  
9. <span data-ttu-id="a7014-168">Haga clic en el **abiertos** para seleccionar el tipo.</span><span class="sxs-lookup"><span data-stu-id="a7014-168">Click the **Open** button to select the type.</span></span>  
  
10. <span data-ttu-id="a7014-169">Haga clic en **Aceptar** para cerrar el **Editor de elementos de configuración de extensiones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a7014-169">Click **OK** to close the **Extension Configuration Element Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="a7014-170">En el panel de detalles de la **enlace extensiones de Editor**, compruebe que aparece la extensión de enlace.</span><span class="sxs-lookup"><span data-stu-id="a7014-170">In the details pane of the **Binding Extensions Editor**, verify that your binding extension appears.</span></span> <span data-ttu-id="a7014-171">En la ilustración siguiente, se resalta MyAdapterExtension.</span><span class="sxs-lookup"><span data-stu-id="a7014-171">In the following figure, MyAdapterExtension is highlighted.</span></span>  
  
     <span data-ttu-id="a7014-172">![Editor de configuración de servicio con extensión agregada. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="a7014-172">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
12. <span data-ttu-id="a7014-173">Cerrar la **Editor de configuración de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a7014-173">Close the **Service Configuration Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7014-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7014-174">See Also</span></span>  
 <span data-ttu-id="a7014-175">[Implementación](../../core/deployment-limitations1.md) </span><span class="sxs-lookup"><span data-stu-id="a7014-175">[Deployment](../../core/deployment-limitations1.md) </span></span>  
 [<span data-ttu-id="a7014-176">Implementar un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="a7014-176">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)
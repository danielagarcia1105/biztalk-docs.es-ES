---
title: "Actualizar o desinstalar el módulo de adaptador de BizTalk 2016 | Documentos de Microsoft"
description: "Usar el Asistente para la instalación o msiexec para cambiar o desinstalar 2016 BAP incluidos con BizTalk Server; incluidos los quite los enlaces y quite las RFC personalizadas"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c30fa3b107113991a8b4893fa2626a53d67159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="3af46-103">Actualizar o desinstalar el módulo de adaptador de BizTalk 2016</span><span class="sxs-lookup"><span data-stu-id="3af46-103">Update or uninstall the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="3af46-104">Cómo cambiar o desinstalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af46-104">How to change or uninstall the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a><span data-ttu-id="3af46-105">Cambiar o actualizar la instalación</span><span class="sxs-lookup"><span data-stu-id="3af46-105">Change or update the installation</span></span>  
<span data-ttu-id="3af46-106">Antes de ejecutar el Asistente para la instalación para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, asegúrese de que el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="3af46-106">Before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] is installed.</span></span> 
  
 <span data-ttu-id="3af46-107">Puede modificar la instalación en modo interactivo (el Asistente para la instalación), o en modo silencioso (la línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="3af46-107">You can modify the installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
### <a name="use-the-setup-wizard"></a><span data-ttu-id="3af46-108">Use el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="3af46-108">Use the setup wizard</span></span>  
  
1.  <span data-ttu-id="3af46-109">Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3af46-109">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="3af46-110">En **programas y características**, seleccione **desinstalar un programa**.</span><span class="sxs-lookup"><span data-stu-id="3af46-110">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3.  <span data-ttu-id="3af46-111">Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **cambio**.</span><span class="sxs-lookup"><span data-stu-id="3af46-111">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4.  <span data-ttu-id="3af46-112">En la pantalla de bienvenida, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3af46-112">On the Welcome screen, select **Next**.</span></span>  
  
5.  <span data-ttu-id="3af46-113">En **cambiar, reparar o quitar instalación**:</span><span class="sxs-lookup"><span data-stu-id="3af46-113">In **Change, repair, or remove installation**:</span></span>  
  
    -   <span data-ttu-id="3af46-114">Para seleccionar los componentes que desea instalar, seleccione **cambio** y vaya al paso 6.</span><span class="sxs-lookup"><span data-stu-id="3af46-114">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
    -   <span data-ttu-id="3af46-115">Para reparar los errores en la instalación más reciente, seleccione **reparar** y vaya al paso 7.</span><span class="sxs-lookup"><span data-stu-id="3af46-115">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
    -   <span data-ttu-id="3af46-116">Para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo, seleccione **quitar** y, a continuación, vaya al paso 10.</span><span class="sxs-lookup"><span data-stu-id="3af46-116">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6.  <span data-ttu-id="3af46-117">Si decide modificar la instalación:</span><span class="sxs-lookup"><span data-stu-id="3af46-117">If you chose to modify the installation:</span></span>  
  
    -   <span data-ttu-id="3af46-118">Expanda el **Microsoft BizTalk Adapter Pack** nodo optar por instalar los adaptadores de base, los proveedores de datos de .NET Framework o ambos.</span><span class="sxs-lookup"><span data-stu-id="3af46-118">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
    -   <span data-ttu-id="3af46-119">Expanda el **Base adaptadores** nodo optar por instalar todos los adaptadores o adaptadores específicos.</span><span class="sxs-lookup"><span data-stu-id="3af46-119">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
    -   <span data-ttu-id="3af46-120">Expanda el **ADO proveedores** nodo optar por instalar todos los proveedores o proveedores específicos.</span><span class="sxs-lookup"><span data-stu-id="3af46-120">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
    -   <span data-ttu-id="3af46-121">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3af46-121">Select **Next**.</span></span>  
  
    -   <span data-ttu-id="3af46-122">Seleccione **cambio**y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-122">Select **Change**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="3af46-123">Si decide reparar la instalación, en la **preparado para reparar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **reparar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-123">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="3af46-124">Inicia el Asistente para reparar la instalación.</span><span class="sxs-lookup"><span data-stu-id="3af46-124">The wizard starts repairing the installation.</span></span>  
  
8.  <span data-ttu-id="3af46-125">Si es necesario, cambie las preferencias en relación con la aceptación de CEIP y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-125">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="3af46-126">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-126">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="3af46-127">Si decide quitar los adaptadores, en el **listo para quitar Microsoft BizTalk Adapter Pack** cuadro de diálogo, seleccione **quitar**y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-127">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
### <a name="use-msiexec-in-silent-mode"></a><span data-ttu-id="3af46-128">Usar msiexec en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="3af46-128">Use msiexec in silent mode</span></span>  
  
1.  <span data-ttu-id="3af46-129">Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="3af46-129">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="3af46-130">Ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3af46-130">Run a command similar to the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3af46-131">Para modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.</span><span class="sxs-lookup"><span data-stu-id="3af46-131">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     <span data-ttu-id="3af46-132">Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]e instala el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af46-132">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
     <span data-ttu-id="3af46-133">Mediante el uso de valores diferentes para la `REMOVE` y `ADDLOCAL` propiedades, puede agregar o quitar componentes específicos.</span><span class="sxs-lookup"><span data-stu-id="3af46-133">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="3af46-134">Hacer referencia a la tabla de **instalar en modo silencioso** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) para obtener información acerca de los valores que puede usar para estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="3af46-134">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for these properties.</span></span>  
  
     <span data-ttu-id="3af46-135">También puede hacer una reparación silenciosa mediante la opción/f como parte del comando msiexec.</span><span class="sxs-lookup"><span data-stu-id="3af46-135">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="3af46-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3af46-136">For example:</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     <span data-ttu-id="3af46-137">Puede utilizar diversas combinaciones diferentes con la opción/f.</span><span class="sxs-lookup"><span data-stu-id="3af46-137">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="3af46-138">Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`.</span><span class="sxs-lookup"><span data-stu-id="3af46-138">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="3af46-139">O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span><span class="sxs-lookup"><span data-stu-id="3af46-139">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3af46-140">Al modificar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación en modo silencioso, no se puede cambiar sus preferencias para participar o excluir el CEIP.</span><span class="sxs-lookup"><span data-stu-id="3af46-140">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="3af46-141">Las preferencias que seleccionó durante la instalación se conserva, incluso si se establece explícitamente el CEIP_OPTIN en true o false.</span><span class="sxs-lookup"><span data-stu-id="3af46-141">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a><span data-ttu-id="3af46-142">Desinstalar o eliminar el módulo de adaptador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3af46-142">Uninstall or remove the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3af46-143">Si ha creado las tablas en la base de datos de SQL Server para que funcione con la característica de tRFC de la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], debe quitarlos manualmente antes de desinstalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af46-143">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before uninstalling the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="3af46-144">El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] de instalación copia un `SapAdapter-DbScript-Uninstall.sql` archivos normalmente en  *\<unidad de instalación >: \Program [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* .</span><span class="sxs-lookup"><span data-stu-id="3af46-144">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a `SapAdapter-DbScript-Uninstall.sql` file typically at *\<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="3af46-145">Ejecute este archivo para quitar las tablas que creó.</span><span class="sxs-lookup"><span data-stu-id="3af46-145">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="3af46-146">Complete los pasos siguientes para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="3af46-146">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="3af46-147">Asegúrese de que tiene el [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] instalado antes de ejecutar el Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="3af46-147">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard.</span></span>  
  
 <span data-ttu-id="3af46-148">Puede quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo (Asistente para la instalación), o en modo silencioso (línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="3af46-148">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
### <a name="uninstall-using-the-setup-wizard"></a><span data-ttu-id="3af46-149">Desinstalar mediante el Asistente para la instalación</span><span class="sxs-lookup"><span data-stu-id="3af46-149">Uninstall using the setup wizard</span></span>  
  
1.  <span data-ttu-id="3af46-150">En **programas y características**, seleccione **desinstalar un programa**.</span><span class="sxs-lookup"><span data-stu-id="3af46-150">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="3af46-151">Haga clic en **Microsoft BizTalk Adapter Pack**y, a continuación, seleccione **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="3af46-151">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="3af46-152">Desinstalar en modo silencioso</span><span class="sxs-lookup"><span data-stu-id="3af46-152">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="3af46-153">Abra un símbolo del sistema y vaya al directorio raíz de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalador.</span><span class="sxs-lookup"><span data-stu-id="3af46-153">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="3af46-154">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3af46-154">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3af46-155">Para quitar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo silencioso en una plataforma basada en x64, en los siguientes comandos, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi`.</span><span class="sxs-lookup"><span data-stu-id="3af46-155">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     <span data-ttu-id="3af46-156">Este comando quita el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] desde el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="3af46-156">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
     <span data-ttu-id="3af46-157">Al proporcionar valores diferentes para la `REMOVE` propiedad, puede quitar los componentes específicos de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="3af46-157">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="3af46-158">Hacer referencia a la tabla de **instalar en modo silencioso** en [instalar BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) para obtener información acerca de los valores que puede usar para esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="3af46-158">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for this property.</span></span>  
  
     <span data-ttu-id="3af46-159">Para quitar completamente el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3af46-159">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     <span data-ttu-id="3af46-160">Para obtener más información sobre el tipo de comando msiexec `msiexec` en la línea de comandos y presione `ENTER`.</span><span class="sxs-lookup"><span data-stu-id="3af46-160">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="3af46-161">O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span><span class="sxs-lookup"><span data-stu-id="3af46-161">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
## <a name="remove-the-bindings"></a><span data-ttu-id="3af46-162">Quitar los enlaces</span><span class="sxs-lookup"><span data-stu-id="3af46-162">Remove the bindings</span></span>  
 <span data-ttu-id="3af46-163">Siga estos pasos *sólo* si se produce un error en el Asistente para la instalación quitar los enlaces del adaptador o el registro del proveedor de datos de .NET Framework desde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3af46-163">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="3af46-164">Vaya al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3af46-164">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="3af46-165">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config  *\<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG*.</span><span class="sxs-lookup"><span data-stu-id="3af46-165">For example, on a 32-bit platform, the machine.config is available under *\<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  
  
2.  <span data-ttu-id="3af46-166">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="3af46-166">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="3af46-167">Quitar el registro de enlace del adaptador:</span><span class="sxs-lookup"><span data-stu-id="3af46-167">Remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="3af46-168">Busque la `system.serviceModel` elemento y quitar lo siguiente en el elemento:</span><span class="sxs-lookup"><span data-stu-id="3af46-168">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="3af46-169">Busque la `bindingElementExtensions` elemento bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3af46-169">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="3af46-170">Quitar las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador disponible.</span><span class="sxs-lookup"><span data-stu-id="3af46-170">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="3af46-171">Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.</span><span class="sxs-lookup"><span data-stu-id="3af46-171">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="3af46-172">Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-172">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-173">Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-173">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-174">Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-174">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-175">Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-175">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-176">Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-176">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="3af46-177">Busque la `bindingExtensions` elemento bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="3af46-177">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="3af46-178">Quitar las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador disponible.</span><span class="sxs-lookup"><span data-stu-id="3af46-178">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="3af46-179">Si el Asistente para la instalación no puede quitar cualquiera, debe quitar todos los enlaces.</span><span class="sxs-lookup"><span data-stu-id="3af46-179">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="3af46-180">Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-180">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-181">Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-181">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-182">Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-182">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-183">Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-183">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-184">Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-184">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="3af46-185">Quitar el registro del proveedor de datos de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3af46-185">Remove the .NET Framework Data Provider registration:</span></span>  
  
    -   <span data-ttu-id="3af46-186">Busque la `DbProviderFactories` elemento bajo el nodo system.data.</span><span class="sxs-lookup"><span data-stu-id="3af46-186">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    -   <span data-ttu-id="3af46-187">Busque los proveedores de datos de .NET Framework que todavía están registrados.</span><span class="sxs-lookup"><span data-stu-id="3af46-187">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="3af46-188">Quitar las siguientes secciones en el `DbProviderFactories` nodo, en función de los proveedores de datos existente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3af46-188">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="3af46-189">Si existen, debe quitar todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="3af46-189">You must remove all the providers if they exist.</span></span>  
  
         <span data-ttu-id="3af46-190">Para [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-190">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="3af46-191">Para [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], quitar:</span><span class="sxs-lookup"><span data-stu-id="3af46-191">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="3af46-192">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="3af46-192">Save and close the machine.config file.</span></span>  
  
## <a name="remove-the-custom-rfcs"></a><span data-ttu-id="3af46-193">Quitar las RFC personalizadas</span><span class="sxs-lookup"><span data-stu-id="3af46-193">Remove the custom RFCs</span></span>  
<span data-ttu-id="3af46-194">Complete este paso para quitar las RFC personalizadas que ha instalado en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3af46-194">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="3af46-195">Vea [instalar o quitar las solicitudes de cambio personalizadas](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="3af46-195">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  

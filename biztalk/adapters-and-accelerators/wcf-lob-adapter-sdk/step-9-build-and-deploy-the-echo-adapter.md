---
title: 'Paso 9: Compilar e implementar el adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e0bae620c43504091c29ed2b03a33e0c7710c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980509"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a><span data-ttu-id="adf03-102">Paso 9: Compilar e implementar el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="adf03-102">Step 9: Build and Deploy the Echo Adapter</span></span>
<span data-ttu-id="adf03-103">![Paso 9 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="adf03-103">![Step 9 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="adf03-104">**Tiempo en completarse:** 10 minutos</span><span class="sxs-lookup"><span data-stu-id="adf03-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="adf03-105">En este paso, realizará las tareas necesarias para implementar el adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="adf03-105">In this step, you will perform the tasks necessary to deploy the Echo Adapter.</span></span> <span data-ttu-id="adf03-106">Esto implica que todos los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="adf03-106">This involves all of the following:</span></span>  
  
- <span data-ttu-id="adf03-107">Cree un archivo de nombre seguro y asignarlo al ensamblado del adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="adf03-107">Create a strong name file and assign it to the Echo Adapter assembly</span></span>  
  
- <span data-ttu-id="adf03-108">Crear el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="adf03-108">Build the Echo Adapter</span></span>  
  
- <span data-ttu-id="adf03-109">Publicar el ensamblado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="adf03-109">Publish the assembly into the GAC</span></span>  
  
- <span data-ttu-id="adf03-110">Registrar el adaptador de Echo con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adf03-110">Register the Echo Adapter with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="adf03-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="adf03-111">Prerequisites</span></span>  
 <span data-ttu-id="adf03-112">Para completar correctamente este paso, debe estar familiarizado con los archivos de nombre seguro y la GAC.</span><span class="sxs-lookup"><span data-stu-id="adf03-112">To successfully complete this step, you should be familiar with strong name files and the GAC.</span></span> <span data-ttu-id="adf03-113">Un conocimiento básico de [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuración es útil, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="adf03-113">A basic understanding of [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuration is helpful but not required.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="adf03-114">Para asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="adf03-114">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="adf03-115">En el Explorador de soluciones, haga clic en el **EchoAdapter** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="adf03-115">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="adf03-116">En el cuadro de diálogo páginas de propiedades EchoAdapter seleccione **firma** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="adf03-116">In the EchoAdapter Property Pages dialog box, select **Signing** from the left pane.</span></span>  
  
3.  <span data-ttu-id="adf03-117">Haga clic en el **firmar el ensamblado** ficha.</span><span class="sxs-lookup"><span data-stu-id="adf03-117">Click the **Sign the assembly** tab.</span></span>  
  
4.  <span data-ttu-id="adf03-118">Elija **\<nuevo... \>** para el archivo de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="adf03-118">Choose **\<new…\>** for the strong name file.</span></span> <span data-ttu-id="adf03-119">Cuando se le pida un nombre de archivo, escriba **EchoAdapter.snk**, anule la selección del proteger mi archivo de clave con una opción de contraseña y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="adf03-119">When prompted for a file name, type **EchoAdapter.snk**,deselect the protect my key file with a password option, then click **OK**.</span></span>  
  
5.  <span data-ttu-id="adf03-120">Haga clic en el **aplicación** ficha.</span><span class="sxs-lookup"><span data-stu-id="adf03-120">Click the **Application** tab.</span></span>  
  
6.  <span data-ttu-id="adf03-121">Cambie el nombre de ensamblado a **Microsoft.Adapters.Samples.EchoV2**.</span><span class="sxs-lookup"><span data-stu-id="adf03-121">Change the assembly name to **Microsoft.Adapters.Samples.EchoV2**.</span></span>  
  
7.  <span data-ttu-id="adf03-122">Haga clic en **archivo** en el menú de Visual Studio, a continuación, elija **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="adf03-122">Click **File** on the Visual Studio menu then choose **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-echo-adapter"></a><span data-ttu-id="adf03-123">Para compilar e implementar el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="adf03-123">To build and deploy Echo Adapter</span></span>  
  
1.  <span data-ttu-id="adf03-124">En el Explorador de soluciones, haga clic en el **EchoAdapter** del proyecto y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="adf03-124">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Build**.</span></span> <span data-ttu-id="adf03-125">Si la compilación no se realiza correctamente, corrija los errores e intente volver a generar el adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="adf03-125">If the build does not succeed, fix any errors and try rebuilding the Echo Adapter.</span></span>  
  
2.  <span data-ttu-id="adf03-126">Abra un símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="adf03-126">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="adf03-127">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="adf03-127">Type the following command:</span></span>  
  
     <span data-ttu-id="adf03-128">**Gacutil.exe /if "\<**  *ruta de acceso a assembly\Microsoft.Adapters.Samples.EchoV2.dll*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="adf03-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **\>"**</span></span>  
  
     <span data-ttu-id="adf03-129">Se instalará el ensamblado en la GAC, sobrescribiendo cualquier ensamblado existente con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="adf03-129">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a><span data-ttu-id="adf03-130">Para registrar el adaptador de Echo con Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="adf03-130">To register the Echo Adapter with Windows Communication Foundation</span></span>  
  
1. <span data-ttu-id="adf03-131">Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="adf03-131">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="adf03-132">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **el Bloc de notas \<ruta de instalación de Windows\>\Microsoft.NET\Framework\\< versión\>\CONFIG\machine.config**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="adf03-132">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="adf03-133">Actualice el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="adf03-133">Update the machine.config file.</span></span> <span data-ttu-id="adf03-134">Si el archivo machine.config no tiene una sección de system.serviceModel, agregue la siguiente sección al final del archivo de configuración, pero antes de que el cierre de raíz de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="adf03-134">If your machine.config does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="adf03-135">Reemplace la versión, referencia cultural, token de clave pública y otra información específica del ensamblado con la información de su adaptador.</span><span class="sxs-lookup"><span data-stu-id="adf03-135">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <system.serviceModel>  
     <client>  
       <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
         name="echov2" />  
     </client>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingElementExtensions>  
       <bindingExtensions>  
         <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - <span data-ttu-id="adf03-136">O BIEN</span><span class="sxs-lookup"><span data-stu-id="adf03-136">OR -</span></span>  
  
     <span data-ttu-id="adf03-137">Si el archivo machine.config contiene una sección de system.serviceModel, determinar qué elementos se encuentran y agregan.</span><span class="sxs-lookup"><span data-stu-id="adf03-137">If your machine.config contains a system.serviceModel section, determine which elements are missing and add them.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="adf03-138">Reemplace la versión, referencia cultural, token de clave pública y otra información específica del ensamblado con la información de su adaptador.</span><span class="sxs-lookup"><span data-stu-id="adf03-138">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <client>  
     <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
       name="echov2" />  
   </client>  
   <extensions>  
     <bindingElementExtensions>  
       <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingElementExtensions>  
     <bindingExtensions>  
       <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingExtensions>  
   </extensions>  
   ```  
  
3. <span data-ttu-id="adf03-139">Guarde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="adf03-139">Save the machine.config file.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="adf03-140">¿Qué simplemente hacer?</span><span class="sxs-lookup"><span data-stu-id="adf03-140">What Did I Just Do?</span></span>  
 <span data-ttu-id="adf03-141">En este paso final del tutorial de adaptador de Echo, agrega un nombre seguro para el adaptador de Echo, compilado e implementa el adaptador y modifica Machine.config para incluir información acerca del adaptador.</span><span class="sxs-lookup"><span data-stu-id="adf03-141">In this final step of the Echo Adapter tutorial, you added a strong name to the Echo Adapter, built and deployed the adapter, then modified Machine.config to include information about the adapter.</span></span> <span data-ttu-id="adf03-142">En este momento, el adaptador de Echo debe estar disponible para las aplicaciones consumidoras.</span><span class="sxs-lookup"><span data-stu-id="adf03-142">At this point, the Echo Adapter should be available to consuming applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="adf03-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="adf03-143">Next Steps</span></span>  
 <span data-ttu-id="adf03-144">Este tutorial está completa.</span><span class="sxs-lookup"><span data-stu-id="adf03-144">This tutorial is complete.</span></span> <span data-ttu-id="adf03-145">Si desea probar la funcionalidad de adaptador de Echo en un proyecto. NET, consulte [Tutorial 2: usar el adaptador de Echo desde .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span><span class="sxs-lookup"><span data-stu-id="adf03-145">If you want to test Echo Adapter functionality in a .NET project, see [Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf03-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="adf03-146">See Also</span></span>  
 <span data-ttu-id="adf03-147">[Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="adf03-147">[Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="adf03-148">Tutorial 2: Usar el adaptador de Echo desde .NET</span><span class="sxs-lookup"><span data-stu-id="adf03-148">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)
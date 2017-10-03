---
title: "Solucionar problemas de instalación con el adaptador de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b254f317740b8fcff0bc97dc0891ae19fb8d594
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a><span data-ttu-id="2acb9-102">Solucionar problemas de instalación con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="2acb9-102">Troubleshoot Installation Issues with the Siebel adapter</span></span>
<span data-ttu-id="2acb9-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="2acb9-103">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="2acb9-104">Esta sección describen técnicas de solución de problemas para resolver errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="2acb9-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="setup-logging"></a><span data-ttu-id="2acb9-105">Registro de la instalación</span><span class="sxs-lookup"><span data-stu-id="2acb9-105">Setup Logging</span></span>  
 <span data-ttu-id="2acb9-106">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2acb9-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="2acb9-107">Además, el programa de instalación también realiza algunas acciones personalizadas como el registro de los enlaces del adaptador.</span><span class="sxs-lookup"><span data-stu-id="2acb9-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="2acb9-108">Puede registrar mensajes para las acciones de estándares, así como personalizados realizadas por el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="2acb9-108">You can log messages for both the standard as well as custom actions performed by the setup.</span></span>  
  
-   <span data-ttu-id="2acb9-109">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación instala los archivos específicos del adaptador con un archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="2acb9-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="2acb9-110">Por lo tanto, el registro para el programa de instalación será el registro MSI estándar.</span><span class="sxs-lookup"><span data-stu-id="2acb9-110">Hence, the logging for the setup will be the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="2acb9-111">Registros para las acciones personalizadas realizadas por el programa de instalación están disponibles en % TEMP%\adaptersetup.log.</span><span class="sxs-lookup"><span data-stu-id="2acb9-111">Logs for the custom actions performed by the setup program are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="2acb9-112">Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="2acb9-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="2acb9-113">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="2acb9-113">Known Issues</span></span>  
  
### <a name="setup-fails-to-register-adapter-bindings"></a><span data-ttu-id="2acb9-114">El programa de instalación no puede registrar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="2acb9-114">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="2acb9-115">**Problema**</span><span class="sxs-lookup"><span data-stu-id="2acb9-115">**Problem**</span></span>  
  
 <span data-ttu-id="2acb9-116">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace o [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="2acb9-116">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding or the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="2acb9-117">**Causa**</span><span class="sxs-lookup"><span data-stu-id="2acb9-117">**Cause**</span></span>  
  
 <span data-ttu-id="2acb9-118">Esto podría producir debido a problemas con la instalación de WCF, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config está dañado.</span><span class="sxs-lookup"><span data-stu-id="2acb9-118">This might result due to problems with WCF installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config being corrupt.</span></span> <span data-ttu-id="2acb9-119">Los enlaces del adaptador se escriben en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="2acb9-119">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="2acb9-120">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="2acb9-120">**Resolution**</span></span>  
  
<span data-ttu-id="2acb9-121">Registrar manualmente el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace y [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2acb9-121">Manually register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding and [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using the following steps:</span></span> 
  
1.  <span data-ttu-id="2acb9-122">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="2acb9-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="2acb9-123">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="2acb9-123">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="2acb9-124">En esta ruta de acceso, \<versión > es la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2acb9-124">In this path, \<version> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="2acb9-125">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="2acb9-125">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="2acb9-126">Para registrar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace:</span><span class="sxs-lookup"><span data-stu-id="2acb9-126">To register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="2acb9-127">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="2acb9-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="2acb9-128">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="2acb9-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="2acb9-129">Busque la falta [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="2acb9-129">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="2acb9-130">Agregue la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="2acb9-130">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="2acb9-131">Para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="2acb9-131">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="2acb9-132">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="2acb9-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="2acb9-133">Busque la falta [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="2acb9-133">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="2acb9-134">Agregue las siguientes secciones bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="2acb9-134">Add the following sections under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="2acb9-135">Para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="2acb9-135">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="2acb9-136">Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="2acb9-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="2acb9-137">Para registrar el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2acb9-137">To register the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="2acb9-138">Busque el elemento DbProviderFactories bajo el nodo system.data.</span><span class="sxs-lookup"><span data-stu-id="2acb9-138">Search for the element DbProviderFactories under the system.data node.</span></span>  
  
    2.  <span data-ttu-id="2acb9-139">Busque la falta [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2acb9-139">Look for the missing [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="2acb9-140">Agregue la siguiente sección bajo el nodo DbProviderFactories.</span><span class="sxs-lookup"><span data-stu-id="2acb9-140">Add the following section under the DbProviderFactories node.</span></span>  
  
         <span data-ttu-id="2acb9-141">Para [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="2acb9-141">For [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="2acb9-142">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="2acb9-142">Save and close the machine.config file.</span></span>  
  
####  <span data-ttu-id="2acb9-143"><a name="BKMK_PubKey"></a>Determinar la versión y la clave pública</span><span class="sxs-lookup"><span data-stu-id="2acb9-143"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="2acb9-144">Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] o [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2acb9-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] or [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="2acb9-145">Para determinar la clave pública</span><span class="sxs-lookup"><span data-stu-id="2acb9-145">To determine the public key</span></span>  
  
1.  <span data-ttu-id="2acb9-146">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="2acb9-146">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="2acb9-147">Haga clic en el archivo DLL para el que desea que el público clave y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2acb9-147">Right-click the DLL for which you want the public key and select **Properties**.</span></span> <span data-ttu-id="2acb9-148">En la tabla siguiente se muestra el nombre de los archivos DLL para cada adaptador y el proveedor.</span><span class="sxs-lookup"><span data-stu-id="2acb9-148">The following table lists the name of the DLLs for each adapter and provider.</span></span>  
  
    |<span data-ttu-id="2acb9-149">Proveedor de adaptador/ADO</span><span class="sxs-lookup"><span data-stu-id="2acb9-149">Adapter/ADO Provider</span></span>|<span data-ttu-id="2acb9-150">Nombre de la DLL</span><span class="sxs-lookup"><span data-stu-id="2acb9-150">Name of the DLL</span></span>|  
    |---------------------------|---------------------|  
    |[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="2acb9-151">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="2acb9-151">Microsoft.Adapters.Siebel</span></span>|  
    |[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="2acb9-152">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="2acb9-152">Microsoft.Data.SiebelClient</span></span>|  
  
3.  <span data-ttu-id="2acb9-153">En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="2acb9-153">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="2acb9-154">Valor de forma similar, en la **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="2acb9-154">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="2acb9-155">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="2acb9-155">Copy the public key, and then click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acb9-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="2acb9-156">See Also</span></span>  
[<span data-ttu-id="2acb9-157">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="2acb9-157">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
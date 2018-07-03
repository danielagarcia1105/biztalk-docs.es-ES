---
title: Solucionar problemas de instalación con el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a72a5e2da055a9e4137e3e8954b72ad32cde40db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982733"
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a><span data-ttu-id="5dbaa-102">Solucionar problemas de instalación con el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="5dbaa-102">Troubleshoot Installation Issues with the SAP adapter</span></span>
<span data-ttu-id="5dbaa-103">Instalación de Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="5dbaa-104">En esta sección se describe las técnicas de solución de problemas para resolver errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  

## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="5dbaa-105">Mensajes de registro de acciones de instalación</span><span class="sxs-lookup"><span data-stu-id="5dbaa-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="5dbaa-106">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbaa-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5dbaa-107">Además, el programa de instalación también lleva a cabo determinadas acciones como el registro de los enlaces del adaptador personalizados.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="5dbaa-108">Puede registrar mensajes para las acciones estándares como personalizadas que realiza la instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  

- <span data-ttu-id="5dbaa-109">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación instala los archivos específicos del adaptador mediante MSI.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="5dbaa-110">Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-110">Hence, the logging for the setup is the standard MSI logging.</span></span>  

- <span data-ttu-id="5dbaa-111">Los registros para las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-111">Logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="5dbaa-112">Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  

##  <a name="BKMK_SAPSetupBinding"></a> <span data-ttu-id="5dbaa-113">Se produce un error en el programa de instalación registrar los enlaces del adaptador o proveedores de datos</span><span class="sxs-lookup"><span data-stu-id="5dbaa-113">Setup fails to register adapter bindings or data providers</span></span>  
 <span data-ttu-id="5dbaa-114">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-114">**Problem**</span></span>  

 <span data-ttu-id="5dbaa-115">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] produce un error en el Asistente para la instalación registrar los enlaces del adaptador o el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-115">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings or the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], but proceeds with the adapter installation.</span></span>  

 <span data-ttu-id="5dbaa-116">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-116">**Cause**</span></span>  

 <span data-ttu-id="5dbaa-117">Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-117">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="5dbaa-118">Los enlaces del adaptador se escriben en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-118">The adapter bindings are written to the machine.config file.</span></span>  

 <span data-ttu-id="5dbaa-119">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-119">**Resolution**</span></span>  

 <span data-ttu-id="5dbaa-120">Se debe registrar manualmente el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace o [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbaa-120">You should manually register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding or the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  

### <a name="register-the-adapter-bindings-or-the-data-provider"></a><span data-ttu-id="5dbaa-121">Registrar los enlaces del adaptador o el proveedor de datos</span><span class="sxs-lookup"><span data-stu-id="5dbaa-121">Register the adapter bindings or the data provider</span></span>  

1. <span data-ttu-id="5dbaa-122">Navegue al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="5dbaa-123">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-123">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    <span data-ttu-id="5dbaa-124">En esta ruta de acceso, \<versión\> es la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-124">In this path, \<version\> is the version of the .NET Framework.</span></span>  

2. <span data-ttu-id="5dbaa-125">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-125">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="5dbaa-126">Para registrar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-126">To register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding:</span></span>  

   1. <span data-ttu-id="5dbaa-127">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
      </client>  
      ```  

   2. <span data-ttu-id="5dbaa-128">Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="5dbaa-129">Busque el campo que falta [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-129">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="5dbaa-130">Agregue la siguiente sección en el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="5dbaa-130">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="5dbaa-131">Para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-131">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="5dbaa-132">Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="5dbaa-133">Busque el campo que falta [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-133">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="5dbaa-134">Agregue la siguiente sección en el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="5dbaa-134">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="5dbaa-135">Para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-135">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

      > [!NOTE]
      >  <span data-ttu-id="5dbaa-136">Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="5dbaa-137">Para registrar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-137">To register the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  

   1. <span data-ttu-id="5dbaa-138">Busque el elemento "DbProviderFactories" bajo el nodo "system.data".</span><span class="sxs-lookup"><span data-stu-id="5dbaa-138">Search for the element "DbProviderFactories" under the "system.data" node.</span></span>  

   2. <span data-ttu-id="5dbaa-139">Busque el campo que falta [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbaa-139">Look for the missing [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="5dbaa-140">Agregue la siguiente sección en el nodo "DbProviderFactories".</span><span class="sxs-lookup"><span data-stu-id="5dbaa-140">Add the following section under the "DbProviderFactories" node.</span></span>  

       <span data-ttu-id="5dbaa-141">Para [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-141">For [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], add:</span></span>  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="5dbaa-142">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-142">Save and close the machine.config file.</span></span>  

###  <a name="BKMK_PubKey"></a> <span data-ttu-id="5dbaa-143">Determinación de la clave pública y versión</span><span class="sxs-lookup"><span data-stu-id="5dbaa-143">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="5dbaa-144">Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] o [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbaa-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] or [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  

1. <span data-ttu-id="5dbaa-145">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="5dbaa-146">Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-146">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="5dbaa-147">En la tabla siguiente se muestra el nombre de los archivos DLL para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbaa-147">The following table lists the name of the DLLs for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  


   |                           <span data-ttu-id="5dbaa-148">Proveedor de datos del adaptador</span><span class="sxs-lookup"><span data-stu-id="5dbaa-148">Adapter/Data Provider</span></span>                           |     <span data-ttu-id="5dbaa-149">Nombre del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="5dbaa-149">Name of the DLL</span></span>      |
   |---------------------------------------------------------------------------|--------------------------|
   |    [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]    |  <span data-ttu-id="5dbaa-150">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="5dbaa-150">Microsoft.Adapters.SAP</span></span>  |
   | [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] | <span data-ttu-id="5dbaa-151">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="5dbaa-151">Microsoft.Data.SAPClient</span></span> |


3. <span data-ttu-id="5dbaa-152">En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-152">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="5dbaa-153">De forma similar, valor frente a la **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-153">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="5dbaa-154">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-154">Copy the public key, and then click **Cancel**.</span></span>  

##  <a name="BKMK_SAPConsumeBinding"></a> <span data-ttu-id="5dbaa-155">Ningún adaptador válidos es error instalados</span><span class="sxs-lookup"><span data-stu-id="5dbaa-155">No valid adapters are installed error</span></span>

 <span data-ttu-id="5dbaa-156">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-156">**Problem**</span></span>  

 <span data-ttu-id="5dbaa-157">Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-157">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  

```  
No valid adapters are installed on this machine  
```  

 <span data-ttu-id="5dbaa-158">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-158">**Cause**</span></span>  

 <span data-ttu-id="5dbaa-159">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-159">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5dbaa-160">Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-160">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5dbaa-161">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-161">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5dbaa-162">Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando inicie la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], comprueba los enlaces en la versión de 32 bits del archivo machine.config del complemento y se produce un error a un error.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-162">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="5dbaa-163">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-163">**Resolution**</span></span>  

- <span data-ttu-id="5dbaa-164">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-164">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5dbaa-165">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-165">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5dbaa-166">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-166">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="5dbaa-167">Agregue las versiones de 32 bits y 64 bits de los archivos DLL de cliente para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (por ejemplo, librfc32u.dll) a la variable PATH.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-167">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="5dbaa-168">La versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-168">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="5dbaa-169">La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-169">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5dbaa-170">Si se ejecuta el adaptador (32 o 64 bits) en un equipo que tenga un sistema operativo de 64 bits y utiliza el adaptador para escribir una aplicación, debe marcar la aplicación en el mismo tipo que el adaptador (32 o 64 bits).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-170">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="5dbaa-171">Además, la versión del SDK de RFC (32 o 64 bits) debe ser igual que la versión del adaptador (32 o 64 bits).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-171">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
  >   
  >  <span data-ttu-id="5dbaa-172">Por ejemplo, si un adaptador de 32 bits se ejecuta en un equipo con un sistema operativo de 64 bits, la aplicación de cliente del adaptador debe marcarse como de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-172">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  

   <span data-ttu-id="5dbaa-173">Para obtener más información acerca de lo archivos DLL de cliente de SAP, consulte [instalar RFC de personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-173">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  

##  <a name="BKMK_SAPInvalidBinding"></a> <span data-ttu-id="5dbaa-174">Error de enlace no válido durante la configuración de puertos de adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="5dbaa-174">Invalid binding error while configuring SAP adapter ports</span></span>  
 <span data-ttu-id="5dbaa-175">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-175">**Problem**</span></span>  

 <span data-ttu-id="5dbaa-176">Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dbaa-176">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  

 <span data-ttu-id="5dbaa-177">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-177">**Cause**</span></span>  

 <span data-ttu-id="5dbaa-178">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-178">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5dbaa-179">Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-179">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5dbaa-180">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-180">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5dbaa-181">Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración que se ejecuta como un proceso de 32 bits y, por tanto, al configurar un puerto para el adaptador, comprueba los enlaces en la versión de 32 bits del archivo machine.config y se produce un error a un error.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-181">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="5dbaa-182">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5dbaa-182">**Resolution**</span></span>  

- <span data-ttu-id="5dbaa-183">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-183">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5dbaa-184">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-184">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5dbaa-185">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-185">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="5dbaa-186">Agregue las versiones de 32 bits y 64 bits de los archivos DLL de cliente para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (por ejemplo, librfc32u.dll) a la variable PATH.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-186">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="5dbaa-187">La versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-187">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="5dbaa-188">La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-188">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5dbaa-189">Si se ejecuta el adaptador (32 o 64 bits) en un equipo que tenga un sistema operativo de 64 bits y utiliza el adaptador para escribir una aplicación, debe marcar la aplicación en el mismo tipo que el adaptador (32 o 64 bits).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-189">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="5dbaa-190">Además, la versión del SDK de RFC (32 o 64 bits) debe ser igual que la versión del adaptador (32 o 64 bits).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-190">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
  >   
  >  <span data-ttu-id="5dbaa-191">Por ejemplo, si un adaptador de 32 bits se ejecuta en un equipo con un sistema operativo de 64 bits, la aplicación de cliente del adaptador debe marcarse como de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5dbaa-191">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  

   <span data-ttu-id="5dbaa-192">Para obtener más información acerca de lo archivos DLL de cliente de SAP, consulte [instalar RFC de personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="5dbaa-192">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dbaa-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dbaa-193">See Also</span></span>  
[<span data-ttu-id="5dbaa-194">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="5dbaa-194">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
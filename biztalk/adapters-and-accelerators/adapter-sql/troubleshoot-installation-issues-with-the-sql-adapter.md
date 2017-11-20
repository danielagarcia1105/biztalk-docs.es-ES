---
title: "Solucionar problemas de instalación con el adaptador de SQl | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48778158-6064-4731-be72-1af855ebe373
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07a160c428ac9df0f75b219af5bafb0727205cbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-sql-adapter"></a><span data-ttu-id="0e593-102">Solucionar problemas de instalación con el adaptador de SQl</span><span class="sxs-lookup"><span data-stu-id="0e593-102">Troubleshoot Installation Issues with the SQl adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="0e593-103">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] está disponible como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] , así como un adaptador independiente.</span><span class="sxs-lookup"><span data-stu-id="0e593-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is available as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as well as a separate adapter.</span></span> <span data-ttu-id="0e593-104">Si tiene acceso a este tema para saber acerca de los problemas de instalación con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] que es independiente de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], todas las referencias a la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación se debe interpretar como [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-104">If you are accessing this topic to know about installation issues with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] that is separate from the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], all references to the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup must be interpreted as [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="0e593-105">Instalación del software Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="0e593-105">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="0e593-106">En esta sección se describe el uso de técnicas de solución de problemas para resolver errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-106">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="0e593-107">Mensajes de registro de acciones de instalación</span><span class="sxs-lookup"><span data-stu-id="0e593-107">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="0e593-108">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e593-108">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0e593-109">Además, el programa de instalación también realiza algunas acciones personalizadas como el registro de los enlaces del adaptador.</span><span class="sxs-lookup"><span data-stu-id="0e593-109">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="0e593-110">Puede registrar mensajes para las acciones estándares, así como personalizadas que realiza el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-110">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="0e593-111">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación instala los archivos de específicas del adaptador con un archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="0e593-111">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="0e593-112">Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.</span><span class="sxs-lookup"><span data-stu-id="0e593-112">Therefore, the logging for the setup is the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="0e593-113">Todos los registros de las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log.</span><span class="sxs-lookup"><span data-stu-id="0e593-113">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="0e593-114">Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0e593-114">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="0e593-115">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="0e593-115">Known Issues</span></span>  
 <span data-ttu-id="0e593-116">Éstos son los errores más comunes que pueden surgir al instalar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con sus causa probable y la resolución.</span><span class="sxs-lookup"><span data-stu-id="0e593-116">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="0e593-117"><a name="BKMK_SQLSetupBinding"></a>El programa de instalación no puede registrar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="0e593-117"><a name="BKMK_SQLSetupBinding"></a> Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="0e593-118">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0e593-118">**Problem**</span></span>  
  
 <span data-ttu-id="0e593-119">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar los enlaces del adaptador, pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="0e593-119">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup Wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="0e593-120">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0e593-120">**Cause**</span></span>  
  
 <span data-ttu-id="0e593-121">Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config está dañado.</span><span class="sxs-lookup"><span data-stu-id="0e593-121">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="0e593-122">Los enlaces del adaptador se escriben en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-122">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="0e593-123">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0e593-123">**Resolution**</span></span>  
  
 <span data-ttu-id="0e593-124">Debe registrar manualmente el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="0e593-124">You should manually register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="0e593-125">Para registrar el enlace del adaptador</span><span class="sxs-lookup"><span data-stu-id="0e593-125">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="0e593-126">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0e593-126">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="0e593-127">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="0e593-127">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="0e593-128">En esta ruta de acceso, \<versión > es la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e593-128">In this path, \<version> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="0e593-129">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="0e593-129">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="0e593-130">Para registrar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace:</span><span class="sxs-lookup"><span data-stu-id="0e593-130">To register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="0e593-131">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="0e593-131">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="0e593-132">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="0e593-132">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="0e593-133">Busque la falta [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="0e593-133">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="0e593-134">Agregue la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="0e593-134">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="0e593-135">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="0e593-135">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="0e593-136">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="0e593-136">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="0e593-137">Busque la falta [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="0e593-137">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="0e593-138">Agregue la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="0e593-138">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="0e593-139">Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="0e593-139">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0e593-140">Para obtener información acerca de cómo determinar la clave pública y la versión, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="0e593-140">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="0e593-141">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-141">Save and close the machine.config file.</span></span>  
  
####  <span data-ttu-id="0e593-142"><a name="BKMK_PubKey"></a>Determinar la versión y la clave pública</span><span class="sxs-lookup"><span data-stu-id="0e593-142"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="0e593-143">Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e593-143">Perform the following steps to determine the public key for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="0e593-144">Para determinar la clave pública</span><span class="sxs-lookup"><span data-stu-id="0e593-144">To determine the public key</span></span>  
  
1.  <span data-ttu-id="0e593-145">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="0e593-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="0e593-146">Haga clic en el archivo DLL para el que desea que la clave pública y la versión y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0e593-146">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="0e593-147">En la tabla siguiente muestra el nombre del archivo DLL para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e593-147">The following table lists the name of the DLL for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="0e593-148">Adaptador</span><span class="sxs-lookup"><span data-stu-id="0e593-148">Adapter</span></span>|<span data-ttu-id="0e593-149">Nombre de la DLL</span><span class="sxs-lookup"><span data-stu-id="0e593-149">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="0e593-150">Microsoft.Adapters.Sql</span><span class="sxs-lookup"><span data-stu-id="0e593-150">Microsoft.Adapters.Sql</span></span>|  
  
3.  <span data-ttu-id="0e593-151">En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="0e593-151">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="0e593-152">Valor de forma similar, en la **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="0e593-152">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="0e593-153">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="0e593-153">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <span data-ttu-id="0e593-154"><a name="BKMK_SQLConsumeBinding"></a>Error al usar el complemento Consume Adapter Service o agregar Adapter Service Reference complemento en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="0e593-154"><a name="BKMK_SQLConsumeBinding"></a> Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="0e593-155">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0e593-155">**Problem**</span></span>  
  
 <span data-ttu-id="0e593-156">Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="0e593-156">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="0e593-157">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0e593-157">**Cause**</span></span>  
  
 <span data-ttu-id="0e593-158">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-158">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="0e593-159">Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0e593-159">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="0e593-160">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-160">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="0e593-161">Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando se inicia el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], el complemento comprueba los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.</span><span class="sxs-lookup"><span data-stu-id="0e593-161">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="0e593-162">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0e593-162">**Resolution**</span></span>  
  
 <span data-ttu-id="0e593-163">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-163">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e593-164">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-164">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="0e593-165">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="0e593-165">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
###  <span data-ttu-id="0e593-166"><a name="BKMK_SQLInvalidBinding"></a>Error de enlace no válido al configurar los puertos de adaptador SQL en la consola de administración de BizTalk Server en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="0e593-166"><a name="BKMK_SQLInvalidBinding"></a> Invalid binding error while configuring SQL adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="0e593-167">**Problema**</span><span class="sxs-lookup"><span data-stu-id="0e593-167">**Problem**</span></span>  
  
 <span data-ttu-id="0e593-168">Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e593-168">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sqlBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="0e593-169">**Causa**</span><span class="sxs-lookup"><span data-stu-id="0e593-169">**Cause**</span></span>  
  
 <span data-ttu-id="0e593-170">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-170">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="0e593-171">Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0e593-171">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="0e593-172">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="0e593-172">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="0e593-173">Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración se ejecuta como un proceso de 32 bits y, por tanto, cuando configura un puerto para el adaptador, comprueba si los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.</span><span class="sxs-lookup"><span data-stu-id="0e593-173">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="0e593-174">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0e593-174">**Resolution**</span></span>  
  
 <span data-ttu-id="0e593-175">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-175">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e593-176">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="0e593-176">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="0e593-177">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="0e593-177">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e593-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e593-178">See Also</span></span>  
 [<span data-ttu-id="0e593-179">Solucionar problemas del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="0e593-179">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
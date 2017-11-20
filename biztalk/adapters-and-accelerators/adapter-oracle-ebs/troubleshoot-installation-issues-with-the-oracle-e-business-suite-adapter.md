---
title: "Solucionar problemas de instalación con el adaptador de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 387ca48954fc075e696a8d3b093fbc9f1b5d7259
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="5bcb1-102">Solucionar problemas de instalación con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="5bcb1-102">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="5bcb1-103">Instalación del software Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="5bcb1-104">En esta sección se describe el uso de técnicas de solución de problemas para resolver errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-104">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="5bcb1-105">Mensajes de registro de acciones de instalación</span><span class="sxs-lookup"><span data-stu-id="5bcb1-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="5bcb1-106">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcb1-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5bcb1-107">Además, el programa de instalación también realiza algunas acciones personalizadas como el registro de los enlaces del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="5bcb1-108">Puede registrar mensajes para las acciones estándares, así como personalizadas que realiza el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="5bcb1-109">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación instala los archivos de específicas del adaptador con un archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="5bcb1-110">Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> <span data-ttu-id="5bcb1-111">[Registro de Windows Installer](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) proporcionan más detalles.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-111">[Windows Installer Logging](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) provides more details.</span></span> 
  
-   <span data-ttu-id="5bcb1-112">Todos los registros de las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-112">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="5bcb1-113">Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-113">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="5bcb1-114">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="5bcb1-114">Known Issues</span></span>  
 <span data-ttu-id="5bcb1-115">Éstos son los errores más comunes que pueden surgir al instalar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con sus causa probable y la resolución.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-115">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="5bcb1-116"><a name="BKMK_OraAppBinding"></a>El programa de instalación no puede registrar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="5bcb1-116"><a name="BKMK_OraAppBinding"></a> Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="5bcb1-117">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-117">**Problem**</span></span>  
  
 <span data-ttu-id="5bcb1-118">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar los enlaces del adaptador, pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-118">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="5bcb1-119">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-119">**Cause**</span></span>  
  
 <span data-ttu-id="5bcb1-120">Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config está dañado.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-120">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="5bcb1-121">Los enlaces del adaptador se escriben en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-121">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="5bcb1-122">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-122">**Resolution**</span></span>  
  
 <span data-ttu-id="5bcb1-123">Debe registrar manualmente el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-123">You should manually register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="5bcb1-124">Para registrar el enlace del adaptador</span><span class="sxs-lookup"><span data-stu-id="5bcb1-124">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="5bcb1-125">Navegue hasta el archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-125">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="5bcb1-126">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema >: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-126">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="5bcb1-127">En esta ruta de acceso, \< *versión*> es la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-127">In this path, \<*version*> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="5bcb1-128">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-128">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="5bcb1-129">Para registrar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-129">To register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="5bcb1-130">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-130">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="5bcb1-131">Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-131">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="5bcb1-132">Busque la falta [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-132">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="5bcb1-133">Agregue la siguiente sección bajo el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="5bcb1-133">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="5bcb1-134">Para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-134">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="5bcb1-135">Busque el elemento "bindingExtensions" en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-135">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="5bcb1-136">Busque la falta [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-136">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="5bcb1-137">Agregue la siguiente sección bajo el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="5bcb1-137">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="5bcb1-138">Para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-138">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5bcb1-139">Para obtener información acerca de cómo determinar la clave pública y la versión, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="5bcb1-139">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="5bcb1-140">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-140">Save and close the machine.config file.</span></span>  
  
####  <span data-ttu-id="5bcb1-141"><a name="BKMK_PubKey"></a>Determinar la versión y la clave pública</span><span class="sxs-lookup"><span data-stu-id="5bcb1-141"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="5bcb1-142">Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcb1-142">Perform the following steps to determine the public key for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="5bcb1-143">Para determinar la clave pública</span><span class="sxs-lookup"><span data-stu-id="5bcb1-143">To determine the public key</span></span>  
  
1.  <span data-ttu-id="5bcb1-144">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-144">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="5bcb1-145">Haga clic en el archivo DLL para el que desea que la clave pública y la versión y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-145">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="5bcb1-146">En la tabla siguiente muestra el nombre del archivo DLL para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcb1-146">The following table lists the name of the DLL for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
    |<span data-ttu-id="5bcb1-147">Adaptador</span><span class="sxs-lookup"><span data-stu-id="5bcb1-147">Adapter</span></span>|<span data-ttu-id="5bcb1-148">Nombre de la DLL</span><span class="sxs-lookup"><span data-stu-id="5bcb1-148">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="5bcb1-149">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="5bcb1-149">Microsoft.Adapters.OracleEBS</span></span>|  
  
3.  <span data-ttu-id="5bcb1-150">En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-150">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="5bcb1-151">Valor de forma similar, en la **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-151">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="5bcb1-152">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-152">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <span data-ttu-id="5bcb1-153"><a name="BKMK_ConsumeOraApp"></a>Error al usar el complemento Consume Adapter Service o agregar Adapter Service Reference complemento en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5bcb1-153"><a name="BKMK_ConsumeOraApp"></a> Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="5bcb1-154">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-154">**Problem**</span></span>  
  
 <span data-ttu-id="5bcb1-155">Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-155">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="5bcb1-156">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-156">**Cause**</span></span>  
  
 <span data-ttu-id="5bcb1-157">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-157">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5bcb1-158">Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-158">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5bcb1-159">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-159">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5bcb1-160">Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando se inicia el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], el complemento comprueba los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-160">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="5bcb1-161">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-161">**Resolution**</span></span>  
  
-   <span data-ttu-id="5bcb1-162">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-162">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5bcb1-163">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-163">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5bcb1-164">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-164">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="5bcb1-165">Instalar las versiones de 32 bits y 64 bits de los componentes de acceso de datos de Oracle para el cliente de Oracle 11.1.0.6 con conjunto de revisión 11.1.0.7.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-165">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bcb1-166">Para asegurarse de que la aplicación funcione con la versión más reciente de ODP.NET, debe tener las "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-166">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="5bcb1-167">Para obtener más información, vea "Proveedor de datos de Oracle para .NET FAQ" en [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span><span class="sxs-lookup"><span data-stu-id="5bcb1-167">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
###  <span data-ttu-id="5bcb1-168"><a name="BKMK_OraAppInvalidBinding"></a>Error de enlace no válido al configurar los puertos de adaptador de Oracle E-Business Suite en la consola de administración de BizTalk Server en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5bcb1-168"><a name="BKMK_OraAppInvalidBinding"></a> Invalid binding error while configuring Oracle E-Business Suite adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="5bcb1-169">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-169">**Problem**</span></span>  
  
 <span data-ttu-id="5bcb1-170">Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bcb1-170">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="5bcb1-171">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-171">**Cause**</span></span>  
  
 <span data-ttu-id="5bcb1-172">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-172">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5bcb1-173">Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-173">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5bcb1-174">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-174">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5bcb1-175">Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración se ejecuta como un proceso de 32 bits y, por tanto, cuando configura un puerto para el adaptador, comprueba si los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-175">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="5bcb1-176">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5bcb1-176">**Resolution**</span></span>  
  
-   <span data-ttu-id="5bcb1-177">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-177">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5bcb1-178">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-178">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5bcb1-179">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-179">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="5bcb1-180">Instalar las versiones de 32 bits y 64 bits de los componentes de acceso de datos de Oracle para el cliente de Oracle 11.1.0.6 con conjunto de revisión 11.1.0.7.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-180">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bcb1-181">Para asegurarse de que la aplicación funcione con la versión más reciente de ODP.NET, debe tener las "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-181">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="5bcb1-182">Para obtener más información, vea "Proveedor de datos de Oracle para .NET FAQ" en [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span><span class="sxs-lookup"><span data-stu-id="5bcb1-182">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcb1-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bcb1-183">See Also</span></span>  
[<span data-ttu-id="5bcb1-184">Solucionar problemas del adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="5bcb1-184">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
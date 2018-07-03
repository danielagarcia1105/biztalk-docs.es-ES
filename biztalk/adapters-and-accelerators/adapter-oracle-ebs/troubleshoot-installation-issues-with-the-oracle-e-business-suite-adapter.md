---
title: Solucionar problemas de instalación con el adaptador de Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fb1d5f0e1f17870c9824b30e5da55a2740cb81b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968133"
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="5c66d-102">Solucionar problemas de instalación con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="5c66d-102">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="5c66d-103">Instalación de Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c66d-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="5c66d-104">En esta sección se analiza el uso de técnicas de solución de problemas para resolver errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-104">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  

## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="5c66d-105">Mensajes de registro de acciones de instalación</span><span class="sxs-lookup"><span data-stu-id="5c66d-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="5c66d-106">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c66d-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5c66d-107">Además, el programa de instalación también lleva a cabo determinadas acciones como el registro de los enlaces del adaptador personalizados.</span><span class="sxs-lookup"><span data-stu-id="5c66d-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="5c66d-108">Puede registrar mensajes para las acciones estándares como personalizadas que realiza la instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  

- <span data-ttu-id="5c66d-109">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación instala los archivos específicos del adaptador mediante MSI.</span><span class="sxs-lookup"><span data-stu-id="5c66d-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="5c66d-110">Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.</span><span class="sxs-lookup"><span data-stu-id="5c66d-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> <span data-ttu-id="5c66d-111">[Registro de Windows Installer](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) proporciona más detalles.</span><span class="sxs-lookup"><span data-stu-id="5c66d-111">[Windows Installer Logging](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) provides more details.</span></span> 

- <span data-ttu-id="5c66d-112">Todos los registros de las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log.</span><span class="sxs-lookup"><span data-stu-id="5c66d-112">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="5c66d-113">Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="5c66d-113">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  

## <a name="known-issues"></a><span data-ttu-id="5c66d-114">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="5c66d-114">Known Issues</span></span>  
 <span data-ttu-id="5c66d-115">Los siguientes son los errores más comunes que pueden surgir al instalar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con su causa y resolución.</span><span class="sxs-lookup"><span data-stu-id="5c66d-115">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  



###  <a name="BKMK_OraAppBinding"></a> <span data-ttu-id="5c66d-116">Se produce un error en el programa de instalación registrar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="5c66d-116">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="5c66d-117">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5c66d-117">**Problem**</span></span>  

 <span data-ttu-id="5c66d-118">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar los enlaces del adaptador, pero continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c66d-118">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  

 <span data-ttu-id="5c66d-119">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5c66d-119">**Cause**</span></span>  

 <span data-ttu-id="5c66d-120">Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados.</span><span class="sxs-lookup"><span data-stu-id="5c66d-120">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="5c66d-121">Los enlaces del adaptador se escriben en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-121">The adapter bindings are written to the machine.config file.</span></span>  

 <span data-ttu-id="5c66d-122">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5c66d-122">**Resolution**</span></span>  

 <span data-ttu-id="5c66d-123">Se debe registrar manualmente el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5c66d-123">You should manually register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span>  

##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="5c66d-124">Para registrar el enlace del adaptador</span><span class="sxs-lookup"><span data-stu-id="5c66d-124">To register the adapter binding</span></span>  

1. <span data-ttu-id="5c66d-125">Navegue al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5c66d-125">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="5c66d-126">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="5c66d-126">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    <span data-ttu-id="5c66d-127">En esta ruta de acceso, \< *versión* \> es la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c66d-127">In this path, \<*version*\> is the version of the .NET Framework.</span></span>  

2. <span data-ttu-id="5c66d-128">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="5c66d-128">Open the file by using a text editor.</span></span>  

3. <span data-ttu-id="5c66d-129">Para registrar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace:</span><span class="sxs-lookup"><span data-stu-id="5c66d-129">To register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding:</span></span>  

   1. <span data-ttu-id="5c66d-130">Busque el elemento "system.serviceModel" y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="5c66d-130">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
      </client>  
      ```  

   2. <span data-ttu-id="5c66d-131">Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5c66d-131">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="5c66d-132">Busque el campo que falta [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5c66d-132">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="5c66d-133">Agregue la siguiente sección en el nodo "bindingElementExtensions".</span><span class="sxs-lookup"><span data-stu-id="5c66d-133">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="5c66d-134">Para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5c66d-134">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="5c66d-135">Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="5c66d-135">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="5c66d-136">Busque el campo que falta [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace.</span><span class="sxs-lookup"><span data-stu-id="5c66d-136">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="5c66d-137">Agregue la siguiente sección en el nodo "bindingExtensions".</span><span class="sxs-lookup"><span data-stu-id="5c66d-137">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="5c66d-138">Para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="5c66d-138">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="5c66d-139">Para obtener información sobre cómo determinar la clave pública y la versión, consulte [determinar la clave pública y la versión](#BKMK_PubKey).</span><span class="sxs-lookup"><span data-stu-id="5c66d-139">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="5c66d-140">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-140">Save and close the machine.config file.</span></span>  

####  <a name="BKMK_PubKey"></a> <span data-ttu-id="5c66d-141">Determinación de la clave pública y versión</span><span class="sxs-lookup"><span data-stu-id="5c66d-141">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="5c66d-142">Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c66d-142">Perform the following steps to determine the public key for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

###### <a name="to-determine-the-public-key"></a><span data-ttu-id="5c66d-143">Para determinar la clave pública</span><span class="sxs-lookup"><span data-stu-id="5c66d-143">To determine the public key</span></span>  

1. <span data-ttu-id="5c66d-144">Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.</span><span class="sxs-lookup"><span data-stu-id="5c66d-144">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="5c66d-145">Haga clic en el archivo DLL para el que desea que la clave pública y la versión y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5c66d-145">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="5c66d-146">En la tabla siguiente se muestra el nombre del archivo DLL para [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c66d-146">The following table lists the name of the DLL for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  


   |                                         <span data-ttu-id="5c66d-147">Adaptador</span><span class="sxs-lookup"><span data-stu-id="5c66d-147">Adapter</span></span>                                         |       <span data-ttu-id="5c66d-148">Nombre del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="5c66d-148">Name of the DLL</span></span>        |
   |-----------------------------------------------------------------------------------------|------------------------------|
   | [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] | <span data-ttu-id="5c66d-149">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="5c66d-149">Microsoft.Adapters.OracleEBS</span></span> |


3. <span data-ttu-id="5c66d-150">En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5c66d-150">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="5c66d-151">De forma similar, valor frente a la **versión** etiqueta Especifica el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="5c66d-151">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="5c66d-152">Copie la clave pública y, a continuación, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5c66d-152">Copy the public key, and then click **Cancel**.</span></span>  

###  <a name="BKMK_ConsumeOraApp"></a> <span data-ttu-id="5c66d-153">Error al usar el complemento Consume Adapter Service o Add Adapter Service Reference complemento en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5c66d-153">Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="5c66d-154">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5c66d-154">**Problem**</span></span>  

 <span data-ttu-id="5c66d-155">Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="5c66d-155">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  

```  
No valid adapters are installed on this machine  
```  

 <span data-ttu-id="5c66d-156">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5c66d-156">**Cause**</span></span>  

 <span data-ttu-id="5c66d-157">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-157">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5c66d-158">Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5c66d-158">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5c66d-159">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-159">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5c66d-160">Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando inicie la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], comprueba los enlaces en la versión de 32 bits del archivo machine.config del complemento y se produce un error a un error.</span><span class="sxs-lookup"><span data-stu-id="5c66d-160">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="5c66d-161">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5c66d-161">**Resolution**</span></span>  

- <span data-ttu-id="5c66d-162">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-162">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5c66d-163">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-163">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5c66d-164">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5c66d-164">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="5c66d-165">Instale las versiones de 32 bits y 64 bits de los componentes de acceso de datos de Oracle para el cliente de Oracle 11.1.0.6 con revisión conjunto 11.1.0.7.</span><span class="sxs-lookup"><span data-stu-id="5c66d-165">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="5c66d-166">Para asegurarse de que la aplicación funciona con la versión más reciente de ODP.NET, debe tener el "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="5c66d-166">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="5c66d-167">Para obtener más información, vea "Proveedor de datos de Oracle para .NET FAQ" en [ http://go.microsoft.com/fwlink/p/?LinkId=92834 ](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span><span class="sxs-lookup"><span data-stu-id="5c66d-167">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  

###  <a name="BKMK_OraAppInvalidBinding"></a> <span data-ttu-id="5c66d-168">Error de enlace no válido durante la configuración de puertos de adaptador de Oracle E-Business Suite en la consola de administración de BizTalk Server en una instalación de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5c66d-168">Invalid binding error while configuring Oracle E-Business Suite adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="5c66d-169">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5c66d-169">**Problem**</span></span>  

 <span data-ttu-id="5c66d-170">Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c66d-170">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  

 <span data-ttu-id="5c66d-171">**Causa**</span><span class="sxs-lookup"><span data-stu-id="5c66d-171">**Cause**</span></span>  

 <span data-ttu-id="5c66d-172">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-172">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="5c66d-173">Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5c66d-173">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="5c66d-174">Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="5c66d-174">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="5c66d-175">Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración que se ejecuta como un proceso de 32 bits y, por tanto, al configurar un puerto para el adaptador, comprueba los enlaces en la versión de 32 bits del archivo machine.config y se produce un error a un error.</span><span class="sxs-lookup"><span data-stu-id="5c66d-175">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="5c66d-176">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="5c66d-176">**Resolution**</span></span>  

- <span data-ttu-id="5c66d-177">Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-177">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="5c66d-178">Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="5c66d-178">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="5c66d-179">Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="5c66d-179">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="5c66d-180">Instale las versiones de 32 bits y 64 bits de los componentes de acceso de datos de Oracle para el cliente de Oracle 11.1.0.6 con revisión conjunto 11.1.0.7.</span><span class="sxs-lookup"><span data-stu-id="5c66d-180">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="5c66d-181">Para asegurarse de que la aplicación funciona con la versión más reciente de ODP.NET, debe tener el "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="5c66d-181">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="5c66d-182">Para obtener más información, vea "Proveedor de datos de Oracle para .NET FAQ" en [ http://go.microsoft.com/fwlink/p/?LinkId=92834 ](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span><span class="sxs-lookup"><span data-stu-id="5c66d-182">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  

## <a name="see-also"></a><span data-ttu-id="5c66d-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c66d-183">See Also</span></span>  
[<span data-ttu-id="5c66d-184">Solucionar problemas del adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="5c66d-184">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
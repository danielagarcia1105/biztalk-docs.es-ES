---
title: Registrar los pasos de instalación de módulo de adaptador de BizTalk 2016 | Microsoft Docs
description: Pasos para completar después de instalar BAP 2016, incluido agregan adaptador de administración de BizTalk, actualización de Oracle y enlaces del adaptador de registro.
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43a454e1e6f1dc65d8a2e2c5493aacf9375374b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997381"
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a><span data-ttu-id="e6723-103">Pasos posteriores a la instalación de módulo de adaptador de BizTalk 2016</span><span class="sxs-lookup"><span data-stu-id="e6723-103">Post installation steps for BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="e6723-104">Después de instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], hay algunos pasos posteriores a la instalación.</span><span class="sxs-lookup"><span data-stu-id="e6723-104">After you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], there are some post-installation steps.</span></span> <span data-ttu-id="e6723-105">En este tema se enumera estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e6723-105">This topic lists these steps.</span></span>   

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="e6723-106">Agregar el adaptador para la administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e6723-106">Add the adapter to BizTalk Administration</span></span>

1. <span data-ttu-id="e6723-107">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="e6723-107">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="e6723-108">Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="e6723-108">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  

3. <span data-ttu-id="e6723-109">Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="e6723-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  

    <span data-ttu-id="e6723-110">![Agregar un adaptador](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="e6723-110">![Add an adapter](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  

4. <span data-ttu-id="e6723-111">En el **propiedades del adaptador**, seleccione un adaptador en la lista desplegable, como **SAP de WCF**y, a continuación, escriba un nombre, como **SAP de WCF**.</span><span class="sxs-lookup"><span data-stu-id="e6723-111">In the **Adapter Properties**, select an adapter from the drop-down list, such as **WCF-SAP**, and then enter a name, such as **WCF-SAP**.</span></span>  

    <span data-ttu-id="e6723-112">![Agregar adaptador SAP a BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="e6723-112">![Add SAP Adapter to BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  

5. <span data-ttu-id="e6723-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6723-113">Select **OK**.</span></span>  

## <a name="use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="e6723-114">Usar una versión más reciente de Oracle.DataAccess.dll</span><span class="sxs-lookup"><span data-stu-id="e6723-114">Use a newer Oracle.DataAccess.dll version</span></span>  

<span data-ttu-id="e6723-115">Al configurar un puerto para utilizar el adaptador de WCF-OracleDB o usar Visual Studio para consumir un adaptador generado, se muestra un mensaje que el adaptador necesita Oracle.DataAccess.dll versión 2.111.7.0.</span><span class="sxs-lookup"><span data-stu-id="e6723-115">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="e6723-116">Para resolver este mensaje, instale una versión compatible de Oracle.DataAccess.dll (consulte [admite la lista de versiones](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)) y, a continuación, actualice el `bindingRedirect` elemento en el archivo de configuración de OracleDB mediante los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e6723-116">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file using the following steps:</span></span>  

1.  <span data-ttu-id="e6723-117">En el servidor BizTalk Server, vaya a las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="e6723-117">On the BizTalk Server, go to the following folders:</span></span>  

     <span data-ttu-id="e6723-118">*unidad*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="e6723-118">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  

     <span data-ttu-id="e6723-119">*unidad*: \Program archivos (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="e6723-119">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  

2.  <span data-ttu-id="e6723-120">Abra el archivo Microsoft.Adapters.OracleDB.config.</span><span class="sxs-lookup"><span data-stu-id="e6723-120">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  

3.  <span data-ttu-id="e6723-121">Busque la sección siguiente y, a continuación, copiar y pegar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6723-121">Find the following section, and then copy/paste the following:</span></span>  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  <span data-ttu-id="e6723-122">En este ejemplo, establecemos *newVersion* a 2.112.1.00.</span><span class="sxs-lookup"><span data-stu-id="e6723-122">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="e6723-123">Establezca este valor en la versión que tenga instalada.</span><span class="sxs-lookup"><span data-stu-id="e6723-123">Set this value to the version you have installed.</span></span>  

> [!IMPORTANT]
> - <span data-ttu-id="e6723-124">Si hay varios servidores de BizTalk en este grupo, debe realizar este cambio en todos los servidores de BizTalk en el grupo.</span><span class="sxs-lookup"><span data-stu-id="e6723-124">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> - <span data-ttu-id="e6723-125">El *newVersion* valor debe actualizarse en función de la versión del archivo Oracle.DataAccess.dll instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6723-125">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="e6723-126">Oracle.DataAccess.dll se incluye con el cliente de Oracle se instala desde Oracle.</span><span class="sxs-lookup"><span data-stu-id="e6723-126">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="e6723-127">Solo se debe instalar una versión de cliente de Oracle que está [compatibles con BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6723-127">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  

## <a name="create-sql-server-database-objects-sap-adapter-only"></a><span data-ttu-id="e6723-128">Crear objetos de base de datos de SQL Server (solo para el adaptador SAP)</span><span class="sxs-lookup"><span data-stu-id="e6723-128">Create SQL Server Database objects (SAP adapter only)</span></span>  
 <span data-ttu-id="e6723-129">Para invocar trfc en un sistema SAP, ejecute el *SapAdapter-DbScript-Install.sql* secuencia de comandos SQL.</span><span class="sxs-lookup"><span data-stu-id="e6723-129">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="e6723-130">Este script se instala con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación y crea objetos de base de datos en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6723-130">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="e6723-131">El script se instala normalmente en *\<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span><span class="sxs-lookup"><span data-stu-id="e6723-131">The script is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="e6723-132">Puede ejecutar este script en cualquier base de datos de SQL Server, siempre y cuando escriba ese nombre de base de datos mientras se usa el adaptador para invocar trfc.</span><span class="sxs-lookup"><span data-stu-id="e6723-132">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>

## <a name="register-the-adapter-bindings"></a><span data-ttu-id="e6723-133">Registrar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="e6723-133">Register the adapter bindings</span></span>
<span data-ttu-id="e6723-134">Durante la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, el Asistente para la instalación puede producir un error al registrar los enlaces del adaptador o el proveedor de datos de .NET Framework para mySAP Business Suite.</span><span class="sxs-lookup"><span data-stu-id="e6723-134">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite.</span></span> <span data-ttu-id="e6723-135">Y el programa de instalación continúa con la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="e6723-135">And the setup proceeds with the adapter installation.</span></span> <span data-ttu-id="e6723-136">Esto puede deberse a la instalación de Windows Communication Foundation (WCF), el [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados.</span><span class="sxs-lookup"><span data-stu-id="e6723-136">This may be caused by the Windows Communication Foundation (WCF) installation, the [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e6723-137">Complete los pasos siguientes *sólo* si se produce un error en el Asistente para instalación registrar los enlaces del adaptador, o proveedores de datos de .NET Framework en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6723-137">Complete the following steps *only* if the setup wizard fails to register the adapter bindings, or .NET Framework Data Providers in the machine.config file.</span></span>  

1. <span data-ttu-id="e6723-138">Vaya al archivo machine.config en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6723-138">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="e6723-139">Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config  *\<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG*.</span><span class="sxs-lookup"><span data-stu-id="e6723-139">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  

2. <span data-ttu-id="e6723-140">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="e6723-140">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="e6723-141">Registrar los enlaces del adaptador:</span><span class="sxs-lookup"><span data-stu-id="e6723-141">Register the adapter bindings:</span></span>  

   1. <span data-ttu-id="e6723-142">Busque el `system.serviceModel` elemento y agregue lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="e6723-142">Search for the `system.serviceModel` element, and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="e6723-143">Busque el `bindingElementExtensions` elemento bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6723-143">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="e6723-144">Busque el enlace del adaptador que faltan.</span><span class="sxs-lookup"><span data-stu-id="e6723-144">Look for the missing adapter binding.</span></span> <span data-ttu-id="e6723-145">Agregue las siguientes secciones en el `bindingElementExtensions` nodo, dependiendo del enlace del adaptador que faltan.</span><span class="sxs-lookup"><span data-stu-id="e6723-145">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="e6723-146">Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.</span><span class="sxs-lookup"><span data-stu-id="e6723-146">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="e6723-147">Para el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-147">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-148">Para el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-148">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-149">Para el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-149">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-150">Para el [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-150">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-151">Para el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-151">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="e6723-152">Busque el `bindingExtensions` elemento bajo system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="e6723-152">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="e6723-153">Busque el enlace del adaptador que faltan.</span><span class="sxs-lookup"><span data-stu-id="e6723-153">Look for the missing adapter binding.</span></span> <span data-ttu-id="e6723-154">Agregue las siguientes secciones en el `bindingExtensions` nodo, dependiendo del enlace del adaptador que faltan.</span><span class="sxs-lookup"><span data-stu-id="e6723-154">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="e6723-155">Debe registrar todos los enlaces si se produce un error en el Asistente para instalación registrar cualquiera.</span><span class="sxs-lookup"><span data-stu-id="e6723-155">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="e6723-156">Para [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-156">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-157">Para [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-157">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-158">Para [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-158">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-159">Para [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-159">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-160">Para [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-160">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="e6723-161">Para obtener el valor de clave público, consulte **determinar la clave pública y la versión** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="e6723-161">To get the public key value, see **Determine the public key and version** (in this topic).</span></span>  

4. <span data-ttu-id="e6723-162">Registre los proveedores de datos de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6723-162">Register the .NET Framework data providers:</span></span>  

   1. <span data-ttu-id="e6723-163">Busque el `DbProviderFactories` elemento bajo el nodo system.data.</span><span class="sxs-lookup"><span data-stu-id="e6723-163">Search for the `DbProviderFactories` element under the system.data node.</span></span>  

   2. <span data-ttu-id="e6723-164">Busque los proveedores de datos de .NET Framework que falta.</span><span class="sxs-lookup"><span data-stu-id="e6723-164">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="e6723-165">Agregue las siguientes secciones en el `DbProviderFactories` nodo, en función del proveedor que falta.</span><span class="sxs-lookup"><span data-stu-id="e6723-165">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="e6723-166">Debe registrar todos los proveedores de si se produce un error en el Asistente para instalación registrar cualquiera.</span><span class="sxs-lookup"><span data-stu-id="e6723-166">You must register all the providers if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="e6723-167">Para el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-167">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="e6723-168">Para el [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], agregue:</span><span class="sxs-lookup"><span data-stu-id="e6723-168">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="e6723-169">Guarde y cierre el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="e6723-169">Save and close the machine.config file.</span></span>  

## <a name="determine-the-public-key-and-version"></a><span data-ttu-id="e6723-170">Determinar la clave pública y la versión</span><span class="sxs-lookup"><span data-stu-id="e6723-170">Determine the public key and version</span></span>  
 <span data-ttu-id="e6723-171">Complete los pasos siguientes para determinar la clave pública y la versión para un adaptador o el proveedor de datos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6723-171">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  

1. <span data-ttu-id="e6723-172">Vaya al directorio de Windows, normalmente *C:\WINDOWS\assembly*.</span><span class="sxs-lookup"><span data-stu-id="e6723-172">Go to the Windows directory, typically *C:\WINDOWS\assembly*.</span></span>  

2. <span data-ttu-id="e6723-173">Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e6723-173">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="e6723-174">En la tabla siguiente se muestra el nombre de los archivos DLL para cada adaptador y el proveedor:</span><span class="sxs-lookup"><span data-stu-id="e6723-174">The following table lists the name of the DLLs for each adapter and provider:</span></span>  


   |                         <span data-ttu-id="e6723-175">Proveedor de datos de adaptador y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6723-175">Adapter/.NET Framework Data Provider</span></span>                         |       <span data-ttu-id="e6723-176">Nombre del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="e6723-176">Name of the DLL</span></span>        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    <span data-ttu-id="e6723-177">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="e6723-177">Microsoft.Adapters.SAP</span></span>    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  <span data-ttu-id="e6723-178">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="e6723-178">Microsoft.Adapters.Siebel</span></span>   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | <span data-ttu-id="e6723-179">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="e6723-179">Microsoft.Adapters.OracleDB</span></span>  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | <span data-ttu-id="e6723-180">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="e6723-180">Microsoft.Adapters.OracleEBS</span></span> |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  <span data-ttu-id="e6723-181">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="e6723-181">Microsoft.Adapters.Sql.dll</span></span>  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   <span data-ttu-id="e6723-182">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="e6723-182">Microsoft.Data.SAPClient</span></span>   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | <span data-ttu-id="e6723-183">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="e6723-183">Microsoft.Data.SiebelClient</span></span>  |


3. <span data-ttu-id="e6723-184">En el **General** ficha, el **Token de clave pública** valor es la clave pública para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e6723-184">On the **General** tab, the **Public Key Token** value is the public key for the DLL.</span></span> <span data-ttu-id="e6723-185">El **versión** valor es el número de versión para el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e6723-185">The **Version** value is the version number for the DLL.</span></span>  

4. <span data-ttu-id="e6723-186">Copie la clave pública y, a continuación, seleccione **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e6723-186">Copy the public key, and then select **Cancel**.</span></span>  

## <a name="install-the-custom-rfcs"></a><span data-ttu-id="e6723-187">Instalar la RFC personalizadas</span><span class="sxs-lookup"><span data-stu-id="e6723-187">Install the custom RFCs</span></span>  
<span data-ttu-id="e6723-188">Solo es necesario *si* que desea usar el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6723-188">Required only *if* you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="e6723-189">Consulte [instalar personalizado RFC](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) en el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentación.</span><span class="sxs-lookup"><span data-stu-id="e6723-189">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="e6723-190">Si está utilizando una versión anterior de la RFC personalizadas que se valió la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], que debe actualizar a la RFC proporcionada con esta versión.</span><span class="sxs-lookup"><span data-stu-id="e6723-190">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="e6723-191">Hacer esto mediante la eliminación de los documentos RFC anteriores y, a continuación, instalar las RFC incluida con esta versión.</span><span class="sxs-lookup"><span data-stu-id="e6723-191">Do this by removing the earlier RFCs, and then installing the RFCs included with this release.</span></span>  

## <a name="install-the-enterprise-applications"></a><span data-ttu-id="e6723-192">Instalar las aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="e6723-192">Install the enterprise applications</span></span>  
<span data-ttu-id="e6723-193">Para que los pasos y orientación para instalar los sistemas de LOB de la empresa diferente, se recomienda que usar las guías de instalación proporcionadas por el sistema de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e6723-193">For the steps and guidance to install the different enterprise LOB systems, we recommend you use the installation guides provided by the enterprise system.</span></span> <span data-ttu-id="e6723-194">También consulte su documentación del adaptador para cambios de configuración específica, si existe.</span><span class="sxs-lookup"><span data-stu-id="e6723-194">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="e6723-195">Lista de comprobación de instalación y posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="e6723-195">Installation and post-installation checklist</span></span>  

- <span data-ttu-id="e6723-196">Asegúrese de que ha instalado todo el [requisitos previos de software](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) con la opción de instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="e6723-196">Make sure you installed all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) with the correct installation option.</span></span>

- <span data-ttu-id="e6723-197">Asegúrese de que tiene la versión admitida de las aplicaciones de LOB enterprise instalado en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6723-197">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="e6723-198">Consulte [sistemas admitidos línea de negocio (LOB)](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6723-198">See [Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).</span></span>  

- <span data-ttu-id="e6723-199">Para instalar sólo el adaptador para la empresa del sistema LOB que desea conectarse, asegúrese de que ha instalado el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] utilizando el **personalizado** opción de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6723-199">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="e6723-200">Asegúrese de que no ha usado el **completar** opción de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6723-200">Make sure you did not use the **Complete** installation option.</span></span> <span data-ttu-id="e6723-201">Consulte [instalar BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).</span><span class="sxs-lookup"><span data-stu-id="e6723-201">See [Installing the BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).</span></span>  

- <span data-ttu-id="e6723-202">Si desea realizar llamadas de tRFC al sistema SAP con el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], asegúrese de crear las tablas necesarias en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6723-202">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="e6723-203">Consulte **objetos de base de datos de creación de SQL Server** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="e6723-203">See **Create SQL Server Database objects** (in this topic).</span></span>

- <span data-ttu-id="e6723-204">Mientras se está ejecutando el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Asistente para la instalación, puede aparecer un mensaje de error que indica que el programa de instalación no se pudo registrar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="e6723-204">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="e6723-205">Si es así, registrarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="e6723-205">If so, register them manually.</span></span> <span data-ttu-id="e6723-206">Consulte **registrar los enlaces del adaptador** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="e6723-206">See **Register the adapter bindings** (in this topic).</span></span>  

- <span data-ttu-id="e6723-207">Si decide instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] instalación, asegúrese de instalar la RFC personalizadas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="e6723-207">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="e6723-208">Consulte [instalar RFC personalizadas](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="e6723-208">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="more-good-info"></a><span data-ttu-id="e6723-209">Obtener más información buena</span><span class="sxs-lookup"><span data-stu-id="e6723-209">More good info</span></span>
[<span data-ttu-id="e6723-210">Cambiar o quitar BizTalk Adapter Pack</span><span class="sxs-lookup"><span data-stu-id="e6723-210">Change or remove the BizTalk Adapter Pack</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="e6723-211">BizTalk Adapter Pack preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="e6723-211">BizTalk Adapter Pack FAQ</span></span>](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
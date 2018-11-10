---
title: Archivo de registro de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9798d56c4f3896e652a288d20b4e39e6a2537d3c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752964"
---
# <a name="adapter-registration-file"></a><span data-ttu-id="5c904-102">Archivo de registro del adaptador</span><span class="sxs-lookup"><span data-stu-id="5c904-102">Adapter Registration File</span></span>
<span data-ttu-id="5c904-103">Después de que el código del adaptador personalizado se haya generado correctamente, se debe registrar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c904-103">After the custom adapter code has been successfully built it must be registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5c904-104">Para ello, actualice el Registro con la configuración del adaptador adecuada.</span><span class="sxs-lookup"><span data-stu-id="5c904-104">You do this by updating the registry with the appropriate adapter settings.</span></span> <span data-ttu-id="5c904-105">Puede escribir de forma manual un archivo de Registro, pero hay más probabilidad de errores debido a la precisión y complejidad de la información que hay que escribir.</span><span class="sxs-lookup"><span data-stu-id="5c904-105">You can manually write a registry file, but this is prone to errors due to the preciseness and complexity of the information that you need to enter.</span></span> <span data-ttu-id="5c904-106">Una decisión más acertada consiste en ejecutar el Asistente para el Registro del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c904-106">A better decision is to run the Adapter Registry Wizard.</span></span> <span data-ttu-id="5c904-107">Este asistente le proporciona las mismas opciones de que dispone al crear un archivo de Registro nuevo y reduce la probabilidad de errores en el archivo.</span><span class="sxs-lookup"><span data-stu-id="5c904-107">The Adapter Registry Wizard gives you all the same options as creating a registry file from scratch, and reduces the likelihood of errors in the file.</span></span> <span data-ttu-id="5c904-108">Para obtener más información acerca del Asistente para registro de adaptador, vea [asistente](../core/adapter-registry-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c904-108">For more information about the Adapter Registry Wizard, see [Adapter Registry Wizard](../core/adapter-registry-wizard.md).</span></span>  
  
 <span data-ttu-id="5c904-109">El archivo StaticAdapterManagement.reg y dynamicadaptermanagement.reg se encuentran en  *\<unidad\>*: \Program Files\Microsoft Server\SDK\Samples\AdaptersDevelopment\File el adaptador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5c904-109">The StaticAdapterManagement.reg file and DynamicAdapterManagement.reg file are located at *\<drive\>*:\Program Files\Microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File Adapter.</span></span> <span data-ttu-id="5c904-110">Al ejecutar uno de estos archivos (hacer doble clic o haga clic en él y seleccione **mezcla**), que registra el adaptador de archivo de ejemplo con el registro y se instala el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5c904-110">When you run one of these files (you can double-click it or right-click it and select **Merge**), it registers the sample file adapter with the registry and installs the assembly into the global assembly cache.</span></span> <span data-ttu-id="5c904-111">Para registrar el adaptador personalizado, la mejor opción consiste en crear un archivo de Registro nuevo mediante el Asistente para el Registro del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5c904-111">To register your custom adapter the best option is to create a new registry file by using the Adapter Registry Wizard.</span></span> <span data-ttu-id="5c904-112">Si el adaptador estático personalizado es parecido al adaptador de ejemplo y decide modificar el archivo de Registro existente, abra y modifique las propiedades siguientes en el archivo StaticAdapterManagement.reg:</span><span class="sxs-lookup"><span data-stu-id="5c904-112">If your custom static adapter is similar to the sample adapter, and you decide to modify the existing registry file instead, open and modify the following properties in the StaticAdapterManagement.reg file:</span></span>  
  
-   <span data-ttu-id="5c904-113">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="5c904-113">**Constraints**</span></span>  
  
-   <span data-ttu-id="5c904-114">**InboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="5c904-114">**InboundTypeName**</span></span>  
  
-   <span data-ttu-id="5c904-115">**InboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="5c904-115">**InboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="5c904-116">**OutboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="5c904-116">**OutboundTypeName**</span></span>  
  
-   <span data-ttu-id="5c904-117">**OutboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="5c904-117">**OutboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="5c904-118">**AdapterMgmtTypeName**</span><span class="sxs-lookup"><span data-stu-id="5c904-118">**AdapterMgmtTypeName**</span></span>  
  
-   <span data-ttu-id="5c904-119">**AdapterMgmtAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="5c904-119">**AdapterMgmtAssemblyPath**</span></span>  
  
-   <span data-ttu-id="5c904-120">**PropertyNameSpace**</span><span class="sxs-lookup"><span data-stu-id="5c904-120">**PropertyNameSpace**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c904-121">Para **OutboundAssemblyPath** y **AdapterMgmtAssemblyPath** se recomienda que no incluya la ruta de acceso local en el valor de propiedad, porque la configuración podría dañarse cuando se instala en diferentes ubicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="5c904-121">For **OutboundAssemblyPath** and **AdapterMgmtAssemblyPath** we recommend that you not include the local path in the property value, because the configuration could break when installed on different server locations.</span></span> <span data-ttu-id="5c904-122">Una opción mejor consiste en utilizar un nombre seguro e instalarlo en la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="5c904-122">A better choice is to use a strong name and install it in the global assembly cache.</span></span>  
  
 <span data-ttu-id="5c904-123">Para especificar el tipo .NET que implementa el receptor del adaptador, el transmisor del adaptador y la administración del adaptador, existen dos opciones:</span><span class="sxs-lookup"><span data-stu-id="5c904-123">You have two options for specifying the .NET type that implements the adapter receiver, adapter transmitter, and adapter management:</span></span>  
  
1. <span data-ttu-id="5c904-124">Instalar el adaptador en una carpeta y especifique \* TypeName y \*AssemblyPath donde \*TypeName es de tipo. Nombre completo de la clase y \*AssemblyPath es la ruta de acceso y el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5c904-124">Install the adapter to a folder and specify \*TypeName and \*AssemblyPath where \*TypeName is type.FullName of the class and \*AssemblyPath is the path and file name of the assembly.</span></span>  
  
2. <span data-ttu-id="5c904-125">Instalar el adaptador en la caché global de ensamblados y especificar sólo \* TypeName donde \*TypeName es de tipo. AssemblyQualifiedName de la clase.</span><span class="sxs-lookup"><span data-stu-id="5c904-125">Install the adapter in the global assembly cache and specify just \*TypeName where \*TypeName is type.AssemblyQualifiedName of the class.</span></span> <span data-ttu-id="5c904-126">Ésta es la opción recomendada.</span><span class="sxs-lookup"><span data-stu-id="5c904-126">This is the recommended option.</span></span>  
  
   <span data-ttu-id="5c904-127">Todos los adaptadores deben tener las claves de Registro siguientes con el GUID especificado:</span><span class="sxs-lookup"><span data-stu-id="5c904-127">All adapters must have the following registry keys with the specified GUID:</span></span>  
  
- <span data-ttu-id="5c904-128">**Implementa categorías\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span><span class="sxs-lookup"><span data-stu-id="5c904-128">**Implemented Categories\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span></span>  
  
- <span data-ttu-id="5c904-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span><span class="sxs-lookup"><span data-stu-id="5c904-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span></span>  
  
- <span data-ttu-id="5c904-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span><span class="sxs-lookup"><span data-stu-id="5c904-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span></span>  
  
- <span data-ttu-id="5c904-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span><span class="sxs-lookup"><span data-stu-id="5c904-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span></span>  
  
- <span data-ttu-id="5c904-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span><span class="sxs-lookup"><span data-stu-id="5c904-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span></span>  
  
  <span data-ttu-id="5c904-133">Los adaptadores basados en el marco de trabajo de adaptadores deben utilizar estos GUID específicos para las páginas de propiedades de ubicación y controlador de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="5c904-133">Adapters based on the adapter framework must use these specific GUIDS for send and receive handler and location property pages.</span></span> <span data-ttu-id="5c904-134">Tenga en cuenta que si un adaptador es un adaptador de envío solo necesita el **OutboundProtocol_PageProv**y **TransmitLocation_PageProv**GUID.</span><span class="sxs-lookup"><span data-stu-id="5c904-134">Note that if an adapter is a send-only adapter it just needs the **OutboundProtocol_PageProv**and **TransmitLocation_PageProv**GUIDs.</span></span> <span data-ttu-id="5c904-135">De forma similar un adaptador de recepción simplemente requiere la **InboundProtocol_PageProv** y **ReceiveLocation_PageProv** GUID.</span><span class="sxs-lookup"><span data-stu-id="5c904-135">Similarly a receive-only adapter merely requires the **InboundProtocol_PageProv** and **ReceiveLocation_PageProv** GUIDs.</span></span>  
  
  <span data-ttu-id="5c904-136">El siguiente código pertenece al archivo StaticAdapterManagement.reg y el código del archivo DynamicAdapterManagement.reg es casi idéntico.</span><span class="sxs-lookup"><span data-stu-id="5c904-136">The following code is from the StaticAdapterManagement.reg file, and the code for the DynamicAdapterManagement.reg file is almost identical.</span></span> <span data-ttu-id="5c904-137">Para obtener más información sobre cada una de las propiedades del registro, consulte [registrar un adaptador](../core/registering-an-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="5c904-137">For more information about each of the registry properties, see [Registering an Adapter](../core/registering-an-adapter.md).</span></span> <span data-ttu-id="5c904-138">Después de realizar cambios en el archivo de Registro, guárdelo y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="5c904-138">After making the changes to the registry file, save the file and run it.</span></span>  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a><span data-ttu-id="5c904-139">Para registrar el adaptador estático de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c904-139">To register the static sample adapter</span></span>  
  
1. <span data-ttu-id="5c904-140">Complete el siguiente procedimiento para ejecutar el adaptador de archivo de ejemplo del SDK.</span><span class="sxs-lookup"><span data-stu-id="5c904-140">Complete the procedure to run the file adapter sample in the SDK.</span></span> <span data-ttu-id="5c904-141">Para obtener más información, consulte [adaptador de archivo (ejemplo de BizTalk Server)](../core/file-adapter-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5c904-141">For more information, see [File Adapter (BizTalk Server Sample)](../core/file-adapter-biztalk-server-sample.md).</span></span>  
  
2. <span data-ttu-id="5c904-142">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5c904-142">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
3. <span data-ttu-id="5c904-143">Vaya a la unidad de instalación de BizTalk Server y, a continuación, vaya a **<** `drive` **>: \Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples Adaptador \AdaptersUsage\File**.</span><span class="sxs-lookup"><span data-stu-id="5c904-143">Navigate to the installation drive for BizTalk Server, and then navigate to **<**`drive`**>:\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\SDK\Samples\AdaptersUsage\File Adapter**.</span></span>  
  
4. <span data-ttu-id="5c904-144">Para agregar el adaptador de ejemplo en el registro, haga doble clic en **StaticAdapterManagement.reg**. (Si desea agregar el adaptador de archivo dinámico al registro, ejecute **DynamicAdapterManagement.reg** en su lugar y usar ese archivo según corresponda.)</span><span class="sxs-lookup"><span data-stu-id="5c904-144">To add the sample adapter to the registry, double-click **StaticAdapterManagement.reg**. (If you want to add the dynamic file adapter to the registry run **DynamicAdapterManagement.reg** instead and use that file everywhere else as appropriate.)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5c904-145">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se ha instalado en la unidad C del equipo, debe modificar el archivo StaticAdapterManagement.reg con la ruta de instalación adecuada.</span><span class="sxs-lookup"><span data-stu-id="5c904-145">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is not installed on drive C of your computer, you must modify the StaticAdapterManagement.reg file with the appropriate installation path.</span></span> <span data-ttu-id="5c904-146">Busque el archivo C: y reemplácelo por la unidad de instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="5c904-146">Search the file for C: and replace it with the correct installation drive.</span></span>  
  
5. <span data-ttu-id="5c904-147">En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo, comprobando que la información era se agrega al registro.</span><span class="sxs-lookup"><span data-stu-id="5c904-147">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK** to close the dialog box, verifying that the information was added to the registry.</span></span>  
  
6. <span data-ttu-id="5c904-148">Para cerrar el Explorador de Windows, en el **archivo** menú, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5c904-148">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
    <span data-ttu-id="5c904-149">Ahora el adaptador estático de ejemplo estará registrado con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c904-149">The sample static adapter is now registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
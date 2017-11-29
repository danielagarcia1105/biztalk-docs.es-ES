---
title: Adaptador de HTTP (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f443bf0b60f0bb90a914824b3922110ee1b300
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-biztalk-server-sample"></a><span data-ttu-id="b09d7-102">Adaptador de HTTP (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b09d7-102">HTTP Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="b09d7-103">En el ejemplo de adaptador de HTTP se muestra cómo se implementan los paradigmas de comunicación de solicitud-respuesta y de petición-respuesta que se usan en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b09d7-103">The HTTP Adapter sample demonstrates how to implement the request/response and solicit/response communication paradigms used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b09d7-104">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b09d7-104">Where to Find This Sample</span></span>  
 <span data-ttu-id="b09d7-105">*\<Ejemplos de ruta de acceso >*\AdaptersDevelopment\HttpAdapter\\</span><span class="sxs-lookup"><span data-stu-id="b09d7-105">*\<Samples Path>*\AdaptersDevelopment\HttpAdapter\\</span></span>  
  
 <span data-ttu-id="b09d7-106">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="b09d7-106">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b09d7-107">Archivos</span><span class="sxs-lookup"><span data-stu-id="b09d7-107">File(s)</span></span>|<span data-ttu-id="b09d7-108">Description</span><span class="sxs-lookup"><span data-stu-id="b09d7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b09d7-109">\Design-Time\Adapter Management</span><span class="sxs-lookup"><span data-stu-id="b09d7-109">\Design-Time\Adapter Management</span></span>|<span data-ttu-id="b09d7-110">Contiene el proyecto que implementa la parte de tiempo de diseño de este adaptador.</span><span class="sxs-lookup"><span data-stu-id="b09d7-110">Contains the project that implements the design time portion of this adapter.</span></span>|  
|<span data-ttu-id="b09d7-111">\Run-Time\HttpReceive</span><span class="sxs-lookup"><span data-stu-id="b09d7-111">\Run-Time\HttpReceive</span></span>|<span data-ttu-id="b09d7-112">Contiene el proyecto que implementa la del patrón de comunicación del adaptador de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="b09d7-112">Contains the project that implements the request/response adapter communication pattern.</span></span> <span data-ttu-id="b09d7-113">Se trata de un receptor aislado.</span><span class="sxs-lookup"><span data-stu-id="b09d7-113">This is an isolated receiver.</span></span>|  
|<span data-ttu-id="b09d7-114">\Run-Time\HttpSend</span><span class="sxs-lookup"><span data-stu-id="b09d7-114">\Run-Time\HttpSend</span></span>|<span data-ttu-id="b09d7-115">Contiene el proyecto que implementa la del patrón de comunicación del adaptador de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="b09d7-115">Contains the project that implements the solicit/response adapter communication pattern.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="b09d7-116">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b09d7-116">How to Use This Sample</span></span>  
 <span data-ttu-id="b09d7-117">El propósito de este ejemplo es constituir un marco de trabajo que pueda usarse para el desarrollo de adaptadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b09d7-117">This sample is meant as a framework for you to use in developing custom adapters.</span></span> <span data-ttu-id="b09d7-118">En algunos casos, es posible que BizTalk Server necesite transportar mensajes a una aplicación personalizada específica o usar un protocolo para el que no exista un adaptador nativo.</span><span class="sxs-lookup"><span data-stu-id="b09d7-118">In some cases BizTalk Server may need to transport messages to a specific custom application or use a protocol for which a native adapter that does not exist.</span></span> <span data-ttu-id="b09d7-119">Las compañías de terceros han escrito adaptadores compatibles con otros protocolos.</span><span class="sxs-lookup"><span data-stu-id="b09d7-119">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="b09d7-120">Antes de decidirse a escribir un adaptador personalizado, puede que desee saber si ya hay un adaptador para el protocolo.</span><span class="sxs-lookup"><span data-stu-id="b09d7-120">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="b09d7-121">Si no consigue encontrar un adaptador compatible para satisfacer los requisitos de comunicación, puede desarrollar un adaptador personalizado propio.</span><span class="sxs-lookup"><span data-stu-id="b09d7-121">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  
  
 <span data-ttu-id="b09d7-122">La escritura de un adaptador personalizado puede resultar todo un desafío.</span><span class="sxs-lookup"><span data-stu-id="b09d7-122">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="b09d7-123">Para simplificar este proceso, Microsoft ha desarrollado una base denominada el marco de trabajo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="b09d7-123">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="b09d7-124">Puede usar este marco de trabajo como base para el desarrollo junto con el código fuente de adaptador de ejemplo que se encuentra en el SDK de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b09d7-124">You can use this framework as a basis for your development along with sample adapter source code in the BizTalk Server SDK.</span></span>  <span data-ttu-id="b09d7-125">Para obtener más información sobre adaptadores personalizados y el marco de trabajo, consulte la **Vea también** sección al final de este documento.</span><span class="sxs-lookup"><span data-stu-id="b09d7-125">For more information on custom adapters, and the Adapter Framework, please refer to the **See Also** section at the end of this document.</span></span>  
  
## <a name="building-and-initializing-the-sample-adapter"></a><span data-ttu-id="b09d7-126">Crear e inicializar el adaptador de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b09d7-126">Building and Initializing the Sample Adapter</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b09d7-127">Si la instalación de BizTalk es de 64 bits o se modifica la ubicación de la instalación, OutboundAssemblyPath, InboundAssemblyPath y AdapterMgmtAssemblyPath deben cambiarse según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b09d7-127">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  
  
#### <a name="to-build-and-initialize-the-http-adapter-sample"></a><span data-ttu-id="b09d7-128">Para crear e inicializar el ejemplo del adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="b09d7-128">To build and initialize the HTTP Adapter sample</span></span>  
  
1.  <span data-ttu-id="b09d7-129">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="b09d7-129">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="b09d7-130">\<*Ejemplos de ruta de acceso*> \AdaptersDevelopment\HttpAdapter</span><span class="sxs-lookup"><span data-stu-id="b09d7-130">\<*Samples Path*>\AdaptersDevelopment\HttpAdapter</span></span>  
  
2.  <span data-ttu-id="b09d7-131">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b09d7-131">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="b09d7-132">Compila el adaptador de HTTP y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="b09d7-132">Compiles the HTTPAdapter and all of its dependencies.</span></span>  
  
    -   <span data-ttu-id="b09d7-133">Crea una aplicación de Internet Information Services (IIS) que se usa para la recepción en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="b09d7-133">Creates an Internet Information Services (IIS) application used by the receiver side of the adapter.</span></span>  
  
 <span data-ttu-id="b09d7-134">En IIS 7,0, debe asegurarse de que la identidad del grupo de aplicaciones que se ejecuta en esta aplicación de IIS es miembro de los grupos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b09d7-134">On IIS 7.0, you must ensure the identity of the application pool running this IIS application is a member of the following groups:</span></span>  
  
-   <span data-ttu-id="b09d7-135">Grupo de usuarios de hosts aislados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b09d7-135">BizTalk Isolated Host Users group.</span></span>  
  
-   <span data-ttu-id="b09d7-136">Grupo IIS_WPG.</span><span class="sxs-lookup"><span data-stu-id="b09d7-136">IIS_WPG group.</span></span>  
  
-   <span data-ttu-id="b09d7-137">En IIS 7.0, debe migrar la aplicación para que funcione con el modo .NET integrado.</span><span class="sxs-lookup"><span data-stu-id="b09d7-137">On IIS 7.0, you must migrate the application to work with the Integrated .NET mode.</span></span> <span data-ttu-id="b09d7-138">Puede migrar la configuración de la aplicación, incluido el contenido de la \<httpHandlers > sección de configuración, con lo siguiente desde una ventana de línea de comandos (la ventana debe estar ejecutándose como administrador):</span><span class="sxs-lookup"><span data-stu-id="b09d7-138">You can migrate the application configuration, including the contents of the \<httpHandlers> configuration section, by using the following from a command line window (the window must be running as Administrator):</span></span>  
  
    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  
  
-   <span data-ttu-id="b09d7-139">Después de migrar la aplicación, se ejecutará en los modos .NET clásico e integrado, así como en plataformas de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="b09d7-139">After you migrate your application, it will run in both Classic and Integrated .NET modes, as well as on downlevel platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b09d7-140">Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b09d7-140">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b09d7-141">Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="b09d7-141">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="b09d7-142">Utilice este par de claves para firmar los ensamblados resultantes.</span><span class="sxs-lookup"><span data-stu-id="b09d7-142">Use this key pair to sign the resulting assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b09d7-143">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="b09d7-143">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="b09d7-144">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="b09d7-144">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="registering-the-sample-adapter"></a><span data-ttu-id="b09d7-145">Registrar el adaptador de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b09d7-145">Registering the Sample Adapter</span></span>  
  
#### <a name="to-register-the-http-adapter-sample"></a><span data-ttu-id="b09d7-146">Para registrar el ejemplo de adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="b09d7-146">To register the HTTP Adapter sample</span></span>  
  
1.  <span data-ttu-id="b09d7-147">En el Explorador de Windows, vaya a la unidad de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y, a continuación, navegue hasta \<ruta de ejemplos > \AdaptersDevelopment\HTTPAdapter.</span><span class="sxs-lookup"><span data-stu-id="b09d7-147">In Windows Explorer, navigate to the installation drive for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then navigate to \<Samples Path>\AdaptersDevelopment\HTTPAdapter.</span></span>  
  
2.  <span data-ttu-id="b09d7-148">Para agregar el adaptador de ejemplo en el registro, haga doble clic en **HTTP.NET.reg**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-148">To add the sample adapter to the registry, double-click **HTTP.NET.reg**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b09d7-149">HTTP.NET.reg incluye las rutas de acceso codificadas para el directorio de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b09d7-149">HTTP.NET.reg includes hard-coded paths to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation directory.</span></span> <span data-ttu-id="b09d7-150">Si no instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la ubicación predeterminada o si actualizó la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a partir de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], deberá modificar el archivo HTTP.NET.reg con las rutas apropiadas.</span><span class="sxs-lookup"><span data-stu-id="b09d7-150">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must modify the file HTTP.NET.reg with the appropriate paths.</span></span> <span data-ttu-id="b09d7-151">Actualice las rutas asociadas a los valores "OutboundAssemblyPath" y "AdapterMgmtAssemblyPath" para que señalen la ubicación correcta de los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="b09d7-151">Update the paths associated with the "OutboundAssemblyPath" and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b09d7-152">Si instala BizTalk en un equipo de 64 bits, cambie todas las instancias de la entrada de registro HKEY_CLASSES_ROOT\CLSID\ a HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ en el **HTTP.NET.reg** archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="b09d7-152">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **HTTP.NET.reg** registry file.</span></span>  
  
3.  <span data-ttu-id="b09d7-153">En el **Editor del registro** cuadro de diálogo, haga clic en **Sí** para agregar el adaptador de ejemplo en el registro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-153">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b09d7-154">Para cerrar el Explorador de Windows, en la **archivo** menú, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-154">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
## <a name="installing-the-sample-adapter"></a><span data-ttu-id="b09d7-155">Instalar el adaptador de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b09d7-155">Installing the Sample Adapter</span></span>  
  
#### <a name="to-install-the-http-adapter-sample"></a><span data-ttu-id="b09d7-156">Para instalar el ejemplo del adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="b09d7-156">To install the HTTP Adapter sample</span></span>  
  
1.  <span data-ttu-id="b09d7-157">Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, seleccione **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-157">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b09d7-158">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] de árbol, a continuación, expanda el **grupo de BizTalk** de árbol, a continuación, expanda el **configuración de plataforma** árbol.</span><span class="sxs-lookup"><span data-stu-id="b09d7-158">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand the **BizTalk Group** tree, then expand the **Platform Settings** tree.</span></span>  
  
3.  <span data-ttu-id="b09d7-159">Haga clic en **adaptadores**, haga clic en **New**y, a continuación, haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-159">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="b09d7-160">En el **propiedades del adaptador** diálogo cuadro, realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b09d7-160">In the **Adapter Properties** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="b09d7-161">Use</span><span class="sxs-lookup"><span data-stu-id="b09d7-161">Use this</span></span>|<span data-ttu-id="b09d7-162">Para</span><span class="sxs-lookup"><span data-stu-id="b09d7-162">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b09d7-163">Nombre</span><span class="sxs-lookup"><span data-stu-id="b09d7-163">Name</span></span>|<span data-ttu-id="b09d7-164">Tipo de **HTTP.NET**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-164">Type **HTTP.NET**.</span></span>|  
    |<span data-ttu-id="b09d7-165">Adaptador</span><span class="sxs-lookup"><span data-stu-id="b09d7-165">Adapter</span></span>|<span data-ttu-id="b09d7-166">Seleccione **HTTP.NET** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b09d7-166">Select **HTTP.NET** from the drop-down list.</span></span>|  
    |<span data-ttu-id="b09d7-167">Description</span><span class="sxs-lookup"><span data-stu-id="b09d7-167">Description</span></span>|<span data-ttu-id="b09d7-168">Tipo de **ejemplo de adaptador de HTTP.NET**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-168">Type **Sample HTTP.NET Adapter**.</span></span>|  
  
5.  <span data-ttu-id="b09d7-169">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-169">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b09d7-170">El adaptador aparece en la lista de adaptadores de la ventana derecha de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b09d7-170">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  
  
## <a name="stopping-and-restarting-the-host-instance"></a><span data-ttu-id="b09d7-171">Detener y reiniciar la instancia de host</span><span class="sxs-lookup"><span data-stu-id="b09d7-171">Stopping and Restarting the Host Instance</span></span>  
  
#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a><span data-ttu-id="b09d7-172">Para detener y reiniciar la instancia de host para el ejemplo de adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="b09d7-172">To stop and restart the host instance for the HTTP Adapter sample</span></span>  
  
1.  <span data-ttu-id="b09d7-173">Haga clic en el **iniciar** menú, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y seleccione [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b09d7-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and select [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="b09d7-174">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] de árbol, a continuación, expanda **configuración de plataforma**y haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-174">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand **Platform Settings**, and click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="b09d7-175">En el panel de resultados, haga clic en la instancia de host (normalmente, el nombre del equipo) y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-175">In the results pane, right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  
  
     <span data-ttu-id="b09d7-176">El estado de la instancia de host cambia a **detenido**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-176">The status of the host instance changes to **Stopped**.</span></span>  
  
4.  <span data-ttu-id="b09d7-177">En el panel de resultados, haga clic en la instancia de host y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b09d7-177">In the results pane, right-click the host instance, and then click **Start**.</span></span>  
  
 <span data-ttu-id="b09d7-178">La aplicación ya puede utilizar el adaptador de HTTP.NET.</span><span class="sxs-lookup"><span data-stu-id="b09d7-178">The HTTP.NET adapter is now ready to be used by your application.</span></span> <span data-ttu-id="b09d7-179">Al configurar el adaptador, el formato para la **directorio Virtual** propiedades de transporte tiene el formato: /httpreceive/httpreceive.aspx?optionalQueryString.</span><span class="sxs-lookup"><span data-stu-id="b09d7-179">When configuring the adapter, the format for the **Virtual Directory** transport property is of the form: /httpreceive/httpreceive.aspx?optionalQueryString.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="b09d7-180">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b09d7-180">Comments</span></span>  
 <span data-ttu-id="b09d7-181">El hace de adaptador HTTP.NET uso de las clases de BaseAdapter proporcionada en *\<ruta de ejemplos >*\AdaptersDevelopment\BaseAdapter\v1.0... 2\\.</span><span class="sxs-lookup"><span data-stu-id="b09d7-181">The HTTP.NET adapter makes use of the BaseAdapter classes provided in *\<Samples Path>*\AdaptersDevelopment\BaseAdapter\v1.0..2\\.</span></span> <span data-ttu-id="b09d7-182">Las clases que se proporcionan en el proyecto BaseAdapter tienen como finalidad acelerar el desarrollo del adaptador.</span><span class="sxs-lookup"><span data-stu-id="b09d7-182">The classes provided in the BaseAdapter project are intended to accelerate adapter development.</span></span> <span data-ttu-id="b09d7-183">Vea los comentarios de código BaseAdapter para obtener más información acerca de las clases proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="b09d7-183">Refer to the BaseAdapter code comments for details about the classes provided.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09d7-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="b09d7-184">See Also</span></span>  
 <span data-ttu-id="b09d7-185">[Registrar un adaptador](../core/registering-an-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-185">[Registering an Adapter](../core/registering-an-adapter.md) </span></span>  
 <span data-ttu-id="b09d7-186">[Ejemplos de adaptadores - uso](../core/adapter-samples-usage.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-186">[Adapter Samples - Usage](../core/adapter-samples-usage.md) </span></span>  
 <span data-ttu-id="b09d7-187">[Desarrollar adaptadores personalizados](../core/developing-custom-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-187">[Developing Custom Adapters](../core/developing-custom-adapters.md) </span></span>  
 <span data-ttu-id="b09d7-188">[¿Qué es el marco de trabajo?](../core/what-is-the-adapter-framework.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-188">[What Is the Adapter Framework?](../core/what-is-the-adapter-framework.md) </span></span>  
 <span data-ttu-id="b09d7-189">[Con las herramientas de marco de trabajo de adaptador](../core/using-the-adapter-framework-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-189">[Using the Adapter Framework Tools](../core/using-the-adapter-framework-tools.md) </span></span>  
 <span data-ttu-id="b09d7-190">[Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-190">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="b09d7-191">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-191">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="b09d7-192">[Cómo implementar un adaptador personalizado](../core/how-to-deploy-a-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-192">[How to Deploy a Custom Adapter](../core/how-to-deploy-a-custom-adapter.md) </span></span>  
 <span data-ttu-id="b09d7-193">[Sugerencias para diseñar un adaptador](../core/tips-for-designing-your-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b09d7-193">[Tips for Designing Your Adapter](../core/tips-for-designing-your-adapter.md) </span></span>  
 [<span data-ttu-id="b09d7-194">Configuración de tiempo de diseño de adaptador</span><span class="sxs-lookup"><span data-stu-id="b09d7-194">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)
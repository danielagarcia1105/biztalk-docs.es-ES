---
title: "Instalar el en línea y las versiones de adaptador del servicio en la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: "97"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf374b4efb219f1221275819713787565a325b0
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a><span data-ttu-id="eabb1-102">Cómo instalar las versiones de adaptador y en línea de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-102">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>
<span data-ttu-id="eabb1-103">Los pasos siguientes describen cómo preparar el equipo para instalar las versiones de adaptador y en línea de la solución orientada a servicios y cómo realizar la instalación en el mismo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-103">The following steps describe how to prepare the computer for installing the inline and adapter versions of the service oriented solution, and how to install the solution on this computer.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="eabb1-104">El servicio en la solución orientada a servicios se encuentra en la carpeta \< *carpeta de instalación de BizTalk Server*> \SDK\Scenarios\SO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-104">The service oriented solution is located in the folder \<*BizTalk Server Installation Folder*>\SDK\Scenarios\SO.</span></span>  
>  - <span data-ttu-id="eabb1-105">Si la solución no requiere un gran sistema, puede modificar el enlace de puertos para utilizar el servicio Web de código auxiliar para las transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-105">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="eabb1-106">El servicio Web genera transacciones localmente para emular las transacciones de gran sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-106">The Web service generates transactions locally to emulate the mainframe transactions.</span></span>  
  
##  <span data-ttu-id="eabb1-107"><a name="step1"></a>Preparar el equipo para instalar las versiones de adaptador y en línea de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-107"><a name="step1"></a> Prepare the computer for installing the adapter and inline versions of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-108">Si ha instalado Windows SharePoint Services, excluya (raíz) del sitio Web predeterminado de rutas administradas de Windows SharePoint Services como sigue: haga clic en **iniciar**, seleccione **todos los programas**, seleccione  **Herramientas administrativas**y, a continuación, haga clic en **Administración Central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-108">If you installed Windows SharePoint Services, exclude the (root) of the Default Web Site from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-109">En **configuración del servidor Virtual**, seleccione **configurar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-109">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="eabb1-110">En el **lista de servidores virtuales** página, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-110">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="eabb1-111">En el **configuración del servidor Virtual** página, haga clic en **definir rutas administradas**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-111">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="eabb1-112">En el **rutas incluidas** sección de la **definir rutas administradas** página, seleccione **raíz** y, a continuación, haga clic en **quitar rutas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-112">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="eabb1-113">En el símbolo del sistema, ejecute IISReset.</span><span class="sxs-lookup"><span data-stu-id="eabb1-113">At a command prompt, perform an IISReset.</span></span>  
  
2.  <span data-ttu-id="eabb1-114">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **administración de equipos** consola y, a continuación, agregue el Cuenta de servicio de BizTalk al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="eabb1-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="eabb1-115">Cierre la sesión y, a continuación, inicie una sesión en el equipo con la cuenta de servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-115">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
4.  <span data-ttu-id="eabb1-116">En un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la variable de entorno %BTSSolutionsPath%.</span><span class="sxs-lookup"><span data-stu-id="eabb1-116">At a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable.</span></span> <span data-ttu-id="eabb1-117">A continuación, cierre el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-117">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="eabb1-118">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="eabb1-118">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eabb1-119">Si está utilizando un equipo de 64 bits, escriba %ProgramFiles(x86)% en lugar de %ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="eabb1-119">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eabb1-120">Para obtener más información acerca del comando SETX, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span><span class="sxs-lookup"><span data-stu-id="eabb1-120">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <span data-ttu-id="eabb1-121"><a name="step3"></a>Quite la versión de código auxiliar de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-121"><a name="step3"></a> Remove the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-122">Abra la **consola de administración de BizTalk Server** como se indica a continuación: haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en  **Administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-122">Open the **BizTalk Server Administration Console** as follows: Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eabb1-123">En el **consola de administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, haga clic en **BTSScn.SO.CustomerService**y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-123">In the **BizTalk Server Administration Console**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, right-click **BTSScn.SO.CustomerService**, and then click **Stop**.</span></span> <span data-ttu-id="eabb1-124">En el **detener aplicación** cuadro de diálogo, seleccione **detención completa: finalizar instancias**y, a continuación, haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-124">In the **Stop Application** dialog box, select **Full Stop - Terminate Instances**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-125">No tiene que quitar la versión de código auxiliar para instalar las versiones de adaptador y en línea.</span><span class="sxs-lookup"><span data-stu-id="eabb1-125">You don't need to remove the stub version for installing the inline and adapter versions.</span></span> <span data-ttu-id="eabb1-126">Si desea colocar todas las versiones juntas, debería omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="eabb1-126">If you want to put all the versions together, you should skip this step.</span></span>  
  
3.  <span data-ttu-id="eabb1-127">Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eabb1-127">Open a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="eabb1-128">Este comando cambia el host predeterminado de secuencias de comandos a CScript.exe:</span><span class="sxs-lookup"><span data-stu-id="eabb1-128">This command changes the default script host to CScript.exe:</span></span>  
  
    -   `cscript /H:CScript`  
  
4.  <span data-ttu-id="eabb1-129">En el símbolo del sistema, cambie el directorio actual a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eabb1-129">At the command prompt, change the current directory to %BTSSolutonsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER:</span></span>  
  
    -   `UnEnlistStub.vbs`  
  
5.  <span data-ttu-id="eabb1-130">En el símbolo del sistema, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eabb1-130">At the command prompt, type the following command, and then press ENTER:</span></span>  
  
    -   `UndeployStub.vbs`  
  
6.  <span data-ttu-id="eabb1-131">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="eabb1-131">At the command prompt, run the following command</span></span>  
  
     <span data-ttu-id="eabb1-132">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="eabb1-132">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
     <span data-ttu-id="eabb1-133">De este modo, se configurará la ruta para buscar las utilidades de SAE.</span><span class="sxs-lookup"><span data-stu-id="eabb1-133">This sets the path to find the BAM utilities.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-134">Si está utilizando un equipo de 64 bits, escriba `%ProgramFiles(x86)%` en lugar de `%ProgramFiles%`.</span><span class="sxs-lookup"><span data-stu-id="eabb1-134">If you are using a 64-bit computer, type `%ProgramFiles(x86)%` instead of `%ProgramFiles%`.</span></span>  
  
7.  <span data-ttu-id="eabb1-135">En el símbolo del sistema, cambie el directorio a %BTSSolutionsPath%\SO\BTSSoln\BAM y, a continuación, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="eabb1-135">At the command prompt, change the directory to %BTSSolutionsPath%\SO\BTSSoln\BAM, and then run the following command:</span></span>  
  
    -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  
  
8.  <span data-ttu-id="eabb1-136">En el símbolo del sistema, cambie al directorio \< *Enterprise Single Sign-On directorio de instalación*>, y, a continuación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="eabb1-136">At the command prompt, change the directory to \<*Enterprise Single Sign-On Install Directory*>, and then run the following command:</span></span>  
  
    -   `ssomanage -tickets no no`  
  
9. <span data-ttu-id="eabb1-137">En el símbolo del sistema, ejecute el comando siguiente para eliminar la aplicación afiliada de SSO WoodgroveBank.CustomerService:</span><span class="sxs-lookup"><span data-stu-id="eabb1-137">At the command prompt, run the following command to delete the WoodgroveBank.CustomerService SSO Affiliated application:</span></span>  
  
    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  
  
10. <span data-ttu-id="eabb1-138">En el símbolo del sistema, ejecute los comandos siguientes para eliminar los sitios Web que utiliza la versión de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="eabb1-138">At the command prompt, run the following commands to delete the Web sites used by the stub version.</span></span> <span data-ttu-id="eabb1-139">Para obtener más información acerca de iisvdir.vbs, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span><span class="sxs-lookup"><span data-stu-id="eabb1-139">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  
  
11. <span data-ttu-id="eabb1-140">Iniciar el Administrador de Internet Information Services (IIS) como sigue: haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas de administración**y, a continuación, haga clic en **De Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-140">Start Internet Information Services (IIS) Manager as follows: Click **Start**, point to **All Programs**, point to **Administration Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    -   <span data-ttu-id="eabb1-141">Expanda el **grupos de aplicaciones**, haga clic en el grupo de aplicaciones que creó para las aplicaciones Web anteriores, haga clic en **eliminar**y, a continuación, haga clic en **Aceptar** en la confirmación cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-141">Expand the **Application Pools**, right-click the application pool you crated for the previous Web applications, click **Delete**, and then click **OK** in the confirmation dialog box.</span></span>  
  
12. <span data-ttu-id="eabb1-142">Haga clic en **iniciar**, seleccione **el Panel de Control**, haga clic en **agregar o quitar programas**y, a continuación, desinstalar el cliente IBM WebSphere MQ para Windows.</span><span class="sxs-lookup"><span data-stu-id="eabb1-142">Click **Start**, point to **Control Panel**, click **Add or Remove Programs**, and then uninstall the IBM WebSphere MQ Client for Windows.</span></span>  
  
13. <span data-ttu-id="eabb1-143">Iniciar **Visual Studio Command Prompt** y, a continuación, ejecute el siguiente comando para eliminar el archivo amqmdnet.dll que instaló para la versión de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="eabb1-143">Start **Visual Studio Command Prompt** and then run the following command to delete the amqmdnet.dll you installed for the stub version.</span></span>  
  
    -   `gacutil /u amqmdnet`  
  
##  <span data-ttu-id="eabb1-144"><a name="step5"></a>Preparar los sistemas back-end para la solución orientada a servicios tener acceso a</span><span class="sxs-lookup"><span data-stu-id="eabb1-144"><a name="step5"></a> Prepare the back-end systems for the Service Oriented Solution to access</span></span>  
  
1.  <span data-ttu-id="eabb1-145">Instalar IBM WebSphere MQ para Windows Server en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="eabb1-145">Install IBM WebSphere MQ for Windows Server on the local computer.</span></span>  
  
    1.  <span data-ttu-id="eabb1-146">Mantenga todos los valores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="eabb1-146">Keep all the default settings.</span></span> <span data-ttu-id="eabb1-147">Configurar la **configuración predeterminada** al final de la **Prepare WebSphere MQ Wizard**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-147">Set up the **Default Configuration** at the end of the **Prepare WebSphere MQ Wizard**.</span></span> <span data-ttu-id="eabb1-148">El Administrador de cola se denomina QM_\<*el nombre del equipo*>.</span><span class="sxs-lookup"><span data-stu-id="eabb1-148">The queue manager is named as QM_\<*your computer name*>.</span></span>  
  
    2.  <span data-ttu-id="eabb1-149">Instale Fix Pack10 (CSD10).</span><span class="sxs-lookup"><span data-stu-id="eabb1-149">Install the Fix Pack 10 (CSD10).</span></span> <span data-ttu-id="eabb1-150">Mantenga todos los valores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="eabb1-150">Keep all the default settings.</span></span>  
  
2.  <span data-ttu-id="eabb1-151">Instale MQSeries Agent.</span><span class="sxs-lookup"><span data-stu-id="eabb1-151">Install the MQSeries Agent.</span></span>  
  
    1.  <span data-ttu-id="eabb1-152">Vuelva a ejecutar el programa de instalación de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eabb1-152">Rerun the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] setup program.</span></span>  
  
    2.  <span data-ttu-id="eabb1-153">En el **mantenimiento del programa** página, seleccione **modificar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-153">On the **Program Maintenance** page, select **Modify**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="eabb1-154">En el **instalación de componentes** página, expanda la **Software adicional** nodo y, a continuación, seleccione **MQSeries Agent**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-154">On the **Component Installation** page, expand the **Additional Software** node, and then select **MQSeries Agent**.</span></span>  
  
    4.  <span data-ttu-id="eabb1-155">En el **finalización** página, asegúrese de que **iniciar de Asistente de configuración de BizTalk MQSeries Agent** no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="eabb1-155">On the **Completion** page, make sure that **Launch BizTalk MQSeries Agent Configuration Wizard** is not selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-156">El **MQSeries Agent** casilla se activa después de IBM WebSphere MQ para Windows está instalado.</span><span class="sxs-lookup"><span data-stu-id="eabb1-156">The **MQSeries Agent** check box is activated only after the IBM WebSphere MQ for Windows is installed.</span></span>  
  
3.  <span data-ttu-id="eabb1-157">Abra un **Visual Studio Command Prompt**, cambie el directorio a la \< *directorio de instalación de MQSeries de IBM*> carpeta \bin y, a continuación, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="eabb1-157">Open a **Visual Studio Command Prompt**, change the directory to the \<*IBM MQSeries Installation Directory*>\bin folder, and then run the following command:</span></span>  
  
    -   `gacutil /i amqmdnet.dll`  
  
4.  <span data-ttu-id="eabb1-158">Instale Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] si desea instalar Microsoft Host Integration Server 2004 para obtener acceso al gran sistema (mainframe).</span><span class="sxs-lookup"><span data-stu-id="eabb1-158">Install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] if you want to install Microsoft Host Integration Server 2004 to access the mainframe.</span></span> <span data-ttu-id="eabb1-159">En el programa de instalación en el **opciones** página, seleccione **Visual C# .NET**y, a continuación, desactive las casillas de verificación de otros componentes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-159">In the setup program, on the **Options** page, select **Visual C# .NET**, and then clear other components checkboxes.</span></span> <span data-ttu-id="eabb1-160">No es necesario instalar otros componentes de la **Visual C# .NET**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-160">You don't need to install other components than the **Visual C# .NET**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-161">TI Designer de Host Integration Server 2004 requiere [!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eabb1-161">The TI Designer in Host Integration Server 2004 requires [!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)].</span></span>  
  
5.  <span data-ttu-id="eabb1-162">Instale y configure Microsoft Host Integration Server 2004 si tiene que obtener acceso a un gran sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-162">Install and configure Microsoft Host Integration Server 2004 if you have a mainframe to be accessed.</span></span> <span data-ttu-id="eabb1-163">Mantenga todos los valores de configuración predeterminados.</span><span class="sxs-lookup"><span data-stu-id="eabb1-163">Keep all the default settings.</span></span>  
  
#### <a name="create-the-mqseries-queues"></a><span data-ttu-id="eabb1-164">Crear las colas de MQSeries</span><span class="sxs-lookup"><span data-stu-id="eabb1-164">Create the MQSeries queues</span></span>  
  
1.  <span data-ttu-id="eabb1-165">Abra WebSphere MQ Explorer, expanda **administradores de cola**y, a continuación, expanda el Administrador de cola en el que desea crear las colas.</span><span class="sxs-lookup"><span data-stu-id="eabb1-165">Open the WebSphere MQ Explorer, expand **Queue Managers**, and then expand the queue manager in which you want to create the queues.</span></span> <span data-ttu-id="eabb1-166">Normalmente, un administrador de cola se denomina QM_\<*el nombre del equipo*>.</span><span class="sxs-lookup"><span data-stu-id="eabb1-166">Typically, a queue manager is named as QM_\<*your computer name*>.</span></span>  
  
2.  <span data-ttu-id="eabb1-167">En WebSphere MQ Explorer, haga clic en **colas**, seleccione **New**, haga clic en **cola Local**y, a continuación, crear las colas locales siguientes para la versión del adaptador de la solución:</span><span class="sxs-lookup"><span data-stu-id="eabb1-167">In the WebSphere MQ Explorer, right-click **Queues**, point to **New**, click **Local Queue**, and then create the following local queues for the adapter version of the solution:</span></span>  
  
    -   <span data-ttu-id="eabb1-168">AdapterSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-168">AdapterSOAInputQueue</span></span>  
  
    -   <span data-ttu-id="eabb1-169">AdapterSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-169">AdapterSOAOutputQueue</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-170">Aunque no es necesario, las colas pueden compartir un clúster de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-170">The queues can share an MQSeries cluster, but they are not required to do so.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-171">Los nombres administradores de cola MQSeries y los nombres de cola distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eabb1-171">MQSeries queue manager names and queue names are case sensitive.</span></span>  
  
3.  <span data-ttu-id="eabb1-172">Repita el paso anterior para crear las colas locales siguientes para la versión en línea:</span><span class="sxs-lookup"><span data-stu-id="eabb1-172">Repeat the previous step to create the following local queues for the inline version:</span></span>  
  
    -   <span data-ttu-id="eabb1-173">InlineSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-173">InlineSOAOutputQueue</span></span>  
  
    -   <span data-ttu-id="eabb1-174">InlineSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-174">InlineSOAInputQueue</span></span>  
  
4.  <span data-ttu-id="eabb1-175">Repita el paso anterior para crear las colas locales siguientes para el simulador de seguimiento de pago</span><span class="sxs-lookup"><span data-stu-id="eabb1-175">Repeat the previous step to create the following local queues for the Payment Tracker simulator.</span></span> <span data-ttu-id="eabb1-176">(el simulador de seguimiento de pago se utiliza tanto en la versión de adaptador como en la versión en línea):</span><span class="sxs-lookup"><span data-stu-id="eabb1-176">(The Payment Tracker simulator is used in both the adapter and inline versions):</span></span>  
  
    -   <span data-ttu-id="eabb1-177">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-177">LastPaymentsInputQueue</span></span>  
  
    -   <span data-ttu-id="eabb1-178">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-178">LastPaymentsOutputQueue</span></span>  
  
#### <a name="complete-configuration-of-the-mqseries-adapter"></a><span data-ttu-id="eabb1-179">Completar la configuración del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="eabb1-179">Complete configuration of the MQSeries adapter</span></span>  
  
1.  <span data-ttu-id="eabb1-180">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **el Asistente para la configuración de BizTalk MQSeries Agent**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-180">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk MQSeries Agent Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="eabb1-181">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-181">On the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="eabb1-182">En el **identidad de aplicación** página, seleccione **este usuario**y, a continuación, escriba el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="eabb1-182">On the **Application Identity** page, select **This User**, and then enter the user name and password.</span></span> <span data-ttu-id="eabb1-183">La aplicación COM+ de MQSeries Agent se ejecutará bajo esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="eabb1-183">The COM+ application for the MQSeries Agent will run under this user account.</span></span> <span data-ttu-id="eabb1-184">Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-184">For this walkthrough, use the same user account that the BizTalk service is using.</span></span> <span data-ttu-id="eabb1-185">Si no lo es, las cuentas de usuario para servicios de BizTalk que aloja el adaptador de MQSeries deben agregarse a la **CreatorOwner** rol de la aplicación COM +.</span><span class="sxs-lookup"><span data-stu-id="eabb1-185">If it is not, the user accounts for BizTalk services hosting the MQSeries Adapter must be added to the **CreatorOwner** role of the COM+ application.</span></span>  
  
4.  <span data-ttu-id="eabb1-186">Haga clic en **Sí** en el **MQSConfigWiz** cuadro de diálogo, si se le solicita que la cuenta de usuario que escribió en el paso anterior tiene privilegio administrativo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-186">Click **Yes** on the **MQSConfigWiz** dialog box, if prompted that the user account that you entered in the previous step has the administrative privilege.</span></span>  
  
5.  <span data-ttu-id="eabb1-187">En el **nombre de la función** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-187">On the **Name of Role** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="eabb1-188">En el **crear el MQSAgent COM + Application** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-188">On the **Creating the MQSAgent COM+ Application** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="configure-the-mainframe-cics-application"></a><span data-ttu-id="eabb1-189">Configurar la aplicación CICS de gran sistema</span><span class="sxs-lookup"><span data-stu-id="eabb1-189">Configure the mainframe CICS application</span></span>  
  
1.  <span data-ttu-id="eabb1-190">En la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTIComponent, abra el archivo bizcbl.txt y su "libro de copia" (MainFrameProgramVTCS2Description.txt) con el Bloc de notas y, a continuación, revise su contenido.</span><span class="sxs-lookup"><span data-stu-id="eabb1-190">Using Notepad, open the bizcbl.txt and its "copy book" (MainFrameProgramVTCS2Description.txt) in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then review the contents.</span></span>  
  
    -   <span data-ttu-id="eabb1-191">Bizcbl.txt incluye el procedimiento COBOL para devolver las instrucciones aleatorias de la cuenta a partir de la entrada de números en la misma.</span><span class="sxs-lookup"><span data-stu-id="eabb1-191">Bizcbl.txt includes the COBOL procedure returning the randomized account statements from account number input.</span></span>  
  
    -   <span data-ttu-id="eabb1-192">MainFrameProgramVTCS2Descriptoin.txt contiene COMMAREA, que describe la información de los datos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="eabb1-192">MainFrameProgramVTCS2Descriptoin.txt contains COMMAREA which describes the input and output data information.</span></span> <span data-ttu-id="eabb1-193">COMMAREA es un bloque de memoria contigua que se utiliza para pasar datos entre los programas llamados y los que realizan las llamadas (en ambas direcciones).</span><span class="sxs-lookup"><span data-stu-id="eabb1-193">COMMAREA is a block of contiguous memory used to pass data back and forth between called and calling programs.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-194">También puede usar el libro de copia para generar el archivo de metadatos de Transaction Integrator (TI) con el complemento TI Designer en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eabb1-194">You can also use the copy book to generate the Transaction Integrator (TI) metadata file using Visual Studio with the TI Designer plug-in.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-195">Aunque los pasos siguientes son fundamentales para realizar una implementación correcta, no suele llevarlos a cabo el programador de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="eabb1-195">Although the following steps are crucial to the successful deployment, they are not usually performed by the BizTalk Server developer.</span></span> <span data-ttu-id="eabb1-196">El éxito de la implementación depende de que el personal del gran sistema configure el entorno mainframe correctamente.</span><span class="sxs-lookup"><span data-stu-id="eabb1-196">You must rely on the mainframe personnel to properly configure the mainframe environment.</span></span> <span data-ttu-id="eabb1-197">El software necesario para realizar este tutorial suele estar instalado en la mayoría de los entornos de gran sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-197">The software required for this walkthrough is usually installed in the most mainframe environments.</span></span> <span data-ttu-id="eabb1-198">Para obtener más información acerca del entorno de sistema operativo mínimo de gran sistema, consulte la documentación de Host Integration Server.</span><span class="sxs-lookup"><span data-stu-id="eabb1-198">For more information about the minimum mainframe operating system environment, see the Host Integration Server documentation.</span></span>  
  
2.  <span data-ttu-id="eabb1-199">Copie el código COBOL en el host mediante FTP o utilizando un método similar.</span><span class="sxs-lookup"><span data-stu-id="eabb1-199">Copy the COBOL code to the host by method like FTP.</span></span>  
  
3.  <span data-ttu-id="eabb1-200">Compile el código COBOL y el libro de copia.</span><span class="sxs-lookup"><span data-stu-id="eabb1-200">Compile the COBOL code and copy book.</span></span> <span data-ttu-id="eabb1-201">En el código siguiente, se muestra un ejemplo del lenguaje de control de tareas (JCL) del compilador COBOL.</span><span class="sxs-lookup"><span data-stu-id="eabb1-201">The following code shows a sample of Job Control Language (JCL) for the COBOL compiler.</span></span>  
  
    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  
  
4.  <span data-ttu-id="eabb1-202">Edite el vínculo con el código fuente compilado para crear un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="eabb1-202">Link edit the compiled source to create the executable.</span></span> <span data-ttu-id="eabb1-203">El código siguiente muestra un ejemplo de JCL para la edición de un vínculo de COBOL.</span><span class="sxs-lookup"><span data-stu-id="eabb1-203">The following code shows a sample of JCL for COBOL link edit.</span></span>  
  
    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  
  
5.  <span data-ttu-id="eabb1-204">Configure la aplicación CICS de gran sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-204">Configure the CICS mainframe application.</span></span>  
  
    -   <span data-ttu-id="eabb1-205">En este paso, el programador de grandes sistemas o el programador de CICS debe instalar las definiciones de recurso de Servicio TCP/IP, Sesión, Conexión, Transacción y Programa.</span><span class="sxs-lookup"><span data-stu-id="eabb1-205">In this step, the mainframe systems programmer or CICS developer must install TCPIPSERVICE, Session, Connection, Transaction, and Program resource definitions.</span></span>  
  
    -   <span data-ttu-id="eabb1-206">Para obtener una dirección IP, un número de puerto y un vínculo al programa al que puede tener acceso, vea con los administradores del gran sistema.</span><span class="sxs-lookup"><span data-stu-id="eabb1-206">You should consult with mainframe administrators to get an IP address, port number, and a Link to Program name that you can access.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eabb1-207">Este tutorial supone que el gran sistema utiliza un servidor de aplicaciones CICS y que el modelo de programación de la transacción es TCP/IP (vínculo Modo de escucha mejorado [ELM]).</span><span class="sxs-lookup"><span data-stu-id="eabb1-207">This walkthrough assumes that the mainframe uses a CICS application server and that the programming model for the transaction is TCP/IP (Enhanced Listener Mode (ELM) Link).</span></span>  
  
##  <span data-ttu-id="eabb1-208"><a name="step7"></a>Configurar el servidor Web para las capas de sockets seguros (SSL)</span><span class="sxs-lookup"><span data-stu-id="eabb1-208"><a name="step7"></a> Configure the Web server for Secure Socket Layers (SSL)</span></span>  
  
#### <a name="install-certificate-services"></a><span data-ttu-id="eabb1-209">Instalar servicios de Certificate Server</span><span class="sxs-lookup"><span data-stu-id="eabb1-209">Install Certificate Services</span></span>  
  
1.  <span data-ttu-id="eabb1-210">Haga clic en **iniciar**, seleccione **el Panel de Control**y, a continuación, haga clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-210">Click **Start**, point to **Control Panel**, and then click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="eabb1-211">En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-211">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="eabb1-212">En el **Asistente para componentes de Windows**, seleccione la **servicios de Certificate Server**, haga clic en **siguiente**y, a continuación, siga las que aparecen en pantalla instrucciones para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="eabb1-212">In the **Windows Components Wizard**, select the **Certificate Services**, click **Next**, and then follow the on-screen instructions to complete the installation.</span></span>  
  
#### <a name="create-a-certificate-request"></a><span data-ttu-id="eabb1-213">Crear una solicitud de certificado</span><span class="sxs-lookup"><span data-stu-id="eabb1-213">Create a certificate request</span></span>  
  
1.  <span data-ttu-id="eabb1-214">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, haga clic en **propiedades** , haga clic en el **seguridad de directorios** ficha y, a continuación, haga clic en **certificado de servidor**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-214">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, click **Properties**, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
2.  <span data-ttu-id="eabb1-215">En el **bienvenida** página de la **Asistente para certificados de servidor Web**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-215">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="eabb1-216">En el **certificado de servicio** página, seleccione **crear un nuevo certificado**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-216">On the **Service Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="eabb1-217">En el **Petición demorada o inmediata** página, haga clic en **preparar la petición ahora pero enviarla más tarde**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-217">On the **Delayed or Immediate Request** page, click **Prepare the request now, but send it later**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="eabb1-218">En el **nombre y la configuración de seguridad** página mantener todos los valores predeterminados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-218">On the **Name and Security Settings** page, keep all the default settings, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="eabb1-219">En el **información de la organización** página, escriba el nombre de la unidad organizativa y organización de su empresa y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-219">On the **Organization Information** page, type your company's organization and organizational unit names, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="eabb1-220">En el **nombre común de su sitio Web** página, escriba el nombre del equipo en el **nombre común** cuadro y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-220">On the **Your Site's Common Name** page, type your computer name in the **Common name** box, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="eabb1-221">En el **información geográfica** página, rellene la información geográfica y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-221">On the **Geographical Information** page, fill out your geographical information, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="eabb1-222">En el **nombre de archivo de solicitud de certificado** página, escriba `c:\certreq.txt` en el **nombre de archivo** cuadro y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-222">On the **Certificate Request File Name** page, type `c:\certreq.txt` in the **File name** box, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="eabb1-223">En el **resumen del archivo de petición** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-223">On the **Request File Summary** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="submit-the-certificate-request-to-the-certification-authority"></a><span data-ttu-id="eabb1-224">Enviar la solicitud de certificado a la entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="eabb1-224">Submit the certificate request to the Certification Authority</span></span>  
  
1.  <span data-ttu-id="eabb1-225">En Internet Explorer, en el cuadro Dirección, escriba `http://localhost/certsrvt`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="eabb1-225">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="eabb1-226">En el **bienvenida** página, haga clic en **solicitar un certificado**y, a continuación, haga clic en **solicitud de certificado avanzada** en el **solicitar un certificado** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-226">On the **Welcome** page, click **Request a Certificate**, and then click **Advanced certificate request** on the **Request a Certificate** page.</span></span>  
  
3.  <span data-ttu-id="eabb1-227">En el **solicitud de certificado avanzada** página, haga clic en **enviar una solicitud de certificado mediante un base64 codificado archivo PKCS #10 o una solicitud de renovación mediante un archivo de PKCS #7 codificado en base64**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-227">On the **Advanced Certificate Request** page, click **Submit a certificate request using a base64 encoded PKCS #10 file or a renewal request using a base64 encoded PKCS #7 file**.</span></span>  
  
4.  <span data-ttu-id="eabb1-228">Copiar todo el texto de la c:\certreq.txt que creó en el procedimiento "para crear una solicitud de certificado", péguelo en el **solicitud guardada** cuadro en el **enviar una solicitud de certificado o una solicitud de renovación** página y, a continuación, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-228">Copy all the text from the c:\certreq.txt that you created in the procedure "To create a certificate request", paste it to the **Saved Request** box on the **Submit a Certificate Request or Renewal Request** page, and then click **Submit**.</span></span>  
  
#### <a name="issue-a-certificate-using-certification-authority-management-tool"></a><span data-ttu-id="eabb1-229">Emitir un certificado con la herramienta de administración de la entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="eabb1-229">Issue a certificate using Certification Authority management tool</span></span>  
  
1.  <span data-ttu-id="eabb1-230">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-230">Click **Start**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="eabb1-231">En el **entidad de certificación** de la consola, expanda el nombre de la entidad de certificación, el **solicitud pendiente**, haga clic en la solicitud de certificado que envió en el paso anterior, punto para **todas las tareas**y, a continuación, haga clic en **problema**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-231">In the **Certification Authority** console, expand your certification authority's name, expand the **Pending Request**, right-click the certificate request that you submitted in the previous step, point to **All Tasks**, and then click **Issue**.</span></span>  
  
3.  <span data-ttu-id="eabb1-232">Cerrar la **entidad de certificación** consola.</span><span class="sxs-lookup"><span data-stu-id="eabb1-232">Close the **Certification Authority** console.</span></span>  
  
#### <a name="download-the-certificate-to-the-web-server"></a><span data-ttu-id="eabb1-233">Descargar el certificado en el servidor Web</span><span class="sxs-lookup"><span data-stu-id="eabb1-233">Download the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="eabb1-234">En Internet Explorer, en el cuadro Dirección, escriba `http://localhost/certsrvt`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="eabb1-234">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="eabb1-235">En el **bienvenida** página, haga clic en **ver el estado de una solicitud de certificado pendiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-235">On the **Welcome** page, click **View the status of a pending certificate request**.</span></span>  
  
3.  <span data-ttu-id="eabb1-236">En el **ver el estado de una solicitud de certificado pendiente** página, haga clic en el certificado **solicitud** que creó en el procedimiento "para crear una solicitud de certificado".</span><span class="sxs-lookup"><span data-stu-id="eabb1-236">On the **View the Status of a Pending Certificate Request** page, click the certificate **request** that you created in the procedure "To create a certificate request".</span></span>  
  
4.  <span data-ttu-id="eabb1-237">En el **certificado emitido** , seleccione cualquiera de los esquemas de codificación y, a continuación, haga clic en **Descargar certificado**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-237">On the **Certificate Issued** page, select either of the encoding schemes, and then click **Download certificate**.</span></span>  
  
5.  <span data-ttu-id="eabb1-238">En el **advertencia de seguridad** cuadro de diálogo, haga clic en **guardar**y, a continuación, guarde el certificado como c:\certnew.cer.</span><span class="sxs-lookup"><span data-stu-id="eabb1-238">On the **Security Warning** dialog box, click **Save**, and then save the certificate as c:\certnew.cer.</span></span>  
  
#### <a name="install-the-certificate-to-the-web-server"></a><span data-ttu-id="eabb1-239">Instale el certificado en el servidor Web</span><span class="sxs-lookup"><span data-stu-id="eabb1-239">Install the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="eabb1-240">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado** para la que se creó la solicitud de certificado y, a continuación, Haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-240">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site** for which you created the certificate request, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="eabb1-241">En el **propiedades** cuadro de diálogo, haga clic en el **seguridad de directorios** ficha y, a continuación, haga clic en **certificado de servidor**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-241">On the **Properties** dialog box, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
3.  <span data-ttu-id="eabb1-242">En el **bienvenida** página de la **Asistente para certificados de servidor Web**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-242">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="eabb1-243">En el **solicitud de certificado pendiente** página, seleccione **procesar la petición pendiente e instalar el certificado**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-243">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="eabb1-244">En el **procesar una solicitud pendiente** página, escriba `c:\certnew.cer` en el **ruta de acceso y nombre de archivo** cuadro de texto y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-244">On the **Process a Pending Request** page, type `c:\certnew.cer` in the **Path and file name** text box, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="eabb1-245">Haga clic en **siguiente** en el **puerto SSL** página, haga clic en **siguiente** en el **resumen del certificado** página y, a continuación, haga clic en **finalizar** en el **confirmación** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-245">Click **Next** on the **SSL Port** page, click **Next** on the **Certificate Summery** page, and then click **Finish** on the **Confirmation** page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-246">En este tutorial, no necesita instalar el certificado de servidor en el almacén de entidades emisoras de certificados raíz de confianza del equipo local, ya que tanto los Servicios de Certificate Server como el servidor Web están instalados en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-246">In this walkthrough you don't need to install the server certificate to the Trusted Root Certification Authorities store on the local computer because both Certificate Services and Web server are installed on the same computer.</span></span>  
  
##  <span data-ttu-id="eabb1-247"><a name="step9"></a>Crear los servicios Web para los sistemas back-end</span><span class="sxs-lookup"><span data-stu-id="eabb1-247"><a name="step9"></a> Create the Web services for the back-end systems</span></span>  
  
1.  <span data-ttu-id="eabb1-248">En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **delgrupodeaplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-248">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-249">La solución orientada a servicios obtiene acceso al gran sistema a través de este servicio Web.</span><span class="sxs-lookup"><span data-stu-id="eabb1-249">The service oriented solution accesses the mainframe through this Web service.</span></span>  
  
2.  <span data-ttu-id="eabb1-250">En el **Agregar nuevo grupo de aplicaciones** diálogo cuadro, escriba la **Id. de grupo de aplicaciones** (cualquier valor) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-250">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="eabb1-251">En el **Internet Information Services (IIS) Manager**, haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-251">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="eabb1-252">En el **propiedades** página, haga clic en el **identidad** ficha, seleccione **Configurable**, escriba la **nombre de usuario** y **contraseña** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-252">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="eabb1-253">Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-253">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
#### <a name="create-the-pendingtransactions-web-service-for-runtime"></a><span data-ttu-id="eabb1-254">Crear el servicio Web de transacciones pendientes para el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="eabb1-254">Create the PendingTransactions Web service for runtime</span></span>  
  
1.  <span data-ttu-id="eabb1-255">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-255">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-256">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="eabb1-256">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="eabb1-257">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-257">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-258">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-258">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-259">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-259">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="eabb1-260">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-260">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-261">En el **seguridad de directorios** , haga clic en **editar** modificar **autenticación y control de acceso**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-261">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="eabb1-262">Seleccione **la autenticación básica (la contraseña se envía en texto no cifrado)**y desactive las demás **de acceso de autenticación** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="eabb1-262">Select **Basic authentication (password is sent in clear text)**, and clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="eabb1-263">Haga clic en **Aceptar** para cerrar el **métodos de autenticación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-263">Click **OK** to close the **Authentication Methods** dialog box.</span></span>  
  
    2.  <span data-ttu-id="eabb1-264">En el **seguridad de directorios** , haga clic en **editar** en el **una comunicación segura** cuadro del grupo y, a continuación, busque **Requerir canal seguro (SSL)**en la **comunicaciones seguras** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-264">In the **Directory Security** tab, click **Edit** under the **Secure Communication** group box, and then check **Require secure channel (SSL)** in the **Secure Communications** dialog box.</span></span>  
  
    3.  <span data-ttu-id="eabb1-265">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** al grupo de aplicaciones que creó en el procedimiento "para crear un nuevo grupo de aplicaciones de IIS para los servicios Web de transacciones pendientes".</span><span class="sxs-lookup"><span data-stu-id="eabb1-265">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="create-the-pendingtransactions-web-service-for-development-environment"></a><span data-ttu-id="eabb1-266">Crear el servicio Web de transacciones pendientes para el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="eabb1-266">Create the PendingTransactions Web service for development environment</span></span>  
  
1.  <span data-ttu-id="eabb1-267">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-267">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-268">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="eabb1-268">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="eabb1-269">Alias = PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-269">Alias = PendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-270">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-270">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-271">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-271">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="eabb1-272">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en PendingTransactions y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-272">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-273">En el **seguridad de directorios** , haga clic en **editar** modificar **autenticación y control de acceso**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-273">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="eabb1-274">Seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-274">Select **Enable anonymous access**.</span></span> <span data-ttu-id="eabb1-275">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-275">Click **OK** to exit.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eabb1-276">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] usará la aplicación Web PendingTransactions para el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-276">The PendingTransactions Web application for development environment will be used by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="eabb1-277">Esta aplicación Web no es necesaria para un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="eabb1-277">You don't need this Web application for production environment.</span></span>  
  
    2.  <span data-ttu-id="eabb1-278">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** al grupo de aplicaciones que creó en el procedimiento "para crear un nuevo grupo de aplicaciones de IIS para los servicios Web de transacciones pendientes".</span><span class="sxs-lookup"><span data-stu-id="eabb1-278">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="create-the-stub-sap-web-service"></a><span data-ttu-id="eabb1-279">Crear el servicio Web SAP de código auxiliar</span><span class="sxs-lookup"><span data-stu-id="eabb1-279">Create the Stub SAP Web service</span></span>  
  
1.  <span data-ttu-id="eabb1-280">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-280">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-281">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web SAP de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="eabb1-281">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="eabb1-282">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-282">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
     <span data-ttu-id="eabb1-283">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-283">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
     <span data-ttu-id="eabb1-284">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-284">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="eabb1-285">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="eabb1-285">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="eabb1-286">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el procedimiento "para crear una nueva aplicación IIS grupo para los servicios Web de transacciones pendientes".</span><span class="sxs-lookup"><span data-stu-id="eabb1-286">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
    2.  <span data-ttu-id="eabb1-287">En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-287">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="eabb1-288">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-288">Click **OK** to exit.</span></span>  
  
##  <span data-ttu-id="eabb1-289"><a name="step11"></a>Crear el componente TI para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-289"><a name="step11"></a> Create the TI component for the Service Oriented Solution</span></span>  
  
#### <a name="create-a-com-application-for-the-ti-component"></a><span data-ttu-id="eabb1-290">Crear una aplicación COM + para el componente TI</span><span class="sxs-lookup"><span data-stu-id="eabb1-290">Create a COM+ application for the TI component</span></span>  
  
1.  <span data-ttu-id="eabb1-291">En un símbolo del sistema, ejecute %systemroot%\system32\com\comexp.msc.</span><span class="sxs-lookup"><span data-stu-id="eabb1-291">At a command prompt, run %systemroot%\system32\com\comexp.msc.</span></span>  
  
2.  <span data-ttu-id="eabb1-292">En **servicios de componentes** de la consola, expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, haga clic en  **La aplicación COM +**, seleccione **New**y, a continuación, haga clic en **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-292">In **Component Services** console, expand **Component Services**, expand **Computers**, expand **My Computer**, right-click **COM+ Application**, point to **New**, and then click **Application**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-293">En el **bienvenida** página, haga clic en **siguiente**y, a continuación, haga clic en **crear una aplicación vacía** en el **instale o cree una nueva aplicación** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-293">On the **Welcome** page, click **Next**, and then click **Create an empty application** on the **Install or Create a New Application** page.</span></span>  
  
    2.  <span data-ttu-id="eabb1-294">Tipo de `BTSScn SO TI Component` en el **escriba un nombre para la nueva aplicación** cuadro, seleccione **aplicación de servidor** como **tipo de activación**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-294">Type `BTSScn SO TI Component` in the **Enter a name for the new application** box, select **Server application** as **Activation type**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="eabb1-295">En el **cuenta** cuadro de grupo de la **establecer identidad de la aplicación** página, seleccione **Este usuario**y, a continuación, escriba el nombre de usuario y la contraseña en la **usuario**y **contraseña** cuadros.</span><span class="sxs-lookup"><span data-stu-id="eabb1-295">In the **Account** group box of the **Set Application Identity** page, select **This user**, and then type the user name and password in the **User** and **Password** boxes.</span></span> <span data-ttu-id="eabb1-296">La nueva aplicación COM+ se ejecutará bajo esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="eabb1-296">The new COM+ application will run under this user account.</span></span> <span data-ttu-id="eabb1-297">La cuenta de usuario debe ser un miembro del grupo local de usuarios en tiempo de ejecución de HIS.</span><span class="sxs-lookup"><span data-stu-id="eabb1-297">This user account must be a member of local HIS Runtime Users group.</span></span> <span data-ttu-id="eabb1-298">Para este tutorial, use la misma cuenta de usuario que está utilizando el servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-298">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
    4.  <span data-ttu-id="eabb1-299">En el **agregar funciones de aplicación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-299">On the **Add Application Roles** page, click **Next**.</span></span>  
  
    5.  <span data-ttu-id="eabb1-300">En el **agregar usuarios a funciones** página, expanda **CreatorOwner**, haga clic en **usuarios**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-300">On the **Add Users to Roles** page, expand **CreatorOwner**, click **Users**, and then click **Add**.</span></span>  
  
    6.  <span data-ttu-id="eabb1-301">En el **Seleccionar usuarios o grupos** cuadro de diálogo, seleccione una cuenta de usuario que se utilizará para tener acceso a los clientes de mainframe.</span><span class="sxs-lookup"><span data-stu-id="eabb1-301">On the **Select Users or Groups** dialog box, select a user account that will be used for accessing the mainframe.</span></span> <span data-ttu-id="eabb1-302">Para este tutorial, agregue la cuenta local UserID.</span><span class="sxs-lookup"><span data-stu-id="eabb1-302">For this walkthrough, add UserID local account.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eabb1-303">Para tener acceso a la transacción CICS a través del componente TI, puede utilizar la aplicación COM+ o la aplicación Web que contiene el componente .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="eabb1-303">To access the CICS transaction through the TI component, you can use the COM+ application or the Web application hosting the .NET Remoting component.</span></span> <span data-ttu-id="eabb1-304">Este tutorial utiliza la aplicación COM+ y la interoperabilidad COM para componentes TI para obtener acceso al gran sistema y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="eabb1-304">This walkthrough uses the COM+ application and COM Interop for TI components to access the mainframe to improve performance.</span></span>  
  
    7.  <span data-ttu-id="eabb1-305">En el **finalización** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-305">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="create-a-remote-environment-to-access-the-mainframe"></a><span data-ttu-id="eabb1-306">Crear un entorno remoto para obtener acceso al mismo</span><span class="sxs-lookup"><span data-stu-id="eabb1-306">Create a Remote Environment to access the mainframe</span></span>  
  
1.  <span data-ttu-id="eabb1-307">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Host Integration Server 2004**y, a continuación, haga clic en **TI Manager**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-307">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="eabb1-308">En el **TI Manager** de la consola, haga clic en **Transaction Integrator (Configuration)**, expanda **Windows Initiated Processing**, haga clic en **remoto Entornos**, seleccione **New**y, a continuación, haga clic en **Remote Environment**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-308">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, expand **Windows Initiated Processing**, right-click **Remote Environments**, point to **New**, and then click **Remote Environment**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-309">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-309">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="eabb1-310">En el **configura un nuevo entorno remoto** página, escriba el **Remote Application Name**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-310">On the **Configure a New Remote Environment** page, type the **Remote Application Name**, and then click **Next**.</span></span> <span data-ttu-id="eabb1-311">Para este tutorial, utilice el nombre Mainframe_TCP.</span><span class="sxs-lookup"><span data-stu-id="eabb1-311">For this walkthrough, use Mainframe_TCP for the name.</span></span>  
  
    3.  <span data-ttu-id="eabb1-312">En el **Configure Host Environment and Programming Model** página, seleccione **CICS** para el **host de destino** y **ELM Link** para el  **Modelo de programación**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-312">On the **Configure Host Environment and Programming Model** page, select **CICS** for the **Target host** and **ELM Link** for the **Programming model**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="eabb1-313">En **el punto de conexión configurar, TCP/IP** página, escriba la dirección IP del gran sistema en el **dirección IP/DNS** cuadro y, a continuación, haga clic en **editar** para agregar el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="eabb1-313">On **the Configure Endpoint TCP/IP** page, type the IP address for your mainframe in the **IP/DNS address** box, and then click **Edit** to add the port number.</span></span> <span data-ttu-id="eabb1-314">Su COM de HIS tendrá acceso a las transacciones a través de la dirección de extremo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-314">Your HIS COM will access the transactions through the endpoint address.</span></span>  
  
    5.  <span data-ttu-id="eabb1-315">En el **finalización** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-315">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="create-the-ti-component-for-the-service-oriented-solution"></a><span data-ttu-id="eabb1-316">Crear el componente TI para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-316">Create the TI Component for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-317">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Host Integration Server 2004**y, a continuación, haga clic en **TI Manager**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-317">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="eabb1-318">En el **TI Manager** de la consola, haga clic en **Transaction Integrator (Configuration)**, haga clic en **Windows Initiated Processing**y, a continuación, haga clic en **objetos**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-318">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, click **Windows Initiated Processing**, and then click **Objects**.</span></span> <span data-ttu-id="eabb1-319">Haga clic en **objetos**, haga clic en **New**y, a continuación, haga clic en **objeto**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-319">Right-click **Objects**, click **New**, and then click **Object**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-320">En el **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-320">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="eabb1-321">En el **especificar Or Locate An Object** página, haga clic en **examinar**, elija SOHISTIUsingCOM.TLB en la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTIComponent y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-321">On the **Specify Or Locate An Object** page, click **Browse**, choose the SOHISTIUsingCOM.TLB in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="eabb1-322">En el **Define Environment Characteristics para el objeto COM** página, seleccione **btsscn SO TI Component** para el **aplicación COM +**y, a continuación, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="eabb1-322">On the **Define Environment Characteristics for The COM Object** page, select **BTSScn SO TI Component** for the **COM+ application**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="eabb1-323">En el **Define Remote Environment** página, seleccione el entorno remoto que ha creado en el procedimiento anterior para el **entorno remoto y, a continuación, haga clic en siguiente.**</span><span class="sxs-lookup"><span data-stu-id="eabb1-323">On the **Define Remote Environment** page, select the remote environment that you created in the previous procedure for the **Remote environment, and then click Next.**</span></span>  
  
    5.  <span data-ttu-id="eabb1-324">En el **Creation of WIP Objects** página, haga clic en **siguiente**y, a continuación, haga clic en **finalizar** en el **finalización** página.</span><span class="sxs-lookup"><span data-stu-id="eabb1-324">On the **Creation of WIP Objects** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="test-the-connectivity-to-the-mainframe"></a><span data-ttu-id="eabb1-325">Probar la conectividad con el gran sistema</span><span class="sxs-lookup"><span data-stu-id="eabb1-325">Test the connectivity to the mainframe</span></span>  
  
1.  <span data-ttu-id="eabb1-326">En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester y haga doble clic en el archivo Interop.SOHISTIUsingCOM.dll.reg.</span><span class="sxs-lookup"><span data-stu-id="eabb1-326">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester folder, and then double-click the Interop.SOHISTIUsingCOM.dll.reg file.</span></span> <span data-ttu-id="eabb1-327">Al hacerlo, agregará los valores de registro de la aplicación HISTISimpleTester para llamar al componente TI en tiempo de ejecución mediante RCW.</span><span class="sxs-lookup"><span data-stu-id="eabb1-327">This adds registry values for the HISTISimpleTester application to call the TI component through the Runtime Callable Wrapper (RCW).</span></span>  
  
2.  <span data-ttu-id="eabb1-328">En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\ y, a continuación, ejecute SetupMFAccess.bat.</span><span class="sxs-lookup"><span data-stu-id="eabb1-328">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\ folder, and then run SetupMFAccess.bat.</span></span>  
  
3.  <span data-ttu-id="eabb1-329">En el Explorador de Windows, vaya a la carpeta %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug y, a continuación, ejecute BTSScnSOHISTIComponentSimpleTester.exe.</span><span class="sxs-lookup"><span data-stu-id="eabb1-329">In Windows Explorer, navigate to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug folder, and then run BTSScnSOHISTIComponentSimpleTester.exe.</span></span>  
  
    -   <span data-ttu-id="eabb1-330">En la aplicación HISTISimpleTester, haga clic en **Call Mainframe Program - usar COM**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-330">In the HISTISimpleTester application, click **Call Mainframe Program - Using COM**.</span></span> <span data-ttu-id="eabb1-331">Devuelve cinco registros de la aplicación COBOL que se ejecuta en el gran sistema (mainframe).</span><span class="sxs-lookup"><span data-stu-id="eabb1-331">It returns five records from the COBOL application running on the mainframe.</span></span>  
  
##  <span data-ttu-id="eabb1-332"><a name="step13"></a>Crear los directorios virtuales para la orquestación de servicios Web</span><span class="sxs-lookup"><span data-stu-id="eabb1-332"><a name="step13"></a> Create the virtual directories for the orchestration Web services</span></span>  
  
1.  <span data-ttu-id="eabb1-333">En el **Internet Information Services (IIS) Manager**, haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, seleccione **delgrupodeaplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-333">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-334">En el **Agregar nuevo grupo de aplicaciones** diálogo cuadro, escriba la **Id. de grupo de aplicaciones** (cualquier valor) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-334">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="eabb1-335">Haga clic en el grupo de aplicaciones recién creado y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-335">Right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="eabb1-336">En el **propiedades** página, haga clic en el **identidad** ficha, seleccione **Configurable**, escriba la **nombre de usuario** y **contraseña** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-336">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="eabb1-337">Para este tutorial, use la misma cuenta de usuario que utiliza el servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-337">For this walkthrough use the same user account that the BizTalk service is using.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-338">Este usuario debe tener permiso para ejecutar el servicio Web de proxy de orquestación y debe agregarse a uno de los grupos de administradores de BizTalk Server, administradores de SSO o administradores de aplicaciones afiliadas de SSO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-338">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
2.  <span data-ttu-id="eabb1-339">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-339">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-340">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión del adaptador:</span><span class="sxs-lookup"><span data-stu-id="eabb1-340">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="eabb1-341">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span><span class="sxs-lookup"><span data-stu-id="eabb1-341">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span></span>  
  
     <span data-ttu-id="eabb1-342">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span><span class="sxs-lookup"><span data-stu-id="eabb1-342">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span></span>  
  
     <span data-ttu-id="eabb1-343">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-343">Access Permissions = Read, Run scripts</span></span>  
  
3.  <span data-ttu-id="eabb1-344">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web,** expandir la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="eabb1-344">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="eabb1-345">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="eabb1-345">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> that you created in the previous step.</span></span>  
  
    2.  <span data-ttu-id="eabb1-346">En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="eabb1-346">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="eabb1-347">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-347">Click **OK** to exit.</span></span>  
  
4.  <span data-ttu-id="eabb1-348">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-348">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-349">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el proxy de servicio Web para la versión en línea:</span><span class="sxs-lookup"><span data-stu-id="eabb1-349">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the inline version:</span></span>  
  
     <span data-ttu-id="eabb1-350">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span><span class="sxs-lookup"><span data-stu-id="eabb1-350">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span></span>  
  
     <span data-ttu-id="eabb1-351">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span><span class="sxs-lookup"><span data-stu-id="eabb1-351">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span></span>  
  
     <span data-ttu-id="eabb1-352">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-352">Access Permissions = Read, Run scripts</span></span>  
  
5.  <span data-ttu-id="eabb1-353">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="eabb1-353">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="eabb1-354">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="eabb1-354">On the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you just created.</span></span>  
  
    2.  <span data-ttu-id="eabb1-355">Haga clic en **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro de grupo, seleccione **autenticación integrada de Windows habilitado**y, a continuación, desactive las demás **de acceso de autenticación** casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="eabb1-355">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="eabb1-356">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-356">Click **OK** to exit.</span></span>  
  
##  <span data-ttu-id="eabb1-357"><a name="step15"></a>Crear solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-357"><a name="step15"></a> Build the Service Oriented Solution</span></span>  
  
-   <span data-ttu-id="eabb1-358">En un símbolo del sistema, cambie el directorio a % BTSSolutionsPath%\SO\BTSSoln, escriba `SetupBTSSoln.bat`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="eabb1-358">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln, type `SetupBTSSoln.bat`, and then press ENTER.</span></span> <span data-ttu-id="eabb1-359">El archivo SetupBTSSoln.bat realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="eabb1-359">The SetupBTSSoln.bat performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="eabb1-360">Crea una clave de nombre seguro único (SNK) para firmar los ensamblados de la solución SO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-360">Creates a unique strong name key (SNK) for signing the assemblies of the SO Solution.</span></span>  
  
    -   <span data-ttu-id="eabb1-361">Extrae el símbolo de clave pública de la clave SNK y actualiza los archivos de enlace con el símbolo público.</span><span class="sxs-lookup"><span data-stu-id="eabb1-361">Extracts the public key token from the SNK and updates the binding files with the public token.</span></span>  
  
    -   <span data-ttu-id="eabb1-362">Genera la solución SO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-362">Builds the SO solution.</span></span>  
  
    -   <span data-ttu-id="eabb1-363">Genera SSOApplicationConfig en la carpeta %BTSSolutionsPath%\Common.</span><span class="sxs-lookup"><span data-stu-id="eabb1-363">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
##  <span data-ttu-id="eabb1-364"><a name="step17"></a>Crear aplicaciones afiliadas SSO</span><span class="sxs-lookup"><span data-stu-id="eabb1-364"><a name="step17"></a> Create the SSO affiliate applications</span></span>  
  
1.  <span data-ttu-id="eabb1-365">Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts.</span><span class="sxs-lookup"><span data-stu-id="eabb1-365">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="eabb1-366">En el símbolo del sistema, abra el archivo PendTransAffApp.xml con el Bloc de notas y revíselo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-366">At the command prompt, open the PendTransAffApp.xml using Notepad, and review it.</span></span> <span data-ttu-id="eabb1-367">No es necesario realizar cambios en este archivo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-367">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-368">El archivo PendTransAffApp.xml define la aplicación afiliada SSO WoodgroveBank.PendingTransactions, para el sistema de servidor de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-368">The PendTransAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PendingTransactions, for the Pending Transactions back-end system.</span></span> <span data-ttu-id="eabb1-369">También define los grupos administrativos y de usuarios de la aplicación afiliada SSO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-369">It also defines the user and administrative groups for the SSO affiliate application.</span></span> <span data-ttu-id="eabb1-370">En este tutorial, utilice **usuarios de la aplicación de BizTalk** y **administradores de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-370">For this walkthrough, use **BizTalk Application Users** and **BizTalk Server Administrators**.</span></span>  
    >   
    >  <span data-ttu-id="eabb1-371">Si desea utilizar grupos diferentes de la aplicación afiliada SSO, debe crear grupos de Windows (con cualquier nombre) en Active Directory y, a continuación, cambie la **appAdminAccount** y **appUserAccount** nodos en el archivo PendTransAffApp.xml.</span><span class="sxs-lookup"><span data-stu-id="eabb1-371">If you want to use different groups for the SSO affiliate application, you need to create Windows groups (with any name) in the Active Directory, and then change the **appAdminAccount** and **appUserAccount** nodes in the PendTransAffApp.xml.</span></span> <span data-ttu-id="eabb1-372">Si lo hace, debe establecer el valor de **groupApp** atributo de **marcas** nodo en "Sí".</span><span class="sxs-lookup"><span data-stu-id="eabb1-372">If you do this, you should set the value for **groupApp** attribute of **flags** node to "yes".</span></span>  
    >   
    >  <span data-ttu-id="eabb1-373">Para obtener más información sobre las aplicaciones afiliadas SSO, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="eabb1-373">For more information about SSO affiliate applications, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
3.  <span data-ttu-id="eabb1-374">En el símbolo del sistema, abra el archivo PendTransUserMap.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-374">At the command prompt, open the PendTransUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-375">El archivo PendTransUserMap.xml contiene las asignaciones de usuario para el sistema de servidor de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-375">The PendTransUserMap.xml file contains the user mappings for the Pending Transactions back-end system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-376">Para el **externalUserId** nodo, use el identificador de usuario externo para el sistema de back-end de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-376">For the **externalUserId** node, use the external user ID for the Pending Transactions back-end system.</span></span> <span data-ttu-id="eabb1-377">Para este tutorial, utilice UserID como identificador externo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-377">For this walkthrough, use UserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-378">Para el **windowsUserId** nodo, escriba el usuario que el nombre del **externalUserId** se asignarán a.</span><span class="sxs-lookup"><span data-stu-id="eabb1-378">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="eabb1-379">Puede utilizar tanto un grupo de dominio como una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="eabb1-379">You can use both a domain group and a domain user account.</span></span> <span data-ttu-id="eabb1-380">El usuario debe ser miembro del grupo al que se permitirá utilizar el sistema de servidor de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-380">This user must be a member of the group that will be allowed to use the Pending Transactions back-end system.</span></span> <span data-ttu-id="eabb1-381">En este tutorial, utilice el nombre de usuario del servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-381">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-382">Para el **windowsDomain** nodo, escriba el nombre de dominio de la **windowsUserId**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-382">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
4.  <span data-ttu-id="eabb1-383">En el símbolo del sistema, abra el archivo PmntTrckAffApp.xml con el Bloc de notas y, a continuación, analice su contenido.</span><span class="sxs-lookup"><span data-stu-id="eabb1-383">At the command prompt, open the PmntTrckAffApp.xml file using Notepad, and review the contents of the file.</span></span> <span data-ttu-id="eabb1-384">No es necesario realizar cambios en este archivo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-384">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-385">El archivo PmntTrckAffApp.xml define la aplicación afiliada SSO WoodgroveBank.PaymentTracker para el sistema de servidor de seguimiento de pago.</span><span class="sxs-lookup"><span data-stu-id="eabb1-385">The PmntTrckAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PaymentTracker, for the Payment Tracker back-end system.</span></span>  
  
5.  <span data-ttu-id="eabb1-386">En el símbolo del sistema, abra el archivo PmntTrckUserMap.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-386">At the command prompt, open the PmntTrckUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-387">La aplicación afiliada SSO de seguimiento de pago se utilizará para el adaptador de MQSeries, y el Id. de usuario y contraseña externos asignados se enviarán con las propiedades de encabezado de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-387">The Payment Tracker SSO affiliated application will be used for the MQSeries Adapter and the mapped external user ID/password are sent through MQSeries header properties.</span></span> <span data-ttu-id="eabb1-388">MQSeries Server valida sólo la cuenta de servicio de BizTalk con la que se está ejecutando el adaptador de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-388">The MQSeries Server validates only the BizTalk service account, under which MQSeries Adapter is running.</span></span> <span data-ttu-id="eabb1-389">No valida ninguna credencial de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-389">It doesn't validate any external user credential.</span></span>  
    >   
    >  <span data-ttu-id="eabb1-390">Para obtener más información acerca de SSO afiliadas aplicaciones para el adaptador de MQSeries, vea [cómo configurar ubicaciones de recepción de MQSeries adaptador y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span><span class="sxs-lookup"><span data-stu-id="eabb1-390">For more information about SSO affiliated applications for the MQSeries Adapter, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-391">El archivo PmntTrckUserMap.xml contiene las asignaciones de usuario SSO para el sistema de servidor de seguimiento de pago.</span><span class="sxs-lookup"><span data-stu-id="eabb1-391">The PmntTrckUserMap.xml file contains the SSO user mappings for the Payment Tracker back-end system.</span></span> <span data-ttu-id="eabb1-392">El programa de simulador de seguimiento de pago simula las condiciones de acierto y error de la autenticación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="eabb1-392">The Payment Tracker simulator program simulates both success and failure conditions for user authentication.</span></span>  
    >   
    >  <span data-ttu-id="eabb1-393">El programa autentica correctamente todos los identificadores de usuario que comienzan con las letras **PT** (por ejemplo, **PTUserID**) pero no puede autenticar los identificadores que no comienzan por usuario **PT**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-393">The program successfully authenticates all user IDs that begin with the letters **PT** (for example, **PTUserID**), and fails to authenticate any user IDs that do not begin with **PT**.</span></span> <span data-ttu-id="eabb1-394">Esto permite elegir el Id. de usuario correcto según la condición que desee probar.</span><span class="sxs-lookup"><span data-stu-id="eabb1-394">This enables you to choose the appropriate user ID depending on the condition that you would like to test.</span></span> <span data-ttu-id="eabb1-395">También puede repetir todo el **asignación** nodo para cada identificador de usuario y definir varias asignaciones en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-395">You can also repeat the entire **mapping** node for each user ID and define multiple mappings in the same file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-396">Para el **externalUserId** nodo, escriba el identificador de usuario externo para el sistema de back-end de seguimiento de pago.</span><span class="sxs-lookup"><span data-stu-id="eabb1-396">For the **externalUserId** node, enter the external user ID for the Payment Tracker back-end system.</span></span> <span data-ttu-id="eabb1-397">Para este tutorial, utilice PTUserID como identificador externo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-397">For this walkthrough, use PTUserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-398">Para el **windowsUserId** nodo, escriba el usuario que el nombre del **externalUserId** se asignarán a.</span><span class="sxs-lookup"><span data-stu-id="eabb1-398">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="eabb1-399">El usuario debe ser miembro del grupo al que se permitirá utilizar el sistema de servidor de seguimiento de pago.</span><span class="sxs-lookup"><span data-stu-id="eabb1-399">This user must be a member of the group that will be allowed to use the Payment Tracker back-end system.</span></span> <span data-ttu-id="eabb1-400">En este tutorial, utilice el nombre de usuario del servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="eabb1-400">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-401">Para el **windowsDomain** nodo, escriba el nombre de dominio de la **windowsUserId**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-401">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
6.  <span data-ttu-id="eabb1-402">En el símbolo del sistema, abra el archivo ConfigStoreApp.xml con el Bloc de notas y, a continuación, analice su contenido.</span><span class="sxs-lookup"><span data-stu-id="eabb1-402">At the command prompt, open the ConfigStoreApp.xml file using Notepad, and then review the contents of the file.</span></span>  
  
     <span data-ttu-id="eabb1-403">Este archivo define la aplicación de almacenamiento de configuración de SSO que el escenario emplea para mantener los parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="eabb1-403">This file defines the configuration store application in SSO that the scenario uses to keep configuration parameters.</span></span> <span data-ttu-id="eabb1-404">Entre los parámetros de configuración, se encuentra el valor de tiempo de espera para la comunicación con SAP (tanto para la versión en línea como para la de adaptador), el nombre del administrador de cola y las colas que se emplearán al utilizar la versión en línea.</span><span class="sxs-lookup"><span data-stu-id="eabb1-404">Some of the configuration parameters include the Timeout value when communicating with SAP (for both the adapter and inline versions) and the name of the queue manager and queues to use when using the inline version.</span></span> <span data-ttu-id="eabb1-405">No es necesario realizar cambios en este archivo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-405">No changes to this file are necessary.</span></span>  
  
7.  <span data-ttu-id="eabb1-406">En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con el Bloc de notas y revise y cambie su contenido de acuerdo con los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="eabb1-406">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, review and change the contents of the file as the following table.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-407">Este archivo de comandos establece los valores de los parámetros de configuración de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-407">This command file sets the values for the configuration parameters in the SSO database.</span></span> <span data-ttu-id="eabb1-408">Contiene varios comandos establecidos que asignan valores a variables locales al principio del archivo de comandos.</span><span class="sxs-lookup"><span data-stu-id="eabb1-408">It contains several set commands that assign the values to local variables in the beginning of the command file.</span></span>  
    >   
    >  <span data-ttu-id="eabb1-409">Los valores SAPAdapterTimeout, PendingTransactionsAdapterTimeout y PaymentTrackingAdapterTimeout se utilizan en la versión de adaptador.</span><span class="sxs-lookup"><span data-stu-id="eabb1-409">The SAPAdapterTimeout, PendingTransactionsAdapterTimeout, and PaymentTrackingAdapterTimeout values are used in the adapter version.</span></span> <span data-ttu-id="eabb1-410">Los valores restantes se utilizan en la versión en línea.</span><span class="sxs-lookup"><span data-stu-id="eabb1-410">The remaining values are used in the inline version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-411">Puede escribir "" (dos comillas dobles) para los valores predeterminados marcados \<especificado por el usuario > en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="eabb1-411">You can enter " " (two double quotes) for the default values marked \<User Specified> in the following table.</span></span>  
  
    |<span data-ttu-id="eabb1-412">Parámetro</span><span class="sxs-lookup"><span data-stu-id="eabb1-412">Parameter</span></span>|<span data-ttu-id="eabb1-413">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="eabb1-413">Default Value</span></span>|<span data-ttu-id="eabb1-414">Description</span><span class="sxs-lookup"><span data-stu-id="eabb1-414">Description</span></span>|  
    |---------------|-------------------|-----------------|  
    |<span data-ttu-id="eabb1-415">SAPAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-415">SAPAdapterTimeout</span></span>|<span data-ttu-id="eabb1-416">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-416">20000</span></span>|<span data-ttu-id="eabb1-417">Tiempo máximo de espera (en milisegundos) de una solicitud al back-end SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-417">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="eabb1-418">SAPInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-418">SAPInlineTimeout</span></span>|<span data-ttu-id="eabb1-419">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-419">20000</span></span>|<span data-ttu-id="eabb1-420">Tiempo máximo de espera (en milisegundos) de una solicitud al back-end SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-420">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="eabb1-421">SAPInlineHostName</span><span class="sxs-lookup"><span data-stu-id="eabb1-421">SAPInlineHostName</span></span>|<span data-ttu-id="eabb1-422">\<Especificado por el usuario ></span><span class="sxs-lookup"><span data-stu-id="eabb1-422">\<User Specified></span></span>|<span data-ttu-id="eabb1-423">Identificador de servidor SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-423">SAP back-end identifier</span></span>|  
    |<span data-ttu-id="eabb1-424">SAPInlineClientNumber</span><span class="sxs-lookup"><span data-stu-id="eabb1-424">SAPInlineClientNumber</span></span>|<span data-ttu-id="eabb1-425">\<Especificado por el usuario ></span><span class="sxs-lookup"><span data-stu-id="eabb1-425">\<User Specified></span></span>|<span data-ttu-id="eabb1-426">Número de cliente SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-426">SAP Client number</span></span>|  
    |<span data-ttu-id="eabb1-427">SAPInlineSystemNumber</span><span class="sxs-lookup"><span data-stu-id="eabb1-427">SAPInlineSystemNumber</span></span>|<span data-ttu-id="eabb1-428">\<Especificado por el usuario ></span><span class="sxs-lookup"><span data-stu-id="eabb1-428">\<User Specified></span></span>|<span data-ttu-id="eabb1-429">Número de sistema SAP</span><span class="sxs-lookup"><span data-stu-id="eabb1-429">SAP System number</span></span>|  
    |<span data-ttu-id="eabb1-430">SAPInlineUserName</span><span class="sxs-lookup"><span data-stu-id="eabb1-430">SAPInlineUserName</span></span>|<span data-ttu-id="eabb1-431">\<Especificado por el usuario ></span><span class="sxs-lookup"><span data-stu-id="eabb1-431">\<User Specified></span></span>|<span data-ttu-id="eabb1-432">Nombre de usuario utilizado para conectarse al servidor SAP.</span><span class="sxs-lookup"><span data-stu-id="eabb1-432">The user name used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="eabb1-433">SAPInlinePassword</span><span class="sxs-lookup"><span data-stu-id="eabb1-433">SAPInlinePassword</span></span>|<span data-ttu-id="eabb1-434">\<Especificado por el usuario ></span><span class="sxs-lookup"><span data-stu-id="eabb1-434">\<User Specified></span></span>|<span data-ttu-id="eabb1-435">Contraseña utilizada para conectarse al servidor SAP.</span><span class="sxs-lookup"><span data-stu-id="eabb1-435">The password used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="eabb1-436">PendingTransactionsAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-436">PendingTransactionsAdapterTimeout</span></span>|<span data-ttu-id="eabb1-437">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-437">20000</span></span>|<span data-ttu-id="eabb1-438">Tiempo máximo de espera (en milisegundos) para una solicitud al servidor de transacciones pendientes</span><span class="sxs-lookup"><span data-stu-id="eabb1-438">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="eabb1-439">PendingTransactionsInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-439">PendingTransactionsInlineTimeout</span></span>|<span data-ttu-id="eabb1-440">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-440">20000</span></span>|<span data-ttu-id="eabb1-441">Tiempo máximo de espera (en milisegundos) para una solicitud al servidor de transacciones pendientes</span><span class="sxs-lookup"><span data-stu-id="eabb1-441">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="eabb1-442">PendingTransactionsInlineURL</span><span class="sxs-lookup"><span data-stu-id="eabb1-442">PendingTransactionsInlineURL</span></span>|<span data-ttu-id="eabb1-443">https://\<*el nombre del equipo*> /Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span><span class="sxs-lookup"><span data-stu-id="eabb1-443">https://\<*your computer name*>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span></span>|<span data-ttu-id="eabb1-444">Dirección URL del servicio transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-444">URL of the Pending Transactions service.</span></span> <span data-ttu-id="eabb1-445">\<*El nombre del equipo*> debe coincidir con el **nombre común** en el procedimiento "para crear una solicitud de certificado".</span><span class="sxs-lookup"><span data-stu-id="eabb1-445">\<*Your computer name*> must match the **common name** in the procedure "To create a certificate request".</span></span> <span data-ttu-id="eabb1-446">No debe utilizar "localhost" para \< *el nombre del equipo*>.</span><span class="sxs-lookup"><span data-stu-id="eabb1-446">You must not use "localhost" for \<*Your computer name*>.</span></span>|  
    |<span data-ttu-id="eabb1-447">PendingTransactionsInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="eabb1-447">PendingTransactionsInlineSSOAffiliateApp</span></span>|<span data-ttu-id="eabb1-448">WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-448">WoodgroveBank.PendingTransactions</span></span>|<span data-ttu-id="eabb1-449">Nombre de la aplicación SSO de transacciones pendientes</span><span class="sxs-lookup"><span data-stu-id="eabb1-449">Pending Transactions SSO application name</span></span>|  
    |<span data-ttu-id="eabb1-450">PaymentTrackingAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-450">PaymentTrackingAdapterTimeout</span></span>|<span data-ttu-id="eabb1-451">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-451">20000</span></span>|<span data-ttu-id="eabb1-452">Tiempo máximo de espera (en milisegundos) para una solicitud al sistema seguimiento de pagos</span><span class="sxs-lookup"><span data-stu-id="eabb1-452">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="eabb1-453">PaymentTrackingInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="eabb1-453">PaymentTrackingInlineTimeout</span></span>|<span data-ttu-id="eabb1-454">20000</span><span class="sxs-lookup"><span data-stu-id="eabb1-454">20000</span></span>|<span data-ttu-id="eabb1-455">Tiempo máximo de espera (en milisegundos) para una solicitud al sistema seguimiento de pagos</span><span class="sxs-lookup"><span data-stu-id="eabb1-455">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="eabb1-456">PaymentTrackingInlineQManager</span><span class="sxs-lookup"><span data-stu-id="eabb1-456">PaymentTrackingInlineQManager</span></span>|<span data-ttu-id="eabb1-457">\<Usuario Specified > (normalmente QM_\<*el nombre del equipo*>).</span><span class="sxs-lookup"><span data-stu-id="eabb1-457">\<User Specified> (Typically QM_\<*your computer name*>).</span></span>|<span data-ttu-id="eabb1-458">Nombre del administrador de la cola MQSeries</span><span class="sxs-lookup"><span data-stu-id="eabb1-458">MQSeries Queue Manager name</span></span>|  
    |<span data-ttu-id="eabb1-459">PaymentTrackingInlineMQChannelDefinition</span><span class="sxs-lookup"><span data-stu-id="eabb1-459">PaymentTrackingInlineMQChannelDefinition</span></span>|<span data-ttu-id="eabb1-460">" " (es necesario escribir las dos comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="eabb1-460">" " (need to enter the two double quotes).</span></span>|<span data-ttu-id="eabb1-461">Si es local, una cadena vacía, o bien el nombre del canal con formato del servidor MQ remoto.</span><span class="sxs-lookup"><span data-stu-id="eabb1-461">Empty string if local, or formatted channel name of the remote MQ server.</span></span> <span data-ttu-id="eabb1-462">Si mantiene todos los valores predeterminados en la configuración de IBM WebSphere MQ, la definición de canal será S__\<*el nombre del equipo*>/TCP /\<*el nombre del equipo*> (1414).</span><span class="sxs-lookup"><span data-stu-id="eabb1-462">If you keep all default settings in configuring IBM WebSphere MQ, the channel definition will be S__\<*your computer name*>/TCP/\<*your computer name*>(1414).</span></span>|  
    |<span data-ttu-id="eabb1-463">PaymentTrackingInlineRequestQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-463">PaymentTrackingInlineRequestQueue</span></span>|<span data-ttu-id="eabb1-464">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-464">LastPaymentsInputQueue</span></span>|<span data-ttu-id="eabb1-465">Nombre de la cola MQ para las solicitudes de seguimiento de pago</span><span class="sxs-lookup"><span data-stu-id="eabb1-465">The MQ Queue name for payment tracking requests</span></span>|  
    |<span data-ttu-id="eabb1-466">PaymentTrackingInlineResponseQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-466">PaymentTrackingInlineResponseQueue</span></span>|<span data-ttu-id="eabb1-467">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="eabb1-467">LastPaymentsOutputQueue</span></span>|<span data-ttu-id="eabb1-468">Nombre de la cola MQ para respuestas de seguimiento de pago</span><span class="sxs-lookup"><span data-stu-id="eabb1-468">The MQ Queue name for payment tracking responses</span></span>|  
    |<span data-ttu-id="eabb1-469">PaymentTrackingInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="eabb1-469">PaymentTrackingInlineSSOAffiliateApp</span></span>|<span data-ttu-id="eabb1-470">WoodgroveBank.PaymentTracker</span><span class="sxs-lookup"><span data-stu-id="eabb1-470">WoodgroveBank.PaymentTracker</span></span>|<span data-ttu-id="eabb1-471">Nombre de la aplicación SSO de seguimiento de pago</span><span class="sxs-lookup"><span data-stu-id="eabb1-471">Payment tracking SSO application name</span></span>|  
    |<span data-ttu-id="eabb1-472">StubSAPWebServiceURL</span><span class="sxs-lookup"><span data-stu-id="eabb1-472">StubSAPWebServiceURL</span></span>|<span data-ttu-id="eabb1-473">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span><span class="sxs-lookup"><span data-stu-id="eabb1-473">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span></span>|<span data-ttu-id="eabb1-474">URL del servicio Web de código auxiliar del sistema SAP de límite de crédito</span><span class="sxs-lookup"><span data-stu-id="eabb1-474">The stub Web service URL of the Credit Limit SAP system</span></span>|  
  
8.  <span data-ttu-id="eabb1-475">En el símbolo del sistema, ejecute el siguiente comando establecer el entorno PATH:</span><span class="sxs-lookup"><span data-stu-id="eabb1-475">At the command prompt, run the following command to set the PATH environment:</span></span>  
  
    -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  
  
9. <span data-ttu-id="eabb1-476">En el símbolo del sistema, ejecute el CreateInitialConfigInSSO.cmd.</span><span class="sxs-lookup"><span data-stu-id="eabb1-476">At the command prompt, run the CreateInitialConfigInSSO.cmd.</span></span> <span data-ttu-id="eabb1-477">Crea las aplicaciones afiliadas de SSO, la aplicación de almacén de configuración de SSO y las asignaciones de usuario para las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="eabb1-477">It creates the SSO Affiliate Applications, the SSO configuration store application, and the user mappings for the affiliate applications.</span></span> <span data-ttu-id="eabb1-478">A continuación, ejecuta SetConfigValuesInSSO.cmd para almacenar los valores de configuración en la aplicación de almacenamiento de la configuración SSO.</span><span class="sxs-lookup"><span data-stu-id="eabb1-478">Then, it executes the SetConfigValuesInSSO.cmd to store configuration values in the SSO configuration store application.</span></span>  
  
10. <span data-ttu-id="eabb1-479">En el símbolo del sistema, ejecute el comando siguiente para establecer la credencial de usuario de la aplicación afiliada de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-479">At the command prompt, run the following command to set the user credential for the Pending Transactions affiliate application.</span></span> <span data-ttu-id="eabb1-480">Use la \< **DomainName**> y \< **UserID**> definido en el archivo PendTransUserMap.xml para el \<WindowsDomain >\\< WindowsUserId\>.</span><span class="sxs-lookup"><span data-stu-id="eabb1-480">Use the \<**DomainName**> and \<**UserID**> defined in the PendTransUserMap.xml for the \<WindowsDomain>\\<WindowsUserId\>.</span></span> <span data-ttu-id="eabb1-481">Este comando pide que facilite la contraseña del usuario externo, UserID, utilizado en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="eabb1-481">This command asks you to enter the password of the external user, UserID, used in this walkthrough.</span></span>  
  
    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  
  
11. <span data-ttu-id="eabb1-482">En el símbolo del sistema, ejecute el comando siguiente para establecer la credencial de usuario de la aplicación afiliada de seguimiento de pago.</span><span class="sxs-lookup"><span data-stu-id="eabb1-482">At the command prompt, run the following command to set the user credential for the Payment Tracker affiliate application.</span></span> <span data-ttu-id="eabb1-483">Use la \< **DomainName**> y \< **UserID**> definido en el archivo PmntTrckUserMap.xml para el \<WindowsDomain >\\< WindowsUserId \>.</span><span class="sxs-lookup"><span data-stu-id="eabb1-483">Use the \<**DomainName**> and \<**UserID**> defined in the PmntTrckUserMap.xml for the \<WindowsDomain>\\<WindowsUserId\>.</span></span> <span data-ttu-id="eabb1-484">Este comando pide que facilite la contraseña del usuario externo, PTUserID, utilizado en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="eabb1-484">This command asks you to enter the password of the external user, PTUserID, used in this walkthrough.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-485">El simulador de seguimiento de pago no valida la credencia de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-485">The Payment Tracker simulator doesn't validate the external user credential.</span></span> <span data-ttu-id="eabb1-486">Puede escribir cualquier contraseña para el identificador PTUserID.</span><span class="sxs-lookup"><span data-stu-id="eabb1-486">You can enter any password for the PTUserID.</span></span>  
  
    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  
  
##  <span data-ttu-id="eabb1-487"><a name="step19"></a>Implementar el archivo de definición de BAM para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-487"><a name="step19"></a> Deploy the BAM definition file for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-488">Abra un símbolo del sistema, escriba el comando siguiente y, a continuación, presione ENTRAR para establecer la ruta para buscar las utilidades de SAE:</span><span class="sxs-lookup"><span data-stu-id="eabb1-488">Open a command prompt, type the following command, and then press ENTER to set the path to find the BAM utilities:</span></span>  
  
    -   <span data-ttu-id="eabb1-489">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="eabb1-489">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
2.  <span data-ttu-id="eabb1-490">En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\BAM, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eabb1-490">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM, type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
##  <span data-ttu-id="eabb1-491"><a name="step21"></a>Implementar solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-491"><a name="step21"></a> Deploy the Service Oriented Solution</span></span>  
  
#### <a name="update-the-binding-files-for-the-service-oriented-solution"></a><span data-ttu-id="eabb1-492">Actualizar los archivos de enlace para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-492">Update the binding files for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-493">En el símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, abra el archivo Deployallbinding.xml en Notepad y, a continuación, realice las siguientes modificaciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-493">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open the Deployallbinding.xml using Notepad, and then make the following edits:</span></span>  
  
    -   <span data-ttu-id="eabb1-494">Cambie el nombre del servidor que aparece en SET MGMT_DB_SERVER y en MBMT_DB al nombre del servidor y de la base de datos que está utilizando BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="eabb1-494">Change the name of the server in the SET MGMT_DB_SERVER and MBMT_DB to the name of the server and database that BizTalk Server is using.</span></span>  
  
    -   <span data-ttu-id="eabb1-495">Cambie el valor de la variable SOLNDIR a "%BTSSolutionsPath%\SO\BTSSoln".</span><span class="sxs-lookup"><span data-stu-id="eabb1-495">Change the value of the SOLNDIR variable to "%BTSSolutionsPath%\SO\BTSSoln".</span></span>  
  
2.  <span data-ttu-id="eabb1-496">En un símbolo de sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Bindings.</span><span class="sxs-lookup"><span data-stu-id="eabb1-496">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Bindings folder.</span></span>  
  
3.  <span data-ttu-id="eabb1-497">Para la versión de adaptador, abra el archivo AdapterSOAOrchBindings.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-497">For the adapter version, open the AdapterSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="eabb1-498">Reemplace todas las apariciones de __MQ_SERVER_NAME\_ \_ con el nombre del servidor de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-498">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="eabb1-499">Reemplace todas las apariciones de __MQ_QMANAGER_NAME\_ \_ con el nombre del Administrador de cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-499">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
    -   <span data-ttu-id="eabb1-500">Reemplace todas las apariciones de __PT_WS_SERVER_NAME\_ \_ en la cadena "\<dirección > https://\__PT_WS_SERVER_NAME\_\_" con el nombre del servidor donde las transacciones pendientes Se implementa el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="eabb1-500">Replace all occurrences of __PT_WS_SERVER_NAME\_\_ in the string "\<Address>https://\__PT_WS_SERVER_NAME\_\_" with the server name where the Pending Transactions Web service is deployed.</span></span> <span data-ttu-id="eabb1-501">El nombre del servidor debe coincidir con el **nombre común** en el paso "para configurar el servidor Web para SSL".</span><span class="sxs-lookup"><span data-stu-id="eabb1-501">The server name must match the **common name** in the step, "To configure the Web server for SSL".</span></span> <span data-ttu-id="eabb1-502">No debe utilizar localhost.</span><span class="sxs-lookup"><span data-stu-id="eabb1-502">You shouldn't use localhost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-503">El archivo de enlace, AdapterSOAOrchBindings.xml, emplea el servicio Web de código auxiliar para las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-503">The binding file, AdapterSOAOrchBindings.xml, uses the stub Web service for:</span></span>  
    >   
    >  1.  <span data-ttu-id="eabb1-504">El sistema de back-end SAP de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="eabb1-504">The Credit Limit back-end SAP system.</span></span>  
    > 2.  <span data-ttu-id="eabb1-505">El adaptador de MQSeries para integrarse con el sistema de back-end de seguimiento de pagos.</span><span class="sxs-lookup"><span data-stu-id="eabb1-505">The MQSeries adapter to integrate with the Payment Tracking back-end system.</span></span>  
    > 3.  <span data-ttu-id="eabb1-506">El servicio web de transacciones pendientes para realizar la llamada al componente .NET TI de HIS y realizar la integración con el sistema de back-end de mainframe.</span><span class="sxs-lookup"><span data-stu-id="eabb1-506">The Pending Transactions Web service to call the HIS TI .NET component to integrate with the mainframe back-end system.</span></span>  
    >   
    >  <span data-ttu-id="eabb1-507">Si no está utilizando un sistema mainframe, deberá emplear el servicio Web de código auxiliar para generar datos para el sistema de transacciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="eabb1-507">If you aren’t using the mainframe, you must use the stub Web service to generate data for the Pending Transactions system.</span></span>  
  
4.  <span data-ttu-id="eabb1-508">Para la versión en línea, abra el archivo InlineSOAOrchBindings.xml con el Bloc de notas y, a continuación, realice las siguientes modificaciones:</span><span class="sxs-lookup"><span data-stu-id="eabb1-508">For the inline version, open the InlineSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="eabb1-509">Reemplace todas las apariciones de __MQ_SERVER_NAME\_ \_ con el nombre del servidor de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-509">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="eabb1-510">Reemplace todas las apariciones de __MQ_QMANAGER_NAME\_ \_ con el nombre del Administrador de cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="eabb1-510">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
#### <a name="deploy-the-service-oriented-solution"></a><span data-ttu-id="eabb1-511">Implementar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-511">Deploy the Service Oriented solution</span></span>  
  
-   <span data-ttu-id="eabb1-512">En un símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eabb1-512">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER.</span></span>  
  
    -   `Deployallbinding.cmd`  
  
    > [!NOTE]
    >  <span data-ttu-id="eabb1-513">El comando Deployallbinding.cmd crea una aplicación de BizTalk denominada BTSScn.SO.CustomerService e importa archivos de enlace para las versiones de adaptador y en línea.</span><span class="sxs-lookup"><span data-stu-id="eabb1-513">The Deployallbinding.cmd creates the BizTalk application named BTSScn.SO.CustomerService and imports binding files for the adapter and inline versions.</span></span>  
  
##  <span data-ttu-id="eabb1-514"><a name="step23"></a>Configurar el código auxiliar de servicios Web de transacciones pendientes cuando no hay un gran sistema</span><span class="sxs-lookup"><span data-stu-id="eabb1-514"><a name="step23"></a> Configure the stub Pending Transactions Web Services when a mainframe is not available</span></span>  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a><span data-ttu-id="eabb1-515">Configurar el servicio Web de transacciones pendientes (para utilizar la versión del adaptador sin un gran sistema) de código auxiliar</span><span class="sxs-lookup"><span data-stu-id="eabb1-515">Configure the stub Pending Transactions Web service (for using the adapter version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="eabb1-516">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-516">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-517">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web de transacciones pendientes para la versión del adaptador de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="eabb1-517">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="eabb1-518">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-518">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-519">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="eabb1-519">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="eabb1-520">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-520">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="eabb1-521">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración como se indica a continuación mediante el **propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-521">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows using the **Properties** dialog box.</span></span>  
  
    1.  <span data-ttu-id="eabb1-522">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso "para crear los directorios virtuales de IIS para la solución".</span><span class="sxs-lookup"><span data-stu-id="eabb1-522">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="eabb1-523">En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-523">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="eabb1-524">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-524">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="eabb1-525">En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda y BTSScn.SO.CustomerService **enviar Puertos**, haga clic en **PendingTransactionSolicitResponsePort**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-525">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand BTSScn.SO.CustomerService, expand **Send Ports**, right-click **PendingTransactionSolicitResponsePort**, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="eabb1-526">En el **General** página, haga clic en **configurar** para mostrar la **propiedades de transporte** diálogo cuadro y, a continuación, modifique la **dirección URL del servicio Web** a el servicio de código auxiliar Web de transacciones pendientes, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eabb1-526">In the **General** page, click **Configure** to display the **Transport Properties** dialog box, and then modify the **Web Service URL** to the stub Pending Transaction Web service, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
    2.  <span data-ttu-id="eabb1-527">Cierre todos los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eabb1-527">Close all of the dialog boxes.</span></span>  
  
#### <a name="configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a><span data-ttu-id="eabb1-528">Configurar el servicio Web de transacciones pendientes (para utilizar la versión en línea sin un gran sistema) de código auxiliar</span><span class="sxs-lookup"><span data-stu-id="eabb1-528">Configure the stub Pending Transactions Web service (for using the inline version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="eabb1-529">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, haga clic en el **sitio Web predeterminado**, seleccione **nuevo**, y a continuación, haga clic en **directorio Virtual** para ejecutar **Asistente para crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-529">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="eabb1-530">Mediante el **Asistente para crear un directorio Virtual**, cree el siguiente directorio virtual para el servicio Web de transacciones pendientes para la versión del adaptador de código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="eabb1-530">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="eabb1-531">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="eabb1-531">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="eabb1-532">Ruta de acceso = \< *directorio de instalación de BizTalk*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="eabb1-532">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="eabb1-533">Permisos de acceso = lectura, ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="eabb1-533">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="eabb1-534">En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda la **sitio Web predeterminado**, haga clic en Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, haga clic en **propiedades**y, a continuación, modifique la configuración tal y como sigue:</span><span class="sxs-lookup"><span data-stu-id="eabb1-534">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="eabb1-535">En el **directorio Virtual** pestaña, establezca el **grupo de aplicaciones** a \< *YourAppPool*> que creó en el paso "para crear los directorios virtuales de IIS para la solución".</span><span class="sxs-lookup"><span data-stu-id="eabb1-535">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="eabb1-536">En el **seguridad de directorios** , haga clic en **editar** en el **autenticación y control de acceso** cuadro del grupo y, a continuación, seleccione **habilitar el acceso anónimo**.</span><span class="sxs-lookup"><span data-stu-id="eabb1-536">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="eabb1-537">Haga clic en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="eabb1-537">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="eabb1-538">Abra un símbolo del sistema y, a continuación, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts.</span><span class="sxs-lookup"><span data-stu-id="eabb1-538">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
4.  <span data-ttu-id="eabb1-539">En el símbolo del sistema, abra el archivo SetConfigValuesInSSO.cmd con el Bloc de notas y, a continuación, establezca el valor de la **PendingTransactionsInlineURL** a la dirección URL del servicio Web de transacción pendiente de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="eabb1-539">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, and then set the value of the **PendingTransactionsInlineURL** to the URL of the stub Pending Transaction Web Service.</span></span>  
  
    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
5.  <span data-ttu-id="eabb1-540">En el símbolo del sistema, escriba `SetConfigValuesInSSO.cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="eabb1-540">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER.</span></span>  
  
##  <span data-ttu-id="eabb1-541"><a name="step25"></a>Inicie el servicio solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-541"><a name="step25"></a> Start the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="eabb1-542">Abra un símbolo del sistema, cambie el directorio a la carpeta %BTSSolutionsPath%\SO\BTSSoln\Scripts, escriba el comando siguiente y, a continuación, presione ENTRAR para iniciar todas las orquestaciones de las versiones de adaptador y en línea.</span><span class="sxs-lookup"><span data-stu-id="eabb1-542">Open a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER to start all orchestrations for the inline and adapter versions.</span></span>  
  
    -   `startAll.vbs`  
  
2.  <span data-ttu-id="eabb1-543">Ejecute la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="eabb1-543">Run the service-oriented solution.</span></span> <span data-ttu-id="eabb1-544">Para obtener más información acerca de cómo ejecutar la solución, vea [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="eabb1-544">For more information about running the solution, see [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eabb1-545">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="eabb1-545">Next Steps</span></span>  
 <span data-ttu-id="eabb1-546">Pruebe las versiones del adaptador y en línea de la solución orientada a servicios en [cómo ejecutar la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="eabb1-546">You test the inline and adapter version of the service-oriented solution in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabb1-547">Vea también</span><span class="sxs-lookup"><span data-stu-id="eabb1-547">See Also</span></span>  
 <span data-ttu-id="eabb1-548">[Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="eabb1-548">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="eabb1-549">[Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="eabb1-549">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="eabb1-550">Solución orientada a servicios de configuración del equipo del desarrollador para el servicio</span><span class="sxs-lookup"><span data-stu-id="eabb1-550">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)
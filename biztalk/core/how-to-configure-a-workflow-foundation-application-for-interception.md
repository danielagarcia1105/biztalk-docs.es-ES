---
title: "Cómo configurar una aplicación de Workflow Foundation para la intercepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad184ce4b0ef619361f44f6eb1ee54a2354f5148
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a><span data-ttu-id="b7781-102">Cómo configurar una aplicación de Workflow Foundation para llevar a cabo una intercepción</span><span class="sxs-lookup"><span data-stu-id="b7781-102">How to Configure a Workflow Foundation Application for Interception</span></span>
<span data-ttu-id="b7781-103">Debe instalar el software interceptor de BAM y configurar la aplicación para utilizar el servicio de interceptor [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] antes de comenzar a recopilar los datos de actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="b7781-103">You must install the BAM interceptor software and configure your application to use the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="b7781-104">Se supone que ha instalado correctamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias, y que ha creado al menos un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b7781-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  
  
## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="b7781-105">Instalar el software de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="b7781-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="b7781-106">Antes de configurar la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] para usar el interceptor de BAM para [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], deberá instalar el software Eventos BAM mediante el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7781-106">Before you can configure your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="b7781-107">Para obtener más información sobre cómo instalar el software eventos BAM y registrar los contadores de rendimiento, consulte [instalar el Software eventos BAM](../core/installing-the-bam-eventing-software.md).</span><span class="sxs-lookup"><span data-stu-id="b7781-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a><span data-ttu-id="b7781-108">Configurar una aplicación de Workflow Foundation para llevar a cabo un seguimiento</span><span class="sxs-lookup"><span data-stu-id="b7781-108">Configuring a Windows Workflow Foundation Application for Tracking</span></span>  
 <span data-ttu-id="b7781-109">Deben llevarse a cabo cuatro tareas antes de que la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] pueda comenzar a escribir la información de eventos de BAM:</span><span class="sxs-lookup"><span data-stu-id="b7781-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application can begin writing BAM event information:</span></span>  
  
-   <span data-ttu-id="b7781-110">Debe crearse un modelo de observación mediante las herramientas de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y, a continuación, implementarlo mediante la herramienta de línea de comandos del administrador de BAM (bm.exe).</span><span class="sxs-lookup"><span data-stu-id="b7781-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command-line tool (bm.exe).</span></span>  
  
-   <span data-ttu-id="b7781-111">Un archivo de configuración de interceptor se debe crear e implementarse mediante la línea de comandos de administrador de BAM-herramienta (bm.exe).</span><span class="sxs-lookup"><span data-stu-id="b7781-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line-tool (bm.exe).</span></span>  
  
-   <span data-ttu-id="b7781-112">El usuario que ejecuta la aplicación host debe ser un miembro del sistema de escritura de evento de actividad BAM adecuado (bam_\<actividad > _EventWriter) roles de SQL Server para permitir que la aplicación leer información de configuración de interceptor y escribir en el de BAM actividades.</span><span class="sxs-lookup"><span data-stu-id="b7781-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  
  
-   <span data-ttu-id="b7781-113">Debe modificar el archivo App.config o la aplicación para cargar el servicio de seguimiento de BAM y, a continuación, reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-113">The App.config file or the application itself must be modified to load the BAM tracking service and then restart the application.</span></span>  
  
 <span data-ttu-id="b7781-114">Los eventos comenzarán a aparecer en la base de datos de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] únicamente después de completar estas tareas correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7781-114">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  
  
### <a name="deploying-an-observation-model"></a><span data-ttu-id="b7781-115">Implementar modelos de observación</span><span class="sxs-lookup"><span data-stu-id="b7781-115">Deploying an Observation Model</span></span>  
 <span data-ttu-id="b7781-116">Debe haberse implementado un modelo de observación antes de implementar un archivo de configuración de interceptor o capturar actividades de BAM en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-116">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="b7781-117">Para implementar un modelo de observación mediante bm.exe</span><span class="sxs-lookup"><span data-stu-id="b7781-117">To deploy an observation model by using bm.exe</span></span>  
  
1.  <span data-ttu-id="b7781-118">Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7781-118">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2.  <span data-ttu-id="b7781-119">Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7781-119">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b7781-120">Utilice el comando de cambio de directorio para mover el directorio que contiene el modelo de observación que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="b7781-120">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="b7781-121">Por ejemplo, **c:\businessprocess\Orders cd**.</span><span class="sxs-lookup"><span data-stu-id="b7781-121">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4.  <span data-ttu-id="b7781-122">Implementar un modelo de observación mediante bm.exe:</span><span class="sxs-lookup"><span data-stu-id="b7781-122">Deploy the observation model by using bm.exe:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b7781-123">Tracking\BM.exe implementar-all - definitionfile:\<*definitionfile.xml*></span><span class="sxs-lookup"><span data-stu-id="b7781-123">Tracking\BM.exe deploy-all -definitionfile:\<*definitionfile.xml*></span></span>  
  
     <span data-ttu-id="b7781-124">Asegúrese de reemplazar \< *definitionfile.xml*> con el nombre del archivo de observación que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="b7781-124">Make sure you replace \<*definitionfile.xml*> with the name of the observation file you want to deploy.</span></span> <span data-ttu-id="b7781-125">Para obtener más opciones, consulte [comandos de administración de Interceptor](../core/interceptor-management-commands.md).</span><span class="sxs-lookup"><span data-stu-id="b7781-125">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7781-126">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b7781-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="b7781-127">Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7781-127">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="b7781-128">Implementar un archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="b7781-128">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="b7781-129">Debe implementar un archivo de configuración de interceptor antes de que la aplicación puede capturar actividades de BAM.</span><span class="sxs-lookup"><span data-stu-id="b7781-129">You must deploy an interceptor configuration file before your application can capture BAM activities.</span></span>  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="b7781-130">Para implementar un archivo de configuración de interceptor mediante bm.exe</span><span class="sxs-lookup"><span data-stu-id="b7781-130">To deploy an interceptor configuration file by using bm.exe</span></span>  
  
1.  <span data-ttu-id="b7781-131">Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="b7781-131">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2.  <span data-ttu-id="b7781-132">Tipo de **cmd** en el **abiertos** campo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7781-132">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b7781-133">Utilice el comando de cambio de directorio para mover el directorio que contiene el archivo de configuración de interceptor que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="b7781-133">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="b7781-134">Por ejemplo, **c:\businessprocess\Orders cd**.</span><span class="sxs-lookup"><span data-stu-id="b7781-134">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4.  <span data-ttu-id="b7781-135">Implementar un archivo de configuración de interceptor mediante bm.exe:</span><span class="sxs-lookup"><span data-stu-id="b7781-135">Deploy the interceptor configuration file by using bm.exe:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b7781-136">Tracking\BM.exe implementar-interceptor - filename:\<*icfile.xml*></span><span class="sxs-lookup"><span data-stu-id="b7781-136">Tracking\BM.exe deploy-interceptor -filename:\<*icfile.xml*></span></span>  
  
     <span data-ttu-id="b7781-137">Asegúrese de reemplazar \< *icfile.xml*> con el nombre del archivo de configuración de interceptor que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="b7781-137">Make sure you replace \<*icfile.xml*> with the name of the interceptor configuration file you want to deploy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7781-138">Puede usar el **-Force: True** marca para invalidar los orígenes de eventos existentes con el mismo nombre que los de su archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="b7781-138">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="b7781-139">Si lo hace, asegúrese de hacer la copia de seguridad de la configuración existente mediante el **get-interceptor** comando.</span><span class="sxs-lookup"><span data-stu-id="b7781-139">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="b7781-140">Con la marca -Force:True puede eliminar cualquier configuración de interceptor que haga referencia a los orígenes de eventos que se están anulando.</span><span class="sxs-lookup"><span data-stu-id="b7781-140">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7781-141">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b7781-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="b7781-142">Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7781-142">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
 <span data-ttu-id="b7781-143">Si ya ha implementado la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], la nueva configuración no se cargará hasta el siguiente intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="b7781-143">If you have already deployed your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="b7781-144">Sin embargo, si configura la aplicación y la reinicia, la configuración se selecciona de inmediato.</span><span class="sxs-lookup"><span data-stu-id="b7781-144">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="b7781-145">Adición de usuarios al rol de actividad de BAM adecuado</span><span class="sxs-lookup"><span data-stu-id="b7781-145">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="b7781-146">El marco de trabajo de interceptor de BAM usa roles de SQL Server por actividad para controlar el acceso a las actividades y a la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="b7781-146">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="b7781-147">Debe agregar la cuenta del usuario que ejecuta la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] a la aplicación de BAM adecuada de la Base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b7781-147">You must add the user account running your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to the appropriate BAM activity role(s) in the BAM Primary Import database.</span></span>  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="b7781-148">Configurar la aplicación para cargar el servicio de seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="b7781-148">Configuring the Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="b7781-149">Hay tres escenarios posibles para cargar el servicio de seguimiento de BAM en la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b7781-149">There are three scenarios for loading the BAM tracking service in your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application:</span></span>  
  
-   <span data-ttu-id="b7781-150">Si la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] ya utiliza WorkflowRuntime para cargar una sección de configuración de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], puede agregar información de servicio de seguimiento de BAM a la sección existente.</span><span class="sxs-lookup"><span data-stu-id="b7781-150">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application already uses WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you can added BAM tracking service information to the existing section.</span></span>  
  
-   <span data-ttu-id="b7781-151">Si la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] no utiliza WorkflowRuntime para cargar una sección de configuración de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], tendrá que agregar código para cargar una sección personalizada desde el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-151">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application does not use WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you will have to add code to load a custom section from your application configuration file.</span></span> <span data-ttu-id="b7781-152">Tendrá que crear la sección y agregarle la información del servicio de seguimiento de BAM.</span><span class="sxs-lookup"><span data-stu-id="b7781-152">You will have to create the section and add the BAM tracking service information to it.</span></span>  
  
-   <span data-ttu-id="b7781-153">Si prefiere codificar la configuración, puede utilizar la API de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] para cargar mediante programación el servicio de seguimiento sin un archivo de configuración, o bien cargar la configuración a partir de un origen personalizado.</span><span class="sxs-lookup"><span data-stu-id="b7781-153">If you prefer to hard-code the configuration, you can use the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] API to programmatically load the tracking service without a configuration file, or to load the configuration from a custom source.</span></span>  
  
 <span data-ttu-id="b7781-154">Al configurar la aplicación [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], tenga en cuenta las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="b7781-154">When configuring the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, note the following considerations:</span></span>  
  
-   <span data-ttu-id="b7781-155">El interceptor de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] sólo admite un BamTrackingService por cada WorkflowRuntime.</span><span class="sxs-lookup"><span data-stu-id="b7781-155">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports only one BamTrackingService per one WorkflowRuntime.</span></span>  
  
-   <span data-ttu-id="b7781-156">El interceptor de [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] admite varias instancias de BamTrackingService por cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-156">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports multiple BamTrackingService instances per application domain.</span></span>  
  
    -   <span data-ttu-id="b7781-157">El número N de BamTrackingService se admite para el número N de WorkflowRuntime.</span><span class="sxs-lookup"><span data-stu-id="b7781-157">N number of BamTrackingService is supported for N number of WorkflowRuntime.</span></span>  
  
-   <span data-ttu-id="b7781-158">El interceptor genera una excepción si se utilizan cadenas de conexión distintas para instancias de BamTrackingService independientes en el mismo dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-158">The interceptor raises an exception if different connection strings are used for separate BamTrackingService instances in the same application domain.</span></span>  
  
-   <span data-ttu-id="b7781-159">El interceptor obtiene el valor de intervalo de sondeo de IC de la primera instancia de BamTrackingService que se inicia.</span><span class="sxs-lookup"><span data-stu-id="b7781-159">The interceptor obtains the IC polling interval value from the first BamTrackingService instance that starts.</span></span>  
  
-   <span data-ttu-id="b7781-160">El interceptor detiene el subproceso de sondeo de IC cuando se detiene el último BamTrackingService del dominio de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b7781-160">The interceptor stops the IC polling thread when last BamTrackingService in application domain is stopped</span></span>  
  
 <span data-ttu-id="b7781-161">Para obtener más información sobre WorkflowRuntime y cargar la información de configuración, consulte [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314).</span><span class="sxs-lookup"><span data-stu-id="b7781-161">For more information on WorkflowRuntime and loading configuration information, see [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314).</span></span>  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a><span data-ttu-id="b7781-162">Para configurar el archivo App.config para el servicio de seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="b7781-162">To configure the App.config file for the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="b7781-163">Abra el archivo App.config relacionado con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="b7781-164">Puede utilizar Notepad.exe u otro editor de texto para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="b7781-164">You can use Notepad.exe or another text editor for this task.</span></span>  
  
2.  <span data-ttu-id="b7781-165">Agregue el servicio de seguimiento de BAM insertando la siguiente información de configuración en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="b7781-165">Add the BAM Tracking service by inserting the following configuration information into the App.config file.</span></span> <span data-ttu-id="b7781-166">Debe situarse de forma que sea un elemento secundario del elemento `configuration`.</span><span class="sxs-lookup"><span data-stu-id="b7781-166">It should be positioned so that it is a child of the `configuration` element.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7781-167">El elemento de sección debe corresponder al nombre utilizado por el código de la aplicación al utilizar la clase WorkflowRuntime.</span><span class="sxs-lookup"><span data-stu-id="b7781-167">The section element should correspond to the name used by your application code when using the WorkflowRuntime class.</span></span>  
  
    ```  
    <!-- The element name must match the one expected by WorkflowRuntime in your WF application -->  
    <WorkflowServiceContainer>  
      <Services>  
        <add type="Microsoft.BizTalk.Bam.Interceptors.Workflow.BamTrackingService, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  
       ConnectionString="Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"   
          PollingIntervalSec="5"/>  
        </Services>  
    </WorkflowServiceContainer>  
    ```  
  
3.  <span data-ttu-id="b7781-168">Modificar el **ConnectionString** atributo para que coincida con su entorno.</span><span class="sxs-lookup"><span data-stu-id="b7781-168">Modify the **ConnectionString** attribute to match your environment.</span></span>  
  
4.  <span data-ttu-id="b7781-169">Reinicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7781-169">Restart your application.</span></span>  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a><span data-ttu-id="b7781-170">Para modificar la aplicación para cargar una sección de configuración personalizada</span><span class="sxs-lookup"><span data-stu-id="b7781-170">To modify your application to load a custom configuration section</span></span>  
  
1.  <span data-ttu-id="b7781-171">Abra el proyecto de Windows Workflow Foundation en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7781-171">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b7781-172">Agregue una nueva instancia de BamTrackingService con los parámetros adecuados en la instancia de la aplicación de WorkflowRuntime:</span><span class="sxs-lookup"><span data-stu-id="b7781-172">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  <span data-ttu-id="b7781-173">Vuelva a compilar e implemente la aplicación modificada.</span><span class="sxs-lookup"><span data-stu-id="b7781-173">Recompile and deploy the modified application.</span></span>  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a><span data-ttu-id="b7781-174">Para modificar la aplicación para cargar mediante programación el servicio de seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="b7781-174">To modify your application to programmatically load the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="b7781-175">Abra el proyecto de Windows Workflow Foundation en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7781-175">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b7781-176">Agregue una nueva instancia de BamTrackingService con los parámetros adecuados en la instancia de la aplicación de WorkflowRuntime:</span><span class="sxs-lookup"><span data-stu-id="b7781-176">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     <span data-ttu-id="b7781-177">Puede agregar o quitar parámetros basándose en su entorno específico.</span><span class="sxs-lookup"><span data-stu-id="b7781-177">You can add or remove parameters based on your specific environment.</span></span>  
  
3.  <span data-ttu-id="b7781-178">Vuelva a compilar e implemente la aplicación modificada.</span><span class="sxs-lookup"><span data-stu-id="b7781-178">Recompile and deploy the modified application.</span></span>
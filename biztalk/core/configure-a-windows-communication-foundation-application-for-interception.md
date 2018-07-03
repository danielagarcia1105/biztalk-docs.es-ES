---
title: Cómo configurar una aplicación de Windows Communication Foundation para la intercepción de | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b18790784f58dbdab7f917a73d041f382943d2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988909"
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a><span data-ttu-id="42c1c-102">Cómo configurar una aplicación de Windows Communication Foundation para llevar a cabo una intercepción</span><span class="sxs-lookup"><span data-stu-id="42c1c-102">How to Configure a Windows Communication Foundation Application for Interception</span></span>
<span data-ttu-id="42c1c-103">Debe instalar el software interceptor de BAM y configurar la aplicación para utilizar el servicio de interceptor [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] de BAM antes de comenzar a recopilar los datos de actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="42c1c-103">You must install the BAM interceptor software and configure your application to use the BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="42c1c-104">Se supone que ha instalado correctamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y sus dependencias, y que ha creado al menos un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="42c1c-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  

## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="42c1c-105">Instalar el software de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="42c1c-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="42c1c-106">Antes de configurar la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] para usar el interceptor de BAM para [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], deberá instalar el software Eventos BAM mediante el programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c1c-106">Before you can configure your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="42c1c-107">Para obtener más información sobre cómo instalar el software eventos BAM y registrar los contadores de rendimiento, consulte [instalar el Software eventos BAM](../core/installing-the-bam-eventing-software.md).</span><span class="sxs-lookup"><span data-stu-id="42c1c-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  

## <a name="configuring-a-wcf-application-for-tracking"></a><span data-ttu-id="42c1c-108">Configurar una aplicación de WCF para llevar a cabo un seguimiento</span><span class="sxs-lookup"><span data-stu-id="42c1c-108">Configuring a WCF Application for Tracking</span></span>  
 <span data-ttu-id="42c1c-109">Deben llevarse a cabo cuatro tareas antes de que la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] pueda comenzar a escribir la información de eventos de BAM:</span><span class="sxs-lookup"><span data-stu-id="42c1c-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application can begin writing BAM event information:</span></span>  

- <span data-ttu-id="42c1c-110">Se debe crear un modelo de observación mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de las herramientas de BAM y, a continuación, se implementa mediante la herramienta de línea de comandos del Administrador de BAM (bm.exe).</span><span class="sxs-lookup"><span data-stu-id="42c1c-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="42c1c-111">Debe crearse e implementarse un archivo de configuración de interceptor mediante la herramienta de línea de comandos del administrador de BAM (bm.exe).</span><span class="sxs-lookup"><span data-stu-id="42c1c-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="42c1c-112">El usuario que ejecuta la aplicación host debe ser miembro del escritor de eventos de actividad BAM adecuado (bam_\<actividad\>_EventWriter) roles de SQL Server para habilitar la aplicación leer el interceptor de información de configuración y escribir para las actividades de BAM.</span><span class="sxs-lookup"><span data-stu-id="42c1c-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity\>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  

- <span data-ttu-id="42c1c-113">Debe modificar el archivo App.config para el servidor y la aplicación cliente para cargar el servicio de seguimiento de BAM.</span><span class="sxs-lookup"><span data-stu-id="42c1c-113">The App.config file for the server and client application must be modified to load the BAM tracking service.</span></span> <span data-ttu-id="42c1c-114">Una vez modificado el archivo App.config, debe reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42c1c-114">After the App.config file has been modified, the application must be restarted.</span></span>  

  <span data-ttu-id="42c1c-115">Los eventos comenzarán a aparecer en la base de datos de BAM de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] únicamente después de completar estas tareas correctamente.</span><span class="sxs-lookup"><span data-stu-id="42c1c-115">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  

### <a name="deploying-an-observation-model"></a><span data-ttu-id="42c1c-116">Implementar modelos de observación</span><span class="sxs-lookup"><span data-stu-id="42c1c-116">Deploying an Observation Model</span></span>  
 <span data-ttu-id="42c1c-117">Debe haberse implementado un modelo de observación antes de implementar un archivo de configuración de interceptor o capturar actividades de BAM en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42c1c-117">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  

##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="42c1c-118">Para implementar un modelo de observación mediante bm.exe</span><span class="sxs-lookup"><span data-stu-id="42c1c-118">To deploy an observation model by using bm.exe</span></span>  

1. <span data-ttu-id="42c1c-119">Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="42c1c-119">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="42c1c-120">Tipo **cmd** en el **abierto** campo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42c1c-120">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="42c1c-121">Utilice el comando de cambio de directorio para mover el directorio que contiene el modelo de observación que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-121">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="42c1c-122">Por ejemplo, **c:\businessprocess\Orders cd**.</span><span class="sxs-lookup"><span data-stu-id="42c1c-122">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="42c1c-123">Implemente un modelo de observación mediante bm.exe:</span><span class="sxs-lookup"><span data-stu-id="42c1c-123">Deploy the observation model using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="42c1c-124">Tracking\bm.exe implementar-all - Definitionfile:\<*definitionfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="42c1c-124">Tracking\bm.exe deploy-all -Definitionfile:\<*definitionfile.xml*\></span></span>  

    <span data-ttu-id="42c1c-125">Asegúrese de reemplazar \< *definitionfile.xml* \> con el nombre del archivo del modelo de observación que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-125">Make sure you replace \<*definitionfile.xml*\> with the name of the observation model file you want to deploy.</span></span> <span data-ttu-id="42c1c-126">Para obtener más opciones, consulte [comandos de administración de Interceptor](../core/interceptor-management-commands.md).</span><span class="sxs-lookup"><span data-stu-id="42c1c-126">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-127">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="42c1c-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="42c1c-128">Tipo **Exit** y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="42c1c-128">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="42c1c-129">Implementar un archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="42c1c-129">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="42c1c-130">Debe implementar un archivo de configuración de interceptor antes de que la aplicación pueda capturar actividades de BAM.</span><span class="sxs-lookup"><span data-stu-id="42c1c-130">You must deploy an interceptor configuration file before your application will be able to capture BAM activities.</span></span>  

##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="42c1c-131">Para implementar un archivo de configuración de interceptor mediante bm.exe</span><span class="sxs-lookup"><span data-stu-id="42c1c-131">To deploy an interceptor configuration file by using bm.exe</span></span>  

1. <span data-ttu-id="42c1c-132">Haga clic en **iniciar** y, a continuación, haga clic en **ejecutar** para abrir el símbolo del sistema de Windows.</span><span class="sxs-lookup"><span data-stu-id="42c1c-132">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="42c1c-133">Tipo **cmd** en el **abierto** campo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42c1c-133">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="42c1c-134">Utilice el comando de cambio de directorio para mover el directorio que contiene el archivo de configuración de interceptor que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-134">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="42c1c-135">Por ejemplo, **c:\businessprocess\Orders cd**.</span><span class="sxs-lookup"><span data-stu-id="42c1c-135">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="42c1c-136">Implementar un archivo de configuración de interceptor mediante bm.exe:</span><span class="sxs-lookup"><span data-stu-id="42c1c-136">Deploy the interceptor configuration file by using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="42c1c-137">Tracking\bm.exe implementar-interceptor - Filename:\<*icfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="42c1c-137">Tracking\bm.exe deploy-interceptor -Filename:\<*icfile.xml*\></span></span>  

    <span data-ttu-id="42c1c-138">Asegúrese de reemplazar \< *icfile.xml* \> con el nombre del archivo de configuración del interceptor que desee implementar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-138">Make sure you replace \<*icfile.xml*\> with the name of the interceptor configuration file you want to deploy.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-139">Puede usar el **-Force: True** marca para invalidar los orígenes de eventos existentes con el mismo nombre que en el archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="42c1c-139">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="42c1c-140">Si lo hace, asegúrese de que la copia de seguridad de la configuración existente mediante el uso de la **get-interceptor** comando.</span><span class="sxs-lookup"><span data-stu-id="42c1c-140">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="42c1c-141">Con la marca -Force:True puede eliminar cualquier configuración de interceptor que haga referencia a los orígenes de eventos que se están anulando.</span><span class="sxs-lookup"><span data-stu-id="42c1c-141">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-142">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="42c1c-142">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="42c1c-143">Tipo **Exit** y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="42c1c-143">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

   <span data-ttu-id="42c1c-144">Si ya ha implementado la aplicación [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], la nueva configuración no se cargará hasta el siguiente intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="42c1c-144">If you have already deployed your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="42c1c-145">Sin embargo, si configura la aplicación y la reinicia, la configuración se selecciona de inmediato.</span><span class="sxs-lookup"><span data-stu-id="42c1c-145">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  

### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="42c1c-146">Adición de usuarios al rol de actividad de BAM adecuado</span><span class="sxs-lookup"><span data-stu-id="42c1c-146">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="42c1c-147">El marco de trabajo de interceptor de BAM usa roles de SQL Server por actividad para controlar el acceso a las actividades y a la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="42c1c-147">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="42c1c-148">Debe agregar la cuenta del usuario que ejecuta la aplicación WCF a los roles de actividad de BAM correspondientes en la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="42c1c-148">You must add the user account running your WCF application to the appropriate BAM activity role(s) in the BAMPrimaryImport database.</span></span>  

### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="42c1c-149">Configurar la aplicación de Windows Communication Foundation para cargar el Servicio de seguimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="42c1c-149">Configuring the Windows Communication Foundation Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="42c1c-150">Configure la aplicación para cargar el Servicio de seguimiento de BAM mediante la agregación de unas cuantas líneas al archivo App.config para la aplicación servidor o cliente.</span><span class="sxs-lookup"><span data-stu-id="42c1c-150">You configure your application to load the BAM tracking service by adding a few lines to the App.config file for your server or client application.</span></span>  

 <span data-ttu-id="42c1c-151">Para habilitar el seguimiento de BAM en su servidor o aplicación cliente de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], necesitará modificar el archivo de configuración App.config para incluir un comportamiento de extremo y una extensión de comportamiento adicionales y agregar un atributo de configuración de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="42c1c-151">To enable BAM tracking in your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server or client application, you will need to modify the App.config configuration file to include an additional endpoint behavior and behavior extension and add a behavior configuration attribute.</span></span> <span data-ttu-id="42c1c-152">Los formatos del servicio y las plantillas de clientes son similares.</span><span class="sxs-lookup"><span data-stu-id="42c1c-152">The formats of the service and client templates are similar.</span></span>  

 <span data-ttu-id="42c1c-153">Al configurar la aplicación de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], tenga en cuenta lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="42c1c-153">When configuring the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, note the following.</span></span> <span data-ttu-id="42c1c-154">Si hay más de un comportamiento de extremo de BAM definido en el archivo App.config para la misma aplicación, es decir, el mismo cliente o servicio, BAM llevará a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="42c1c-154">If there is more than one BAM endpoint behaviors defined in the App.config for the same application, that is, the same client or service, BAM will take the following actions.</span></span>  

-   <span data-ttu-id="42c1c-155">Si las cadenas de conexión son diferentes, BAM producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="42c1c-155">If the connection strings differ, BAM will raise and exception.</span></span>  

-   <span data-ttu-id="42c1c-156">Si sólo difiere el intervalo de sondeo, BAM seleccionará uno y lo moverá.</span><span class="sxs-lookup"><span data-stu-id="42c1c-156">If only the polling interval differs, BAM will select one and move on.</span></span> <span data-ttu-id="42c1c-157">Durante el tiempo de diseño, no es posible determinar cuál se va a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-157">It is not possible at design time to determine which one will be selected.</span></span>  

> [!NOTE]
>  <span data-ttu-id="42c1c-158">Si las cadenas de conexión son iguales, lo que significa que hacen referencia al mismo equipo, el procesamiento de BAM tendrá lugar con normalidad.</span><span class="sxs-lookup"><span data-stu-id="42c1c-158">If the connection strings are the same, meaning that they reference the same computer, BAM processing will proceed normally.</span></span>  

 <span data-ttu-id="42c1c-159">La siguiente plantilla de App.config de ejemplo está configurada para una aplicación de servidor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c1c-159">The following sample App.config template is configured for a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server application.</span></span> <span data-ttu-id="42c1c-160">Define un extremo que usa un comportamiento personalizado "bamEndpointBehavior", configurado para usar el interceptor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c1c-160">It defines an endpoint that uses a custom behavior "bamEndpointBehavior" that is configured to use the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor.</span></span>  

```  
<system.serviceModel>  
  <services>  
    <service name="Service.CreditCardAuthorization">  
      <!-- The endpoint will use the "bamEndpointBehavior" -->   
      <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    </service>  
  </services>  
  <bindings>  
    <wsDualHttpBinding>  
      <binding name="wsDualHttpBinding_ICreditCardAuthorization" transactionFlow="true" />  
    </wsDualHttpBinding>  
  </bindings>  
  <behaviors>  
    <endpointBehaviors>  
      <!-- Define a new behavior named "bamEndpointBehavior" -->  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <extensions>  
    <behaviorExtensions>  
      <!-- Define a new enpoint behavior extension using WCF interceptor -->  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
  </extensions>  
</system.serviceModel>  
```  

 <span data-ttu-id="42c1c-161">Antes de usar su propio archivo App.config, tendrá que realizar algunos cambios pequeños en esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="42c1c-161">You will need to make small changes to this template before using it in your own App.config file.</span></span>  

##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a><span data-ttu-id="42c1c-162">Para usar esta plantilla en su archivo App.config del Servicio WCF</span><span class="sxs-lookup"><span data-stu-id="42c1c-162">To use this template in your WCF service App.config file</span></span>  

1. <span data-ttu-id="42c1c-163">Abra el archivo App.config relacionado con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42c1c-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="42c1c-164">Puede utilizar Notepad.exe u otro editor de texto para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="42c1c-164">You can use Notepad.exe or another text editor for this task.</span></span>  

2. <span data-ttu-id="42c1c-165">Agregue la extensión de comportamiento BamEndpointBehavior de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] al elemento de `extensions` mediante el uso de los siguientes XML:</span><span class="sxs-lookup"><span data-stu-id="42c1c-165">Add the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] BamEndpointBehavior behavior extension to the `extensions` element by using the following XML:</span></span>  

   ```  
   <behaviorExtensions>  
     <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
   </behaviorExtensions>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-166">La extensión de comportamiento se denomina "BamEndpointBehaviorExtension", y puede modificarse según sea necesario para que se adapte a su entorno.</span><span class="sxs-lookup"><span data-stu-id="42c1c-166">The behavior extension is named "BamEndpointBehaviorExtension" and can be changed as needed to suit your environment.</span></span>  

3. <span data-ttu-id="42c1c-167">Agregue un nuevo comportamiento de extremo que use la nueva extensión de comportamiento al elemento `behaviors` mediante el uso de los siguientes XML.</span><span class="sxs-lookup"><span data-stu-id="42c1c-167">Add a new endpoint behavior that uses the new behavior extension to the `behaviors` element by using the following XML.</span></span> <span data-ttu-id="42c1c-168">La extensión de comportamiento proporciona una cadena de conexión y un intervalo de sondeo en segundos.</span><span class="sxs-lookup"><span data-stu-id="42c1c-168">The behavior extension provides a connection string and polling interval in seconds.</span></span>  

   ```  
   <endpointBehaviors>  
     <behavior name="bamEndpointBehavior">  
       <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
     </behavior>  
   </endpointBehaviors>  
   ```  

    <span data-ttu-id="42c1c-169">Sustituya el origen de datos por el nombre del equipo que aloje la base de datos BamPrimaryImport en su entorno.</span><span class="sxs-lookup"><span data-stu-id="42c1c-169">Replace the Data Source with the name of the computer hosting the BamPrimaryImport database in your environment.</span></span> <span data-ttu-id="42c1c-170">Modifique el intervalo de sondeo para que se adapte a sus necesidades; un número alto significa que el interceptor de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] tardará más tiempo en detectar los cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="42c1c-170">Change the polling interval to suit your requirements; a higher number means that the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor will take longer to detect configuration changes.</span></span> <span data-ttu-id="42c1c-171">Si ha cambiado el nombre de la extensión de comportamiento, úselo para sustituir "BamEndpointBehaviorExtension".</span><span class="sxs-lookup"><span data-stu-id="42c1c-171">If you changed the name of the behavior extension, use it to replace "BamEndpointBehaviorExtension".</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-172">El nombre del comportamiento es "bamEndpointBehavior", y puede modificarse para que se adapte a su entorno.</span><span class="sxs-lookup"><span data-stu-id="42c1c-172">The behavior name is "bamEndpointBehavior" and can be changed to suit your environment.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-173">En la especificación de `ConnectionString`, evite el uso de una combinación de nombre de usuario/contraseña en texto sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-173">Avoid using a cleartext username/password combination when specifying `ConnectionString`.</span></span> <span data-ttu-id="42c1c-174">Si lo usa, puede poner en peligro su servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="42c1c-174">Doing so may compromise your database server.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-175">Debe especificar un `PollingIntervalSec` superior o igual a 5 (segundos).</span><span class="sxs-lookup"><span data-stu-id="42c1c-175">You must specify an `PollingIntervalSec` greater than or equal to 5 (seconds).</span></span> <span data-ttu-id="42c1c-176">Si especifica un valor inferior u omite el elemento `PollingIntervalSec`, se producirá un error y la intercepción no se configurará.</span><span class="sxs-lookup"><span data-stu-id="42c1c-176">If you specify a lower value or omit the `PollingIntervalSec` element, an error will be raised and interception will not be configured.</span></span>  

4. <span data-ttu-id="42c1c-177">Agregue el atributo `behaviorConfiguration` al extremo del que va a realizar un seguimiento y proporcione el nombre del nuevo comportamiento:</span><span class="sxs-lookup"><span data-stu-id="42c1c-177">Add the `behaviorConfiguration` attribute to the endpoint you will be tracking and provide the name of the new behavior:</span></span>  

   ```  
   <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="42c1c-178">Si ha usado un nombre de comportamiento diferente, proporciónelo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="42c1c-178">If you used a different behavior name, supply it instead.</span></span>  

    <span data-ttu-id="42c1c-179">Puede aplicar la configuración de comportamiento a varios extremos.</span><span class="sxs-lookup"><span data-stu-id="42c1c-179">You can apply the behavior configuration to multiple endpoints.</span></span>  

5. <span data-ttu-id="42c1c-180">Guarde el archivo App.config modificado y reinicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42c1c-180">Save the modified App.config file and restart your application.</span></span>

---
title: Configurar la FileAct e interactuar adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2bc3aa739bf6914ea9943d84d58d44b1506323
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="ba1ef-102">Configurar la FileAct e interactuar adaptador</span><span class="sxs-lookup"><span data-stu-id="ba1ef-102">Configure the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="ba1ef-103">Configurar los diferentes artefactos utilizados por el [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-103">Configure the different artifacts used by the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] runtime.</span></span> 

  
## <a name="prerequisites"></a><span data-ttu-id="ba1ef-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ba1ef-104">Prerequisites</span></span>  
   
-   <span data-ttu-id="ba1ef-105">Instalar el[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba1ef-105">Install the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span></span>
  
-   <span data-ttu-id="ba1ef-106">Inicie sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="ba1ef-106">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>
  
-   <span data-ttu-id="ba1ef-107">Confirme que está ejecutando SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba1ef-107">Confirm SQL Server is running</span></span>
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="ba1ef-108">Paso 1: Configurar el adaptador de FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="ba1ef-108">Step 1: Configure the FileAct and InterAct adapter</span></span>  
  
1.  <span data-ttu-id="ba1ef-109">En el **FileAct de BizTalk de Microsoft e interactuar configuración del adaptador** asistente, vaya a **Introducción**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-109">In the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard, go to **Overview**.</span></span> <span data-ttu-id="ba1ef-110">En el panel izquierdo, seleccione **en tiempo de ejecución** para configurar los componentes en tiempo de ejecución de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-110">In the left pane, select **Runtime** to configure the runtime components of the adapters.</span></span>  
  
2.  <span data-ttu-id="ba1ef-111">En **configuración en tiempo de ejecución**, en **cuenta**, seleccione los puntos suspensivos […] para escribir el COM más la configuración para el modo de almacenamiento y reenvío.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-111">In **Runtime Configuration**, under **Account**, select the ellipsis […] to enter the COM plus configuration for the Store and Forward mode.</span></span>  
  
3.  <span data-ttu-id="ba1ef-112">En **las credenciales de usuario**, escriba el nombre de usuario (en el *ombre* formato) y una contraseña para la cuenta utilizada en COM además de la configuración.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-112">In **User Credentials**, enter the user name (in the *domain\user name* format) and password for the account used in the COM plus configuration.</span></span> <span data-ttu-id="ba1ef-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-113">Select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba1ef-114">A **las credenciales de usuario** advertencia aparece si la cuenta que especificó tiene privilegios más elevados que se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-114">A **User Credentials** warning appears if the account you entered has higher privileges than are recommended.</span></span> <span data-ttu-id="ba1ef-115">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-115">Select **Yes** to continue.</span></span>
  
4.  <span data-ttu-id="ba1ef-116">Seleccione **aplicar configuración** para aplicar el COM más la configuración para el adaptador de interactuar and FileAct.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-116">Select **Apply configuration** to apply the COM plus configuration to the FileAct and InterAct Adapter.</span></span>  
  
5.  <span data-ttu-id="ba1ef-117">En el **resumen**, revise y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-117">In the **Summary**, review, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="ba1ef-118">Cuando se completa la configuración, revise la lista de componentes.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-118">When the configuration completes, review the list of components.</span></span> <span data-ttu-id="ba1ef-119">Una marca de verificación significa que el componente está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-119">A check mark means that the component is configured successfully.</span></span> <span data-ttu-id="ba1ef-120">Una "X" significa que hay un problema con ese componente.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-120">An "X" means that there is a problem with that component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba1ef-121">Use la **archivo de registro** vínculo para ver los eventos de configuración.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-121">Use the **Logfile** link to view the configuration events.</span></span>  
  
7.  <span data-ttu-id="ba1ef-122">Seleccione **finalizar** para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-122">Select **Finish** to complete the configuration.</span></span> <span data-ttu-id="ba1ef-123">El **Introducción** muestra el estado actual de la configuración de los componentes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-123">The **Overview** shows the current configuration status for the Runtime components.</span></span>  

<span data-ttu-id="ba1ef-124">A continuación, cree el host y las instancias de host para ejecutar estos adaptadores.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-124">Next, create the host and host instances to run these adapters.</span></span>

## <a name="step-2-create-the-host-and-host-instances"></a><span data-ttu-id="ba1ef-125">Paso 2: Crear el host e instancias de host</span><span class="sxs-lookup"><span data-stu-id="ba1ef-125">Step 2: Create the host and host instances</span></span>

<span data-ttu-id="ba1ef-126">Le recomendamos que cree un host dedicado para el adaptador de FileAct y un host independiente dedicado para el adaptador de InterAct.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-126">We recommend that you create a dedicated host for the FileAct adapter and a separate dedicated host for the InterAct adapter.</span></span> <span data-ttu-id="ba1ef-127">Para cada adaptador, cree al menos una instancia de host.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-127">For each adapter, create at least one host instance.</span></span>  

<span data-ttu-id="ba1ef-128">[Administración de Hosts de BizTalk y las instancias de Host](../../core/managing-biztalk-hosts-and-host-instances.md) enumeran los pasos para crear hosts e instancias de host.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-128">[Managing BizTalk Hosts and Host Instances](../../core/managing-biztalk-hosts-and-host-instances.md) list the steps to create hosts and host instances.</span></span> 

<span data-ttu-id="ba1ef-129">Una vez creado, el siguiente paso es agregar el controlador de envío y usar al asociado de mensaje de cliente que creó en la puerta de enlace de Alliance de SWIFT (SAG).</span><span class="sxs-lookup"><span data-stu-id="ba1ef-129">Once created, the next step is to add the send handler, and use the Client Message Partner you created in the SWIFT Alliance Gateway (SAG).</span></span>

## <a name="step-3-create-the-send-handler"></a><span data-ttu-id="ba1ef-130">Paso 3: Crear el controlador de envío</span><span class="sxs-lookup"><span data-stu-id="ba1ef-130">Step 3: Create the send handler</span></span>

<span data-ttu-id="ba1ef-131">Puede utilizar el FileAct y InterAct enviar propiedades del controlador como el envío valores de configuración de puerto, si no se establecen las propiedades en el FileAct individual o puerto de envío de interacción.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-131">You use the FileAct and InterAct send handler properties as the send port configuration values, if the properties are not set on the individual FileAct or InterAct send port.</span></span> 
  
1.  <span data-ttu-id="ba1ef-132">En el **administración de BizTalk Server** de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **deconfiguracióndeplataforma**y, a continuación, expanda **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-132">In the **BizTalk Server Administration** console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="ba1ef-133">Seleccione el **FileAct** o **InterAct** adaptador.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-133">Select the **FileAct** or **InterAct** adapter.</span></span> <span data-ttu-id="ba1ef-134">En el panel derecho, haga doble clic en el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-134">In the right pane, double-click the send handler.</span></span>  
  
3.  <span data-ttu-id="ba1ef-135">En el **nombre de Host** lista desplegable, seleccione el host que creó en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-135">In the **Host name** drop-down list, select the host you created in the previous section.</span></span> <span data-ttu-id="ba1ef-136">A continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-136">Then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="ba1ef-137">En el **propiedades de transporte**, seleccione la **argumento** propiedad y escriba el siguiente argumento como:</span><span class="sxs-lookup"><span data-stu-id="ba1ef-137">In the **Transport Properties**, select the **Argument** property, and enter the following argument as:</span></span>  
  
     `-SagMessagePartner <Client Message Partner created in SAG\>`
  
    > [!NOTE]
    >  <span data-ttu-id="ba1ef-138">Reemplace <`Client Message Partner created in SAG`> con el nombre del asociado de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-138">Replace <`Client Message Partner created in SAG`> with the name of the client message partner.</span></span> <span data-ttu-id="ba1ef-139">Deje los valores predeterminados para el modo de cifrado, modo de FACrypto y propiedades LogMessages.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-139">Leave the default values for the Crypto Mode, FACrypto Mode, and LogMessages properties.</span></span>  
  
5.  <span data-ttu-id="ba1ef-140">Seleccione **Aceptar** para guardar los cambios y, a continuación, cierre la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-140">Select **OK** to save your changes, and then to close the properties window.</span></span> 
  
6.  <span data-ttu-id="ba1ef-141">En **configuración de plataforma**, seleccione **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-141">Under **Platform Settings**, select **Host Instances**.</span></span>  
  
7. <span data-ttu-id="ba1ef-142">Reinicie las instancias de host:</span><span class="sxs-lookup"><span data-stu-id="ba1ef-142">Restart the host instances:</span></span> 

  - <span data-ttu-id="ba1ef-143">Haga clic en la instancia de host de FileAct y **reiniciar**</span><span class="sxs-lookup"><span data-stu-id="ba1ef-143">Right-click the FileAct host instance, and **Restart**</span></span>
  - <span data-ttu-id="ba1ef-144">Haga clic en la instancia de host interactuar y **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-144">Right-click the InterAct host instance, and **Restart**.</span></span>  

<span data-ttu-id="ba1ef-145">A continuación, escriba los asociados de mensaje de servidor en el paramfile SWIFTNet para habilitar la FileAct y adaptadores de recepción interactuar.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-145">Next, enter the server message partners in the SWIFTNet paramfile to enable the FileAct and InterAct receive adapters.</span></span>
  
## <a name="step-4-configure-the-swiftnet-param-file"></a><span data-ttu-id="ba1ef-146">Paso 4: Configurar el archivo de param SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="ba1ef-146">Step 4: Configure the SWIFTNet param file</span></span>

<span data-ttu-id="ba1ef-147">Para habilitar la FileAct e InterAct adaptadores de recepción para inicializar con los valores, el mensaje del servidor socios que creó en SAG deben especificarse en el paramfile SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-147">To enable the FileAct and InterAct receive adapters to initialize with the values, the Server message partners created in SAG must be entered in the SWIFTNet paramfile.</span></span> <span data-ttu-id="ba1ef-148">El paramfile normalmente se encuentra en `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-148">The paramfile is typically located in `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`.</span></span> <span data-ttu-id="ba1ef-149">Después de configurar la paramfile, iniciar **SnlReceiver.exe**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-149">After you configure the paramfile, start **SnlReceiver.exe**.</span></span>  
  
1. <span data-ttu-id="ba1ef-150">Abra la **SWIFTNet paramfile**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-150">Open the **SWIFTNet paramfile**.</span></span> <span data-ttu-id="ba1ef-151">En la ubicación marcada con "***" agregue lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-151">In the location marked with "***" add the following.</span></span> <span data-ttu-id="ba1ef-152">Tenga en cuenta que la `AdapterType` valor puede ser `Interact` o `Fileact`.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-152">Note that the `AdapterType` value can be `Interact` or `Fileact`.</span></span>  
  
     ```spawn "snlreceiver -SagMessagePartner <Server MessagePartnerName\> -AdapterMode <AdapterType\>"```  
       
  
   ```  
    username:snlowner  
    subsystem_name:SampleSubsystem  
    #subsystem_group: SampleSubsystem  
    #subsystem_dependency:Support,Swarm  
    subsystem_nature:critical  
    subsystem_start:  
    ***  
    *END  
    subsystem_stop:  
    *KILL9:snlreceiver  
    *END  
    subsystem_status:  
    *NB:1:snlreceiver  
    *END  
    start_event:SNL001:subsystem SampleSubsystem is up  
    stop_event:SNL002:subsystem SampleSubsystem is down  
   ```  
  
   > [!NOTE]
    >  <span data-ttu-id="ba1ef-153">Antes de empezar SNLreceiver, habilitar los puertos de recepción para el adaptador que usa (FileAct o que interactúen).</span><span class="sxs-lookup"><span data-stu-id="ba1ef-153">Before you start SNLreceiver, enable the receive ports for the adapter you are using (FileAct or InterAct).</span></span>  
  
2. <span data-ttu-id="ba1ef-154">Iniciar y detener SnlReceiver.exe:</span><span class="sxs-lookup"><span data-stu-id="ba1ef-154">Start and stop SnlReceiver.exe:</span></span>

    1.  <span data-ttu-id="ba1ef-155">En el escritorio, seleccione la **remota (API)** icono para abrir el símbolo del sistema de remota (API).</span><span class="sxs-lookup"><span data-stu-id="ba1ef-155">On the desktop, select the **Remote API** icon to open the Remote API command prompt.</span></span>  
  
    2.  <span data-ttu-id="ba1ef-156">En el símbolo del sistema, escriba `Swiftnet start`.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-156">At the command prompt, type `Swiftnet start`.</span></span> <span data-ttu-id="ba1ef-157">Presione ENTRAR para iniciar SnlReceiver.exe.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-157">Select ENTER to start SnlReceiver.exe.</span></span>  
  
    3.  <span data-ttu-id="ba1ef-158">En el símbolo del sistema, escriba `Swiftnet stop`.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-158">At the command prompt, type `Swiftnet stop`.</span></span> <span data-ttu-id="ba1ef-159">Presione ENTRAR para detener SnlReceiver.exe.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-159">Select ENTER to stop SnlReceiver.exe.</span></span>  

  
<span data-ttu-id="ba1ef-160">A continuación, actualice el archivo **autoexec.bat** para establecer las variables de entorno de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-160">Next, update the file **autoexec.bat** to set the SWIFT environment variables.</span></span>

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a><span data-ttu-id="ba1ef-161">Paso 5: Actualizar archivos autoexec.bat para configurar los adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="ba1ef-161">Step 5: Update autoexec.bat to configure the receive adapters</span></span>

<span data-ttu-id="ba1ef-162">Actualización de la **autoexec.bat** archivo para establecer las variables de entorno de SWIFT en el equipo donde instaló el [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] adaptadores de recepción.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-162">Update the **autoexec.bat** file to set the SWIFT environment variables on the computer where you installed the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] receive adapters.</span></span> <span data-ttu-id="ba1ef-163">Las variables de entorno se generan a partir del sistema que tiene el adaptador de recepción que se instalan en la ruta de acceso `c:\SWIFTAlliance` con una instancia del adaptador de recepción denominado **ar1**.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-163">The environment variables are generated from the system that has the receive adapter installed in the path `c:\SWIFTAlliance` with an instance of the receive adapter named **Ra1**.</span></span> <span data-ttu-id="ba1ef-164">Actualizar las variables de entorno SWIFT correctamente para la configuración.</span><span class="sxs-lookup"><span data-stu-id="ba1ef-164">Update the SWIFT environment variables appropriately for your configuration.</span></span>  
  
 <span data-ttu-id="ba1ef-165">El siguiente es un ejemplo del archivo autoexe.bat:</span><span class="sxs-lookup"><span data-stu-id="ba1ef-165">The following is a sample of the autoexe.bat file:</span></span>
  
```  
SET COMPUTERNAME=<Machine Name>  
SET GENLOG_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET GENUTIL_DIR=C:\SWIFTAlliance\RA\bin  
SET HOMEDRIVE=C:  
SET LOGONSERVER=\\SERVERNAME  
SET OSA_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET OSA_INSTANCE=Ra1  
SET PKIEXECDIR=C:\SWIFTAlliance\RA  
SET SAGRA_HOME=C:\SWIFTAlliance\RA  
SET SESSIONNAME=RDP-Tcp#1  
SET SLP_ENV=DEFAULT  
SET SLP_FILE=server.slp  
SET SNL_DOMAIN_NAME=Ra1  
SET SPK_DATA_DIR=C:\SWIFTAlliance\RA\data\pki  
SET SWNET_BIN_PATH=C:\SWIFTAlliance\RA\Ra1\bin  
SET SWNET_CFG_PATH=C:\SWIFTAlliance\RA\Ra1\cfg  
SET SWNET_HOME=C:\SWIFTAlliance\RA  
SET SWNET_HOST=HOSTNAME  
SET SWNET_INST=Ra1  
SET SWNET_LOG_PATH=C:\SWIFTAlliance\RA\Ra1\log  
SET SWNET_SLP_PATH=C:\SWIFTAlliance\RA\data\  
SET SWNET_VERSION=5.0.20  
SET SWTRACE=C:\SWIFTAlliance\RA\Ra1\log  
SET Path=%PATH%;C:\SWIFTAlliance\RA\bin  
SET Path=%PATH%;C:\SWIFTAlliance\RA\lib  
  
```  
  
## <a name="see-some-examples"></a><span data-ttu-id="ba1ef-166">Se muestran algunos ejemplos</span><span class="sxs-lookup"><span data-stu-id="ba1ef-166">See some examples</span></span>
<span data-ttu-id="ba1ef-167">Para obtener ejemplos de mensajes de FileAct e InterAct, consulte [interactuar de ejemplo y los mensajes de FileAct](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ba1ef-167">For examples of FileAct and InterAct messages, see [Sample InterAct and FileAct Messages](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1ef-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba1ef-168">See Also</span></span>  

[<span data-ttu-id="ba1ef-169">Instalar los adaptadores FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="ba1ef-169">Install the FileAct and InterAct Adapter</span></span>](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="ba1ef-170">Desinstalar o reparar el adaptador de FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="ba1ef-170">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="ba1ef-171">Leer los problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="ba1ef-171">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)

---
title: "Solución de problemas y problemas conocidos con el Acelerador de RosettaNet de BizTalk (BTARN) se instalación en el servidor BizTalk Server | Documentos de Microsoft\""
description: "Recomendaciones para la instalación de SQL, la cuenta de servicio para las instancias de host y los errores conocidos con la instalación de BTARN en BizTalk Server"
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdca89c1a7a4ed3834103776f9f28c8631c5de0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a><span data-ttu-id="b86e7-103">Solucionar problemas de la instalación y consulte los problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="b86e7-103">Troubleshoot the installation and see the known install issues</span></span>

  
## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a><span data-ttu-id="b86e7-104">No instale SQL Server en el equipo del controlador de dominio</span><span class="sxs-lookup"><span data-stu-id="b86e7-104">Do not install SQL Server on the domain controller computer</span></span>  
 <span data-ttu-id="b86e7-105">Si instala a SQL Server en el mismo equipo que el equipo de controlador de dominio, devuelve el siguiente mensaje de error cuando intenta crear los puertos de envío SQL:</span><span class="sxs-lookup"><span data-stu-id="b86e7-105">If you install SQL Server on the same computer as your domain controller computer, it returns the following error message when it is trying to create the SQL send ports:</span></span>  
  
```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  

```
  
> [!IMPORTANT]
>  <span data-ttu-id="b86e7-106">No instale a SQL Server en el equipo del controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="b86e7-106">Do not install SQL Server on the domain controller computer.</span></span>  
  
## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a><span data-ttu-id="b86e7-107">La cuenta de servicio para los grupos de aplicaciones debe ser la misma que la cuenta de servicio para las instancias de host y de host aislado</span><span class="sxs-lookup"><span data-stu-id="b86e7-107">Service account for the application pools must be the same as the service account for the Isolated Host and Host instances</span></span>  
 <span data-ttu-id="b86e7-108">Si la cuenta de servicio establecidos para los grupos de aplicación de BTARN es diferente de la cuenta de Host aislado, BTARN no procesa correctamente los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="b86e7-108">If the service account set for the BTARN application pools is different from the Isolated Host account, BTARN does not process incoming messages correctly.</span></span> <span data-ttu-id="b86e7-109">Cuando la página .aspx de recepción llama a la canalización, la canalización no tiene acceso a los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="b86e7-109">When the receive .aspx page calls the pipeline, the pipeline does not have access to the appropriate certificates.</span></span> <span data-ttu-id="b86e7-110">Por lo tanto, no descifrar el mensaje entrante ni validar la firma.</span><span class="sxs-lookup"><span data-stu-id="b86e7-110">Therefore, it does not decrypt the incoming message or validate the signature.</span></span> <span data-ttu-id="b86e7-111">Además, no podrá tener acceso a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b86e7-111">Also, it won't be able to access the MessageBox database.</span></span>  
  

## <a name="known-install-issues"></a><span data-ttu-id="b86e7-112">Problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="b86e7-112">Known install issues</span></span>

  
### <a name="btarn-http-front-end-feature-configuration-fails"></a><span data-ttu-id="b86e7-113">Se produce un error en la configuración de la característica de Front-End de BTARN HTTP</span><span class="sxs-lookup"><span data-stu-id="b86e7-113">BTARN HTTP Front End Feature configuration fails</span></span>  
 <span data-ttu-id="b86e7-114">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b86e7-114">**Problem**</span></span>  
  
 <span data-ttu-id="b86e7-115">Si lleva a cabo una instalación personalizada para instalar solo la característica Front-end HTTP de BTARN, la configuración de BTARN puede dar error después de completarse la instalación con el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="b86e7-115">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail with the following error after setup has completed:</span></span> 

`Failed to create object for feature: WebApp`  
  
 <span data-ttu-id="b86e7-116">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b86e7-116">**Resolution**</span></span>  
  
<span data-ttu-id="b86e7-117">Manualmente, copie los archivos y vuelva a configurar:</span><span class="sxs-lookup"><span data-stu-id="b86e7-117">Manually copy files and reconfigure:</span></span> 
  
1.  <span data-ttu-id="b86e7-118">Copie los dos archivos siguientes desde un equipo de servidor BizTalk Server en el equipo en el que haya instalado la característica de Front-End de HTTP de BTARN:</span><span class="sxs-lookup"><span data-stu-id="b86e7-118">Copy the following two files from an BizTalk Server computer to the computer on which you installed the BTARN HTTP Front End feature:</span></span>
  
    -   <span data-ttu-id="b86e7-119">Microsoft.VC80.ATL.manifest</span><span class="sxs-lookup"><span data-stu-id="b86e7-119">Microsoft.VC80.ATL.manifest</span></span>  
  
    -   <span data-ttu-id="b86e7-120">atl80.dll</span><span class="sxs-lookup"><span data-stu-id="b86e7-120">atl80.dll</span></span>  
  
     <span data-ttu-id="b86e7-121">Si Visual Studio está instalado en el mismo equipo que BizTalk Server, la carpeta de origen de los dos archivos es <*unidad*>: \Program Visual Studio < versión\>\VC\redist\x86\Microsoft.VC100.ATL .</span><span class="sxs-lookup"><span data-stu-id="b86e7-121">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is <*drive*>:\Program Files\Microsoft Visual Studio <version\>\VC\redist\x86\Microsoft.VC100.ATL.</span></span>  
  
     <span data-ttu-id="b86e7-122">Si Visual Studio no está instalado en el mismo equipo de BizTalk Server, la carpeta de origen de los dos archivos se encuentra en <*unidad*>: \WINDOWS\WinSxS.</span><span class="sxs-lookup"><span data-stu-id="b86e7-122">If Visual Studio is not installed on the same BizTalk Server computer, the source folder for the two files is under <*drive*>:\WINDOWS\WinSxS.</span></span>  
  
2.  <span data-ttu-id="b86e7-123">Agregue los archivos que ha copiado al equipo donde instaló la característica Front-end HTTP de BTARN.</span><span class="sxs-lookup"><span data-stu-id="b86e7-123">Add the copied files to the computer on which you installed BTARN HTTP Front End feature.</span></span> <span data-ttu-id="b86e7-124">De forma predeterminada, copie los archivos en <*unidad*>: \Program Acelerador de BizTalk para RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="b86e7-124">By default, copy the files to <*drive*>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet.</span></span>  
  
3.  <span data-ttu-id="b86e7-125">Una vez que haya copiado los archivos en el equipo Front-End HTTP, ejecute **Configuration.exe** nuevo.</span><span class="sxs-lookup"><span data-stu-id="b86e7-125">After you have copied the files to the HTTP Front End computer, run **Configuration.exe** again.</span></span>  
  
### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a><span data-ttu-id="b86e7-126">Algunos ensamblados de BTARN permanecen en la GAC después de desinstalar</span><span class="sxs-lookup"><span data-stu-id="b86e7-126">Some BTARN Assemblies stay in GAC after uninstalling</span></span>  
 <span data-ttu-id="b86e7-127">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b86e7-127">**Problem**</span></span>  
  
 <span data-ttu-id="b86e7-128">Al desinstalar BTARN, algunos ensamblados permanecen en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="b86e7-128">When you uninstall BTARN, some assemblies remain in the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="b86e7-129">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b86e7-129">**Resolution**</span></span>  
  
 <span data-ttu-id="b86e7-130">Quite los ensamblados de la GAC antes de reinstalar BTARN.</span><span class="sxs-lookup"><span data-stu-id="b86e7-130">Remove the assemblies from the GAC before reinstalling BTARN.</span></span>  
  
 <span data-ttu-id="b86e7-131">Use la **BtarnClean** utilidad desde el SDK para quitar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b86e7-131">Use the **BtarnClean** utility from the SDK to remove the assemblies.</span></span> <span data-ttu-id="b86e7-132">La utilidad hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b86e7-132">The utility performs the following actions:</span></span>  
  
-   <span data-ttu-id="b86e7-133">Detiene y da de baja todas las orquestaciones de BTARN.</span><span class="sxs-lookup"><span data-stu-id="b86e7-133">Stops and unenlists all the BTARN orchestrations.</span></span>  
  
-   <span data-ttu-id="b86e7-134">Detiene y elimina todos los puertos asociados.</span><span class="sxs-lookup"><span data-stu-id="b86e7-134">Stops and deletes all the associated ports.</span></span>  
  
-   <span data-ttu-id="b86e7-135">Anula la implementación de todos los ensamblados de Microsoft.Solutions.BTARN.*.</span><span class="sxs-lookup"><span data-stu-id="b86e7-135">Undeploys all the Microsoft.Solutions.BTARN.* assemblies.</span></span>  
  
 <span data-ttu-id="b86e7-136">Después de ejecutar la utilidad, si quedan ensamblados en la GAC, abra el Explorador de Windows, vaya a la carpeta "C:\Windows\Assembly" y elimine manualmente todos los ensamblados que comienzan con Microsoft.Solutions.BTARN.</span><span class="sxs-lookup"><span data-stu-id="b86e7-136">After running the utility, if there are assemblies remaining in the GAC, open Windows Explorer, go to the "C:\Windows\Assembly" folder, and then manually delete all assemblies starting with Microsoft.Solutions.BTARN.</span></span>  
  
### <a name="service-unavailable-error-on-64-bit-os"></a><span data-ttu-id="b86e7-137">Error de servicio no disponible en sistemas operativos de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b86e7-137">Service Unavailable error on 64-bit OS</span></span>
 <span data-ttu-id="b86e7-138">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b86e7-138">**Problem**</span></span>  
  
 <span data-ttu-id="b86e7-139">Es posible que obtenga un `Service Unavailable` error al intentar obtener acceso a HTTP de BTARN recibir una ubicación en sistemas operativos de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b86e7-139">You may get a `Service Unavailable` error when trying to access the BTARN HTTP receive location on 64-bit Windows operating systems.</span></span>  
  
 <span data-ttu-id="b86e7-140">**Causa**</span><span class="sxs-lookup"><span data-stu-id="b86e7-140">**Cause**</span></span>  
  
 <span data-ttu-id="b86e7-141">Esto problema puede deberse al filtro ISAPI "RPCProxy.dll".</span><span class="sxs-lookup"><span data-stu-id="b86e7-141">This issue can be caused by the "RPCProxy.dll" ISAPI filter.</span></span>  
  
 <span data-ttu-id="b86e7-142">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b86e7-142">**Resolution**</span></span>  
  
<span data-ttu-id="b86e7-143">Quite las referencias al filtro ISAPI del proxy RPC y reiniciar IIS:</span><span class="sxs-lookup"><span data-stu-id="b86e7-143">Remove references to the RPC proxy ISAPI filter and restart IIS:</span></span>
  
1.  <span data-ttu-id="b86e7-144">En el Administrador de Internet Information Services (IIS), haga clic en **sitios Web**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b86e7-144">In Internet Information Services (IIS) Manager, right-click **Web Sites**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b86e7-145">En el **propiedades de sitio Web** cuadro de diálogo, haga clic en el **filtros ISAPI** ficha, quite **Proxy RPC** filtrar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b86e7-145">In the **Web Site Properties** dialog box, click the **ISAPI filters** tab, remove **RPC Proxy** filter, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="b86e7-146">Reinicie IIS.</span><span class="sxs-lookup"><span data-stu-id="b86e7-146">Restart IIS.</span></span>  
  
4.  <span data-ttu-id="b86e7-147">Tras reiniciar IIS, intente acceder a http://localhost.</span><span class="sxs-lookup"><span data-stu-id="b86e7-147">After you have restarted IIS, try accessing http://localhost.</span></span> <span data-ttu-id="b86e7-148">Debería obtener el mensaje 400 del explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="b86e7-148">You should get the 400 message back from the Internet browser.</span></span>  
  
### <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="b86e7-149">Modo mixto de SQL Server no admite</span><span class="sxs-lookup"><span data-stu-id="b86e7-149">SQL Server Mixed Mode not supported</span></span>  
<span data-ttu-id="b86e7-150">BTARN no es compatible con SQL Server en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="b86e7-150">BTARN does not support SQL Server in mixed mode.</span></span>  
  
### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a><span data-ttu-id="b86e7-151">Ejecutar setupx64.bat para configurar el ejemplo de orquestación PIPAutomation de doble acción</span><span class="sxs-lookup"><span data-stu-id="b86e7-151">Run setupx64.bat to set up the double action PIPAutomation orchestration sample</span></span> 

<span data-ttu-id="b86e7-152">Ejecutar setupx64.bat en \Program BizTalk Accelerator for rosettanet\sdk\pipautomation\doubleaction para configurar el ejemplo de orquestación de PIPAutomation de doble acción.</span><span class="sxs-lookup"><span data-stu-id="b86e7-152">Run setupx64.bat in \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder to set up the Double Action PIPAutomation Orchestration sample.</span></span>
  
### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a><span data-ttu-id="b86e7-153">Descargar el archivo de instalación de BTARN desde la Web en una carpeta temporal</span><span class="sxs-lookup"><span data-stu-id="b86e7-153">Download the BTARN Setup File from the Web to a Temp Folder</span></span>  
 <span data-ttu-id="b86e7-154">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b86e7-154">**Problem**</span></span>  
  
 <span data-ttu-id="b86e7-155">Si descarga el archivo ejecutable desde el Web autoextraíble de BTARN y guardarlo en la carpeta raíz del servidor BizTalk Server, al intentar ejecutar el archivo ejecutable, BizTalk **Asistente para la instalación** se ejecuta, en lugar del Asistente de instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="b86e7-155">If you download the BTARN self-extracting executable file from the Web, and save it to the BizTalk Server root folder, when you attempt to run the executable, the BizTalk **Setup Wizard** runs, instead of the BTARN Setup wizard.</span></span>  
  
 <span data-ttu-id="b86e7-156">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="b86e7-156">**Resolution**</span></span>  
  
 <span data-ttu-id="b86e7-157">Descargue el ejecutable autoextraíble de BTARN y guarde el archivo en una carpeta temporal.</span><span class="sxs-lookup"><span data-stu-id="b86e7-157">Download the BTARN self-extracting executable, and save the file to a temp folder.</span></span>

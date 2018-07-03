---
title: Solución de problemas y problemas conocidos con el Acelerador de RosettaNet de BizTalk (BTARN) se instalación en el servidor BizTalk Server | Microsoft Docs"
description: Recomendaciones para la instalación de SQL, la cuenta de servicio para las instancias de host y los errores conocidos con la instalación de BTARN en BizTalk Server
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c169a0871826aaaae9341f3ccafcb3e888ffbdbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974629"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a><span data-ttu-id="1e1e3-103">Solucionar problemas de instalación y ver los problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="1e1e3-103">Troubleshoot the installation and see the known install issues</span></span>


## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a><span data-ttu-id="1e1e3-104">No instale SQL Server en el equipo del controlador de dominio</span><span class="sxs-lookup"><span data-stu-id="1e1e3-104">Do not install SQL Server on the domain controller computer</span></span>  
 <span data-ttu-id="1e1e3-105">Si instala a SQL Server en el mismo equipo que el equipo de controlador de dominio, devuelve el siguiente mensaje de error al intentar crear los puertos de envío SQL:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-105">If you install SQL Server on the same computer as your domain controller computer, it returns the following error message when it is trying to create the SQL send ports:</span></span>  

```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  
```

> [!IMPORTANT]
>  <span data-ttu-id="1e1e3-106">No instale a SQL Server en el equipo del controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-106">Do not install SQL Server on the domain controller computer.</span></span>  

## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a><span data-ttu-id="1e1e3-107">La cuenta de servicio para los grupos de aplicaciones debe ser la misma que la cuenta de servicio para las instancias de host y de host aislado</span><span class="sxs-lookup"><span data-stu-id="1e1e3-107">Service account for the application pools must be the same as the service account for the Isolated Host and Host instances</span></span>  
 <span data-ttu-id="1e1e3-108">Si la cuenta de servicio definida para los grupos de aplicaciones de BTARN es diferente de la cuenta de Host aislado, BTARN no procesa correctamente los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-108">If the service account set for the BTARN application pools is different from the Isolated Host account, BTARN does not process incoming messages correctly.</span></span> <span data-ttu-id="1e1e3-109">Cuando la página .aspx de recepción llama a la canalización, la canalización no tiene acceso a los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-109">When the receive .aspx page calls the pipeline, the pipeline does not have access to the appropriate certificates.</span></span> <span data-ttu-id="1e1e3-110">Por lo tanto, no descifrar el mensaje entrante ni validar la firma.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-110">Therefore, it does not decrypt the incoming message or validate the signature.</span></span> <span data-ttu-id="1e1e3-111">Además, no podrá tener acceso a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-111">Also, it won't be able to access the MessageBox database.</span></span>  


## <a name="known-install-issues"></a><span data-ttu-id="1e1e3-112">Problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="1e1e3-112">Known install issues</span></span>


### <a name="btarn-http-front-end-feature-configuration-fails"></a><span data-ttu-id="1e1e3-113">Se produce un error en la configuración de la característica de Front-End de BTARN HTTP</span><span class="sxs-lookup"><span data-stu-id="1e1e3-113">BTARN HTTP Front End Feature configuration fails</span></span>  
 <span data-ttu-id="1e1e3-114">**Problema**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-114">**Problem**</span></span>  

 <span data-ttu-id="1e1e3-115">Si lleva a cabo una instalación personalizada para instalar solo la característica Front-end HTTP de BTARN, la configuración de BTARN puede dar error después de completarse la instalación con el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-115">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail with the following error after setup has completed:</span></span> 

`Failed to create object for feature: WebApp`  

 <span data-ttu-id="1e1e3-116">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-116">**Resolution**</span></span>  

<span data-ttu-id="1e1e3-117">Manualmente, copie los archivos y vuelva a configurar:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-117">Manually copy files and reconfigure:</span></span> 

1. <span data-ttu-id="1e1e3-118">Copie los dos archivos siguientes desde un equipo de BizTalk Server en el equipo en el que instaló la característica Front-End de HTTP de BTARN:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-118">Copy the following two files from an BizTalk Server computer to the computer on which you installed the BTARN HTTP Front End feature:</span></span>

   - <span data-ttu-id="1e1e3-119">Microsoft.VC80.ATL.manifest</span><span class="sxs-lookup"><span data-stu-id="1e1e3-119">Microsoft.VC80.ATL.manifest</span></span>  

   - <span data-ttu-id="1e1e3-120">atl80.dll</span><span class="sxs-lookup"><span data-stu-id="1e1e3-120">atl80.dll</span></span>  

     <span data-ttu-id="1e1e3-121">Si Visual Studio está instalado en el mismo equipo que BizTalk Server, la carpeta de origen de los dos archivos es <*unidad*>: \Program Files\Microsoft Visual Studio < versión\>\VC\redist\x86\Microsoft.VC100.ATL .</span><span class="sxs-lookup"><span data-stu-id="1e1e3-121">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is <*drive*>:\Program Files\Microsoft Visual Studio <version\>\VC\redist\x86\Microsoft.VC100.ATL.</span></span>  

     <span data-ttu-id="1e1e3-122">Si Visual Studio no está instalado en el mismo equipo de BizTalk Server, es la carpeta de origen de los dos archivos en <*unidad*>: \WINDOWS\WinSxS.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-122">If Visual Studio is not installed on the same BizTalk Server computer, the source folder for the two files is under <*drive*>:\WINDOWS\WinSxS.</span></span>  

2. <span data-ttu-id="1e1e3-123">Agregue los archivos que ha copiado al equipo donde instaló la característica Front-end HTTP de BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-123">Add the copied files to the computer on which you installed BTARN HTTP Front End feature.</span></span> <span data-ttu-id="1e1e3-124">De forma predeterminada, copie los archivos en <*unidad*>: \Program Files\Microsoft Acelerador de BizTalk para RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-124">By default, copy the files to <*drive*>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet.</span></span>  

3. <span data-ttu-id="1e1e3-125">Una vez que haya copiado los archivos en el equipo Front-End HTTP, ejecute **Configuration.exe** nuevo.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-125">After you have copied the files to the HTTP Front End computer, run **Configuration.exe** again.</span></span>  

### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a><span data-ttu-id="1e1e3-126">Algunos ensamblados de BTARN permanecen en la GAC después de desinstalar</span><span class="sxs-lookup"><span data-stu-id="1e1e3-126">Some BTARN Assemblies stay in GAC after uninstalling</span></span>  
 <span data-ttu-id="1e1e3-127">**Problema**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-127">**Problem**</span></span>  

 <span data-ttu-id="1e1e3-128">Al desinstalar BTARN, algunos ensamblados permanecen en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="1e1e3-128">When you uninstall BTARN, some assemblies remain in the global assembly cache (GAC).</span></span>  

 <span data-ttu-id="1e1e3-129">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-129">**Resolution**</span></span>  

 <span data-ttu-id="1e1e3-130">Quite los ensamblados de la GAC antes de reinstalar BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-130">Remove the assemblies from the GAC before reinstalling BTARN.</span></span>  

 <span data-ttu-id="1e1e3-131">Use la **BtarnClean** utilidad desde el SDK para quitar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-131">Use the **BtarnClean** utility from the SDK to remove the assemblies.</span></span> <span data-ttu-id="1e1e3-132">La utilidad hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-132">The utility performs the following actions:</span></span>  

- <span data-ttu-id="1e1e3-133">Detiene y da de baja todas las orquestaciones de BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-133">Stops and unenlists all the BTARN orchestrations.</span></span>  

- <span data-ttu-id="1e1e3-134">Detiene y elimina todos los puertos asociados.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-134">Stops and deletes all the associated ports.</span></span>  

- <span data-ttu-id="1e1e3-135">Anula la implementación de todos los ensamblados de Microsoft.Solutions.BTARN.\*.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-135">Undeploys all the Microsoft.Solutions.BTARN.\* assemblies.</span></span>  

  <span data-ttu-id="1e1e3-136">Después de ejecutar la utilidad, si quedan ensamblados en la GAC, abra el Explorador de Windows, vaya a la carpeta "C:\Windows\Assembly" y elimine manualmente todos los ensamblados que comienzan con Microsoft.Solutions.BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-136">After running the utility, if there are assemblies remaining in the GAC, open Windows Explorer, go to the "C:\Windows\Assembly" folder, and then manually delete all assemblies starting with Microsoft.Solutions.BTARN.</span></span>  

### <a name="service-unavailable-error-on-64-bit-os"></a><span data-ttu-id="1e1e3-137">Error de servicio no disponible en el sistema operativo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="1e1e3-137">Service Unavailable error on 64-bit OS</span></span>
 <span data-ttu-id="1e1e3-138">**Problema**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-138">**Problem**</span></span>  

 <span data-ttu-id="1e1e3-139">Es posible que obtenga un `Service Unavailable` ubicación en los sistemas operativos de Windows de 64 bits de recepción de error al intentar acceder a los HTTP de BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-139">You may get a `Service Unavailable` error when trying to access the BTARN HTTP receive location on 64-bit Windows operating systems.</span></span>  

 <span data-ttu-id="1e1e3-140">**Causa**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-140">**Cause**</span></span>  

 <span data-ttu-id="1e1e3-141">Esto problema puede deberse al filtro ISAPI "RPCProxy.dll".</span><span class="sxs-lookup"><span data-stu-id="1e1e3-141">This issue can be caused by the "RPCProxy.dll" ISAPI filter.</span></span>  

 <span data-ttu-id="1e1e3-142">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-142">**Resolution**</span></span>  

<span data-ttu-id="1e1e3-143">Quite las referencias al filtro ISAPI del proxy RPC y reiniciar IIS:</span><span class="sxs-lookup"><span data-stu-id="1e1e3-143">Remove references to the RPC proxy ISAPI filter and restart IIS:</span></span>

1.  <span data-ttu-id="1e1e3-144">En el Administrador de Internet Information Services (IIS), haga clic en **sitios Web**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-144">In Internet Information Services (IIS) Manager, right-click **Web Sites**, and then click **Properties**.</span></span>  

2.  <span data-ttu-id="1e1e3-145">En el **propiedades del sitio Web** cuadro de diálogo, haga clic en el **filtros ISAPI** pestaña, quite **Proxy RPC** filtrar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-145">In the **Web Site Properties** dialog box, click the **ISAPI filters** tab, remove **RPC Proxy** filter, and then click **OK**.</span></span>  

3.  <span data-ttu-id="1e1e3-146">Reinicie IIS.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-146">Restart IIS.</span></span>  

4.  <span data-ttu-id="1e1e3-147">Después de reiniciar IIS, intente obtener acceso a http://localhost.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-147">After you have restarted IIS, try accessing http://localhost.</span></span> <span data-ttu-id="1e1e3-148">Debería obtener el mensaje 400 del explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-148">You should get the 400 message back from the Internet browser.</span></span>  

### <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="1e1e3-149">Modo mixto de SQL Server no admite</span><span class="sxs-lookup"><span data-stu-id="1e1e3-149">SQL Server Mixed Mode not supported</span></span>  
<span data-ttu-id="1e1e3-150">BTARN no es compatible con SQL Server en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-150">BTARN does not support SQL Server in mixed mode.</span></span>  

### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a><span data-ttu-id="1e1e3-151">Ejecutar setupx64.bat para configurar el ejemplo de orquestación PIPAutomation de doble acción</span><span class="sxs-lookup"><span data-stu-id="1e1e3-151">Run setupx64.bat to set up the double action PIPAutomation orchestration sample</span></span> 

<span data-ttu-id="1e1e3-152">Ejecute setupx64.bat en \Program Files\Microsoft Acelerador de BizTalk para la carpeta RosettaNet\SDK\PIPAutomation\DoubleAction configurar el ejemplo de orquestación PIPAutomation de acción doble.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-152">Run setupx64.bat in \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder to set up the Double Action PIPAutomation Orchestration sample.</span></span>

### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a><span data-ttu-id="1e1e3-153">Descargar el archivo de instalación de BTARN desde la Web en una carpeta temporal</span><span class="sxs-lookup"><span data-stu-id="1e1e3-153">Download the BTARN Setup File from the Web to a Temp Folder</span></span>  
 <span data-ttu-id="1e1e3-154">**Problema**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-154">**Problem**</span></span>  

 <span data-ttu-id="1e1e3-155">Si descarga el archivo ejecutable desde el Web autoextraíble de BTARN y guárdelo en la carpeta raíz del servidor BizTalk Server, cuando se intenta ejecutar el archivo ejecutable, BizTalk **Asistente para la instalación** se ejecuta, en lugar del Asistente para la instalación de BTARN.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-155">If you download the BTARN self-extracting executable file from the Web, and save it to the BizTalk Server root folder, when you attempt to run the executable, the BizTalk **Setup Wizard** runs, instead of the BTARN Setup wizard.</span></span>  

 <span data-ttu-id="1e1e3-156">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="1e1e3-156">**Resolution**</span></span>  

 <span data-ttu-id="1e1e3-157">Descargue el ejecutable autoextraíble de BTARN y guarde el archivo en una carpeta temporal.</span><span class="sxs-lookup"><span data-stu-id="1e1e3-157">Download the BTARN self-extracting executable, and save the file to a temp folder.</span></span>

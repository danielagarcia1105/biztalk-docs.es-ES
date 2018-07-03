---
title: Configurar IIS para ubicación de recepción HTTP | Microsoft Docs
description: Crear la aplicación de recepción HTTP de BTS en IIS y probar la configuración del grupo de aplicación de BizTalk Server
ms.custom: ''
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc616fa9834071c2ee8d2b4d63f486ff0abbeab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004829"
---
# <a name="configure-iis-for-an-http-receive-location"></a><span data-ttu-id="fcacd-103">Configurar IIS para ubicación de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="fcacd-103">Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="fcacd-104">HTTP ubicación de recepción utiliza una aplicación dentro de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="fcacd-104">The HTTP receive location uses an application within Internet Information Services (IIS).</span></span> <span data-ttu-id="fcacd-105">Este tema se enumeran los pasos para habilitar el HTTP ubicación dentro de IIS de recepción.</span><span class="sxs-lookup"><span data-stu-id="fcacd-105">This topic lists the steps to enable the HTTP receive location within IIS.</span></span> 

<span data-ttu-id="fcacd-106">Dependiendo del sistema operativo, los pasos para configurar la aplicación de IIS pueden variar.</span><span class="sxs-lookup"><span data-stu-id="fcacd-106">Depending on your operating system, the steps to configure the IIS application may vary.</span></span> <span data-ttu-id="fcacd-107">Siga estos pasos como guía, como la interfaz de usuario puede ser diferente en su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fcacd-107">Use these steps as a guide, as the user interface may be different on your OS.</span></span>
  
## <a name="32-bit-vs-64-bit"></a><span data-ttu-id="fcacd-108">32 bits frente a 64 bits</span><span class="sxs-lookup"><span data-stu-id="fcacd-108">32-bit vs 64-bit</span></span>

<span data-ttu-id="fcacd-109">HTTP ubicación de recepción utiliza la BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="fcacd-109">An HTTP receive location uses the BTSHTTPReceive.dll.</span></span> <span data-ttu-id="fcacd-110">Hay una versión de 64 bits del archivo DLL y de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="fcacd-110">There is a 32-bit and a 64-bit version of the DLL.</span></span> <span data-ttu-id="fcacd-111">Elija qué versión desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="fcacd-111">You choose which version you want to use.</span></span> <span data-ttu-id="fcacd-112">los procesos de 64 bits tienen más memoria disponible, por lo que si procesar los mensajes más grandes, a continuación, la versión de 64 bits puede ser mejor.</span><span class="sxs-lookup"><span data-stu-id="fcacd-112">64-bit processes have more available memory, so if you process larger messages, then the 64-bit version may be best.</span></span> 

<span data-ttu-id="fcacd-113">**ubicación de instalación de 32 bits**: *archivos de programa (x86) \Microsoft BizTalk Server\HttpReceive*.</span><span class="sxs-lookup"><span data-stu-id="fcacd-113">**32-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive*.</span></span>
<span data-ttu-id="fcacd-114">**ubicación de instalación de 64 bits**: *\Microsoft BizTalk Server\HttpReceive64 (x86) de archivos de programa*</span><span class="sxs-lookup"><span data-stu-id="fcacd-114">**64-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive64*</span></span>

<span data-ttu-id="fcacd-115">Para ejecutar la versión de 64 bits de HTTP en modo nativo de 64 bits del adaptador de recepción, abra un símbolo del sistema y ejecute los siguientes scripts:</span><span class="sxs-lookup"><span data-stu-id="fcacd-115">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode,  open a command prompt, and execute the following scripts:</span></span>  

1. <span data-ttu-id="fcacd-116">Tipo: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span><span class="sxs-lookup"><span data-stu-id="fcacd-116">Type: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span></span>  

2. <span data-ttu-id="fcacd-117">Tipo: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span><span class="sxs-lookup"><span data-stu-id="fcacd-117">Type: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcacd-118">No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="fcacd-118">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="fcacd-119">Sólo puede haber un receptor aislado por proceso.</span><span class="sxs-lookup"><span data-stu-id="fcacd-119">You can have only one isolated receiver per process.</span></span>  
  
##  <a name="configure-the-iis-application"></a><span data-ttu-id="fcacd-120">Configurar la aplicación de IIS</span><span class="sxs-lookup"><span data-stu-id="fcacd-120">Configure the IIS application</span></span>
  
1. <span data-ttu-id="fcacd-121">Abra **Internet Information Services** (abrir **administrador del servidor**, seleccione **herramientas**y seleccione **Administrador de Internet Information Services**).</span><span class="sxs-lookup"><span data-stu-id="fcacd-121">Open **Internet Information Services** (open **Server Manager**, select **Tools**, and select **Internet Information Services Manager**).</span></span> 
  
2. <span data-ttu-id="fcacd-122">En IIS, seleccione el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="fcacd-122">In IIS, select your server name.</span></span> <span data-ttu-id="fcacd-123">En el **vista características**, haga doble clic en **asignaciones de controlador**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-123">In the **Features View**, double-click **Handler Mappings**.</span></span> <span data-ttu-id="fcacd-124">En el panel Acciones, seleccione **Agregar asignación de Script**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-124">In the Actions pane, select **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fcacd-125">Al configurar la asignación de script en el nivel de servidor web, la asignación se aplica a todos los sitios web.</span><span class="sxs-lookup"><span data-stu-id="fcacd-125">When you configure the script mapping at the web server-level, the mapping applies to all web sites.</span></span> <span data-ttu-id="fcacd-126">Si desea restringir la asignación a un sitio Web específico o una carpeta virtual, seleccione esa carpeta o sitio web y, a continuación, agregue la asignación de script.</span><span class="sxs-lookup"><span data-stu-id="fcacd-126">If you want to restrict the mapping to a specific Web site or virtual folder, select that web site or folder, and then add the script map.</span></span>  
  
3. <span data-ttu-id="fcacd-127">En **Agregar asignación de Script**, seleccione **ruta de acceso de solicitud**y el tipo `BtsHttpReceive.dll`.</span><span class="sxs-lookup"><span data-stu-id="fcacd-127">In **Add Script Map**, select **Request path**, and type `BtsHttpReceive.dll`.</span></span>  
  
4. <span data-ttu-id="fcacd-128">En **ejecutable**, seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span><span class="sxs-lookup"><span data-stu-id="fcacd-128">In **Executable**, select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="fcacd-129">Seleccione **BtsHttpReceive.dll**y, a continuación, seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-129">Select **BtsHttpReceive.dll**, and then select **Open**.</span></span>  
  
5. <span data-ttu-id="fcacd-130">En **nombre**, escriba `BizTalk HTTP Receive`y, a continuación, seleccione **restricciones de solicitudes**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-130">In **Name**, enter `BizTalk HTTP Receive`, and then select **Request Restrictions**.</span></span> <span data-ttu-id="fcacd-131">En esta ventana:</span><span class="sxs-lookup"><span data-stu-id="fcacd-131">In this window:</span></span>
  
   1. <span data-ttu-id="fcacd-132">En **verbos**, seleccione **uno de los siguientes verbos**y escriba `POST`.</span><span class="sxs-lookup"><span data-stu-id="fcacd-132">In **Verbs**, select **One of the following verbs**, and enter `POST`.</span></span>  
  
   2. <span data-ttu-id="fcacd-133">En **acceso**, seleccione **Script**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-133">In **Access**, select **Script**, and then select **OK**.</span></span>  
  
   3. <span data-ttu-id="fcacd-134">Cuando se le solicite que permita la extensión ISAPI, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-134">When prompted to allow the ISAPI extension, select **Yes**.</span></span>  
  
6. <span data-ttu-id="fcacd-135">Crear un nuevo grupo de aplicaciones (haga clic en **grupos de aplicaciones**, seleccione **Agregar grupo de aplicaciones**).</span><span class="sxs-lookup"><span data-stu-id="fcacd-135">Create a new application pool (right-click **Application Pools**, select **Add application pool**).</span></span> <span data-ttu-id="fcacd-136">**Nombre** el grupo de aplicaciones (como `BTSHTTPReceive`), seleccione **NET Framework v4.0.30319**y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-136">**Name** your application pool (such as `BTSHTTPReceive`), select **NET Framework v4.0.30319**, and select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fcacd-137">El número de versión de .NET puede variar según la versión de .NET Framework instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fcacd-137">The .NET version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="fcacd-138">Aparece el nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fcacd-138">The new application pool is listed.</span></span>  
  
7. <span data-ttu-id="fcacd-139">Seleccione el nuevo grupo de aplicaciones y abra el **configuración avanzada** (**acciones** panel).</span><span class="sxs-lookup"><span data-stu-id="fcacd-139">Select your new application pool, and open the **Advanced Settings** (**Actions** pane).</span></span> <span data-ttu-id="fcacd-140">En esta ventana:</span><span class="sxs-lookup"><span data-stu-id="fcacd-140">In this window:</span></span>

    - <span data-ttu-id="fcacd-141">**Habilitar aplicación de 32 bits**: establecido en **True** si eligió el 32-bit **BtsHttpReceive.dll**</span><span class="sxs-lookup"><span data-stu-id="fcacd-141">**Enable 32-Bit Application**: Set to **True** if you chose the 32-bit **BtsHttpReceive.dll**</span></span>
    - <span data-ttu-id="fcacd-142">**Procesar modelo** sección **identidad**: seleccione los puntos suspensivos (**...** ), seleccione **cuenta personalizada**y, a continuación, **establecer** a una cuenta que sea miembro de la **usuarios de hosts aislados de BizTalk** y  **IIS_WPG** grupos.</span><span class="sxs-lookup"><span data-stu-id="fcacd-142">**Process Model** section, **Identity**: Select the ellipsis (**…**), select **Custom account**, and then **Set** it to an account that is a member of the **BizTalk Isolated Host Users** and **IIS_WPG** groups.</span></span> <span data-ttu-id="fcacd-143">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-143">Select **OK**.</span></span> 
  
8. <span data-ttu-id="fcacd-144">Agregar una nueva aplicación en el sitio web (haga clic en el **sitio Web predeterminado**, seleccione **Agregar aplicación**).</span><span class="sxs-lookup"><span data-stu-id="fcacd-144">Add a new application to the web site (right-click the **Default Web Site**, select **Add Application**).</span></span> <span data-ttu-id="fcacd-145">En esta ventana:</span><span class="sxs-lookup"><span data-stu-id="fcacd-145">In this window:</span></span>
  
   1. <span data-ttu-id="fcacd-146">**Alias** : escriba un alias que se asocia a la aplicación (como `BTS HTTP Receive`y, a continuación, **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-146">**Alias** : Enter an alias that you associate with the application (such as `BTS HTTP Receive`, and then **Select**.</span></span>  
   2. <span data-ttu-id="fcacd-147">Seleccione el nuevo grupo de aplicaciones que acaba de crear y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-147">Select the new application pool you just created, and then select **OK**.</span></span>  
   3. <span data-ttu-id="fcacd-148">**Ruta de acceso física**: seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span><span class="sxs-lookup"><span data-stu-id="fcacd-148">**Physical path**: Select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span>  
   4. <span data-ttu-id="fcacd-149">**Configuración de pruebas** para comprobar que no hay ningún error en la **Probar conexión** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fcacd-149">**Test Settings** to verify there are no errors in the **Test Connection** dialog box.</span></span> <span data-ttu-id="fcacd-150">**Cerrar**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-150">**Close**, and then select **OK**.</span></span>  
  
      > [!TIP]
      > <span data-ttu-id="fcacd-151">Si la configuración de pruebas, se devuelve una advertencia, la identidad del grupo de aplicaciones puede que falten permisos a una carpeta o el acceso a un grupo.</span><span class="sxs-lookup"><span data-stu-id="fcacd-151">If Test Settings returns a warning, the identity of the application pool may be missing permissions to a folder, or access to a group.</span></span> <span data-ttu-id="fcacd-152">Como paso de solución de problemas, seleccione **conectar como**, escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="fcacd-152">As a troubleshooting step, select **Connect As**, enter the **User name** and **Password** for a user account that is a member of the Administrators group.</span></span> 

9. <span data-ttu-id="fcacd-153">Aparece la nueva aplicación aparece en **sitios Web predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="fcacd-153">The new application appears is listed under **Default Web Sites**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcacd-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcacd-154">See Also</span></span>  
 [<span data-ttu-id="fcacd-155">Cómo configurar ubicación de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="fcacd-155">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)

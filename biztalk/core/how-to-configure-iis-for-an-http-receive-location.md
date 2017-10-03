---
title: "Cómo configurar IIS para la ubicación de recepción HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a><span data-ttu-id="6aa39-102">Cómo configurar IIS para la ubicación de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="6aa39-102">How to Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="6aa39-103">En función de la versión de Microsoft Windows que se esté utilizando, se tendrá que configurar Servicios de Internet Information Server (IIS) de forma distinta para trabajar con la ubicación de recepción del adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="6aa39-103">Depending on which version of Microsoft Windows you are using, you will have to configure Microsoft Internet Information Services (IIS) differently to work with the HTTP adapter receive location.</span></span>  
  
 <span data-ttu-id="6aa39-104">Si el sistema operativo es [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], IIS 7.0 proporciona dos modos de aislamiento de aplicaciones diferentes para proteger aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="6aa39-104">If your operating system is [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], IIS 7.0 provides two different application isolation modes to protect Web applications.</span></span> <span data-ttu-id="6aa39-105">El modo de aislamiento de proceso de trabajo es el modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6aa39-105">Worker process isolation mode is the default mode.</span></span> <span data-ttu-id="6aa39-106">Se puede configurar la ubicación de recepción del adaptador de HTTP para trabajar con cualquiera de los dos modos, aunque se recomienda el modo de aislamiento de proceso de trabajo por su funcionalidad de seguridad mejorada.</span><span class="sxs-lookup"><span data-stu-id="6aa39-106">You can configure the HTTP adapter receive location to work with either mode, but worker process isolation mode is recommended for its improved security functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aa39-107">Si el sistema operativo es la x64 edición de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], la versión de 64 bits de HTTP de recepción adaptador se instala en el  *\<unidad >***\Program Files (x86) \Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64** directorio de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6aa39-107">If your operating system is the x64 edition of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], the 64-bit version of the HTTP receive adapter is installed to the *\<drive>***\Program Files (x86)\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\HttpReceive64** directory of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by default.</span></span> <span data-ttu-id="6aa39-108">Para ejecutar la versión de 64 bits del adaptador de recepción HTTP en el modo nativo de 64 bits, debe ejecutar la siguiente secuencia de comandos desde una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6aa39-108">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode you must execute the following script from a command line:</span></span>  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  <span data-ttu-id="6aa39-109">No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="6aa39-109">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="6aa39-110">Sólo puede haber un receptor aislado por proceso.</span><span class="sxs-lookup"><span data-stu-id="6aa39-110">You can have only one isolated receiver per process.</span></span>  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a><span data-ttu-id="6aa39-111">Para configurar el modo de aislamiento de proceso de trabajo de IIS 7.0 para que funcione con el adaptador de HTTP ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="6aa39-111">To configure the IIS 7.0 worker process isolation mode to work with the HTTP adapter receive location</span></span>  
  
1.  <span data-ttu-id="6aa39-112">Haga clic en **iniciar**, seleccione **configuración**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-112">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="6aa39-113">En el Panel de Control, haga doble clic en **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-113">In Control Panel, double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="6aa39-114">En Herramientas administrativas, haga doble clic en **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-114">In Administrative Tools, double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="6aa39-115">En Internet Information Services, seleccione la entrada del servidor Web raíz.</span><span class="sxs-lookup"><span data-stu-id="6aa39-115">In Internet Information Services, select the root Web server entry.</span></span> <span data-ttu-id="6aa39-116">En el **vista características**, haga doble clic en **asignaciones de controlador**y, a continuación, en el panel Acciones, haga clic en **Agregar asignación de Script**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-116">In the **Features View**, double-click **Handler Mappings**, and then in the Actions pane, click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa39-117">Si configura la asignación de script en el nivel de servidor web, esta asignación se aplicará a todos los sitios web secundarios.</span><span class="sxs-lookup"><span data-stu-id="6aa39-117">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="6aa39-118">Si desea restringir la asignación a un sitio web específico o a una carpeta virtual, seleccione el sitio o carpeta de destino en lugar del servidor web.</span><span class="sxs-lookup"><span data-stu-id="6aa39-118">If you want to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
5.  <span data-ttu-id="6aa39-119">En el **Agregar asignación de Script** cuadro de diálogo, en la **ruta de acceso de solicitud** , escriba `BtsHttpReceive.dll`.</span><span class="sxs-lookup"><span data-stu-id="6aa39-119">In the **Add Script Map** dialog box, in the **Request path** field, type `BtsHttpReceive.dll`.</span></span>  
  
6.  <span data-ttu-id="6aa39-120">En el **ejecutable** , a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span><span class="sxs-lookup"><span data-stu-id="6aa39-120">In the **Executable** field, click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="6aa39-121">Seleccione **BtsHttpReceive.dll** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-121">Select **BtsHttpReceive.dll** and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6aa39-122">En el **nombre** , escriba `BizTalk HTTP Receive`y, a continuación, haga clic en **restricciones de solicitudes**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-122">In the **Name** field, type `BizTalk HTTP Receive`, and then click **Request Restrictions**.</span></span>  
  
8.  <span data-ttu-id="6aa39-123">En el **restricciones de solicitudes** cuadro de diálogo, haga clic en el **verbos** ficha y, a continuación, seleccione **uno de los siguientes verbos**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-123">In the **Request Restrictions** dialog box, click the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="6aa39-124">Escriba `POST` como verbo.</span><span class="sxs-lookup"><span data-stu-id="6aa39-124">Enter `POST` as the verb.</span></span>  
  
9. <span data-ttu-id="6aa39-125">En el **acceso** ficha, seleccione **Script**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-125">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="6aa39-126">Cuando se le solicite que permita la extensión ISAPI, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-126">When prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
11. <span data-ttu-id="6aa39-127">Haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, haga clic en **grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-127">Right-click **Application Pools**, point to **New**, and then click **Application pool**.</span></span>  
  
12. <span data-ttu-id="6aa39-128">En el **Agregar grupo de aplicaciones** cuadro de diálogo, en la **nombre** , escriba un nombre para el grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6aa39-128">In the **Add Application Pool** dialog box, in the **Name** box, type a name for the application pool.</span></span> <span data-ttu-id="6aa39-129">Seleccione **NET Framework v4.0.30319** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-129">Select **NET Framework v4.0.30319** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6aa39-130">El número de versión puede variar en función de la versión de .NET Framework instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6aa39-130">The version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="6aa39-131">El nuevo grupo de aplicaciones aparece en la lista de **grupos de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-131">The new application pool appears in the list of **Application Pools**.</span></span>  
  
13. <span data-ttu-id="6aa39-132">En **grupos de aplicaciones**, en la **vista características**, seleccione el nuevo grupo de aplicaciones y, a continuación, haga clic en **configuración avanzada** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="6aa39-132">In **Application Pools**, in the **Features View**, select the new application pool, and then click **Advanced Settings** in the Actions pane.</span></span>  
  
14. <span data-ttu-id="6aa39-133">En el **configuración avanzada** cuadro de diálogo, en la **modelo de proceso** sección, en la **identidad** , a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.</span><span class="sxs-lookup"><span data-stu-id="6aa39-133">In the **Advanced Settings** dialog box, in the **Process Model** section, in the **Identity** field, click the ellipsis (**…**) button.</span></span>  
  
15. <span data-ttu-id="6aa39-134">En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada**y, a continuación, haga clic en **establecer**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-134">In the **Application Pool Identity** dialog box, select **Custom account**, and then click **Set**.</span></span> <span data-ttu-id="6aa39-135">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Configuración avanzada** .</span><span class="sxs-lookup"><span data-stu-id="6aa39-135">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
16. <span data-ttu-id="6aa39-136">En el Administrador de IIS, abra el **sitios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="6aa39-136">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="6aa39-137">Haga clic en el **sitio Web predeterminado** y, a continuación, haga clic en **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-137">Right-click the **Default Web Site** and then click **Add Application**.</span></span>  
  
17. <span data-ttu-id="6aa39-138">En el **Agregar aplicación** cuadro de diálogo **Alias**, escriba un alias para asociarlo con la aplicación y, a continuación, haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-138">In the **Add Application** dialog box, in **Alias**, enter an alias to associate with the application, and then click **Select**.</span></span>  
  
18. <span data-ttu-id="6aa39-139">En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione el nuevo grupo de aplicaciones que creó anteriormente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-139">In the **Select Application Pool** dialog box, select the new application pool you created earlier, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="6aa39-140">Haga clic en el botón de puntos suspensivos (**...** ) botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-140">Click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
20. <span data-ttu-id="6aa39-141">Haga clic en **conectar como** y escriba la **nombre de usuario** y **contraseña** para una cuenta de usuario que es miembro del grupo Administradores y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-141">Click **Connect As** and enter the **User name** and **Password** for a user account that is a member of the Administrators group, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="6aa39-142">Haga clic en **configuración de pruebas** y compruebe que se muestra ningún error en la **Probar conexión** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6aa39-142">Click **Test Settings** and verify that no errors are displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="6aa39-143">Haga clic en **Cerrar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6aa39-143">Click **Close**, and then click **OK**.</span></span>  
  
22. <span data-ttu-id="6aa39-144">La nueva aplicación aparece en la lista de **sitios Web predeterminados** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6aa39-144">The new application appears in the list of **Default Web Sites** in Internet Information Services (IIS) Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa39-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa39-145">See Also</span></span>  
 [<span data-ttu-id="6aa39-146">Cómo configurar ubicación de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="6aa39-146">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)
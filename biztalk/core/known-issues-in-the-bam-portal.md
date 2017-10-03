---
title: Problemas conocidos en el Portal de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa12d0f25a004f2e713f360e00c0f0c1192d304
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="3595c-102">Problemas conocidos del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="3595c-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="3595c-103">Este tema contiene información que le ayudará a identificar y resolver los problemas que pueden surgir al usar el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="3595c-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-are-generated-when-the-bam-portal-and-internet-explorer-7-or-internet-explorer-8-are-on-the-same-computer-and-the-security-settings-are-set-to-low"></a><span data-ttu-id="3595c-104">Se generan errores cuando el portal de BAM e Internet Explorer 7 o Internet Explorer 8 se encuentran en el mismo equipo y la configuración de seguridad se establece en Baja</span><span class="sxs-lookup"><span data-stu-id="3595c-104">Errors Are Generated When the BAM Portal and Internet Explorer 7 or Internet Explorer 8 Are on the Same Computer and the Security Settings Are Set to Low</span></span>  
 <span data-ttu-id="3595c-105">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3595c-105">**Problem**</span></span>  
  
 <span data-ttu-id="3595c-106">Cuando se usa Internet Explorer 7 o Internet Explorer 7 o Internet Explorer 8 con [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] puede aparecer el mensaje de error **Error de servidor en ' / BAM' aplicación** debajo de los siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="3595c-106">When using Internet Explorer 7 or Internet Explorer 7 or Internet Explorer 8 with [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
-   <span data-ttu-id="3595c-107">Al hacer clic en una actividad relacionada que remite a una instancia de actividad inexistente.</span><span class="sxs-lookup"><span data-stu-id="3595c-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
-   <span data-ttu-id="3595c-108">Al hacer clic en el **guardar alerta** botón en el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="3595c-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
    -   <span data-ttu-id="3595c-109">Crear una consulta en el **búsqueda de actividad económica** página y, a continuación, haga clic en **establecer alerta**.</span><span class="sxs-lookup"><span data-stu-id="3595c-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
    -   <span data-ttu-id="3595c-110">Complete los campos de alerta y, a continuación, haga clic en **guardar alerta**.</span><span class="sxs-lookup"><span data-stu-id="3595c-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
    -   <span data-ttu-id="3595c-111">Hace clic en el botón Atrás.</span><span class="sxs-lookup"><span data-stu-id="3595c-111">You click the back button.</span></span>  
  
    -   <span data-ttu-id="3595c-112">Hacer clic en el **guardar alerta** nuevamente en el botón.</span><span class="sxs-lookup"><span data-stu-id="3595c-112">You click the **Save Alert** button again.</span></span>  
  
 <span data-ttu-id="3595c-113">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3595c-113">**Cause**</span></span>  
  
 <span data-ttu-id="3595c-114">Al ejecutar [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] o [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] e Internet Explorer 7 o Internet Explorer 8 con la configuración de seguridad en nivel bajo, las solicitudes web se ejecutan con pocos privilegios.</span><span class="sxs-lookup"><span data-stu-id="3595c-114">When running [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] and Internet Explorer 7 or Internet Explorer 8 with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="3595c-115">Para afrontar el desafío de la seguridad integrada de Windows, Internet Explorer pasa un token de usuario con muy pocos privilegios.</span><span class="sxs-lookup"><span data-stu-id="3595c-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
 <span data-ttu-id="3595c-116">Si se está usando Internet Explorer en el mismo equipo en que está instalado el portal de BAM, y se establece el nivel de seguridad de Internet Explorer como bajo, el portal actúa como el usuario con el token de pocos privilegios.</span><span class="sxs-lookup"><span data-stu-id="3595c-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="3595c-117">Dicho token no concede permisos de escritura en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="3595c-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="3595c-118">Cuando detecta un error, el portal intenta registrarlo en el registro de eventos; esto le hará generar un error, ya que los privilegios reducidos del token de usuario son insuficientes para tener acceso al registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="3595c-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
 <span data-ttu-id="3595c-119">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="3595c-119">**Resolution**</span></span>  
  
 <span data-ttu-id="3595c-120">Si necesita explorar desde el equipo local, debe agregar http://localhost a la lista de sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="3595c-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="to-add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="3595c-121">Para agregar localhost a la lista de sitios de confianza</span><span class="sxs-lookup"><span data-stu-id="3595c-121">To add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="3595c-122">En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="3595c-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="3595c-123">Haga clic en el **seguridad** ficha y, a continuación, haga clic en **sitios de confianza** en el **seleccione una zona para ver o cambiar la configuración de seguridad** ventana.</span><span class="sxs-lookup"><span data-stu-id="3595c-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="3595c-124">Haga clic en el **sitios** botón.</span><span class="sxs-lookup"><span data-stu-id="3595c-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="3595c-125">En el **agregar este sitio Web a la zona** cuadro de texto, escriba **http://localhost**.</span><span class="sxs-lookup"><span data-stu-id="3595c-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="3595c-126">Si el **Requerir comprobación del servidor (https:) para todos los sitios de esta zona** casilla de verificación está activada, desactívela y, a continuación, haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="3595c-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="3595c-127">El sitio, http://localhost, aparecerá en la **sitios Web** lista.</span><span class="sxs-lookup"><span data-stu-id="3595c-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="3595c-128">Si es necesario, restaure la **Requerir comprobación del servidor (https:) para todos los sitios de esta zona** casilla de verificación a su estado original.</span><span class="sxs-lookup"><span data-stu-id="3595c-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="3595c-129">Haga clic en el **cerrar** botón y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3595c-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer-7"></a><span data-ttu-id="3595c-130">Las agregaciones del portal de BAM no llenarán los datos existentes cuando se utilice una dirección IP como URL en Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="3595c-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer 7</span></span>  
 <span data-ttu-id="3595c-131">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3595c-131">**Problem**</span></span>  
  
 <span data-ttu-id="3595c-132">Cuando se usa una dirección IP como una dirección URL con Internet Explorer 7 o Internet Explorer 8 y [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] para ver el portal de BAM, las agregaciones muestran el siguiente mensaje: "sin detalles.</span><span class="sxs-lookup"><span data-stu-id="3595c-132">When using an IP address as a URL with Internet Explorer 7 or Internet Explorer 8 and [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="3595c-133">No se ha podido procesar la consulta."</span><span class="sxs-lookup"><span data-stu-id="3595c-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="3595c-134">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3595c-134">**Cause**</span></span>  
  
 <span data-ttu-id="3595c-135">La configuración de seguridad predeterminada de Internet Explorer 7 o Internet Explorer 8 no permite el acceso a los sitios que usan direcciones IPv4 e IPv6 como URL.</span><span class="sxs-lookup"><span data-stu-id="3595c-135">The default security settings in Internet Explorer 7 or Internet Explorer 8 prevents access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="3595c-136">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="3595c-136">**Resolution**</span></span>  
  
 <span data-ttu-id="3595c-137">Agregue la dirección del sitio a la lista de sitios de confianza y habilite el acceso a los orígenes de datos entre dominios.</span><span class="sxs-lookup"><span data-stu-id="3595c-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="to-add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="3595c-138">Para agregar la dirección IP a la lista de sitios de confianza:</span><span class="sxs-lookup"><span data-stu-id="3595c-138">To add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="3595c-139">En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="3595c-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="3595c-140">Haga clic en el **seguridad** ficha y, a continuación, haga clic en el **sitios de confianza** zona de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3595c-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="3595c-141">Haga clic en el **sitios** botón.</span><span class="sxs-lookup"><span data-stu-id="3595c-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="3595c-142">En **agregar este sitio Web a la zona**, escriba la dirección IP del portal de BAM y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="3595c-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="3595c-143">Haga clic en **Cerrar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3595c-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="to-enable-access-to-data-sources-across-domains"></a><span data-ttu-id="3595c-144">Para habilitar el acceso a orígenes de datos entre dominios:</span><span class="sxs-lookup"><span data-stu-id="3595c-144">To enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="3595c-145">En Internet Explorer, haga clic en **herramientas**y, a continuación, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="3595c-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="3595c-146">Haga clic en el **seguridad** ficha y, a continuación, haga clic en el **sitios de confianza** zona de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3595c-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="3595c-147">Haga clic en el **nivel personalizado** botón mientras se desplaza hacia abajo hasta la **varios** nodo de la **configuración** árbol.</span><span class="sxs-lookup"><span data-stu-id="3595c-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="3595c-148">En el **acceder a orígenes de datos a través de dominios** nodo, haga clic en el **habilitar radio** botón y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3595c-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="3595c-149">BM.exe no se ejecuta en PowerShell</span><span class="sxs-lookup"><span data-stu-id="3595c-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="3595c-150">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3595c-150">**Problem**</span></span>  
  
 <span data-ttu-id="3595c-151">El siguiente comando produce un error al ejecutarse en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3595c-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="3595c-152">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3595c-152">**Cause**</span></span>  
  
 <span data-ttu-id="3595c-153">PowerShell no ha podido localizar la ruta de los archivos .exe y config.</span><span class="sxs-lookup"><span data-stu-id="3595c-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="3595c-154">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="3595c-154">**Resolution**</span></span>  
  
 <span data-ttu-id="3595c-155">Si usa bm.exe en PowerShell, especifique la ruta completa de los archivos .exe y config.</span><span class="sxs-lookup"><span data-stu-id="3595c-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="3595c-156">Por ejemplo: `bm.exe get-config -FileName:config.xml` debe especificarse como `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span><span class="sxs-lookup"><span data-stu-id="3595c-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3595c-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="3595c-157">See Also</span></span>  
 [<span data-ttu-id="3595c-158">Planeación del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="3595c-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
---
title: "Paso 5: Configurar las páginas Web de socio comercial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: "38"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f1dce6a68dc334f9f5f30b1aae938ada6f612a
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2017
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a><span data-ttu-id="20491-102">Paso 5: Configurar las páginas Web de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="20491-102">Step 5: Configure the Trading Partner Web Pages</span></span>
<span data-ttu-id="20491-103">![El paso 5 de 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span><span class="sxs-lookup"><span data-stu-id="20491-103">![Step 5 of 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")</span></span>  
  
 <span data-ttu-id="20491-104">En este paso, realizará las siguientes tareas para configurar páginas Web de socios comerciales:</span><span class="sxs-lookup"><span data-stu-id="20491-104">In this step, you perform the following tasks to set up trading partner Web pages:</span></span>  
  
-   <span data-ttu-id="20491-105">Habilitar el filtro ISAPI de recepción de HTTP de BTS para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="20491-105">Enable the BTS HTTP Receive ISAPI filter that is required for HTTP transport.</span></span>  
  
-   <span data-ttu-id="20491-106">Configurar una carpeta y una página aspx para enrutar la confirmación 997 a la organización del socio comercial Fabrikam que use el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="20491-106">Set up a folder and an aspx page to route the 997 acknowledgment to the partner organization Fabrikam using HTTP transport.</span></span> <span data-ttu-id="20491-107">El directorio virtual de Fabrikam coloca la confirmación 997 en la \\carpeta _997ToFabrikam, que está señalada en la configuración Destination_URL del puerto de 997 envío.</span><span class="sxs-lookup"><span data-stu-id="20491-107">The Fabrikam virtual directory drops the 997 acknowledgment into the \\_997ToFabrikam folder, which is called out in the Destination_URL setting of the 997 send port.</span></span>  
  
-   <span data-ttu-id="20491-108">Configure la página ASPX para enrutar el mensaje original a la organización propia de Contoso.</span><span class="sxs-lookup"><span data-stu-id="20491-108">Set up the ASPX page to route the original message to the home organization Contoso.</span></span> <span data-ttu-id="20491-109">El directorio virtual de Contoso usa BTSHttpReceive.dll para recibir el mensaje AS2 y enviarlo a la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="20491-109">The Contoso virtual directory uses BTSHttpReceive.dll to receive the AS2 message and submit it to the receive location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20491-110">Los procedimientos proporcionados en este tema son para IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="20491-110">The procedures provided in this topic are for IIS 7.0.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20491-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="20491-111">Prerequisites</span></span>  
 <span data-ttu-id="20491-112">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20491-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="20491-113">Para habilitar el filtro ISAPI de BTS</span><span class="sxs-lookup"><span data-stu-id="20491-113">To enable the BTS ISAPI Filter</span></span>  
  
1.  <span data-ttu-id="20491-114">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="20491-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="20491-115">Seleccione la entrada de servidor Web raíz y en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en la **acciones** panel, haga clic en **Agregar asignación de Script**.</span><span class="sxs-lookup"><span data-stu-id="20491-115">Select the root Web server entry and in the **Features View**, double-click **Handler Mappings** and then in the **Actions** pane, click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20491-116">Si configura la asignación de script en el nivel de servidor web, esta asignación se aplicará a todos los sitios web secundarios.</span><span class="sxs-lookup"><span data-stu-id="20491-116">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="20491-117">Si desea restringir la asignación a un sitio Web específico o una carpeta virtual, seleccione el sitio de destino o la carpeta en lugar del servidor Web.</span><span class="sxs-lookup"><span data-stu-id="20491-117">If you wish to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
3.  <span data-ttu-id="20491-118">En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.</span><span class="sxs-lookup"><span data-stu-id="20491-118">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4.  <span data-ttu-id="20491-119">En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span><span class="sxs-lookup"><span data-stu-id="20491-119">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="20491-120">Seleccione **BtsHttpReceive.dll**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-120">Select **BtsHttpReceive.dll**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="20491-121">Escriba `BizTalk HTTP Receive` en el `Name` campo y, a continuación, haga clic en **restricciones de solicitudes**.</span><span class="sxs-lookup"><span data-stu-id="20491-121">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6.  <span data-ttu-id="20491-122">En el **restricciones de solicitudes** cuadro de diálogo, seleccione la **verbos** ficha y, a continuación, seleccione **uno de los siguientes verbos**.</span><span class="sxs-lookup"><span data-stu-id="20491-122">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="20491-123">Escriba `POST` como verbo.</span><span class="sxs-lookup"><span data-stu-id="20491-123">Enter `POST` as the verb.</span></span>  
  
7.  <span data-ttu-id="20491-124">En el **acceso** ficha, seleccione **Script**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-124">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="20491-125">Haga clic en **Aceptar** y cuando se le pida que permita la extensión ISAPI, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="20491-125">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
9. <span data-ttu-id="20491-126">Haga clic en la entrada BTSHttpReceive.dll y, a continuación, seleccione **Editar permisos de función**.</span><span class="sxs-lookup"><span data-stu-id="20491-126">Right-click the BTSHttpReceive.dll entry, and then select **Edit Feature Permissions**.</span></span>  
  
10. <span data-ttu-id="20491-127">Asegúrese de que **lectura**, **Script** y **Execute** están seleccionadas y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-127">Ensure that **Read**, **Script** and **Execute** are selected, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="20491-128">Haga clic en **vista características**y, a continuación, haga doble clic en **restricciones de ISAPI y CGI**.</span><span class="sxs-lookup"><span data-stu-id="20491-128">Click **Features View**, and then double-click **ISAPI and CGI Restrictions**.</span></span>  
  
12. <span data-ttu-id="20491-129">Asegúrese de que existe una entrada para BTSHTTPReceive.dll y que **restricción** está establecido en **permitido**.</span><span class="sxs-lookup"><span data-stu-id="20491-129">Ensure that an entry for BTSHTTPReceive.dll exists, and that **Restriction** is set to **Allowed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20491-130">La entrada Restricción de ISAPI y CGI para BTSHTTPReceive.dll se crea automáticamente cuando crea la asignación de script.</span><span class="sxs-lookup"><span data-stu-id="20491-130">The ISAPI and CGI Restriction entry for BTSHTTPReceive.dll is created automatically when you create the script map.</span></span>  
  
### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="20491-131">Para configurar la página Web de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="20491-131">To configure the Fabrikam Web page</span></span>  
  
1.  <span data-ttu-id="20491-132">En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="20491-132">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2.  <span data-ttu-id="20491-133">En el **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="20491-133">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="20491-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-134">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20491-135">El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="20491-135">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3.  <span data-ttu-id="20491-136">Seleccione **grupos de aplicaciones**, en la **vista características** seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el  **Acciones** panel.</span><span class="sxs-lookup"><span data-stu-id="20491-136">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4.  <span data-ttu-id="20491-137">En el **configuración avanzada** cuadro de diálogo, establezca **aplicaciones de 32 bits** a **True**.</span><span class="sxs-lookup"><span data-stu-id="20491-137">In the **Advanced Settings** dialog box, set **Enable 32-Bit Applications** to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20491-138">Este paso solo es necesario en equipos de 64 bits si desea que IIS se ejecute en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="20491-138">This step is required only on a 64-bit machine if you want IIS to run in a 32-bit mode.</span></span>  
  
5.  <span data-ttu-id="20491-139">Seleccione **identidad** y, a continuación, haga clic en el **puntos suspensivos (...)**  botón.</span><span class="sxs-lookup"><span data-stu-id="20491-139">Select **Identity** and then click the **ellipsis (…)** button.</span></span>  
  
6.  <span data-ttu-id="20491-140">En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.</span><span class="sxs-lookup"><span data-stu-id="20491-140">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
7.  <span data-ttu-id="20491-141">Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="20491-141">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
8.  <span data-ttu-id="20491-142">En el Administrador de IIS, abra el **sitios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="20491-142">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="20491-143">Haga clic en el **sitio Web predeterminado**y, a continuación, seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="20491-143">Right-click the **Default Web Site**, and then select **Add Application**.</span></span>  
  
9. <span data-ttu-id="20491-144">En el **Agregar aplicación** diálogo cuadro, escriba **Fabrikam** en **Alias**y, a continuación, haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="20491-144">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
10. <span data-ttu-id="20491-145">En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-145">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
11. <span data-ttu-id="20491-146">Haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam para la **ruta de acceso física**.</span><span class="sxs-lookup"><span data-stu-id="20491-146">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam for the **Physical path**.</span></span>  
  
12. <span data-ttu-id="20491-147">Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="20491-147">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="20491-148">Haga clic en **Cerrar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-148">Click **Close**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="20491-149">En el Administrador de IIS, seleccione el directorio virtual de Fabrikam y en **vista características**, haga doble clic en **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="20491-149">In IIS Manager, select the Fabrikam virtual directory and in **Features View**, double-click **Authentication**.</span></span>  
  
14. <span data-ttu-id="20491-150">En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="20491-150">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="20491-151">Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.</span><span class="sxs-lookup"><span data-stu-id="20491-151">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="20491-152">Para configurar la página Web de Contoso</span><span class="sxs-lookup"><span data-stu-id="20491-152">To configure the Contoso Web page</span></span>  
  
1.  <span data-ttu-id="20491-153">En el Administrador de IIS, abra el **sitios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="20491-153">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="20491-154">Haga clic en el **sitio Web predeterminado** y, a continuación, seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="20491-154">Right-click the **Default Web Site** and then select **Add Application**.</span></span>  
  
2.  <span data-ttu-id="20491-155">En el **Agregar aplicación** diálogo cuadro, escriba **Contoso** en **Alias**y, a continuación, haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="20491-155">In the **Add Application** dialog box, enter **Contoso** in **Alias**, and then click **Select**.</span></span>  
  
3.  <span data-ttu-id="20491-156">En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-156">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20491-157">BizTalkAppPool se creó anteriormente al configurar la página web de Fabrikam y debe configurarse en la identidad de un usuario que es miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="20491-157">The BizTalkAppPool was created previously when configuring the Fabrikam Web page, and should be set to the identity of a user that is a member of the administrators group.</span></span>  
  
4.  <span data-ttu-id="20491-158">Haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.</span><span class="sxs-lookup"><span data-stu-id="20491-158">Click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
5.  <span data-ttu-id="20491-159">Haga clic en **configuración de pruebas** y comprobar que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="20491-159">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="20491-160">Haga clic en **Cerrar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20491-160">Click **Close**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="20491-161">En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="20491-161">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7.  <span data-ttu-id="20491-162">En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="20491-162">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="20491-163">Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.</span><span class="sxs-lookup"><span data-stu-id="20491-163">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20491-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20491-164">Next Steps</span></span>  
 <span data-ttu-id="20491-165">Configurar la ubicación de recepción (**Receive_AS2**) para recibir el mensaje de AS2 de Fabrikam, tal y como se describe en [paso 6: configurar la ubicación de recepción de EDI y AS2](../core/step-6-configure-the-edi-as2-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="20491-165">You configure the receive location (**Receive_AS2**) to receive the AS2 message from Fabrikam, as described in [Step 6: Configure the EDI-AS2 Receive Location](../core/step-6-configure-the-edi-as2-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20491-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="20491-166">See Also</span></span>  
 [<span data-ttu-id="20491-167">Tutorial 3: Tutorial de AS2</span><span class="sxs-lookup"><span data-stu-id="20491-167">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)

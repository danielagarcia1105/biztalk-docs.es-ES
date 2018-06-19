---
title: Solucionar problemas de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12cd08ae9bee686946c8db14039504411506035f
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710259"
---
# <a name="troubleshooting-bam"></a><span data-ttu-id="3f2c7-102">Solución de problemas de BAM</span><span class="sxs-lookup"><span data-stu-id="3f2c7-102">Troubleshooting BAM</span></span>
<span data-ttu-id="3f2c7-103">En este tema se proporciona información que le ayudará a solucionar problemas que se pueden encontrar al usar la Supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="3f2c7-103">This topic provides information to help you troubleshoot problems you might encounter when using Business Activity Monitoring (BAM).</span></span>  
  
## <a name="bam-deployment-failed"></a><span data-ttu-id="3f2c7-104">Error de implementación de BAM</span><span class="sxs-lookup"><span data-stu-id="3f2c7-104">BAM deployment failed</span></span>  
 <span data-ttu-id="3f2c7-105">Si intenta implementar una definición de BAM que incluye una agregación en tiempo real (ATR) cuando SQL Server Analysis Services no está disponible, el comando Bm.exe mostrará el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-105">If you attempt to deploy a BAM definition that includes a real-time aggregation (RTA) when SQL Server Analysis Services is not available, the Bm.exe command will display the following message:</span></span>  
  
 <span data-ttu-id="3f2c7-106">ERROR: Error en la implementación de BAM.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-106">ERROR: BAM deployment failed.</span></span> <span data-ttu-id="3f2c7-107">No se puede establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-107">A connection cannot be made.</span></span> <span data-ttu-id="3f2c7-108">Asegúrese de que el servidor se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-108">Ensure that the server is running.</span></span> <span data-ttu-id="3f2c7-109">No se estableció ninguna conexión porque el equipo de destino rechazó  *\<dirección IP\>*.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-109">No connection could be made because the target machine actively refused it *\<IP address\>*.</span></span>  
  
 <span data-ttu-id="3f2c7-110">Esto se produce porque SQL Server Analysis Services debe estar instalado, configurado y en ejecución para implementar una definición de BAM que incluya una RTA.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-110">This occurs because SQL Server Analysis Services must have been installed and configured, and must be running in order to deploy a BAM definition that includes an RTA.</span></span>  
  
## <a name="cannot-refresh-the-live-data-workbook"></a><span data-ttu-id="3f2c7-111">No se puede actualizar el libro de trabajo de datos activos</span><span class="sxs-lookup"><span data-stu-id="3f2c7-111">Cannot refresh the live data workbook</span></span>  
 <span data-ttu-id="3f2c7-112">Cuando intenta actualizar los datos de un libro de trabajo de datos activos, es posible que Microsoft Office Excel muestre el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-112">When you try to refresh the data in a live data workbook, Microsoft Office Excel might display the following error:</span></span>  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 <span data-ttu-id="3f2c7-113">Esto se produce porque no se agregó en Excel el complemento de BAM.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-113">This occurs because the BAM add-in has not been added to Excel.</span></span>  
  
#### <a name="add-the-bam-add-in-to-excel"></a><span data-ttu-id="3f2c7-114">Agregar el complemento de BAM para Excel</span><span class="sxs-lookup"><span data-stu-id="3f2c7-114">Add the BAM add-in to Excel</span></span>  
  
1.  <span data-ttu-id="3f2c7-115">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-115">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="3f2c7-116">Haga clic en el **botón de Microsoft Office**y, a continuación, haga clic en **opciones de Excel**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-116">Click the **Microsoft Office Button**, and then click **Excel Options**.</span></span>  
  
3.  <span data-ttu-id="3f2c7-117">En el **opciones de Excel** cuadro de diálogo, haga clic en **Add-Ins**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-117">In the **Excel Options** dialog box, click **Add-Ins**.</span></span>  
  
4.  <span data-ttu-id="3f2c7-118">En el **Add-Ins** panel, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-118">In the **Add-Ins** pane, click **Go**.</span></span>  
  
5.  <span data-ttu-id="3f2c7-119">En el **Add-Ins** cuadro de diálogo, seleccione la **Business Activity Monitoring** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-119">In the **Add-Ins** dialog box, select the **Business Activity Monitoring** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3f2c7-120">![Agregar &#45; cuadro de diálogo de complementos](../core/media/addins.gif "AddIns")</span><span class="sxs-lookup"><span data-stu-id="3f2c7-120">![Add&#45;Ins dialog box](../core/media/addins.gif "AddIns")</span></span>  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a><span data-ttu-id="3f2c7-121">Error: "La biblioteca de objetos no es válida o contiene referencias a definiciones de objetos que no se encontraron" con el complemento Excel de BAM en Office</span><span class="sxs-lookup"><span data-stu-id="3f2c7-121">Error:"Object library invalid or contains references to object definitions that could not be found" with BAM Excel Add-In in Office</span></span>  
 <span data-ttu-id="3f2c7-122">Es posible que reciba este error al intentar usar el complemento de Excel BAM después de actualizar Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-122">You may receive this error, when you try use the BAM Excel Add-In after you upgrade Microsoft Excel.</span></span>  
  
 <span data-ttu-id="3f2c7-123">**Solución:** debido a que el complemento de BAM utiliza controles ActiveX, primero debe eliminar los archivos .exd en caché de los directorios siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-123">**Resolution:** Since the BAM Add-In uses ActiveX controls, you have to delete any cached .exd files from the following directories:</span></span>  
  
-   <span data-ttu-id="3f2c7-124">C:\Documents and Settings\\< nombre de usuario\>\Application Data\Microsoft\Forms</span><span class="sxs-lookup"><span data-stu-id="3f2c7-124">C:\Documents and Settings\\<username\>\Application Data\Microsoft\Forms</span></span>  
  
-   <span data-ttu-id="3f2c7-125">C:\Documents and Settings\\< nombre de usuario\>\AppData\Local\Temp\VBE</span><span class="sxs-lookup"><span data-stu-id="3f2c7-125">C:\Documents and Settings\\<username\>\AppData\Local\Temp\VBE</span></span>  
  
## <a name="bam-portal-cannot-connect"></a><span data-ttu-id="3f2c7-126">El portal de BAM no se puede establecer conexión</span><span class="sxs-lookup"><span data-stu-id="3f2c7-126">BAM portal cannot connect</span></span>  
<span data-ttu-id="3f2c7-127">Ejecutar el portal de BAM como administrador.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-127">Run the BAM portal as an administrator.</span></span>  
  
#### <a name="run-the-bam-portal"></a><span data-ttu-id="3f2c7-128">Ejecutar el portal de BAM</span><span class="sxs-lookup"><span data-stu-id="3f2c7-128">Run the BAM portal</span></span>
  
1.  <span data-ttu-id="3f2c7-129">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Internet Explorer**y, a continuación, haga clic en **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-129">Click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3f2c7-130">En el **User Account Control** cuadro de diálogo, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-130">In the **User Account Control** dialog box, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="3f2c7-131">En la barra de direcciones de Internet Explorer, escriba `http://<server>/BAM`, donde  *\<server\>*  es el nombre del equipo que ejecuta el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-131">In the Internet Explorer address bar, type `http://<server>/BAM`, where *\<server\>* is the name of the computer that is running the BAM portal.</span></span>  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a><span data-ttu-id="3f2c7-132">El portal de BAM no funciona si se otorgan permisos a usuarios no válidos</span><span class="sxs-lookup"><span data-stu-id="3f2c7-132">BAM portal does not work if invalid users are granted permissions</span></span>  
 <span data-ttu-id="3f2c7-133">Si se elimina de AD un usuario de AD que tiene permisos de visualización de BAM, el portal de BAM no se carga correctamente para otros usuarios (excepto DBO).</span><span class="sxs-lookup"><span data-stu-id="3f2c7-133">If an AD user who has the BAM view permissions is removed from the AD, then the BAM portal does not load properly for any user (except DBO).</span></span>  
  
 <span data-ttu-id="3f2c7-134">Para solucionar este problema, quite el usuario no válido del rol de seguridad bam_{viewname}view correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-134">To resolve this issue, remove the invalid user from the corresponding bam_{viewname}view security role.</span></span>  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a><span data-ttu-id="3f2c7-135">No se puede exportar una definición de BAM al host local ni importar del mismo</span><span class="sxs-lookup"><span data-stu-id="3f2c7-135">Cannot export or import a BAM definition to localhost</span></span>  
 <span data-ttu-id="3f2c7-136">Al exportar una definición de BAM como XML, verá el mensaje de error siguiente si intenta exportarla al host local:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-136">When you export a BAM definition as XML, you will see the following error message if you try to export to localhost:</span></span>  
  
 `The system cannot find the path specified.`  
  
 <span data-ttu-id="3f2c7-137">No se admite la exportación de una definición de BAM al host local.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-137">Exporting a BAM definition to localhost is not supported.</span></span> <span data-ttu-id="3f2c7-138">Del mismo modo, no se admite la importación de una definición de BAM desde el host local.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-138">Similarly, importing a BAM definition from localhost is not supported.</span></span>  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a><span data-ttu-id="3f2c7-139">Las alertas no funcionan después de actualizar las ediciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f2c7-139">Alerts do not work after upgrading SQL Server editions</span></span>  
 <span data-ttu-id="3f2c7-140">Si ha actualizado una edición de SQL Server a otra edición (por ejemplo, desde Standard Edition a Enterprise Edition), las alertas de BAM no se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-140">If you have upgraded from one edition of SQL Server to another edition (for example, from Standard Edition to Enterprise Edition), BAM alerts will not restart.</span></span> <span data-ttu-id="3f2c7-141">Para solucionar este problema, elimine las alertas de BAM y volver a crearlos o actualizar el servicio de notificación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-141">To fix this problem, either delete the BAM alerts and re-create them, or upgrade the SQL Server Notification Service.</span></span>  
  
#### <a name="upgrade-the-sql-server-notification-service"></a><span data-ttu-id="3f2c7-142">Actualizar el servicio de notificación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f2c7-142">Upgrade the SQL Server Notification Service</span></span>  
  
1.  <span data-ttu-id="3f2c7-143">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2005**y, a continuación, haga clic en **línea de comandos del servicio de notificación**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-143">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, and then click **Notification Service Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="3f2c7-144">Escriba el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-144">Type the following command at the command prompt:</span></span>  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a><span data-ttu-id="3f2c7-145">Excepción ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="3f2c7-145">ObjectDisposedException Exception</span></span>  
 <span data-ttu-id="3f2c7-146">Si la aplicación está usando el interceptor de WF 3.5 de BAM, puede recibir el siguiente mensaje de error: **System.ObjectDisposedException: no se puede obtener acceso a un objeto desechado**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-146">If your application is using BAM WF 3.5 interceptor, you may receive the following error message: **System.ObjectDisposedException: Cannot access a disposed object**.</span></span> <span data-ttu-id="3f2c7-147">Para obtener más información acerca de este mensaje de error, consulte [ObjectDisposedException Exception](https://support.microsoft.com/help/960754).</span><span class="sxs-lookup"><span data-stu-id="3f2c7-147">For more information about this error message, see [ObjectDisposedException Exception](https://support.microsoft.com/help/960754).</span></span> 

<span data-ttu-id="3f2c7-148">Para resolver este problema, instale el [revisión 960754](https://support.microsoft.com/help/960754).</span><span class="sxs-lookup"><span data-stu-id="3f2c7-148">To resolve this issue, install the [hotfix 960754](https://support.microsoft.com/help/960754).</span></span> 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a><span data-ttu-id="3f2c7-149">El libro de trabajo ha perdido su proyecto VBA, los controles ActiveX y otras características relacionadas con la programabilidad</span><span class="sxs-lookup"><span data-stu-id="3f2c7-149">Workbook has lost its VBA project, ActiveX controls and other programmability-related features</span></span>  
 <span data-ttu-id="3f2c7-150">Al intentar usar BAM.xla en Microsoft Excel, obtendrá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-150">When attempting to use BAM.xla in Microsoft Excel, you may get the following error:</span></span>  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 <span data-ttu-id="3f2c7-151">Para resolver este problema, instale el **Visual Basic para aplicaciones** opción **características compartidas de Office** con Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-151">To resolve this issue, install the **Visual Basic for Applications** option under **Office Shared Features** with Microsoft Office.</span></span>  
  
## <a name="pivot-table-fails-to-get-the-data"></a><span data-ttu-id="3f2c7-152">La tabla dinámica no obtiene los datos</span><span class="sxs-lookup"><span data-stu-id="3f2c7-152">Pivot table fails to get the data</span></span>  
 <span data-ttu-id="3f2c7-153">Dispone de permisos para obtener acceso a las bases de datos de BAM, además de rol y permisos en las vistas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-153">You have permissions to access BAM databases, and also role and permissions on the views which are deployed.</span></span> <span data-ttu-id="3f2c7-154">La página Búsqueda de actividad funciona según lo previsto y se pueden ver los datos.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-154">The Activity Search page works as expected and you can see the data.</span></span> <span data-ttu-id="3f2c7-155">Pero, en la tabla dinámica aparece el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-155">But, in the Pivot table, the following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 <span data-ttu-id="3f2c7-156">Para solucionar este problema, agregue los valores de configuración de DNS correspondientes, según se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-156">To resolve this issue, add the respective DNS settings as follows:</span></span>  
  
1.  <span data-ttu-id="3f2c7-157">Haga clic en **iniciar** y vaya a **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-157">Click **Start** and go to **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="3f2c7-158">Haga clic en **red e Internet** y, a continuación, haga clic en **las conexiones de red**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-158">Click **Network and Internet** and then click **Network Connections**.</span></span>  
  
3.  <span data-ttu-id="3f2c7-159">Haga doble clic en la conexión de red (por ejemplo, la conexión de área Local) y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-159">Right-click on the network connection (like Local Area Connection), and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="3f2c7-160">En el **conexión de área Local** página, seleccione **protocolo de Internet versión 4 (TCP/IPv4)** y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-160">On the **Local Area Connection** page, select **Internet Protocol Version 4 (TCP/IPv4)**, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3f2c7-161">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-161">Click **Advanced**.</span></span> <span data-ttu-id="3f2c7-162">En el **configuración de adelanto de TCP/IP** página, haga clic en el **DNS** ficha.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-162">On the **Advance TCP/IP Settings** page, click the **DNS** tab.</span></span>  
  
6.  <span data-ttu-id="3f2c7-163">Seleccione **anexar estos sufijos DNS** y, a continuación, agregue los sufijos DNS necesarios.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-163">Select **Append these DNS suffixes** and then add the required DNS suffixes.</span></span>  
  
7.  <span data-ttu-id="3f2c7-164">Haga clic en **Aceptar** y cierre todas las ventanas abiertas.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-164">Click **OK** and close all the open windows.</span></span>  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a><span data-ttu-id="3f2c7-165">La vista de tabla dinámica muestra todos los valores como "0"</span><span class="sxs-lookup"><span data-stu-id="3f2c7-165">Pivot table view shows all values as “0”</span></span>  
 <span data-ttu-id="3f2c7-166">Al implementar el portal de BAM, la página Búsqueda de actividad muestra los resultados previstos.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-166">When you deploy the BAM portal, the Activity Search page displays expected results.</span></span> <span data-ttu-id="3f2c7-167">Sin embargo, la vista de tabla dinámica muestra todos los valores como "0".</span><span class="sxs-lookup"><span data-stu-id="3f2c7-167">But, the Pivot table view displays all values as “0”.</span></span> <span data-ttu-id="3f2c7-168">Se muestra el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-168">The following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 <span data-ttu-id="3f2c7-169">Para solucionar este problema, agregue el sitio a la zona, según se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3f2c7-169">To resolve this issue, add the site to the zone as follows:</span></span>  
  
1.  <span data-ttu-id="3f2c7-170">En la ventana de Internet Explorer, haga clic en **herramientas**, a continuación, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-170">In the Internet Explorer window, click **Tools**, then click **Internet Options**.</span></span> <span data-ttu-id="3f2c7-171">Haga clic en el **seguridad** pestaña y, a continuación, seleccione la **sitios de confianza** zona.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-171">Click the **Security** tab, and then select the **Trusted sites** zone.</span></span>  
  
2.  <span data-ttu-id="3f2c7-172">Haga clic en **nivel personalizado** para establecer el nivel de seguridad para la zona.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-172">Click **Custom level** to set the security level for the zone.</span></span>  
  
3.  <span data-ttu-id="3f2c7-173">En el **configuración** página, en la **acceder a orígenes de datos a través de dominios** opción, haga clic en **Prompt**.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-173">On the **Settings** page, under the **Access data sources across domains** option, click **Prompt**.</span></span> <span data-ttu-id="3f2c7-174">Se le preguntará cuando un componente requiera este permiso.</span><span class="sxs-lookup"><span data-stu-id="3f2c7-174">You will be prompted when a component requires this permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2c7-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f2c7-175">See Also</span></span>  
 [<span data-ttu-id="3f2c7-176">Uso de la actividad económica de supervisión</span><span class="sxs-lookup"><span data-stu-id="3f2c7-176">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)
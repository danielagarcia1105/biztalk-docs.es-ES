---
title: "La configuración de alertas BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46ddba35a603217660df22668d548ca7c40eb5f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-bam-alerts"></a><span data-ttu-id="8f1ab-102">Configurar Alertas BAM</span><span class="sxs-lookup"><span data-stu-id="8f1ab-102">Configuring BAM Alerts</span></span>
<span data-ttu-id="8f1ab-103">Los administradores pueden modificar determinados elementos del marco de trabajo de alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-103">Administrators can modify certain elements of the BAM alert framework.</span></span> <span data-ttu-id="8f1ab-104">En este tema se describen las opciones de configuración disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-104">This topic describes the configuration options available to administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f1ab-105">A la hora de crear alertas, debe tener en cuenta que los datos de hora se almacenan con formato de hora local en las bases de datos de esquema de estrella y de servicios de notificación de OLAP.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-105">When creating alerts you should be aware that time data is stored in a Local Time format on the OLAP, Star Schema, and Notification Services databases.</span></span> <span data-ttu-id="8f1ab-106">También se presupone que las tres bases de datos se encuentran en la misma zona horaria.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-106">It is also assumed that all three databases are in the same time zone.</span></span> <span data-ttu-id="8f1ab-107">En la base de datos de importación principal, la información se almacena en formato de hora UTC, y puede encontrarse en la misma zona horaria o en una distinta.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-107">On the Primary Import database, information is stored in the UTC time format and can be in the same or different time zone.</span></span>  
  
## <a name="changing-the-adf-configuration"></a><span data-ttu-id="8f1ab-108">Cambiar la configuración de ADF</span><span class="sxs-lookup"><span data-stu-id="8f1ab-108">Changing the ADF configuration</span></span>  
 <span data-ttu-id="8f1ab-109">Al implementar una vista de la utilidad de administración de BAM utiliza el valor de CommandTimeout especificado en el archivo bm.exe.config para rellenar el archivo de definición de aplicación de Notification Services \<EventRule >\\< ActionTimeout\> elemento.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-109">When deploying a view the BAM Management utility uses the CommandTimeout value specified in the bm.exe.config file to populate Notification Services application definition file \<EventRule>\\<ActionTimeout\> element.</span></span>  
  
 <span data-ttu-id="8f1ab-110">El cambio del valor CommandTimeout en bm.exe.config no cambia el valor CommandTimeout de las vistas implementadas con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-110">Changing the value of CommandTimeout in bm.exe.config does not change the CommandTimeout value for views deployed prior to the change.</span></span>  
  
 <span data-ttu-id="8f1ab-111">El procedimiento siguiente utiliza ProcessBamNSFiles.vbs para obtener la configuración y el archivo de definición de aplicación de servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-111">The procedure below uses the ProcessBamNSFiles.vbs to obtain the configuration and the Notification Services application definition file.</span></span> <span data-ttu-id="8f1ab-112">Para obtener más información sobre la secuencia de comandos, consulte [secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="8f1ab-112">For more information on the script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
 <span data-ttu-id="8f1ab-113">Cómo cambiar ActionTimeout de NS en vistas ya implementadas:</span><span class="sxs-lookup"><span data-stu-id="8f1ab-113">How to change the ActionTimeout for NS for already deployed views:</span></span>  
  
#### <a name="to-change-the-command-timeout-value"></a><span data-ttu-id="8f1ab-114">Para cambiar el valor de tiempo de espera de comando</span><span class="sxs-lookup"><span data-stu-id="8f1ab-114">To change the command timeout value</span></span>  
  
1.  <span data-ttu-id="8f1ab-115">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-115">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="8f1ab-116">Navegue hasta la carpeta de seguimiento, escriba en el símbolo del sistema **cd "C:\Program Files\Microsoft BizTalk Server \<versión > \Tracking"** o **cd "C:\Program Files (x86) \Microsoft BizTalk Server \<versión > \Tracking "** en un equipo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-116">Navigate to the tracking folder by typing at the command prompt **cd “C:\Program Files\Microsoft BizTalk Server \<version>\Tracking”** or **cd “C:\Program Files (x86)\Microsoft BizTalk Server \<version>\Tracking”** on a 64 bit computer.</span></span> <span data-ttu-id="8f1ab-117">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-117">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="8f1ab-118">Recupere el archivo ADF.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-118">Retrieve the ADF file.</span></span> <span data-ttu-id="8f1ab-119">Tipo de **cscript ProcessBamNSFiles.vbs-Get \<ConfigFilePath > \<ADFFilePath > \< servidor PID > \< base de datos PID >**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-119">Type **cscript ProcessBamNSFiles.vbs -Get \<ConfigFilePath> \<ADFFilePath> \< PID Server> \< PID database >**.</span></span> <span data-ttu-id="8f1ab-120">Sustituya ConfigFilePath, ADFFilePath, Servidor PID y Base de datos PID con los valores apropiados para su instalación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-120">Replacing the ConfigFilePath, ADFFilePath, PID Server, and PID database with the appropriate values for your installation.</span></span>  
  
4.  <span data-ttu-id="8f1ab-121">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-121">Press **ENTER**.</span></span>  
  
5.  <span data-ttu-id="8f1ab-122">Abra el archivo ADF en un editor y busque \<ActionTimeout >, actualizar con el valor deseado y tenga en cuenta que este valor es una duración XML.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-122">Open the ADF file in an editor and search for \<ActionTimeout>, update with desired value & please note that this value is an XML duration.</span></span>  
  
6.  <span data-ttu-id="8f1ab-123">Guarde el archivo ADF.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-123">Save the ADF file.</span></span> <span data-ttu-id="8f1ab-124">Tipo de **cscript ProcessBamNSFiles.vbs-Update \<ConfigFilePath > \<ADFFilePath > \< servidor PID > \< base de datos PID >**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-124">Type **cscript ProcessBamNSFiles.vbs -Update \<ConfigFilePath> \<ADFFilePath> \< PID Server> \< PID database >**.</span></span>  
  
7.  <span data-ttu-id="8f1ab-125">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-125">Press **ENTER**.</span></span>  
  
### <a name="notification-service-configuration-tips"></a><span data-ttu-id="8f1ab-126">Sugerencias de configuración de los servicios de notificación</span><span class="sxs-lookup"><span data-stu-id="8f1ab-126">Notification Service configuration tips</span></span>  
 <span data-ttu-id="8f1ab-127">Si configura alertas BAM de modo que las bases de datos de alertas residan en un equipo remoto que ejecute [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], los componentes de bases de datos de los servicios de notificación deben estar instalados en la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-127">If you configure BAM Alerts in such a way as to place the Alerts databases on a remote computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], then the Notification Services Database Components must be installed on the SQL Server instance.</span></span> <span data-ttu-id="8f1ab-128">Si estos componentes no están presentes en la instancia de SQL, la configuración de alertas BAM generará un error que indicará que no se han podido conceder permisos a los procedimientos almacenados extendidos de los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-128">If these components are not present on the SQL instance, then configuration of BAM Alerts will fail with an error indicating that permissions could not be granted to the Notification Services Extended Stored Procedures.</span></span> <span data-ttu-id="8f1ab-129">Para obtener más información acerca de cómo instalar el componente de Notification Services, vea [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999).</span><span class="sxs-lookup"><span data-stu-id="8f1ab-129">For more information on installing the Notification Services component, see [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999).</span></span>  
  
 <span data-ttu-id="8f1ab-130">BAM le permite cambiar la cuenta que utiliza BAM para obtener acceso a los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-130">BAM allows you to change the account that BAM uses to access the Notification Services.</span></span> <span data-ttu-id="8f1ab-131">Si cambia esta cuenta de cualquier forma que no sea ejecutando NSControl, recibirá un error que le informará de que debe utilizar NSControl para cambiarla.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-131">If you change this account in any way other than running NSControl, you will receive an error informing you to use the NSControl to change the account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f1ab-132">No puede usar las cuentas LocalSystem o SYSTEM para instalar y configurar los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-132">You cannot use the LocalSystem or SYSTEM accounts for installing and configuring Notification Services.</span></span> <span data-ttu-id="8f1ab-133">Son cuentas especiales en las que no puede iniciar sesión y que no puede usar para conceder permisos de archivo y SQL Server al usuario de alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-133">These are special accounts that you cannot log on to and that you cannot use to grant file and SQL Server permissions to the BAM alerts user.</span></span>  
>   
>  <span data-ttu-id="8f1ab-134">Para instalar y configurar servicios de notificación, cree una nueva cuenta de usuario en el equipo local, concédala todos los permisos necesarios y, después, úsela para configurar los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-134">To install and configure Notification Services, create a new user account on the local computer, grant it all the requisite permissions, and then use it to configure Notification Services.</span></span>  
  
##### <a name="to-change-ns-user-account-for-bam"></a><span data-ttu-id="8f1ab-135">Para cambiar la cuenta de usuario de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="8f1ab-135">To change NS user account for BAM</span></span>  
  
1.  <span data-ttu-id="8f1ab-136">Utilice NSControl para actualizar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-136">Use NSControl to update the user account.</span></span>  
  
2.  <span data-ttu-id="8f1ab-137">Conceda al usuario de servicios de notificación los permisos de lectura, escritura y modificación en el directorio compartido Ubicación de archivo de alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-137">Grant the NS user read, write, and change permissions to the BAM Alerts File Location share.</span></span>  
  
3.  <span data-ttu-id="8f1ab-138">Agregue al usuario de servicios de notificación como miembro de la función NSRunService en las bases de datos de instancia y de aplicación de BAMAlerts.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-138">Add the NS user as a member of NSRunService role in both the BAMAlerts instance and application databases.</span></span>  
  
4.  <span data-ttu-id="8f1ab-139">Conceder los derechos de usuario en el equipo local mediante la documentación en [http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005).</span><span class="sxs-lookup"><span data-stu-id="8f1ab-139">Grant the NS User rights on the local machine using the documentation at [http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005).</span></span>  
  
5.  <span data-ttu-id="8f1ab-140">Conceda los derechos de NS para el servicio NS de base de datos según [http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008).</span><span class="sxs-lookup"><span data-stu-id="8f1ab-140">Grant the NS rights to the NS database according to [http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008).</span></span>  
  
6.  <span data-ttu-id="8f1ab-141">Conceda al usuario de servicios de notificación derechos de inicio de sesión en el servidor SQL Server y acceso de base de datos a la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-141">Grant the NS user login rights to SQL server and database access to the Primary Import database.</span></span>  
  
7.  <span data-ttu-id="8f1ab-142">Agregue al usuario de servicios de notificación en la función SQL BAM_ManagmentNSReader.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-142">Add the NS user to the BAM_ManagmentNSReader SQL role.</span></span>  
  
8.  <span data-ttu-id="8f1ab-143">Agregue al usuario de servicios de notificación en el rol “Alertas BAM” de la base de datos BamAnalysis.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-143">Add the NS user to the "BAM Alerts" role in BamAnalysis database.</span></span>  
  
 <span data-ttu-id="8f1ab-144">Si modifica la ubicación de descarga de archivos para las alertas entregadas por el archivo,</span><span class="sxs-lookup"><span data-stu-id="8f1ab-144">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="8f1ab-145">deberá reiniciar los servicios de notificación de SQL.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-145">You must restart the SQL Notifications Services.</span></span>  
  
 <span data-ttu-id="8f1ab-146">Si no se reinician los servicios de notificación, las alertas se seguirán entregando en la ubicación de entrega de archivos original.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-146">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="8f1ab-147">Para cambiar la ubicación de entrega de archivos, modifique la siguiente línea del archivo de configuración de BAM y use el comando update-config de la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="8f1ab-147">The file drop location is changed by modifying the following line of the BAM configuration file and using the BAM manangement utility update-config command.</span></span>  
  
 <span data-ttu-id="8f1ab-148">\<Nombre de propiedad = "FileDropUNC" >\\\\< nombre de equipo\>\alerts \< /Property ></span><span class="sxs-lookup"><span data-stu-id="8f1ab-148">\<Property Name="FileDropUNC">\\\\<computer name\>\alerts\</Property></span></span>  
  
 <span data-ttu-id="8f1ab-149">Para obtener más información sobre la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8f1ab-149">For more information on the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>
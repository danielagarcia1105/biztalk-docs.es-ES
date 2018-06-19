---
title: Cómo configurar el Portal de BAM para trabajar en un clúster NLB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20693f00d536414b44a7577277cf9acd3e5af530
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969690"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a><span data-ttu-id="e7002-102">Cómo configurar el portal de BAM para trabajar en un clúster NLB</span><span class="sxs-lookup"><span data-stu-id="e7002-102">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>
<span data-ttu-id="e7002-103">Se puede configurar el portal de BAM para trabajar en un clúster de equilibrio de carga de red (NLB).</span><span class="sxs-lookup"><span data-stu-id="e7002-103">The BAM portal can be configured to work in a network load balancing (NLB) cluster.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7002-104">Portal de BAM *sólo* se ejecuta en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e7002-104">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="e7002-105">Si se instala IIS en un equipo de 64 bits, debe comprobar que ASP.NET 2.0 esté habilitado en el modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e7002-105">If IIS is installed on a 64-bit machine, then confirm ASP.NET 2.0 is enabled in 32-bit mode.</span></span> <span data-ttu-id="e7002-106">Para ello, abra el Administrador de IIS, abra **grupo de aplicaciones**, seleccione el grupo de aplicaciones (BAMAppPool) y, a continuación, haga clic en **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="e7002-106">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="e7002-107">En **Habilitar aplicaciones de 32 bits**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="e7002-107">In **Enable 32-bit applications**, select **True**.</span></span>  
>   
>  <span data-ttu-id="e7002-108">Para los requisitos adicionales de Portal de BAM, consulte [planeación para el Portal de BAM](../core/planning-for-the-bam-portal.md).</span><span class="sxs-lookup"><span data-stu-id="e7002-108">For additional BAM Portal requirements, see [Planning for the BAM Portal](../core/planning-for-the-bam-portal.md).</span></span>  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a><span data-ttu-id="e7002-109">Para configurar el portal de BAM en un clúster NLB</span><span class="sxs-lookup"><span data-stu-id="e7002-109">To prepare to configure BAM portal on an NLB cluster</span></span>  
  
1.  <span data-ttu-id="e7002-110">Instale y configure el portal en el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="e7002-110">Install and configure the portal on the first computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-111">Sólo se configura el portal en el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="e7002-111">You only configure the portal on the first computer.</span></span> <span data-ttu-id="e7002-112">Tiene la opción de habilitar el portal de BAM en un equipo diferente o en otros equipos del clúster, pero la configuración sólo se realiza en el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="e7002-112">You have the option of enabling the BAM portal on other the other computers in the cluster, but the configuration is done only on the first computer.</span></span>  
  
2.  <span data-ttu-id="e7002-113">Instale los componentes del portal en todos los equipos que se van a incluir en el clúster NLB y, a continuación, una el resto de equipos del clúster al grupo de equipos de BizTalk en el que está configurado el portal.</span><span class="sxs-lookup"><span data-stu-id="e7002-113">Install the portal components on all the computers to be included in the NLB cluster, and then join the other computers in the cluster to the BizTalk group of the computer on which the portal is configured.</span></span> <span data-ttu-id="e7002-114">Debe habilitar los grupos de BizTalk Server y unirse al grupo apropiado.</span><span class="sxs-lookup"><span data-stu-id="e7002-114">You must enable the BizTalk groups and join the appropriate group.</span></span>  
  
3.  <span data-ttu-id="e7002-115">Seleccione la base de datos de administración de BizTalk que está configurada para el equipo en el que está instalado el portal.</span><span class="sxs-lookup"><span data-stu-id="e7002-115">Select the BizTalk Management database configured for the computer on which the portal is installed.</span></span>  
  
4.  <span data-ttu-id="e7002-116">Cree el clúster NLB</span><span class="sxs-lookup"><span data-stu-id="e7002-116">Create the NLB cluster.</span></span> <span data-ttu-id="e7002-117">Para obtener más información acerca de cómo crear y administrar clústeres de equilibrio de carga de red, vea "Crear y administrar red cargar clústeres de equilibrio" en [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).</span><span class="sxs-lookup"><span data-stu-id="e7002-117">For more information about how to create and manage network load balancing clusters, see "Create and Manage Network Load Balancing Clusters" at [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-118">Antes de continuar, debería confirmar que el clúster NLB funciona correctamente fuera del contexto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7002-118">You should confirm that your NLB cluster is working properly outside of the BizTalk Server context before continuing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-119">Para configurar NLB basado en hardware, consulte la documentación de su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="e7002-119">To set up hardware-based NLB, refer to your hardware provider's documentation.</span></span>  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a><span data-ttu-id="e7002-120">Para actualizar la configuración de BAM para reflejar la ubicación del clúster</span><span class="sxs-lookup"><span data-stu-id="e7002-120">To update the BAM configuration to reflect the location of the cluster</span></span>  
  
1.  <span data-ttu-id="e7002-121">Use la utilidad de administración de BAM para obtener la configuración actual de BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-121">Use the BAM Management Utility to get the current BAM configuration.</span></span> <span data-ttu-id="e7002-122">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y el tipo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config-MyConfig.</span><span class="sxs-lookup"><span data-stu-id="e7002-122">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config -FileName:MyConfig.xml.</span></span>  
  
2.  <span data-ttu-id="e7002-123">Reemplace el nombre de host local por el nombre del clúster NLB.</span><span class="sxs-lookup"><span data-stu-id="e7002-123">Replace the local host name with the name of the NLB cluster.</span></span> <span data-ttu-id="e7002-124">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\myconfig.</span><span class="sxs-lookup"><span data-stu-id="e7002-124">To do this, click **Start**, click **Run**, and type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml.</span></span>  
  
3.  <span data-ttu-id="e7002-125">Únicamente para NLB basado en hardware, compruebe que el archivo de configuración contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7002-125">For hardware-based NLB only, verify the configuration file has the following:</span></span>  
  
    ```  
    <GlobalProperty Name="BAMVRoot">  
    http://<NLB IP Address>:portname/BAM</GlobalProperty>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-126">Los pasos 4 y 5 no son necesarios cuando se actualiza la configuración BAM en NLB basado en hardware.</span><span class="sxs-lookup"><span data-stu-id="e7002-126">Steps 4 and 5 are not necessary when updating the BAM configuration on hardware-based NLB.</span></span>  
  
4.  <span data-ttu-id="e7002-127">Modifique la línea siguiente para seleccionar el clúster NLB al reemplazar el nombre del equipo (machinename) por el nombre del clúster:</span><span class="sxs-lookup"><span data-stu-id="e7002-127">Modify the following line to point to the NLB cluster by replacing the computer name (machinename) with the cluster name:</span></span>  
  
    ```  
    <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
    </GlobalProperty>   
    ```  
  
5.  <span data-ttu-id="e7002-128">Guarde la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="e7002-128">Save the new configuration.</span></span> <span data-ttu-id="e7002-129">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**y el tipo [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config-MyConfig.</span><span class="sxs-lookup"><span data-stu-id="e7002-129">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config -FileName:MyConfig.xml.</span></span>  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a><span data-ttu-id="e7002-130">Para editar el archivo web.config del portal de BAM para cambiar el BAMmanagementService y las URL de QueryService para que apunten al nombre del servidor de NLB.</span><span class="sxs-lookup"><span data-stu-id="e7002-130">To edit the BAM portal web.config file to change the BAMmanagementService and QueryService URLs to point to the NLB server name.</span></span> <span data-ttu-id="e7002-131">Nota: Este procedimiento no es necesario para NLB basado en hardware.</span><span class="sxs-lookup"><span data-stu-id="e7002-131">Note: This procedure is not necessary for hardware-based NLB.</span></span>  
  
1.  <span data-ttu-id="e7002-132">Abra el archivo web.config mediante el Bloc de notas haciendo clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Bamportal\web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7002-132">Open the web.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="e7002-133">Modifique el nombre de equipo (machinename) y el nombre de puerto siguientes en las dos líneas que aparecen a continuación para que señalen al nombre del clúster:</span><span class="sxs-lookup"><span data-stu-id="e7002-133">Modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
    ```  
  
3.  <span data-ttu-id="e7002-134">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="e7002-134">Save the file.</span></span> <span data-ttu-id="e7002-135">Para ello, haga clic en **archivo**y, a continuación, haga clic en **guardar** en la barra de menús del Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e7002-135">To do this, click **File**, and then click **Save** on the Notepad menu bar.</span></span>  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a><span data-ttu-id="e7002-136">Para configurar cada equipo adicional en el clúster</span><span class="sxs-lookup"><span data-stu-id="e7002-136">To configure each additional computer in the cluster</span></span>  
  
1.  <span data-ttu-id="e7002-137">Copie el archivo web.config en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal en cada equipo adicional del clúster.</span><span class="sxs-lookup"><span data-stu-id="e7002-137">Copy the web.config file to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal folder on each additional computer in the cluster.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-138">En los pasos siguientes todas las referencias a la **archivos de programa** carpeta será **archivos de programa (x86)** para equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e7002-138">In the following steps all references to the **Program Files** folder will be **Program Files (x86)** for 64 bit computers.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e7002-139">En los pasos siguientes, cuando crea directorios virtuales, asegúrese de que no hayan valores idénticos a los de los tres directorios virtuales de BAM que creó la configuración de BizTalk Server en el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="e7002-139">In the following steps, when you are creating the virtual directories, check to make sure they have the exact settings as the three BAM virtual directories created by the BizTalk Server Configuration on first computer.</span></span> <span data-ttu-id="e7002-140">Confirme las rutas de archivos, la versión de ASP.NET, los permisos de directorios y el grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7002-140">Confirm your file paths, the ASP.NET version, your directory permissions, and application pool.</span></span>  <span data-ttu-id="e7002-141">Utilice la misma cuenta de servicio de dominio para ejecutar BAMAppPool en el equipo que está configurando que la que utilizó para configurar el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="e7002-141">Use the same domain service account to run the BAMAppPool on the computer you are setting up as you used when setting up the first computer.</span></span> <span data-ttu-id="e7002-142">Asegúrese de que BAMAppPool se ejecuta en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="e7002-142">Make sure the BAMAppPool is running on all of the computers.</span></span> <span data-ttu-id="e7002-143">Hay dos archivos web.config que debe configurar.</span><span class="sxs-lookup"><span data-stu-id="e7002-143">There are two web.config files you must copy.</span></span>  
    >   
    >  <span data-ttu-id="e7002-144">Además del archivo web.config de [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, debe copiar el archivo web.config en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService y [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService en las mismas carpetas de este sistema.</span><span class="sxs-lookup"><span data-stu-id="e7002-144">In addition to the web.config file [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, you must copy the web.config file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService and [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService to the same folders on this computer.</span></span>  
  
2.  <span data-ttu-id="e7002-145">Únicamente para NLB basado en hardware, modifique el siguiente nombre de equipo (machinename) y el nombre de puerto de las dos líneas siguientes para que apunten al nombre del clúster:</span><span class="sxs-lookup"><span data-stu-id="e7002-145">For hardware-based NLB only, modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
    ```  
    <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
    <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
    ```  
  
3.  <span data-ttu-id="e7002-146">Cree un grupo de aplicaciones denominado BAMAppPool.</span><span class="sxs-lookup"><span data-stu-id="e7002-146">Create an application pool called BAMAppPool.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-147">La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, y %InstallationFolder%/BamPortal/BAMQueryService.</span><span class="sxs-lookup"><span data-stu-id="e7002-147">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
4.  <span data-ttu-id="e7002-148">Cree un directorio virtual en el sitio Web predeterminado denominado BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-148">Create a virtual directory under the Default Website called BAM.</span></span>  
  
5.  <span data-ttu-id="e7002-149">Cambie el grupo de aplicaciones del directorio virtual de BAM a BAMAppPool.</span><span class="sxs-lookup"><span data-stu-id="e7002-149">Change the application pool of BAM virtual directory to BAMAppPool.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-150">La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService y %InstallationFolder%/BamPortal/BAMQueryService.</span><span class="sxs-lookup"><span data-stu-id="e7002-150">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
6.  <span data-ttu-id="e7002-151">Cree un directorio virtual denominado BAMManagementService en BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-151">Create a virtual directory called BAMManagementService under BAM.</span></span>  
  
7.  <span data-ttu-id="e7002-152">Cambie el grupo de aplicaciones de BAMManagementService a BAMAppPool.</span><span class="sxs-lookup"><span data-stu-id="e7002-152">Change the application pool of BAMManagementService to BAMAppPool.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-153">La ruta de directorio para los directorios virtuales debería ser %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, y %InstallationFolder%/BamPortal/BAMQueryService.</span><span class="sxs-lookup"><span data-stu-id="e7002-153">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
8.  <span data-ttu-id="e7002-154">Cree un directorio virtual denominado BAMQueryService en BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-154">Create a virtual directory called BAMQueryService under BAM.</span></span>  
  
9. <span data-ttu-id="e7002-155">Cambie el grupo de aplicaciones de BAMQueryService a BAMAppPool.</span><span class="sxs-lookup"><span data-stu-id="e7002-155">Change the application pool of BAMQueryService to BAMAppPool.</span></span>  
  
10. <span data-ttu-id="e7002-156">Utilice el INETMGR, ubicado en el directorio virtual ficha ASP NET de propiedades, para cambiar la versión para BAM, BAMMANAGEMENTSERVICE y BAMQUERYSERVICE configurar la versión de las aplicaciones a .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e7002-156">Use the INETMGR, located on the virtual directory Properites ASP NET Tab, to change the version for BAM, BAMMANAGEMENTSERVICE, and BAMQUERYSERVICE to set the version of the Applications to .NET Framework 4.</span></span>  
  
11. <span data-ttu-id="e7002-157">Ejecute aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span><span class="sxs-lookup"><span data-stu-id="e7002-157">Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span></span>  <span data-ttu-id="e7002-158">Cuenta de servicio que se indica es la cuenta de usuario del servicio Web de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-158">The account specified here is the BAM Management Web Service User account.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e7002-159">Portal de BAM *sólo* se ejecuta en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e7002-159">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="e7002-160">Si se instala IIS en un equipo de 64 bits, ASP.NET 2.0 debe estar habilitado en el modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e7002-160">If IIS is installed on a 64-bit machine, ASP.NET 2.0 must be enabled in 32-bit mode.</span></span> <span data-ttu-id="e7002-161">Para ello, abra el Administrador de IIS, abra **grupo de aplicaciones**, seleccione el grupo de aplicaciones (BAMAppPool) y, a continuación, haga clic en **configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="e7002-161">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="e7002-162">En **Habilitar aplicaciones de 32 bits**, seleccione **True**.</span><span class="sxs-lookup"><span data-stu-id="e7002-162">In **Enable 32-bit applications**, select **True**.</span></span>  
    >   
    >  <span data-ttu-id="e7002-163">[Planeación del Portal de BAM](../core/planning-for-the-bam-portal.md) incluyen los requisitos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e7002-163">[Planning for the BAM Portal](../core/planning-for-the-bam-portal.md) lists additional requirements.</span></span>  
  
12. <span data-ttu-id="e7002-164">Configure la lectura ACL para el usuario AppPool en WebServices al ejecutar SubInACL, una herramienta de línea de comandos que permite a los administradores obtener información de seguridad sobre archivos, claves de Registro y servicios, así como transferir información de usuario a usuario, de grupo local o global a grupo, y de dominio a dominio.</span><span class="sxs-lookup"><span data-stu-id="e7002-164">Set the read ACLs for the AppPool user on WebServices by running SubInACL, a command-line tool that enables administrators to obtain security information about files, registry keys, and services, and to transfer this information from user to user, from local or global group to group, and from domain to domain.</span></span>  
  
13. <span data-ttu-id="e7002-165">Descargue SubInAcl desde [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).</span><span class="sxs-lookup"><span data-stu-id="e7002-165">Download SubInAcl from [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).</span></span>  
  
14. <span data-ttu-id="e7002-166">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e7002-166">Open a command prompt.</span></span> <span data-ttu-id="e7002-167">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7002-167">To do this, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="e7002-168">Escriba lo siguiente en el símbolo del sistema: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/ conceder = servicio de red = R"</span><span class="sxs-lookup"><span data-stu-id="e7002-168">Type the following at the command prompt: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/grant=Network Service=R"</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-169">El propósito de este comando es conceder acceso de lectura al usuario de grupo de aplicaciones de BAM a la clave del registro SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity.</span><span class="sxs-lookup"><span data-stu-id="e7002-169">The purpose of this command is to grant the BAM Application Pool user read access to the SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity registry key.</span></span> <span data-ttu-id="e7002-170">Este ejemplo utiliza el servicio de red ya que es el servicio predeterminado que utiliza IIS para el grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7002-170">The example uses Network Service since it is the default used by IIS for Application Pool.</span></span> <span data-ttu-id="e7002-171">Si no utiliza los valores predeterminados de IIS, debería sustituir al usuario del grupo de aplicaciones que utiliza la implementación.</span><span class="sxs-lookup"><span data-stu-id="e7002-171">If you do not use the default IIS settings, you should substitute the application pool user that your deployment uses.</span></span>  
  
16. <span data-ttu-id="e7002-172">Escriba lo siguiente en el símbolo del sistema: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3. 0" "/ conceder =\<BAM WebService Account\>"</span><span class="sxs-lookup"><span data-stu-id="e7002-172">Type the following at the command prompt: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0" "/grant=\<BAM WebService Account\>”</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-173">El objetivo de este comando es conceder a la cuenta de usuario del servicio Web de administración de BAM acceso de lectura a la clave del Registro SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity.</span><span class="sxs-lookup"><span data-stu-id="e7002-173">The purpose of this command is to grant the BAM Management Web Service User account read access to the SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity registry key.</span></span>  
  
17. <span data-ttu-id="e7002-174">Compruebe que la identidad del grupo de aplicaciones bajo el que se ejecuta el servicio web BAMManagement tiene acceso de lectura para la clave ASPNET_SETREG.</span><span class="sxs-lookup"><span data-stu-id="e7002-174">Verify that the identity that the application pool that the BAMManagement Web service runs under has read access to the ASPNET_SETREG key.</span></span>  
  
18. <span data-ttu-id="e7002-175">Utilice la herramienta de administrador de Administración de equipos para agregar al usuario de servicio Web de administración de BAM y a la cuenta de usuario de grupo de aplicaciones de BAM al grupo de proceso de trabajo de IIS (IIS_WPG) y al grupo de servicios (STS_WPG) de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e7002-175">Use the Computer Management administrator tool to add the BAM Management Web service user and the BAM application pool user account to the IIS Worker Process Group (IIS_WPG) and SharePoint services group (STS_WPG).</span></span>  
  
19. <span data-ttu-id="e7002-176">Establecer los permisos en las carpetas temporales de ASP.NET para el grupo de aplicaciones y usuarios del servicio Web: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0. \<número mínimo de versión\>\Temporary ASP.NET Files "/T /E /G \<BAM WebService Account\>: F</span><span class="sxs-lookup"><span data-stu-id="e7002-176">Set the permissions on the temporary ASP.NET folders for the applications pool and Web service users: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0.\<min version number\>\Temporary ASP.NET Files" /T /E /G \<BAM WebService Account\>:F</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7002-177">Concede acceso tanto a la cuenta de usuario de servicio Web de administración de BAM como a la cuenta de usuario de grupo de aplicaciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="e7002-177">You grant access to both the BAM Management Web Service User account and the BAM App Pool User account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7002-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7002-178">See Also</span></span>  
 [<span data-ttu-id="e7002-179">Administración del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="e7002-179">Managing the BAM Portal</span></span>](../core/managing-the-bam-portal.md)
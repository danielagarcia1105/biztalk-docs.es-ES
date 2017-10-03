---
title: "Utilidad de administración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7c36900c39f46f636077c5c9d0cb630265cc80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-management-utility"></a><span data-ttu-id="5f30c-102">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-102">BAM Management Utility</span></span>
<span data-ttu-id="5f30c-103">Los administradores de definiciones de Supervisión de la actividad económica (BAM) utilizan la utilidad de administración de BAM para administrar y mantener todos los aspectos de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="5f30c-103">Administrators of Business Activity Monitoring (BAM) definitions use the BAM Management utility to manage and maintain all aspects of the BAM infrastructure.</span></span>  
  
 <span data-ttu-id="5f30c-104">Puede usar la utilidad de BAM para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f30c-104">You can use the BAM utility to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5f30c-105">Utilizar definición de BAM y XML de configuración de BAM como entrada.</span><span class="sxs-lookup"><span data-stu-id="5f30c-105">Consume BAM definition and BAM configuration XML as input.</span></span> <span data-ttu-id="5f30c-106">Los archivos XML o XLS de definición de BAM establecen los datos que se van a agregar y de los que se va a realizar el seguimiento, así como la vista de los datos de seguimiento del usuario empresarial final.</span><span class="sxs-lookup"><span data-stu-id="5f30c-106">The BAM definition XML or XLS files define the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="5f30c-107">El XML de configuración de BAM dicta dónde implementar la infraestructura, como el nombre del servidor, nombre de la base de datos y otra configuración de base de datos.</span><span class="sxs-lookup"><span data-stu-id="5f30c-107">The BAM configuration XML mandates where to deploy the infrastructure, such as the server name, database name, and other database settings.</span></span>  
  
-   <span data-ttu-id="5f30c-108">Implemente la infraestructura en tiempo de ejecución en el servidor, que incluye la base de importación principal de BAM, la base de datos de esquema de estrella de BAM, la base de datos de análisis de BAM y los paquetes correspondientes de Servicios de transformación de datos (DTS).</span><span class="sxs-lookup"><span data-stu-id="5f30c-108">Deploy the run-time infrastructure on the server, which includes the BAM Primary Import database, BAM Star Schema database, BAM Analysis database, and corresponding Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="5f30c-109">Se crean los elementos siguientes en este paso:</span><span class="sxs-lookup"><span data-stu-id="5f30c-109">The following items are created during this step:</span></span>  
  
    -   <span data-ttu-id="5f30c-110">Base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-110">BAM Primary Import database</span></span>  
  
    -   <span data-ttu-id="5f30c-111">Base de datos de esquema de estrella de SAE</span><span class="sxs-lookup"><span data-stu-id="5f30c-111">BAM Star Schema database</span></span>  
  
    -   <span data-ttu-id="5f30c-112">Base de datos de archivo SAE</span><span class="sxs-lookup"><span data-stu-id="5f30c-112">BAM Archive database</span></span>  
  
    -   <span data-ttu-id="5f30c-113">Base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-113">BAM Analysis database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f30c-114">La configuración local del equipo donde se está ejecutando la utilidad de administración de BAM debe ser la misma que la configuración regional utilizada para crear la definición de BAM que se implementa para que los comandos de BAM funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="5f30c-114">The locale setting of the computer running the BAM Management utility must be the same as the locale used to create the BAM definition being deployed in order for the BAM commands to work properly.</span></span> <span data-ttu-id="5f30c-115">Por ejemplo, si ejecuta el **get-views** comando en un equipo configurado con una configuración regional en inglés configuración en una base de datos en un equipo con una configuración regional en francés no podrá usar el nombre de vista devuelta a menos que restablezca su configuración regional del equipo en francés.</span><span class="sxs-lookup"><span data-stu-id="5f30c-115">For example, if you execute the **get-views** command on a computer configured with an English locale setting against a database on a computer with a French locale you will not be able to use the returned view name unless you reset your computer locale to French.</span></span>  
  
 <span data-ttu-id="5f30c-116">Puede utilizar la utilidad de administración de BAM para generar e implementar su configuración de seguimiento en un servidor.</span><span class="sxs-lookup"><span data-stu-id="5f30c-116">You can use the BAM Management utility to generate and deploy your tracking configuration on a server.</span></span> <span data-ttu-id="5f30c-117">La utilidad de administración de BAM es una herramienta de línea de comandos situada en \< *ruta de acceso de instalación*> \Program BizTalk Server \<versión > \Tracking\BM.exe.</span><span class="sxs-lookup"><span data-stu-id="5f30c-117">The BAM Management utility is a command-line tool located at \<*installation path*>\Program Files\Microsoft BizTalk Server \<version>\Tracking\BM.exe.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f30c-118">Para ejecutar la utilidad de administración de BAM, debe ser miembro de la **db_owner** rol de base de datos de SQL Server en las bases de datos de importación principal de BAM, esquema de estrella de BAM y archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="5f30c-118">To run the BAM management utility, you must be member of the **db_owner** SQL Server Database role in the BAM Primary Import, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="5f30c-119">También debe tener permisos de sysadmin en las bases de datos de alertas de BAM si realiza las actualizaciones relacionadas con las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="5f30c-119">You must also have sysadmin permissions on the BAM Alerts databases if making any updates related to BAM Alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f30c-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f30c-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="5f30c-121">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="5f30c-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
## <a name="bam-management-utility-commands"></a><span data-ttu-id="5f30c-122">Comandos de la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-122">BAM Management Utility Commands</span></span>  
 <span data-ttu-id="5f30c-123">Las descripciones de comando usan estas convenciones:</span><span class="sxs-lookup"><span data-stu-id="5f30c-123">The command descriptions use these conventions:</span></span>  
  
-   <span data-ttu-id="5f30c-124">Los corchetes ([]) indican un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="5f30c-124">The square brackets ([]) indicate an optional parameter.</span></span>  
  
-   <span data-ttu-id="5f30c-125">Los corchetes angulares (<>) indican un parámetro requerido.</span><span class="sxs-lookup"><span data-stu-id="5f30c-125">The angled brackets (<>) indicate a required parameter.</span></span>  
  
-   <span data-ttu-id="5f30c-126">Las llaves ({}) indican que ese elemento se debe seleccionar en la lista enumerada.</span><span class="sxs-lookup"><span data-stu-id="5f30c-126">The braces ({}) indicate that one item should be selected from the enumerated list.</span></span>  
  
-   <span data-ttu-id="5f30c-127">Una cuenta de seguridad puede ser un grupo de NT o una cuenta individual de usuarios NT.</span><span class="sxs-lookup"><span data-stu-id="5f30c-127">A security account can be either an NT group or an individual NT user account.</span></span>  
  
-   <span data-ttu-id="5f30c-128">Un archivo de definición de BAM puede ser un archivo XML o un archivo de libro de Excel (.xls) de BAM.</span><span class="sxs-lookup"><span data-stu-id="5f30c-128">A BAM definition file can be either an XML file or a BAM Excel workbook file (.xls).</span></span>  
  
-   <span data-ttu-id="5f30c-129">Si no se proporciona el archivo de configuración de BAM, se predetermina un archivo BamConfiguration.xml en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="5f30c-129">If the BAM configuration file is not supplied, it defaults to BamConfiguration.xml in the current folder.</span></span>  
  
 <span data-ttu-id="5f30c-130">Las descripciones de comandos individuales se incluyen en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5f30c-130">The Individual command descriptions are contained in the following topics:</span></span>  
  
-   [<span data-ttu-id="5f30c-131">Comandos de base de datos</span><span class="sxs-lookup"><span data-stu-id="5f30c-131">Database Commands</span></span>](../core/database-commands.md)  
  
-   [<span data-ttu-id="5f30c-132">Implementación de comandos (modelo de observación) de definición de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-132">Deployment of BAM Definition (Observation Model) Commands</span></span>](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
-   [<span data-ttu-id="5f30c-133">Comandos de administración de infraestructura</span><span class="sxs-lookup"><span data-stu-id="5f30c-133">Infrastructure Management Commands</span></span>](../core/infrastructure-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-134">Comandos de administración de la actividad</span><span class="sxs-lookup"><span data-stu-id="5f30c-134">Activity Management Commands</span></span>](../core/activity-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-135">Comandos de administración de vista</span><span class="sxs-lookup"><span data-stu-id="5f30c-135">View Management Commands</span></span>](../core/view-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-136">Comandos de administración de alertas</span><span class="sxs-lookup"><span data-stu-id="5f30c-136">Alert Management Commands</span></span>](../core/alert-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-137">Comandos de administración de usuario</span><span class="sxs-lookup"><span data-stu-id="5f30c-137">User Management Commands</span></span>](../core/user-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-138">Comandos de administración de la suscripción de alerta</span><span class="sxs-lookup"><span data-stu-id="5f30c-138">Alert Subscription Management Commands</span></span>](../core/alert-subscription-management-commands.md)  
  
-   [<span data-ttu-id="5f30c-139">Comandos de administración de interceptor</span><span class="sxs-lookup"><span data-stu-id="5f30c-139">Interceptor Management Commands</span></span>](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a><span data-ttu-id="5f30c-140">Mostrar la Ayuda de la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-140">Displaying the BAM Management Utility Help</span></span>  
 <span data-ttu-id="5f30c-141">¿Usa el **/?**</span><span class="sxs-lookup"><span data-stu-id="5f30c-141">You use the **/?**</span></span> <span data-ttu-id="5f30c-142">o **ayuda de la utilidad de administración de BAM** comando para mostrar el archivo de Ayuda de la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="5f30c-142">or the **help BAM Management utility** command to display the Help file for the BAM Management utility.</span></span>  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a><span data-ttu-id="5f30c-143">Para mostrar el archivo de Ayuda de la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="5f30c-143">To display the Help file for the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="5f30c-144">Desde un símbolo del sistema, vaya al siguiente directorio: C:\Program Files\Microsoft BizTalk Server \<versión > \Tracking\\.</span><span class="sxs-lookup"><span data-stu-id="5f30c-144">From a command prompt, browse to the following directory: C:\Program Files\Microsoft BizTalk Server \<version>\Tracking\\.</span></span>  
  
2.  <span data-ttu-id="5f30c-145">Tipo de **bm** o **ayuda bm**.</span><span class="sxs-lookup"><span data-stu-id="5f30c-145">Type **bm** or **bm help**.</span></span>  
  
3.  <span data-ttu-id="5f30c-146">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="5f30c-146">Press ENTER.</span></span>
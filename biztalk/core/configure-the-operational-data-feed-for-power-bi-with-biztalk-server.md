---
title: Configurar los datos operativos fuentes para Power BI con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a><span data-ttu-id="db9fc-102">Configurar la fuente en Power BI con BizTalk Server de datos operativos</span><span class="sxs-lookup"><span data-stu-id="db9fc-102">Configure the operational data feed for Power BI with BizTalk Server</span></span>
<span data-ttu-id="db9fc-103">Leer datos operativos proporcionados a través de una fuente oData en [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db9fc-103">Read operational data provided through an oData feed in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="db9fc-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , enviar seguimiento a Power BI mediante la plantilla de Power BI proporcionan o crear los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="db9fc-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="db9fc-105">¿Qué es datos operativos</span><span class="sxs-lookup"><span data-stu-id="db9fc-105">What is operational data</span></span>
<span data-ttu-id="db9fc-106">Datos operativos están obtener información acerca de las instancias y los mensajes que fluyen a través de su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="db9fc-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="db9fc-107">La fuente de datos operativos es los mismos datos que desea obtener en el concentrador de grupo en el [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] consola.</span><span class="sxs-lookup"><span data-stu-id="db9fc-107">The operational data feed is the same data you get looking at Group Hub in the [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] console.</span></span> <span data-ttu-id="db9fc-108">Los datos son accesibles y consultan mediante herramientas de visualización, incluidos los Power BI.</span><span class="sxs-lookup"><span data-stu-id="db9fc-108">The data can be accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="db9fc-109">La fuente incluye las siguientes tablas de datos:</span><span class="sxs-lookup"><span data-stu-id="db9fc-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="db9fc-110">Datos de aplicación</span><span class="sxs-lookup"><span data-stu-id="db9fc-110">Application data</span></span>
* <span data-ttu-id="db9fc-111">AS2 Registros de estado</span><span class="sxs-lookup"><span data-stu-id="db9fc-111">AS2 Status Records</span></span>
* <span data-ttu-id="db9fc-112">Información de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="db9fc-112">Batching information</span></span>
* <span data-ttu-id="db9fc-113">Información de instancia</span><span class="sxs-lookup"><span data-stu-id="db9fc-113">Instance information</span></span>
* <span data-ttu-id="db9fc-114">Registros de agregaciones del intercambio</span><span class="sxs-lookup"><span data-stu-id="db9fc-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="db9fc-115">Registros de estado de intercambio</span><span class="sxs-lookup"><span data-stu-id="db9fc-115">Interchange Status Records</span></span>
* <span data-ttu-id="db9fc-116">Mensajes</span><span class="sxs-lookup"><span data-stu-id="db9fc-116">Messages</span></span>
* <span data-ttu-id="db9fc-117">Suscripciones</span><span class="sxs-lookup"><span data-stu-id="db9fc-117">Subscriptions</span></span>
* <span data-ttu-id="db9fc-118">Eventos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="db9fc-118">Tracked Events</span></span>
* <span data-ttu-id="db9fc-119">Informes de las transacciones</span><span class="sxs-lookup"><span data-stu-id="db9fc-119">Transaction reports</span></span>
* <span data-ttu-id="db9fc-120">Conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="db9fc-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="db9fc-121">[PowerBI.com](http://powerbi.microsoft.com) es un excelente recurso para comprender y aprender más acerca de Power BI.</span><span class="sxs-lookup"><span data-stu-id="db9fc-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db9fc-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="db9fc-122">Prerequisites</span></span>
* <span data-ttu-id="db9fc-123">Descargue e instale [Power BI Desktop](https://powerbi.microsoft.com/desktop/) en cualquier equipo que tenga acceso a la red a la[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db9fc-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="db9fc-124">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db9fc-124">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="db9fc-125">Instalar IIS en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db9fc-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="db9fc-126">En la mayoría [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos, IIS ya está instalado.</span><span class="sxs-lookup"><span data-stu-id="db9fc-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="db9fc-127">Vea [requisitos de Hardware y Software para BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="db9fc-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="enable-operational-data-feed"></a><span data-ttu-id="db9fc-128">Habilitar la fuente de datos operativas</span><span class="sxs-lookup"><span data-stu-id="db9fc-128">Enable operational data feed</span></span>

1. <span data-ttu-id="db9fc-129">Ejecutar Windows PowerShell como administrador (**iniciar** menú, escriba **PowerShell**, haga clic y seleccione **ejecutar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="db9fc-129">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="db9fc-130">Vaya a la carpeta donde [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] está instalado **(x86) de archivos de programa/Microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="db9fc-130">Browse to the folder where [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] is installed **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="db9fc-131">Ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="db9fc-131">Run the following command.</span></span> <span data-ttu-id="db9fc-132">Asegúrese de actualizar su `website`, `domain\user`, `password`, y `domain\group` con sus valores:</span><span class="sxs-lookup"><span data-stu-id="db9fc-132">Be sure to update your `website`, `domain\user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. <span data-ttu-id="db9fc-133">Después de ejecutar la secuencia de comandos, busque la nueva aplicación de IIS:</span><span class="sxs-lookup"><span data-stu-id="db9fc-133">After you run the script, browse the new IIS Application:</span></span>  
    1. <span data-ttu-id="db9fc-134">Abra el explorador web</span><span class="sxs-lookup"><span data-stu-id="db9fc-134">Open your web browser</span></span>
    2. <span data-ttu-id="db9fc-135">Vaya a **http://localhost/BizTalkOperationalDataService**</span><span class="sxs-lookup"><span data-stu-id="db9fc-135">Go to **http://localhost/BizTalkOperationalDataService**</span></span>

## <a name="use-the-power-bi-template"></a><span data-ttu-id="db9fc-136">Usar la plantilla de Power BI</span><span class="sxs-lookup"><span data-stu-id="db9fc-136">Use the Power BI template</span></span>
<span data-ttu-id="db9fc-137">Para obtener acceso al archivo de plantilla de Power BI y usar la visualización proporcionada de Microsoft, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="db9fc-137">To access the Power BI Template file, and use the provided visualization from Microsoft, use the following steps:</span></span>

1. <span data-ttu-id="db9fc-138">Descargue e instale el [Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span><span class="sxs-lookup"><span data-stu-id="db9fc-138">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span></span>
2. <span data-ttu-id="db9fc-139">Vaya a la carpeta de servidor BizTalk Server en **(x86) de archivos de programa \Microsoft BizTalk Server 2016\OperationalDataService**.</span><span class="sxs-lookup"><span data-stu-id="db9fc-139">Browse to your BizTalk Server folder under **Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService**.</span></span>
3. <span data-ttu-id="db9fc-140">Abra la **BizTalkOperationalData.pbit** archivo.</span><span class="sxs-lookup"><span data-stu-id="db9fc-140">Open the **BizTalkOperationalData.pbit** file.</span></span>
4. <span data-ttu-id="db9fc-141">Cuando se le pida desde Power BI, pegue la **http://localhost/\<yourWebSite\>**  dirección URL que ha creado para la fuente de OData.</span><span class="sxs-lookup"><span data-stu-id="db9fc-141">When prompted from Power BI, paste the **http://localhost/\<yourWebSite\>** URL that you created for your OData feed.</span></span> <span data-ttu-id="db9fc-142">Por ejemplo, escriba **http://localhost/OperationalDataService**.</span><span class="sxs-lookup"><span data-stu-id="db9fc-142">For example, enter **http://localhost/OperationalDataService**.</span></span> 

    <span data-ttu-id="db9fc-143">La dirección URL tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="db9fc-143">Your URL looks similar to the following:</span></span> 
    
    ![Pegue la dirección URL de OData en el archivo de plantilla de Power BI](../core/media/pasteurltopowerbitempaltefile.PNG)

5. <span data-ttu-id="db9fc-145">Seleccione **carga** para rellenar los campos en el informe de Power BI.</span><span class="sxs-lookup"><span data-stu-id="db9fc-145">Select **Load** to populate the fields in your Power BI report.</span></span> 
6. <span data-ttu-id="db9fc-146">El archivo de plantilla genera automáticamente la información y las tablas disponibles de la fuente de OData.</span><span class="sxs-lookup"><span data-stu-id="db9fc-146">The Template file automatically generates the information and tables available from the OData feed.</span></span>

<span data-ttu-id="db9fc-147">Los datos operativos se expone a través del equipo, pueden acceder y ejecutados por otras aplicaciones basadas en permisos.</span><span class="sxs-lookup"><span data-stu-id="db9fc-147">The operational data is exposed through the computer, and can be accessed and executed by other applications based on permissions.</span></span> 

<span data-ttu-id="db9fc-148">Para obtener más información sobre Power BI y cómo publicar el informe de online ir a [PowerBI.com](http://powerbi.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="db9fc-148">To learn more about Power BI, and how to publish the report online go to [PowerBI.com](http://powerbi.microsoft.com)</span></span>

## <a name="see-also"></a><span data-ttu-id="db9fc-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="db9fc-149">See also</span></span>

[<span data-ttu-id="db9fc-150">Más información acerca de Power BI</span><span class="sxs-lookup"><span data-stu-id="db9fc-150">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="db9fc-151">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="db9fc-151">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
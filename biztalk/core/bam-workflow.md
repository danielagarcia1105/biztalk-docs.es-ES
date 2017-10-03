---
title: Flujo de trabajo BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19356d6191963ec441f0b85c0e987c8515dcf1f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-workflow"></a><span data-ttu-id="8b707-102">Flujo de trabajo de BAM</span><span class="sxs-lookup"><span data-stu-id="8b707-102">BAM Workflow</span></span>
<span data-ttu-id="8b707-103">En la siguiente ilustración se muestran los cuatro roles de usuario que funcionan con Supervisión de la actividad económica, así como las herramientas que usan.</span><span class="sxs-lookup"><span data-stu-id="8b707-103">The following figure shows the four user roles who work with Business Activity Monitoring, and the tools that they use.</span></span>  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
<span data-ttu-id="8b707-104">Roles de BAM</span><span class="sxs-lookup"><span data-stu-id="8b707-104">BAM Roles</span></span>  
  
 <span data-ttu-id="8b707-105">Los pasos siguientes proporcionan información general de alto nivel sobre el flujo de trabajo para usar Supervisión de la actividad económica.</span><span class="sxs-lookup"><span data-stu-id="8b707-105">The following steps provide a high-level overview of the workflow for using Business Activity Monitoring.</span></span>  
  
## <a name="specifying-the-business-data-to-collect"></a><span data-ttu-id="8b707-106">Especificar los datos económicos que se desea recopilar</span><span class="sxs-lookup"><span data-stu-id="8b707-106">Specifying the business data to collect</span></span>  
 <span data-ttu-id="8b707-107">Los datos económicos se recopilan de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="8b707-107">Business data is collected in the following manner:</span></span>  
  
-   <span data-ttu-id="8b707-108">El analista de negocios usa el Asistente para actividad de BAM para especificar los datos que se deben recopilar para todos los usuarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="8b707-108">The business analyst uses the BAM Activity Wizard to specify what data to collect for all business users.</span></span>  
  
-   <span data-ttu-id="8b707-109">El analista de negocios usa el Asistente para vistas de BAM para definir la vista de cada categoría de usuario empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b707-109">The business analyst uses the BAM View Wizard to define the view for each category of business user.</span></span>  
  
-   <span data-ttu-id="8b707-110">Cuando termina, guarda las actividades y las vistas en un libro de trabajo de Microsoft® Excel llamado Libro de trabajo de definiciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="8b707-110">When finished, he saves the activities and views in a Microsoft® Excel Workbook called the BAM Definition Workbook.</span></span>  
  
-   <span data-ttu-id="8b707-111">El analista de negocios exporta el Libro de trabajo de definiciones de BAM a XML.</span><span class="sxs-lookup"><span data-stu-id="8b707-111">The business analyst exports the BAM Definition Workbook to XML.</span></span>  
  
-   <span data-ttu-id="8b707-112">El administrador del sistema y el programador usan el archivo XML para desempeñar sus roles.</span><span class="sxs-lookup"><span data-stu-id="8b707-112">The system administrator and developer use the XML to perform their roles.</span></span>  
  
-   <span data-ttu-id="8b707-113">Instrucciones para usar el libro de trabajo de la definición de BAM se encuentran en [definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8b707-113">Instructions for using the BAM Definition Workbook are located in [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
## <a name="managing-the-bam-infrastructure"></a><span data-ttu-id="8b707-114">Administrar la infraestructura de BAM</span><span class="sxs-lookup"><span data-stu-id="8b707-114">Managing the BAM Infrastructure</span></span>  
 <span data-ttu-id="8b707-115">Una vez que el analista haya definido la vista de BAM que desea, el administrador del sistema usa la utilidad de administración de BAM (BM.EXE), una herramienta de línea de comandos, para implementar la infraestructura de BAM desde el Libro de trabajo de definiciones de BAM o el XML exportado desde dicho libro.</span><span class="sxs-lookup"><span data-stu-id="8b707-115">After the business analyst has defined the BAM view he wants, the system administrator uses the BAM management utility (BM.EXE), a command-line tool, to deploy the BAM infrastructure from the BAM Definition Workbook or the XML exported from the workbook.</span></span>  
  
 <span data-ttu-id="8b707-116">La utilidad de administración de BAM crea dinámicamente las tablas, los desencadenadores, los paquetes DTS y los cubos de OLAP necesarios para que funcione la vista de BAM.</span><span class="sxs-lookup"><span data-stu-id="8b707-116">The BAM management utility dynamically creates the tables, triggers, DTS packages, and OLAP cubes necessary to support the BAM view.</span></span>  
  
 <span data-ttu-id="8b707-117">Cada vez que el analista de negocios defina una vista de BAM distinta o cambie una existente, el administrador del sistema deberá volver a implementar el Libro de trabajo de definiciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="8b707-117">Each time the business analyst defines a different BAM view, or changes an existing BAM view, the system administrator must redeploy the BAM Definition Workbook.</span></span>  
  
## <a name="mapping-the-xml-to-an-orchestration"></a><span data-ttu-id="8b707-118">Asignar el archivo XML a una orquestación</span><span class="sxs-lookup"><span data-stu-id="8b707-118">Mapping the XML to an orchestration</span></span>  
 <span data-ttu-id="8b707-119">Una vez que el analista de negocios haya exportado el Libro de trabajo de definiciones de BAM a XML, el programador importa el archivo XML al Editor de perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8b707-119">After the business analyst exports the BAM Definition Workbook to XML, the developer imports the XML file into the Tracking Profile Editor.</span></span> <span data-ttu-id="8b707-120">El programador implementa los requisitos de información del analista de negocios, y asigna el archivo XML a una orquestación.</span><span class="sxs-lookup"><span data-stu-id="8b707-120">The developer implements the business analyst's information requirements, mapping the XML to an orchestration.</span></span>  
  
 <span data-ttu-id="8b707-121">Mediante el Editor de perfiles de seguimiento, el programador asigna el archivo XML a una orquestación del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8b707-121">Using the Tracking Profile Editor, the developer performs the following steps to map the XML to an orchestration:</span></span>  
  
-   <span data-ttu-id="8b707-122">Carga el ensamblado implementado que se encuentra almacenado en la base de datos de administración de BizTalk (también llamada base de datos de configuración).</span><span class="sxs-lookup"><span data-stu-id="8b707-122">Loads the deployed assembly that is stored in the BizTalk Management database (also known as the Configuration database).</span></span> <span data-ttu-id="8b707-123">El ensamblado implementado contiene una o más orquestaciones correspondientes a los requisitos especificados por el analista de negocios en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8b707-123">The deployed assembly contains one or more orchestrations corresponding to the requirements that the business analyst specified in Step 1 above.</span></span>  
  
-   <span data-ttu-id="8b707-124">Define los datos que deben extraerse de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="8b707-124">Defines the data to be extracted from an orchestration.</span></span> <span data-ttu-id="8b707-125">Para ello, coloca elementos de los esquemas de mensaje y de las formas de orquestación en el hito económico (evento) y las carpetas de elementos de datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8b707-125">You do this by dropping items from the message schemas and orchestration shapes into the appropriate business milestone (event) and data item folders.</span></span>  
  
-   <span data-ttu-id="8b707-126">Cuando termina, guarda el perfil como un archivo de seguimiento de BizTalk® Server (.btt) en una base de datos de almacenamiento, tal como Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="8b707-126">When he is finished, he saves the profile as a BizTalk® Server tracking (.btt) file, to a storage database such as Visual SourceSafe.</span></span>  
  
 <span data-ttu-id="8b707-127">El programador implementa el archivo .btt en una base de datos de prueba y comprueba el resultado mediante la prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="8b707-127">The developer deploys the .btt file to a testing database, and verifies the result through integration testing.</span></span>  
  
## <a name="deploying-the-tracking-profile"></a><span data-ttu-id="8b707-128">Implementar el perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8b707-128">Deploying the Tracking Profile</span></span>  
 <span data-ttu-id="8b707-129">Mediante el Editor de perfiles de seguimiento, el administrador del sistema implementa el perfil en una o varias bases de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8b707-129">Using the Tracking Profile Editor, the system administrator deploys the profile to one or more BizTalk Management databases.</span></span>  
  
 <span data-ttu-id="8b707-130">Cada vez que el programador cambie la orquestación o cambien los requisitos de los usuarios empresariales y estos últimos desean someter más datos a seguimiento, el administrador del sistema deberá volver a implementar el perfil de seguimiento mediante la utilidad de línea de comandos bttdeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="8b707-130">Each time the developer changes the orchestration, or the requirements of the business users change and they want to track more data, the system administrator needs to redeploy the tracking profile using the bttdeploy.exe command line utility.</span></span>  
  
## <a name="viewing-the-business-data"></a><span data-ttu-id="8b707-131">Ver los datos económicos</span><span class="sxs-lookup"><span data-stu-id="8b707-131">Viewing the business data</span></span>  
 <span data-ttu-id="8b707-132">El usuario empresarial usa el libro de trabajo _LiveData, generado por la utilidad BM.exe.</span><span class="sxs-lookup"><span data-stu-id="8b707-132">The business user uses the _LiveData workbook, which is produced by the BM.exe utility.</span></span> <span data-ttu-id="8b707-133">Cada vez que el usuario empresarial abra el libro de trabajo _LiveData, recibirá una nueva versión en directo de los datos recopilados para supervisar un aspecto específico del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b707-133">Each time the business user opens the _LiveData workbook, he receives a new live version of the data that is collected to monitor a specific aspect of the business process.</span></span>  
  
-   <span data-ttu-id="8b707-134">Para ver los datos que se define como agregación en tiempo real, el usuario empresarial solo tiene que hacer clic en **actualizar** en el libro para ver los datos.</span><span class="sxs-lookup"><span data-stu-id="8b707-134">To view data that is defined as real-time aggregation, the business user just needs to click **Refresh** in the workbook to view the data.</span></span>  
  
-   <span data-ttu-id="8b707-135">Si los datos de la agregación no son de tiempo real, el usuario empresarial ve una instantánea tomada en el momento de ejecutarse el paquete DTS programado.</span><span class="sxs-lookup"><span data-stu-id="8b707-135">If the aggregation data is not real-time, the business user views a snapshot of the business data that is taken at the time that the scheduled DTS package runs.</span></span>  
  
-   <span data-ttu-id="8b707-136">Si la organización tiene requisitos de colaboración, el usuario empresarial puede tener acceso a los datos activos desde el sitio web de BAS.</span><span class="sxs-lookup"><span data-stu-id="8b707-136">If your organization has collaboration requirements, the business user can access the live data from the BAS Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b707-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b707-137">See Also</span></span>  
 <span data-ttu-id="8b707-138">[Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8b707-138">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="8b707-139">Supervisión de actividades económicas con BAM</span><span class="sxs-lookup"><span data-stu-id="8b707-139">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)
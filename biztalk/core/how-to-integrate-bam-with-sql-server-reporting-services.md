---
title: Cómo integrar BAM con SQL Server Reporting Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a55d0fa09267cc23d54533427da326e5028d3f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970258"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a><span data-ttu-id="9e09b-102">Integración de BAM con SQL Server 2005 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9e09b-102">How to Integrate BAM with SQL Server Reporting Services</span></span>
<span data-ttu-id="9e09b-103">La creación de un informe basado en datos en la infraestructura de BAM emplea las tareas habituales asociadas a la creación de un informe para cualquier otro origen de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9e09b-103">Creating a report based on data in the BAM infrastructure use the typical tasks associated with creating a report for any other SQL Server data source.</span></span> <span data-ttu-id="9e09b-104">Para obtener más información acerca de cómo crear un informe con el Diseñador de informes, consulte [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).</span><span class="sxs-lookup"><span data-stu-id="9e09b-104">For more information about creating a report with Report Designer, see [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e09b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e09b-105">Prerequisites</span></span>  
 <span data-ttu-id="9e09b-106">Debe disponer de los permisos para obtener acceso a los datos necesarios para crear el informe.</span><span class="sxs-lookup"><span data-stu-id="9e09b-106">You must have permissions to access the data necessary to create the report.</span></span>  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a><span data-ttu-id="9e09b-107">Cómo crear un informe en BAM mediante SQL Server Reporting Service</span><span class="sxs-lookup"><span data-stu-id="9e09b-107">How to Create a Report in BAM by Using SQL Server Reporting Service</span></span>  
  
1.  <span data-ttu-id="9e09b-108">Seleccione el origen de datos desde el que se creará el informe.</span><span class="sxs-lookup"><span data-stu-id="9e09b-108">Select the data source from which to create the report.</span></span>  
  
     <span data-ttu-id="9e09b-109">BAM proporciona dos orígenes de datos que Reporting Services puede seleccionar.</span><span class="sxs-lookup"><span data-stu-id="9e09b-109">BAM provides two data sources to which Reporting Services can point.</span></span>  
  
    |<span data-ttu-id="9e09b-110">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="9e09b-110">Data Source</span></span>|<span data-ttu-id="9e09b-111">Description</span><span class="sxs-lookup"><span data-stu-id="9e09b-111">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="9e09b-112">Base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="9e09b-112">BAM Primary Import database</span></span>|<span data-ttu-id="9e09b-113">Contiene vistas sobre instancias de actividad y agregaciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9e09b-113">Contains views on activity instances and real-time aggregations.</span></span> <span data-ttu-id="9e09b-114">Seleccione el tipo = "Microsoft SQL Server" y Connection String = "origen de datos =\<*nombre del servidor*\>; Catálogo inicial =\<*nombre de base de datos*\>", donde \< *nombre del servidor* \> y \< *base de datos nombre* \> son los nombres de servidor y base de datos de la base de datos de importación principal de Bam.</span><span class="sxs-lookup"><span data-stu-id="9e09b-114">Select Type=”Microsoft SQL Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your Bam Primary Import database.</span></span>|  
    |<span data-ttu-id="9e09b-115">Base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="9e09b-115">BAM Analysis database</span></span>|<span data-ttu-id="9e09b-116">Contiene datos utilizados para consultar el cubo de análisis.</span><span class="sxs-lookup"><span data-stu-id="9e09b-116">Contains data that is used to query the analysis cube.</span></span> <span data-ttu-id="9e09b-117">Seleccione el tipo = "Microsoft SQL Server Analysis Server" y Connection String = "origen de datos =\<*nombre del servidor*\>; Catálogo inicial =\<*nombre de base de datos*\>", donde \< *nombre del servidor* \> y \< *base de datos nombre* \> son los nombres de servidor y base de datos de la base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="9e09b-117">Select Type=”Microsoft SQL Server Analysis Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your BAM Analysis database.</span></span>|  
  
2.  <span data-ttu-id="9e09b-118">Diseñe la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e09b-118">Design the query.</span></span> <span data-ttu-id="9e09b-119">En el caso de la base de datos de importación principal de BAM, existen dos tipos de vistas:</span><span class="sxs-lookup"><span data-stu-id="9e09b-119">For the BAM Primary Import database, there are two types of views:</span></span>  
  
    |<span data-ttu-id="9e09b-120">Nombre de vista</span><span class="sxs-lookup"><span data-stu-id="9e09b-120">View Name</span></span>|<span data-ttu-id="9e09b-121">Description</span><span class="sxs-lookup"><span data-stu-id="9e09b-121">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="9e09b-122">dbo.bam_\<*nombre de la vista*\>_\<*nombre de la actividad*\>View_View.</span><span class="sxs-lookup"><span data-stu-id="9e09b-122">dbo.bam_\<*view name*\>_\<*activity name*\>View_View.</span></span>|<span data-ttu-id="9e09b-123">Esta vista contiene datos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="9e09b-123">This view contains instance data.</span></span>|  
    |<span data-ttu-id="9e09b-124">dbo.bam_\<*nombre de la vista*\>_\<*nombre de tabla de dinámica de agregación en tiempo real*\>_RTAView</span><span class="sxs-lookup"><span data-stu-id="9e09b-124">dbo.bam_\<*view name*\>_\<*real time aggregation pivot table name*\>_RTAView</span></span>|<span data-ttu-id="9e09b-125">Esta vista contiene datos utilizados en las agregaciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9e09b-125">This view contains data used in real-time aggregations.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="9e09b-126">Puede escribir **seleccione \* de vista** devolver el resultado deseado establecido.</span><span class="sxs-lookup"><span data-stu-id="9e09b-126">You can type **select \* from view** to return the desired result set.</span></span> <span data-ttu-id="9e09b-127">Para la base de datos de análisis de BAM, haga clic en el generador de consultas y arrastre las dimensiones y medidas del cubo denominado \< *nombre de la vista* \> devolver el resultado deseado establecido.</span><span class="sxs-lookup"><span data-stu-id="9e09b-127">For the BAM Analysis database, click the query builder and drag the dimensions and measures of the cube named \<*view name*\> to return the desired result set.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e09b-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9e09b-128">Next Steps</span></span>  
 <span data-ttu-id="9e09b-129">Complete los pasos del Asistente para informes con el fin de especificar qué datos va a presentar y el modo de presentación.</span><span class="sxs-lookup"><span data-stu-id="9e09b-129">Complete the steps in the Report Wizard to specify which data you are going to present and how the data is to be presented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e09b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e09b-130">See Also</span></span>  
 [<span data-ttu-id="9e09b-131">Administración de bases de datos de BAM</span><span class="sxs-lookup"><span data-stu-id="9e09b-131">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
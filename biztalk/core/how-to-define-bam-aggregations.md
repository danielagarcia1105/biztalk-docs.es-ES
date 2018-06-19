---
title: Cómo definir agregaciones de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1b5b377611eb8e28088cb2d0c2f2ed6f829de8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249516"
---
# <a name="how-to-define-bam-aggregations"></a><span data-ttu-id="89ee8-102">Cómo definir agregaciones de BAM</span><span class="sxs-lookup"><span data-stu-id="89ee8-102">How to Define BAM Aggregations</span></span>
<span data-ttu-id="89ee8-103">BAM admite dos tipos de agregación de datos:</span><span class="sxs-lookup"><span data-stu-id="89ee8-103">BAM supports two types of data aggregation:</span></span>  
  
-   <span data-ttu-id="89ee8-104">Agregaciones de procesamiento analítico en línea (OLAP)</span><span class="sxs-lookup"><span data-stu-id="89ee8-104">Online analytical processing (OLAP) aggregations</span></span>  
  
-   <span data-ttu-id="89ee8-105">Agregaciones en tiempo real (ATR)</span><span class="sxs-lookup"><span data-stu-id="89ee8-105">Real-time aggregations (RTA)</span></span>  
  
 <span data-ttu-id="89ee8-106">BAM usa Microsoft SQL Server Analysis para implementar agregaciones OLAP.</span><span class="sxs-lookup"><span data-stu-id="89ee8-106">BAM uses Microsoft SQL Server Analysis Services to implement OLAP aggregations.</span></span>  
  
 <span data-ttu-id="89ee8-107">Debe configurar los desencadenadores de la base de datos de importación principal de BAM para definir las ATR.</span><span class="sxs-lookup"><span data-stu-id="89ee8-107">You must configure the triggers on the BAM Primary Import database that define RTA.</span></span>  
  
### <a name="to-define-olap-aggregations"></a><span data-ttu-id="89ee8-108">Para definir las agregaciones OLAP</span><span class="sxs-lookup"><span data-stu-id="89ee8-108">To define OLAP aggregations</span></span>  
  
1.  <span data-ttu-id="89ee8-109">En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, desactive el botón ATR de la barra de herramientas y, por último, guarde el libro.</span><span class="sxs-lookup"><span data-stu-id="89ee8-109">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, clear the RTA toolbar button, and then save the workbook.</span></span>  
  
    -   <span data-ttu-id="89ee8-110">Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea [definir una vista de SAE](../core/defining-a-bam-view.md).</span><span class="sxs-lookup"><span data-stu-id="89ee8-110">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
2.  <span data-ttu-id="89ee8-111">Implemente el libro.</span><span class="sxs-lookup"><span data-stu-id="89ee8-111">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="89ee8-112">Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="89ee8-112">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="89ee8-113">Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="89ee8-113">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  
  
    -   <span data-ttu-id="89ee8-114">Para obtener información sobre la **DirectEventStream** de clases, consulte [clase DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span><span class="sxs-lookup"><span data-stu-id="89ee8-114">For information about the **DirectEventStream** class, see [DirectEventStream Class](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span>  
  
4.  <span data-ttu-id="89ee8-115">Ejecute el paquete de Servicios de transformación de datos (DTS) del cubo de actualización.</span><span class="sxs-lookup"><span data-stu-id="89ee8-115">Run the update cube Data Transformation Services (DTS) package.</span></span>  
  
    -   <span data-ttu-id="89ee8-116">Para obtener información acerca de cómo ejecutar el paquete DTS del cubo de actualización, vea [paquetes DTS de SAE](../core/bam-dts-packages.md).</span><span class="sxs-lookup"><span data-stu-id="89ee8-116">For information about running the update cube DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
5.  <span data-ttu-id="89ee8-117">Abra la copia de datos activos más reciente del libro para ver las agregaciones OLAP.</span><span class="sxs-lookup"><span data-stu-id="89ee8-117">Open the most recent live data copy of the workbook to see the OLAP aggregations.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="89ee8-118">Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes.</span><span class="sxs-lookup"><span data-stu-id="89ee8-118">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="89ee8-119">En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.</span><span class="sxs-lookup"><span data-stu-id="89ee8-119">Instead, BAM increments the file name of the live data copy.</span></span>  
  
### <a name="to-define-the-rta"></a><span data-ttu-id="89ee8-120">Para definir la ATR</span><span class="sxs-lookup"><span data-stu-id="89ee8-120">To define the RTA</span></span>  
  
1.  <span data-ttu-id="89ee8-121">En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, seleccione el botón ATR de la barra de herramientas y, a continuación, guarde el libro.</span><span class="sxs-lookup"><span data-stu-id="89ee8-121">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, select the RTA toolbar button, and then save the workbook.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="89ee8-122">No defina varias ATR que usan la misma actividad de BAM .</span><span class="sxs-lookup"><span data-stu-id="89ee8-122">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="89ee8-123">Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="89ee8-123">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
    -   <span data-ttu-id="89ee8-124">Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea "Definir una vista de actividad económica" y "Definir agregaciones" en la *Guía de usuario de los trabajadores de información*.</span><span class="sxs-lookup"><span data-stu-id="89ee8-124">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see "Defining a Business Activity View" and "Defining Aggregations" in the *Information Workers User Guide*.</span></span>  
  
2.  <span data-ttu-id="89ee8-125">Implemente el libro.</span><span class="sxs-lookup"><span data-stu-id="89ee8-125">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="89ee8-126">Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="89ee8-126">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="89ee8-127">Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="89ee8-127">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  

  
4.  <span data-ttu-id="89ee8-128">Abra la copia de datos activos más reciente del libro para ver las ATR.</span><span class="sxs-lookup"><span data-stu-id="89ee8-128">Open the most recent live data copy of the workbook to see the RTAs.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="89ee8-129">Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes.</span><span class="sxs-lookup"><span data-stu-id="89ee8-129">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="89ee8-130">En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.</span><span class="sxs-lookup"><span data-stu-id="89ee8-130">Instead, BAM increments the file name of the live data copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ee8-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="89ee8-131">See Also</span></span>  
 <span data-ttu-id="89ee8-132">[Paquetes DTS de BAM](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="89ee8-132">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 <span data-ttu-id="89ee8-133">[Cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="89ee8-133">[How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md) </span></span>  
 <span data-ttu-id="89ee8-134">[Actualización de OLAP y ATR propiedades de la cadena de conexión](../core/updating-olap-and-rta-connection-string-properties.md) </span><span class="sxs-lookup"><span data-stu-id="89ee8-134">[Updating OLAP and RTA Connection String Properties](../core/updating-olap-and-rta-connection-string-properties.md) </span></span>  
 [<span data-ttu-id="89ee8-135">Administración de la infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="89ee8-135">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)
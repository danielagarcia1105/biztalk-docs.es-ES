---
title: Cómo definir agregaciones de BAM | Microsoft Docs
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
ms.openlocfilehash: 57df4978f2b133794efd8fbdc99819bcedf144cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015909"
---
# <a name="how-to-define-bam-aggregations"></a><span data-ttu-id="41476-102">Cómo definir agregaciones de BAM</span><span class="sxs-lookup"><span data-stu-id="41476-102">How to Define BAM Aggregations</span></span>
<span data-ttu-id="41476-103">BAM admite dos tipos de agregación de datos:</span><span class="sxs-lookup"><span data-stu-id="41476-103">BAM supports two types of data aggregation:</span></span>  
  
- <span data-ttu-id="41476-104">Agregaciones de procesamiento analítico en línea (OLAP)</span><span class="sxs-lookup"><span data-stu-id="41476-104">Online analytical processing (OLAP) aggregations</span></span>  
  
- <span data-ttu-id="41476-105">Agregaciones en tiempo real (ATR)</span><span class="sxs-lookup"><span data-stu-id="41476-105">Real-time aggregations (RTA)</span></span>  
  
  <span data-ttu-id="41476-106">BAM usa Microsoft SQL Server Analysis para implementar agregaciones OLAP.</span><span class="sxs-lookup"><span data-stu-id="41476-106">BAM uses Microsoft SQL Server Analysis Services to implement OLAP aggregations.</span></span>  
  
  <span data-ttu-id="41476-107">Debe configurar los desencadenadores de la base de datos de importación principal de BAM para definir las ATR.</span><span class="sxs-lookup"><span data-stu-id="41476-107">You must configure the triggers on the BAM Primary Import database that define RTA.</span></span>  
  
### <a name="to-define-olap-aggregations"></a><span data-ttu-id="41476-108">Para definir las agregaciones OLAP</span><span class="sxs-lookup"><span data-stu-id="41476-108">To define OLAP aggregations</span></span>  
  
1.  <span data-ttu-id="41476-109">En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, desactive el botón ATR de la barra de herramientas y, por último, guarde el libro.</span><span class="sxs-lookup"><span data-stu-id="41476-109">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, clear the RTA toolbar button, and then save the workbook.</span></span>  
  
    -   <span data-ttu-id="41476-110">Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea [definir una vista de BAM](../core/defining-a-bam-view.md).</span><span class="sxs-lookup"><span data-stu-id="41476-110">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
2.  <span data-ttu-id="41476-111">Implemente el libro.</span><span class="sxs-lookup"><span data-stu-id="41476-111">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="41476-112">Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="41476-112">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="41476-113">Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="41476-113">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  
  
    -   <span data-ttu-id="41476-114">Para obtener información sobre la **DirectEventStream** de clases, vea [clase DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span><span class="sxs-lookup"><span data-stu-id="41476-114">For information about the **DirectEventStream** class, see [DirectEventStream Class](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span>  
  
4.  <span data-ttu-id="41476-115">Ejecute el paquete de Servicios de transformación de datos (DTS) del cubo de actualización.</span><span class="sxs-lookup"><span data-stu-id="41476-115">Run the update cube Data Transformation Services (DTS) package.</span></span>  
  
    -   <span data-ttu-id="41476-116">Para obtener información acerca de cómo ejecutar el paquete DTS del cubo de actualización, vea [paquetes DTS de BAM](../core/bam-dts-packages.md).</span><span class="sxs-lookup"><span data-stu-id="41476-116">For information about running the update cube DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
5.  <span data-ttu-id="41476-117">Abra la copia de datos activos más reciente del libro para ver las agregaciones OLAP.</span><span class="sxs-lookup"><span data-stu-id="41476-117">Open the most recent live data copy of the workbook to see the OLAP aggregations.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="41476-118">Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes.</span><span class="sxs-lookup"><span data-stu-id="41476-118">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="41476-119">En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.</span><span class="sxs-lookup"><span data-stu-id="41476-119">Instead, BAM increments the file name of the live data copy.</span></span>  
  
### <a name="to-define-the-rta"></a><span data-ttu-id="41476-120">Para definir la ATR</span><span class="sxs-lookup"><span data-stu-id="41476-120">To define the RTA</span></span>  
  
1.  <span data-ttu-id="41476-121">En el libro de Excel de BAM, cree una vista, agregue al menos una dimensión y una medida al informe de tabla dinámica, seleccione el botón ATR de la barra de herramientas y, a continuación, guarde el libro.</span><span class="sxs-lookup"><span data-stu-id="41476-121">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, select the RTA toolbar button, and then save the workbook.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="41476-122">No defina varias ATR que usan la misma actividad de BAM .</span><span class="sxs-lookup"><span data-stu-id="41476-122">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="41476-123">Si lo hace, los datos de ATR serán incorrectos cuando archive los datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="41476-123">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
    -   <span data-ttu-id="41476-124">Para obtener información acerca de cómo abrir el libro BAM, crear una vista y agregar dimensiones y medidas, vea "Definir una vista de actividad económica" y "Definir agregaciones" en el *Guía de usuario de los trabajadores de información*.</span><span class="sxs-lookup"><span data-stu-id="41476-124">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see "Defining a Business Activity View" and "Defining Aggregations" in the *Information Workers User Guide*.</span></span>  
  
2.  <span data-ttu-id="41476-125">Implemente el libro.</span><span class="sxs-lookup"><span data-stu-id="41476-125">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="41476-126">Para implementar el libro, siga las instrucciones de [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="41476-126">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="41476-127">Un programador de soluciones utiliza el **DirectEventStream** clase para importar eventos a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="41476-127">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  

  
4.  <span data-ttu-id="41476-128">Abra la copia de datos activos más reciente del libro para ver las ATR.</span><span class="sxs-lookup"><span data-stu-id="41476-128">Open the most recent live data copy of the workbook to see the RTAs.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="41476-129">Por motivos de seguridad, BAM no elimina del libro las copias de datos activos existentes.</span><span class="sxs-lookup"><span data-stu-id="41476-129">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="41476-130">En su lugar, BAM incrementa el nombre de archivo de la copia de datos activos.</span><span class="sxs-lookup"><span data-stu-id="41476-130">Instead, BAM increments the file name of the live data copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41476-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="41476-131">See Also</span></span>  
 <span data-ttu-id="41476-132">[Paquetes DTS de BAM](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="41476-132">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 <span data-ttu-id="41476-133">[Cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="41476-133">[How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md) </span></span>  
 <span data-ttu-id="41476-134">[Actualización de OLAP y ATR propiedades de la cadena de conexión](../core/updating-olap-and-rta-connection-string-properties.md) </span><span class="sxs-lookup"><span data-stu-id="41476-134">[Updating OLAP and RTA Connection String Properties](../core/updating-olap-and-rta-connection-string-properties.md) </span></span>  
 [<span data-ttu-id="41476-135">Administración de la infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="41476-135">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)
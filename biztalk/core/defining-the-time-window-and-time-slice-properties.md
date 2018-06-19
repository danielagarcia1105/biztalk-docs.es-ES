---
title: Definir el período de tiempo y las propiedades del período de tiempo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239060"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a><span data-ttu-id="ea932-102">Definir las propiedades del período de tiempo y de la ventana de tiempo</span><span class="sxs-lookup"><span data-stu-id="ea932-102">Defining the Time Window and Time Slice Properties</span></span>
<span data-ttu-id="ea932-103">Los administradores utilizan las propiedades TimeWindow y TimeSlice en el archivo BAMConfiguration.xml para determinar la actividad de los datos de las tablas de agregación en tiempo real de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="ea932-103">Administrators use the TimeWindow and the TimeSlice properties in the BAMConfiguration.xml file to define the life of the data in the real-time aggregation tables in the BAM primary import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea932-104">Para aprobar los cambios realizados en el archivo de configuración de BAM, los administradores deberán anular la implementación de la configuración de BAM actual, y después implementar el archivo BAMConfiguration.xml actualizado.</span><span class="sxs-lookup"><span data-stu-id="ea932-104">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="ea932-105">Para obtener información acerca de cómo anular la implementación de una definición de BAM, consulte [cómo quitar definiciones de BAM](../core/how-to-remove-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="ea932-105">For information about undeploying a BAM definition, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="ea932-106">Para obtener información acerca de cómo implementar una definición de BAM, consulte [cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="ea932-106">For information about deploying a BAM definition, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="ea932-107">Si desea cambiar los valores TimeWindow y TimeSlice sin anular la implementación de la infraestructura de BAM, modifique las columnas de la tabla BAM_Metadata_Activities en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="ea932-107">If you want to change the TimeWindow and TimeSlice values without undeploying the BAM infrastructure, you can modifying the columns in the BAM_Metadata_Activities table in the BAM primary import database.</span></span>  
  
## <a name="timeslice"></a><span data-ttu-id="ea932-108">TimeSlice</span><span class="sxs-lookup"><span data-stu-id="ea932-108">TimeSlice</span></span>  
 <span data-ttu-id="ea932-109">La propiedad TimeSlice se utiliza para agrupar datos de instancias completas de BAM.</span><span class="sxs-lookup"><span data-stu-id="ea932-109">You use the TimeSlice property to group completed BAM instance data.</span></span> <span data-ttu-id="ea932-110">La propiedad TimeSlice utiliza el tiempo en el que se escriben los datos como datos de la instancia del grupo de BAM en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="ea932-110">The TimeSlice property uses time that the data is written to the BAM primary import database to group BAM instance data.</span></span>  
  
 <span data-ttu-id="ea932-111">Por ejemplo, la instancia A se haya completado y se mantiene en la base de datos de importación principal de BAM en 1/1/2000 1:02 a.m.</span><span class="sxs-lookup"><span data-stu-id="ea932-111">For example, instance A is completed and persisted in the BAM primary import database at 1/1/2000 1:02 a.m.</span></span> <span data-ttu-id="ea932-112">La instancia B se haya completado y se mantiene en la base de datos de importación principal de BAM en 1/1/2000 1:04 a.m.</span><span class="sxs-lookup"><span data-stu-id="ea932-112">Instance B is completed and persisted in the BAM primary import database at 1/1/2000 1:04 a.m.</span></span> <span data-ttu-id="ea932-113">Si establece el valor de la propiedad TimeSlice en cinco minutos, la instancia A y B de la instancia se agrupan juntos.</span><span class="sxs-lookup"><span data-stu-id="ea932-113">If you set the value of the TimeSlice property to five minutes, instance A and instance B are grouped together.</span></span>  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a><span data-ttu-id="ea932-114">Para cambiar el valor TimeSlice en el archivo de configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="ea932-114">To change the TimeSlice value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="ea932-115">Cambie el valor en esta línea del archivo de configuración de BAM:</span><span class="sxs-lookup"><span data-stu-id="ea932-115">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="ea932-116">Para cambiar el valor TimeSlice en la tabla BAM_Metadata_Activities</span><span class="sxs-lookup"><span data-stu-id="ea932-116">To change the TimeSlice value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="ea932-117">Modifique los valores RTATimeSlic que se encuentran en la tabla bam_Metadata_Activities de la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="ea932-117">Modify the RTATimeSlice values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="ea932-118">Si implementa varias agregaciones en tiempo real (ATR) para una o más actividades, puede especificar una ventana de tiempo diferente para cada ATR.</span><span class="sxs-lookup"><span data-stu-id="ea932-118">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea932-119">El valor de la ventana ATR debe ser un número entero, mientras que la unidad de tiempo siempre son minutos.</span><span class="sxs-lookup"><span data-stu-id="ea932-119">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="timewindow"></a><span data-ttu-id="ea932-120">TimeWindow</span><span class="sxs-lookup"><span data-stu-id="ea932-120">TimeWindow</span></span>  
 <span data-ttu-id="ea932-121">Cuando ejecuta el paquete DTS de CubeUpdate, el paquete transporta datos desde la base de datos de importación principal de BAM a los cubos de BAM.</span><span class="sxs-lookup"><span data-stu-id="ea932-121">When you run the CubeUpdate DTS package, the package moves data from the BAM primary import database into the BAM cubes.</span></span> <span data-ttu-id="ea932-122">El paquete transporta datos de agregación en tiempo real como instancias de datos de BAM siempre que todos los datos del grupo tengan una antigüedad superior a la determinada en la propiedad de la ventana ATR.</span><span class="sxs-lookup"><span data-stu-id="ea932-122">The package moves real-time aggregation data as grouped BAM data instances after all of the data in the group is older than the age specified in the RTA window property.</span></span>  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a><span data-ttu-id="ea932-123">Para cambiar el valor TimeWindow en el archivo de configuración de BAM</span><span class="sxs-lookup"><span data-stu-id="ea932-123">To change the TimeWindow value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="ea932-124">Cambie el valor en esta línea del archivo de configuración de BAM:</span><span class="sxs-lookup"><span data-stu-id="ea932-124">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="ea932-125">Para cambiar el valor TimeWindow en la tabla BAM_Metadata_Activities</span><span class="sxs-lookup"><span data-stu-id="ea932-125">To change the TimeWindow value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="ea932-126">Modifique los valores RTAWindow que se encuentran en la tabla bam_Metadata_Activities de la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="ea932-126">Modify the RTAWindow values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="ea932-127">Si implementa varias agregaciones en tiempo real (ATR) para una o más actividades, puede especificar una ventana de tiempo diferente para cada ATR.</span><span class="sxs-lookup"><span data-stu-id="ea932-127">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea932-128">El valor de la ventana ATR debe ser un número entero, mientras que la unidad de tiempo siempre son minutos.</span><span class="sxs-lookup"><span data-stu-id="ea932-128">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea932-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea932-129">See Also</span></span>  
 <span data-ttu-id="ea932-130">[Esquema de configuración de BAM](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="ea932-130">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 [<span data-ttu-id="ea932-131">Recomendaciones de seguridad BAM</span><span class="sxs-lookup"><span data-stu-id="ea932-131">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)
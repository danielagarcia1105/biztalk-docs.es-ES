---
title: Archivar los datos de la base de datos de importación principal | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230420"
---
# <a name="archiving-primary-import-database-data"></a><span data-ttu-id="f904f-102">Archivar datos de la base de datos de importación principal</span><span class="sxs-lookup"><span data-stu-id="f904f-102">Archiving Primary Import Database Data</span></span>
<span data-ttu-id="f904f-103">Un administrador puede determinar la ventana de tiempo que se va a utilizar para archivar los datos de instancia de actividad en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="f904f-103">An administrator can specify the time window for archiving activity instance data in the primary import database.</span></span> <span data-ttu-id="f904f-104">Se utilizan las propiedades OnlineWindowTimeUnit y OnlineWindowTimeLength de la tabla BAM_Metadata_Activities en la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="f904f-104">You use the OnlineWindowTimeUnit and OnlineWindowTimeLength properties in the BAM_Metadata_Activities table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="f904f-105">Si los usuarios empresariales han implementado varias actividades, puede determinar una ventana de tiempo diferente para cada actividad.</span><span class="sxs-lookup"><span data-stu-id="f904f-105">If business users have deployed multiple activities, you can specify a different time window for each activity.</span></span> <span data-ttu-id="f904f-106">Para obtener información acerca de cómo implementar actividades, vea "Definir una actividad de negocio" en *Guía de usuario para trabajadores de información*.</span><span class="sxs-lookup"><span data-stu-id="f904f-106">For information about deploying activities, see "Defining a Business Activity" in *Information Workers Users Guide*.</span></span>  
  
 <span data-ttu-id="f904f-107">En la tabla siguiente se describen los valores que puede utilizar para OnlineWindowTimeUnit y OnlineWindowTimeLength.</span><span class="sxs-lookup"><span data-stu-id="f904f-107">The following table describes the values you can use for OnlineWindowTimeUnit and OnlineWindowTimeLength.</span></span>  
  
|<span data-ttu-id="f904f-108">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f904f-108">Property</span></span>|<span data-ttu-id="f904f-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f904f-109">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="f904f-110">OnlineWindowTimeUnit</span><span class="sxs-lookup"><span data-stu-id="f904f-110">OnlineWindowTimeUnit</span></span>|<span data-ttu-id="f904f-111">Esta propiedad puede ser: mes, día, hora o minuto.</span><span class="sxs-lookup"><span data-stu-id="f904f-111">This property can be: month, day, hour, or minute.</span></span> <span data-ttu-id="f904f-112">El valor predeterminado de esta propiedad es mes.</span><span class="sxs-lookup"><span data-stu-id="f904f-112">The default value of this property is month.</span></span>|  
|<span data-ttu-id="f904f-113">OnlineWindowTimeLength</span><span class="sxs-lookup"><span data-stu-id="f904f-113">OnlineWindowTimeLength</span></span>|<span data-ttu-id="f904f-114">Esta propiedad debe ser un entero.</span><span class="sxs-lookup"><span data-stu-id="f904f-114">This property must be an integer.</span></span> <span data-ttu-id="f904f-115">El valor predeterminado de esta propiedad es 6.</span><span class="sxs-lookup"><span data-stu-id="f904f-115">The default value of this property is 6.</span></span>|  
  
 <span data-ttu-id="f904f-116">BAM extrae datos de la base de datos de importación principal mediante partición, cuando la partición es más antigua que la ventana en línea (hora actual – OnlineWindowTimeLength de OnlineWindowTimeUnit).</span><span class="sxs-lookup"><span data-stu-id="f904f-116">BAM moves data out of the BAM primary import database by partition, when the partition is older than the online window (current time - OnlineWindowTimeLength of OnlineWindowTimeUnit).</span></span> <span data-ttu-id="f904f-117">Por ejemplo, se quitan las particiones anteriores a 5 días para OnlineWindowTimeLength = 5 y OnlineWindowTimeUnit = día.</span><span class="sxs-lookup"><span data-stu-id="f904f-117">For example, for OnlineWindowTimeLength = 5 and OnlineWindowTimeUnit = day, partitions older than 5 days are removed.</span></span>  
  
 <span data-ttu-id="f904f-118">BAM mueve datos de instancia de actividad a la base de datos de archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="f904f-118">BAM moves archived activity instance data into the BAM archiving database.</span></span> <span data-ttu-id="f904f-119">Durante la configuración de BAM para BizTalk se determina la base de datos de archivo de BAM.</span><span class="sxs-lookup"><span data-stu-id="f904f-119">You specify the BAM archiving database during BizTalk BAM Configuration.</span></span> <span data-ttu-id="f904f-120">Para obtener información acerca de la configuración de BAM de BizTalk, consulte [esquema de configuración de BAM](../core/bam-configuration-schema.md).</span><span class="sxs-lookup"><span data-stu-id="f904f-120">For information about BizTalk BAM configuration, see [BAM Configuration Schema](../core/bam-configuration-schema.md).</span></span>  
  
 <span data-ttu-id="f904f-121">BAM no archivará los datos de la instancia de actividad si no se ejecuta el paquete de Servicios de transformación de datos (DTS) de la actualización de cubos de BAM, que procesa los datos de la instancia en el cubo de actividad.</span><span class="sxs-lookup"><span data-stu-id="f904f-121">BAM will not archive activity instance data if you have not run the BAM cube update Data Transformation Services (DTS) package, which processes the instance data into the activity cube.</span></span>  
  
 <span data-ttu-id="f904f-122">Para obtener información acerca de cómo ejecutar el paquete DTS de mantenimiento de datos BAM, consulte [paquetes DTS de SAE](../core/bam-dts-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f904f-122">For information about running the BAM data maintenance DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
 <span data-ttu-id="f904f-123">Con el tiempo, la base de datos BAMArchive aumenta de tamaño según se vayan agregando datos de instancia de actividad.</span><span class="sxs-lookup"><span data-stu-id="f904f-123">Over time the BAMArchive database will grow in size as activity instance data is added.</span></span> <span data-ttu-id="f904f-124">Aunque no hay ningún modo sencillo de truncar una base de datos completa, puede truncar periódicamente el registro de transacciones de la base de datos para reducir los requisitos de almacenamiento y realizar una copia de seguridad periódica y archivar toda la base de datos BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="f904f-124">Although there is no straightforward way to truncate an entire database, you can periodically truncate the database transaction log to reduce the storage requirements, and you can periodically back up and archive the entire BAMArchive database.</span></span> <span data-ttu-id="f904f-125">Vea “Truncar el registro de transacciones” en los Libros en pantalla de SQL Server para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f904f-125">See “Truncating the transaction log” in SQL Server Books Online for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f904f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f904f-126">See Also</span></span>  
 <span data-ttu-id="f904f-127">[Definir el período de tiempo y las propiedades del período de tiempo](../core/defining-the-time-window-and-time-slice-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f904f-127">[Defining the Time Window and Time Slice Properties](../core/defining-the-time-window-and-time-slice-properties.md) </span></span>  
 [<span data-ttu-id="f904f-128">Administración de la infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="f904f-128">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)
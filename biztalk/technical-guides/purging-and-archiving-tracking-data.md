---
title: Depuración y el archivo de datos de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302940"
---
# <a name="purging-and-archiving-tracking-data"></a><span data-ttu-id="23040-102">Depuración y el archivo de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="23040-102">Purging and Archiving Tracking Data</span></span>
<span data-ttu-id="23040-103">Es importante configurar y habilitar el trabajo DTA Purge and Archive SQL Agent.</span><span class="sxs-lookup"><span data-stu-id="23040-103">It is important to configure and enable the DTA Purge and Archive SQL Agent job.</span></span> <span data-ttu-id="23040-104">Este trabajo archiva y purga los datos antiguos de la base de datos de seguimiento de BizTalk (DTA).</span><span class="sxs-lookup"><span data-stu-id="23040-104">This job archives and purges old data from the BizTalk Tracking (DTA) database.</span></span> <span data-ttu-id="23040-105">Esto es esencial para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.</span><span class="sxs-lookup"><span data-stu-id="23040-105">This is essential for a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="23040-106">Una base de datos de seguimiento grande empezarán a afectar al rendimiento del host de seguimiento y los demás procesos que consulta la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="23040-106">A large Tracking database will begin to affect the performance of the tracking host and any other processes that query the Tracking database.</span></span> <span data-ttu-id="23040-107">Si no se purgan los datos de seguimiento de la base de datos de seguimiento, la base de datos siguen creciendo a.</span><span class="sxs-lookup"><span data-stu-id="23040-107">If the tracking data is not purged from the Tracking database, the database will continue to grow.</span></span>  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a><span data-ttu-id="23040-108">Directrices para usar la DTA purgar y archivar trabajo</span><span class="sxs-lookup"><span data-stu-id="23040-108">Guidelines for Using the DTA Purge and Archive Job</span></span>  
  
-   <span data-ttu-id="23040-109">**Asegúrese de que el trabajo DTA Purge and Archive SQL Agent está correctamente configurado, habilitado y se completan correctamente.**</span><span class="sxs-lookup"><span data-stu-id="23040-109">**Ensure that the DTA Purge and Archive SQL Agent job is properly configured, enabled, and successfully completing.**</span></span>  
  
     <span data-ttu-id="23040-110">Este trabajo no está habilitado de forma predeterminada porque primero debe configurarlo para que incluya un directorio donde se pueden escribir los archivos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="23040-110">This job is not enabled by default because you must first configure it to include a directory where the archive files can be written.</span></span>  
  
-   <span data-ttu-id="23040-111">**Si solo necesita purgar los datos antiguos y no necesita archivarla en primer lugar y, después, cambiar el código SQL el trabajo del agente para llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase".**</span><span class="sxs-lookup"><span data-stu-id="23040-111">**If you only need to purge the old data and do not need to archive it first, then change the SQL Agent job to call the stored procedure “dtasp_PurgeTrackingDatabase”.**</span></span>  
  
     <span data-ttu-id="23040-112">Esto omite el paso de archivo y solo realiza la purga.</span><span class="sxs-lookup"><span data-stu-id="23040-112">This skips the archive step, and just does the purge.</span></span> <span data-ttu-id="23040-113">Para obtener más información acerca de este procedimiento almacenado y cambiar el trabajo del Agente SQL para utilizarla, vea ["How to purgar datos desde el BizTalk seguimiento Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).</span><span class="sxs-lookup"><span data-stu-id="23040-113">For more information about this stored procedure and changing the SQL Agent job to use it, see ["How to Purge Data from the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).</span></span>  
  
-   <span data-ttu-id="23040-114">**Asegúrese de que el trabajo está capacitado para purgar los datos de seguimiento de velocidad a la que se generan el seguimiento de los datos entrantes.**</span><span class="sxs-lookup"><span data-stu-id="23040-114">**Ensure that the job is able to purge the tracking data as fast as the incoming tracking data is generated.**</span></span>  
  
     <span data-ttu-id="23040-115">Es aceptable para el trabajo obtener durante las horas pico de carga, pero siempre debe ser capaz de ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="23040-115">It is acceptable for the job to get behind during peak load times, but it should always be able to catch up.</span></span> <span data-ttu-id="23040-116">Si el trabajo de purga se queda atrás y nunca es capaz de ponerse al día, siguen creciendo a la base de datos de seguimiento y rendimiento finalmente se verá afectado negativamente.</span><span class="sxs-lookup"><span data-stu-id="23040-116">If the purge job gets behind and is never able to catch up, the Tracking database will continue to grow, and performance will eventually be adversely affected.</span></span>  
  
-   <span data-ttu-id="23040-117">**Revise la purga condicional y purga incondicional parámetros para garantizar que se mantiene datos durante el período de tiempo óptimo.**</span><span class="sxs-lookup"><span data-stu-id="23040-117">**Review the soft purge and hard purge parameters to ensure that you are keeping data for the optimal length of time.**</span></span>  
  
     <span data-ttu-id="23040-118">Para obtener más información acerca de estos parámetros, consulte ["Archivado y purga el seguimiento de base de datos BizTalk"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).</span><span class="sxs-lookup"><span data-stu-id="23040-118">For more information about these parameters see ["Archiving and Purging the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).</span></span>  
  
-   <span data-ttu-id="23040-119">**Si necesita mantener el seguimiento de guardar los archivos, asegúrese de que tiene un proceso en su lugar para restaurar y utilizarlos correctamente.**</span><span class="sxs-lookup"><span data-stu-id="23040-119">**If you need to keep the tracking archive files, ensure that you have a process in place to successfully restore and use them.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23040-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="23040-120">See Also</span></span>  
 [<span data-ttu-id="23040-121">Lista de comprobación: Configurar SQL Server</span><span class="sxs-lookup"><span data-stu-id="23040-121">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)
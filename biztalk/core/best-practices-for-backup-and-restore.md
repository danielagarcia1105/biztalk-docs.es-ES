---
title: "Procedimientos recomendados para copias de seguridad y restauración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aaf721ba-50ce-4334-b86d-e856b54d3486
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23657dcc843744741d6315b6a8c18ca3d35e1fe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backup-and-restore"></a><span data-ttu-id="2e871-102">Prácticas recomendadas para efectuar copias de seguridad y restauraciones</span><span class="sxs-lookup"><span data-stu-id="2e871-102">Best Practices for Backup and Restore</span></span>
-   <span data-ttu-id="2e871-103">**Crear una copia de seguridad y plan de restauraciones**</span><span class="sxs-lookup"><span data-stu-id="2e871-103">**Create a backup and restore plan**</span></span>  
  
     <span data-ttu-id="2e871-104">Asegúrese de que el plan de copia de seguridad especifica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e871-104">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="2e871-105">El equipo en el que se almacenarán las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2e871-105">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="2e871-106">Los programas que se utilizarán para realizar una copia de seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="2e871-106">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="2e871-107">Los equipos de los que desea realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2e871-107">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="2e871-108">La programación en la que se realizará la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2e871-108">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="2e871-109">La ubicación fuera del sitio donde se archivarán las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2e871-109">The offsite location where you will archive backups</span></span>  
  
-   <span data-ttu-id="2e871-110">**Mantener un registro escrito de todos los cambios en el sistema BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="2e871-110">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
     <span data-ttu-id="2e871-111">Asegúrese de anotar todos los cambios que se han aplicado al sistema, como Service Packs, revisiones y QFE.</span><span class="sxs-lookup"><span data-stu-id="2e871-111">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="2e871-112">Esto es fundamental para que el sistema se restaure del modo más parecido posible al que existía antes de que se produjera el error en el hardware.</span><span class="sxs-lookup"><span data-stu-id="2e871-112">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
-   <span data-ttu-id="2e871-113">**Implementar las siguientes medidas para ayudar a prevenir o minimizar el efecto de un desastre:**</span><span class="sxs-lookup"><span data-stu-id="2e871-113">**Implement the following measures to help prevent or minimize the effect of a disaster:**</span></span>  
  
    -   <span data-ttu-id="2e871-114">Tenga disponibles las actualizaciones de software y firmware.</span><span class="sxs-lookup"><span data-stu-id="2e871-114">Have your software and firmware updates available.</span></span>  
  
    -   <span data-ttu-id="2e871-115">Tenga preparados todos los discos de instalación del software.</span><span class="sxs-lookup"><span data-stu-id="2e871-115">Have all software installation disks readily available.</span></span> <span data-ttu-id="2e871-116">Incluye el software del sistema (por ejemplo, unidades especializadas) y el software de aplicaciones (por ejemplo, BizTalk Server).</span><span class="sxs-lookup"><span data-stu-id="2e871-116">This includes both system software such as specialized drivers, and application software such as BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="2e871-117">Disponga de un plan para supervisar los servidores de forma proactiva.</span><span class="sxs-lookup"><span data-stu-id="2e871-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="2e871-118">Esta medida es muy importante, ya que las instancias de orquestación en un host con errores no puede recuperarlas un segundo host hasta que no transcurran diez minutos.</span><span class="sxs-lookup"><span data-stu-id="2e871-118">This is very important, since orchestration instances on a failed host may not be recovered by a second host for up to ten minutes.</span></span>  
  
    -   <span data-ttu-id="2e871-119">Mantenga registros del hardware.</span><span class="sxs-lookup"><span data-stu-id="2e871-119">Maintain hardware records.</span></span>  
  
    -   <span data-ttu-id="2e871-120">Mantenga registros del software.</span><span class="sxs-lookup"><span data-stu-id="2e871-120">Maintain software records.</span></span>  
  
-   <span data-ttu-id="2e871-121">**Implementar la tolerancia a errores en su organización en el nivel de hardware o software**</span><span class="sxs-lookup"><span data-stu-id="2e871-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
     <span data-ttu-id="2e871-122">La implementación de clústeres y la matriz redundante de discos independientes (RAID) posibilita que el sistema pueda recuperarse de un error en el hardware.</span><span class="sxs-lookup"><span data-stu-id="2e871-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
-   <span data-ttu-id="2e871-123">**Archivar los medios de copia de seguridad de forma regular en una ubicación segura**</span><span class="sxs-lookup"><span data-stu-id="2e871-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
     <span data-ttu-id="2e871-124">Cree una programación para archivar los medios de copia de seguridad de forma periódica y mantenga los archivos en una ubicación segura y fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="2e871-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="2e871-125">Con este procedimiento, se asegura la disponibilidad de una copia de seguridad para cuando resulte necesaria.</span><span class="sxs-lookup"><span data-stu-id="2e871-125">This ensures that you have a backup available when you need it.</span></span>  
  
-   <span data-ttu-id="2e871-126">**Comprobar la integridad de las copias de seguridad y que se producen sin errores**</span><span class="sxs-lookup"><span data-stu-id="2e871-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
     <span data-ttu-id="2e871-127">Supervise todos los trabajos de copia de seguridad y asegúrese de que finalizan sin errores.</span><span class="sxs-lookup"><span data-stu-id="2e871-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
-   <span data-ttu-id="2e871-128">**Mantener hardware idéntico de repuesto disponible**</span><span class="sxs-lookup"><span data-stu-id="2e871-128">**Keep identical spare hardware available**</span></span>  
  
     <span data-ttu-id="2e871-129">Al tener disponible un hardware idéntico de repuesto se asegura poder reemplazar con rapidez el hardware defectuoso y comenzar a trabajar con él sin dilación.</span><span class="sxs-lookup"><span data-stu-id="2e871-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up-and-running more quickly.</span></span>  
  
-   <span data-ttu-id="2e871-130">**Documentar y probar los procedimientos de recuperación**</span><span class="sxs-lookup"><span data-stu-id="2e871-130">**Document and test your recovery procedures**</span></span>  
  
     <span data-ttu-id="2e871-131">Lo ideal sería que se ejecutara la prueba de recuperación ante desastres, antes de ejecutar el sistema en producción.</span><span class="sxs-lookup"><span data-stu-id="2e871-131">Ideally, disaster recovery testing should be conducted before running your system in production.</span></span> <span data-ttu-id="2e871-132">Al tener planes y llevar a cabo pruebas de versiones preliminares, se asegura de que el personal de IT pueda recuperar los sistemas de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e871-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span> <span data-ttu-id="2e871-133">Generalmente significa que debe intentar de forma periódica restaurar la copia de seguridad del sistema en el hardware real que usará.</span><span class="sxs-lookup"><span data-stu-id="2e871-133">This generally means that you must periodically attempt to retore the system backup to the actual hardware you will use</span></span>  
  
-   <span data-ttu-id="2e871-134">**Entrenar su personal de TI en los procedimientos de recuperación ante desastres**</span><span class="sxs-lookup"><span data-stu-id="2e871-134">**Train your IT staff on disaster recovery procedures**</span></span>  
  
     <span data-ttu-id="2e871-135">Asegúrese de que el personal de IT cuenta con los conocimientos adecuados para recuperar el sistema si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="2e871-135">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
-   <span data-ttu-id="2e871-136">**Practicar la restauración de copia de seguridad en un entorno de prueba**</span><span class="sxs-lookup"><span data-stu-id="2e871-136">**Practice restoring from backup in a test environment**</span></span>  
  
     <span data-ttu-id="2e871-137">Practique la recuperación del sistema BizTalk Server en un entorno de prueba para asegurarse de que puede restaurarlo en el entorno de producción si se produce un fallo.</span><span class="sxs-lookup"><span data-stu-id="2e871-137">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e871-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e871-138">See Also</span></span>  
 [<span data-ttu-id="2e871-139">Copia de seguridad y restauración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2e871-139">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)
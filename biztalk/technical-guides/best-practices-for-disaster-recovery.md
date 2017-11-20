---
title: "Procedimientos recomendados para la recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afbb0a57-0d31-4a2f-847c-02b40361c0ed
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e988055205203c5c4bc7a4d9d6e84706414967c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-disaster-recovery"></a><span data-ttu-id="f822b-102">Prácticas recomendadas para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="f822b-102">Best Practices for Disaster Recovery</span></span>
<span data-ttu-id="f822b-103">Para obtener información sobre los procedimientos recomendados para la recuperación ante desastres para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], consulte [prácticas recomendadas para la copia de seguridad y restauración](http://go.microsoft.com/fwlink/?LinkId=151391) (http://go.microsoft.com/fwlink/?LinkId=151391) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="f822b-103">For information about best practices for disaster recovery for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see [Best Practices for Backup and Restore](http://go.microsoft.com/fwlink/?LinkId=151391) (http://go.microsoft.com/fwlink/?LinkId=151391) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="f822b-104">**Crear una copia de seguridad y plan de restauraciones**</span><span class="sxs-lookup"><span data-stu-id="f822b-104">**Create a backup and restore plan**</span></span>  
  
-   <span data-ttu-id="f822b-105">Asegúrese de que el plan de copia de seguridad especifica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f822b-105">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="f822b-106">El equipo en el que se almacenarán las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f822b-106">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="f822b-107">Los programas que se utilizarán para realizar una copia de seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="f822b-107">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="f822b-108">Los equipos de los que desea realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f822b-108">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="f822b-109">La programación en la que se realizará la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f822b-109">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="f822b-110">La ubicación fuera del sitio donde se archivarán las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f822b-110">The offsite location where you will archive backups</span></span>  
  
 <span data-ttu-id="f822b-111">**Mantener un registro escrito de todos los cambios en el sistema BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="f822b-111">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
-   <span data-ttu-id="f822b-112">Asegúrese de anotar todos los cambios que se han aplicado al sistema, como Service Packs, revisiones y QFE.</span><span class="sxs-lookup"><span data-stu-id="f822b-112">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="f822b-113">Esto es fundamental para que el sistema se restaure del modo más parecido posible al que existía antes de que se produjera el error en el hardware.</span><span class="sxs-lookup"><span data-stu-id="f822b-113">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
 <span data-ttu-id="f822b-114">**Implementar las siguientes medidas para ayudar a prevenir o minimizar el efecto de un desastre**</span><span class="sxs-lookup"><span data-stu-id="f822b-114">**Implement the following measures to help prevent or minimize the effect of a disaster**</span></span>  
  
-   <span data-ttu-id="f822b-115">Tenga disponibles las actualizaciones de software y firmware.</span><span class="sxs-lookup"><span data-stu-id="f822b-115">Have your software and firmware updates available.</span></span>  
  
-   <span data-ttu-id="f822b-116">Procure que todos los discos de software se encuentren disponibles y se pueda tener acceso a ellos con facilidad.</span><span class="sxs-lookup"><span data-stu-id="f822b-116">Have all software disks readily available.</span></span>  
  
-   <span data-ttu-id="f822b-117">Disponga de un plan para supervisar los servidores de forma proactiva.</span><span class="sxs-lookup"><span data-stu-id="f822b-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="f822b-118">Esto es muy importante, ya que las instancias de orquestación en un host con errores no se pueden recuperar un segundo host hasta 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="f822b-118">This is very important since orchestration instances on a failed host may not be recovered by a second host for up to 10 minutes.</span></span>  
  
-   <span data-ttu-id="f822b-119">Mantenga registros del hardware.</span><span class="sxs-lookup"><span data-stu-id="f822b-119">Maintain hardware records.</span></span>  
  
-   <span data-ttu-id="f822b-120">Mantenga registros del software.</span><span class="sxs-lookup"><span data-stu-id="f822b-120">Maintain software records.</span></span>  
  
 <span data-ttu-id="f822b-121">**Implementar la tolerancia a errores en su organización en el nivel de hardware o software**</span><span class="sxs-lookup"><span data-stu-id="f822b-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
-   <span data-ttu-id="f822b-122">La implementación de clústeres y la matriz redundante de discos independientes (RAID) posibilita que el sistema pueda recuperarse de un error en el hardware.</span><span class="sxs-lookup"><span data-stu-id="f822b-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
 <span data-ttu-id="f822b-123">**Archivar los medios de copia de seguridad de forma regular en una ubicación segura**</span><span class="sxs-lookup"><span data-stu-id="f822b-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
-   <span data-ttu-id="f822b-124">Cree una programación para archivar los medios de copia de seguridad de forma periódica y mantenga los archivos en una ubicación segura y fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="f822b-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="f822b-125">Con este procedimiento, se asegura la disponibilidad de una copia de seguridad para cuando resulte necesaria.</span><span class="sxs-lookup"><span data-stu-id="f822b-125">This ensures that you have a backup available when you need it.</span></span>  
  
 <span data-ttu-id="f822b-126">**Comprobar la integridad de las copias de seguridad y que se producen sin errores**</span><span class="sxs-lookup"><span data-stu-id="f822b-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
-   <span data-ttu-id="f822b-127">Supervise todos los trabajos de copia de seguridad y asegúrese de que finalizan sin errores.</span><span class="sxs-lookup"><span data-stu-id="f822b-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
 <span data-ttu-id="f822b-128">**Mantener hardware idéntico de repuesto disponible**</span><span class="sxs-lookup"><span data-stu-id="f822b-128">**Keep identical spare hardware available**</span></span>  
  
-   <span data-ttu-id="f822b-129">La existencia de hardware idéntico de repuesto disponible, se garantiza que puede reemplazar rápidamente hardware defectuoso para desarrollar y ejecutar más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="f822b-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up and running more quickly.</span></span>  
  
 <span data-ttu-id="f822b-130">**Documentar y probar los procedimientos de recuperación**</span><span class="sxs-lookup"><span data-stu-id="f822b-130">**Document and test your recovery procedures**</span></span>  
  
-   <span data-ttu-id="f822b-131">La prueba de recuperación ante desastres debería llevarse a cabo antes de ejecutar el sistema en la fase de producción.</span><span class="sxs-lookup"><span data-stu-id="f822b-131">Disaster recovery testing should be conducted before ever running your system in production.</span></span> <span data-ttu-id="f822b-132">Al tener planes y llevar a cabo pruebas de versiones preliminares, se asegura de que el personal de IT pueda recuperar los sistemas de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f822b-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span>  
  
 <span data-ttu-id="f822b-133">**Entrenar su personal de TI en los procedimientos de recuperación ante desastres**</span><span class="sxs-lookup"><span data-stu-id="f822b-133">**Train your IT staff on disaster recovery procedures**</span></span>  
  
-   <span data-ttu-id="f822b-134">Asegúrese de que el personal de IT cuenta con los conocimientos adecuados para recuperar el sistema si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="f822b-134">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
 <span data-ttu-id="f822b-135">**Practicar la restauración de una copia de seguridad en un entorno de prueba**</span><span class="sxs-lookup"><span data-stu-id="f822b-135">**Practice restoring from a backup in a test environment**</span></span>  
  
-   <span data-ttu-id="f822b-136">Practique la recuperación del sistema BizTalk Server en un entorno de prueba para asegurarse de que puede restaurarlo en el entorno de producción si se produce un fallo.</span><span class="sxs-lookup"><span data-stu-id="f822b-136">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f822b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f822b-137">See Also</span></span>  
 [<span data-ttu-id="f822b-138">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="f822b-138">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)
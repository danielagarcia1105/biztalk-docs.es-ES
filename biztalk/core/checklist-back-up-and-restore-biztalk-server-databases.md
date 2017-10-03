---
title: "Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3c8c68eb62273562b0f703ae79c0db76ec837c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a><span data-ttu-id="e5e43-102">Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-102">Checklist: Back Up and Restore BizTalk Server Databases</span></span>
<span data-ttu-id="e5e43-103">Antes de intentar realizar una copia de seguridad de BizTalk Server o de efectuar su restauración, asegúrese de familiarizarse con los procesos que entran en juego.</span><span class="sxs-lookup"><span data-stu-id="e5e43-103">Before attempting to back up or restore BizTalk Server, be sure to familiarize yourself with the processes involved.</span></span>  
  
## <a name="backing-up-biztalk-server"></a><span data-ttu-id="e5e43-104">Realizar una copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-104">Backing Up BizTalk Server</span></span>  
  
|<span data-ttu-id="e5e43-105">Paso</span><span class="sxs-lookup"><span data-stu-id="e5e43-105">Step</span></span>|<span data-ttu-id="e5e43-106">Referencia</span><span class="sxs-lookup"><span data-stu-id="e5e43-106">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="e5e43-107">Aprenda cómo realizar una copia de seguridad de BizTalk Server y cómo efectuar su restauración.</span><span class="sxs-lookup"><span data-stu-id="e5e43-107">Learn how to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="e5e43-108">Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos</span><span class="sxs-lookup"><span data-stu-id="e5e43-108">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [<span data-ttu-id="e5e43-109">Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-109">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|<span data-ttu-id="e5e43-110">Asegúrese de contar con los permisos apropiados para realizar una copia de seguridad de BizTalk Server y efectuar su restauración.</span><span class="sxs-lookup"><span data-stu-id="e5e43-110">Ensure that you have appropriate permissions to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="e5e43-111">Derechos de usuario mínimos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e5e43-111">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)|  
|<span data-ttu-id="e5e43-112">Configure el trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e5e43-112">Configure the Backup BizTalk Server job.</span></span>|[<span data-ttu-id="e5e43-113">Cómo configurar el trabajo de copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-113">How to Configure the Backup BizTalk Server Job</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|<span data-ttu-id="e5e43-114">Configure el servidor en el que se almacenarán las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e5e43-114">Configure the server where backups will be stored.</span></span>|[<span data-ttu-id="e5e43-115">Cómo configurar el sistema de destino de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="e5e43-115">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|<span data-ttu-id="e5e43-116">Si está utilizando Supervisión de la actividad económica (SAE), realice una copia de seguridad de la base de datos de SAE.</span><span class="sxs-lookup"><span data-stu-id="e5e43-116">If you are using Business Activity Monitoring (BAM), back up the BAM databases.</span></span>|[<span data-ttu-id="e5e43-117">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="e5e43-117">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)|  
|<span data-ttu-id="e5e43-118">Si está utilizando el inicio de sesión único empresarial, realice una copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="e5e43-118">If you are using Enterprise Single Sign-on, back up the master secret.</span></span>|[<span data-ttu-id="e5e43-119">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="e5e43-119">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a><span data-ttu-id="e5e43-120">Restaurar BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-120">Restoring BizTalk Server</span></span>  
  
|<span data-ttu-id="e5e43-121">Paso</span><span class="sxs-lookup"><span data-stu-id="e5e43-121">Step</span></span>|<span data-ttu-id="e5e43-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="e5e43-122">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="e5e43-123">Restaure las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e5e43-123">Restore your databases.</span></span>|[<span data-ttu-id="e5e43-124">Cómo restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="e5e43-124">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)|  
|<span data-ttu-id="e5e43-125">Actualice las referencias a los nombres de base de datos de SAE.</span><span class="sxs-lookup"><span data-stu-id="e5e43-125">Update references to the BAM database names.</span></span>|[<span data-ttu-id="e5e43-126">Cómo realizar una copia del análisis de seguimiento y análisis de BAM bases de datos de servidor</span><span class="sxs-lookup"><span data-stu-id="e5e43-126">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [<span data-ttu-id="e5e43-127">Cómo actualizar referencias al servidor de análisis BAM y nombres de base de datos de esquema en estrella</span><span class="sxs-lookup"><span data-stu-id="e5e43-127">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [<span data-ttu-id="e5e43-128">Cómo actualizar referencias al nombre de base de datos de archivo BAM</span><span class="sxs-lookup"><span data-stu-id="e5e43-128">How to Update References to the BAM Archive Database Name</span></span>](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [<span data-ttu-id="e5e43-129">Cómo actualizar referencias a la cadena de conexión y el nombre de base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="e5e43-129">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [<span data-ttu-id="e5e43-130">Cómo actualizar referencias a la notificación de BAM de servicios de bases de datos</span><span class="sxs-lookup"><span data-stu-id="e5e43-130">How to Update References to the BAM Notification Services Databases</span></span>](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [<span data-ttu-id="e5e43-131">Cómo resolver instancias de actividad incompletas</span><span class="sxs-lookup"><span data-stu-id="e5e43-131">How to Resolve Incomplete Activity Instances</span></span>](../core/how-to-resolve-incomplete-activity-instances.md)|  
|<span data-ttu-id="e5e43-132">Si está utilizando el inicio de sesión único empresarial, restaure el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="e5e43-132">If you are using Enterprise Single Sign-on, restore the master secret.</span></span>|[<span data-ttu-id="e5e43-133">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="e5e43-133">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e5e43-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5e43-134">See Also</span></span>  
 [<span data-ttu-id="e5e43-135">Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e5e43-135">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
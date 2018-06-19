---
title: Planear la plataforma para tolerancia a errores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32cb8913ff48ed954e6e57140417966846641f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265028"
---
# <a name="planning-your-platform-for-fault-tolerance"></a><span data-ttu-id="8f1fc-102">Planear la plataforma para tolerancia a errores</span><span class="sxs-lookup"><span data-stu-id="8f1fc-102">Planning Your Platform for Fault Tolerance</span></span>
<span data-ttu-id="8f1fc-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está basado en las plataformas Microsoft Windows y Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on the Microsoft Windows and Microsoft SQL Server platforms.</span></span> <span data-ttu-id="8f1fc-104">La capacidad de BizTalk Server de sobrevivir o recuperarse de un desastre depende de la capacidad de supervivencia o recuperación de la plataforma subyacente.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-104">The ability of BizTalk Server to survive or recover from a disaster depends on the ability of the underlying platform to survive or recover.</span></span>  
  
 <span data-ttu-id="8f1fc-105">Para las bases de datos de supervisión de la actividad económica (BAM) y la base de datos de cuadro de mensajes, se recomienda que realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f1fc-105">For your Business Activity Monitoring (BAM) databases and your MessageBox database, we recommend you do the following:</span></span>  
  
-   <span data-ttu-id="8f1fc-106">Configure la agrupación de conmutación por error, disponible en SQL Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-106">Set up fail-over clustering, which is available in SQL Server Enterprise Edition.</span></span> <span data-ttu-id="8f1fc-107">La agrupación de conmutación por error permite a SQL Server cambiar automáticamente el procesamiento de una instancia de SQL Server de un servidor que ha dejado de funcionar a un servidor en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-107">Fail-over clustering enables SQL Server to automatically switch the processing for an instance of SQL Server from a failed server to a working server.</span></span>  
  
     <span data-ttu-id="8f1fc-108">La base de datos de importación principal de BAM recopila datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-108">The BAM Primary Import database collects event data.</span></span> <span data-ttu-id="8f1fc-109">Si se produce un desastre, se perderán los datos que se hayan escrito en la base de datos de importación principal de BAM desde la última copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-109">In the event of a disaster, data that was written to the BAM Primary Import database since the last backup will be lost.</span></span> <span data-ttu-id="8f1fc-110">Puesto que no hay forma de regenerar los eventos perdidos, es especialmente importante habilitar la agrupación de conmutación por error en la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="8f1fc-110">Because there is no way to regenerate lost events, it is especially important that you enable fail over clustering on your BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="8f1fc-111">Utilice la matriz redundante de discos independientes (RAID) de SQL Server, especialmente para las bases de datos de cuadros de mensajes y de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-111">Use SQL Server RAID (redundant array of independent disks), especially for the MessageBox database and the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="8f1fc-112">Utilice los recursos siguientes para diseñar las implementaciones de Windows y SQL Server con tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-112">Use the following resources to design your Windows and SQL Server deployments for fault tolerance.</span></span> <span data-ttu-id="8f1fc-113">Dedique el tiempo que sea necesario a obtener información sobre las tecnologías de redundancia de servidores y hardware, como la agrupación y el reflejo de disco, para prevenir las interrupciones del servicio y la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-113">Take time to learn about hardware and server redundancy technologies, such as clustering and disk mirroring, to prevent service outages and data loss.</span></span>  
  
-   [<span data-ttu-id="8f1fc-114">Notas del producto: Alta disponibilidad: Always On Technologies</span><span class="sxs-lookup"><span data-stu-id="8f1fc-114">White Paper: High Availability—Always On Technologies</span></span>](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
     <span data-ttu-id="8f1fc-115">Las notas del producto “ High Availability – Always On Technologies” describen las funciones de alta disponibilidad que se encuentran disponibles con SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-115">The “High Availability – Always On Technologies” whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
-   [<span data-ttu-id="8f1fc-116">Información general sobre soluciones de alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="8f1fc-116">High Availability Solutions Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
     <span data-ttu-id="8f1fc-117">Introduce varias soluciones de alta disponibilidad para SQL Server 2008 que mejoran la disponibilidades de servidores o bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-117">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
-   [<span data-ttu-id="8f1fc-118">Capítulo 15: opciones de alta disponibilidad, el Kit de recursos SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f1fc-118">Chapter 15 - High Availability Options, SQL Server Resource Kit</span></span>](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
     <span data-ttu-id="8f1fc-119">El Kit de recursos de Microsoft SQL Server abarca una amplia gama de áreas de planeamiento administrativo y de implementación.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-119">The Microsoft SQL Server Resource Kit covers a wide range of administrative and deployment planning areas.</span></span> <span data-ttu-id="8f1fc-120">En el capítulo 15, se trata el planeamiento de la recuperación y la tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-120">Chapter 15 covers planning for fault tolerance and recovery.</span></span>  
  
-   [<span data-ttu-id="8f1fc-121">Guía paso a paso de servicios de implementación de Windows</span><span class="sxs-lookup"><span data-stu-id="8f1fc-121">Windows Deployment Services Step-by-Step Guide</span></span>](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
     <span data-ttu-id="8f1fc-122">Contiene instrucciones paso a paso sobre el uso del rol Servicios de implementación de Windows en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8f1fc-122">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008</span></span>  
  
-   <span data-ttu-id="8f1fc-123">[Kit de implementación de Windows Server 2003: Planeación de implementaciones de servidor](http://go.microsoft.com/fwlink/?LinkId=24433).</span><span class="sxs-lookup"><span data-stu-id="8f1fc-123">[Windows Server 2003 Deployment Kit: Planning Server Deployments](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
     <span data-ttu-id="8f1fc-124">Este libro contiene información sobre cómo planear el almacenamiento en servidores y sobre el diseño y la implementación de servidores de archivos, servidores de impresión y servidores de Terminal Server en organizaciones de mediano y gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-124">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
     <span data-ttu-id="8f1fc-125">También puede usar las instrucciones de este libro para planear la administración de servidores remotos, diseñar e implementar clústeres de servidores, y diseñar e implementar clústeres de equilibrio de carga de red con el fin de maximizar la disponibilidad y la escalabilidad de los servidores.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-125">You can also use the guidelines in this book to maximize the availability and scalability of your servers by planning for remote server management, designing and deploying server clusters, and designing and deploying Network Load Balancing clusters.</span></span>  
  
## <a name="backing-up-your-platform"></a><span data-ttu-id="8f1fc-126">Copia de seguridad de la plataforma</span><span class="sxs-lookup"><span data-stu-id="8f1fc-126">Backing Up Your Platform</span></span>  
 <span data-ttu-id="8f1fc-127">Una vez configurado el sistema, prepare copias de seguridad completas de los servidores para poder restablecer rápidamente un servidor idéntico en caso de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-127">After you have configured your system, prepare full backups of your servers so you can quickly restore an identical server in the event of data loss.</span></span>  
  
 <span data-ttu-id="8f1fc-128">Para realizar una copia de seguridad de la plataforma, siga los procedimientos de copia de seguridad documentados para cada una de las tecnologías siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f1fc-128">To back up your platform, perform the documented backup procedures for each of the following technologies:</span></span>  
  
-   <span data-ttu-id="8f1fc-129">Microsoft Windows Server Standard, Enterprise o Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="8f1fc-129">Microsoft Windows Server Standard, Enterprise, or Datacenter Edition</span></span>  
  
-   <span data-ttu-id="8f1fc-130">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="8f1fc-130">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="8f1fc-131">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f1fc-131">Microsoft SQL Server</span></span>  
  
-   <span data-ttu-id="8f1fc-132">Windows SharePoint Services, que es usado por el adaptador de los servicios de Windows SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-132">Windows SharePoint Services, which is used by the Windows SharePoint Services adapter.</span></span>  
  
 <span data-ttu-id="8f1fc-133">Siga las recomendaciones de la "Guía de operaciones de BizTalk Server" para "Backing up BizTalk Server" disponible en [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](http://go.microsoft.com/fwlink/?LinkId=130498).</span><span class="sxs-lookup"><span data-stu-id="8f1fc-133">Follow the recommendations in the “BizTalk Server Operations Guide” for “Backing up BizTalk Server” available at [Checklist: Increasing Availability with Disaster Recovery](http://go.microsoft.com/fwlink/?LinkId=130498).</span></span>  
  
 <span data-ttu-id="8f1fc-134">Pruebe exhaustivamente los procedimientos de copia de seguridad y restauración, y colóquelos en una ubicación segura y remota.</span><span class="sxs-lookup"><span data-stu-id="8f1fc-134">Thoroughly test your backup and restore procedures, and put them in a safe, remote location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1fc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f1fc-135">See Also</span></span>  
 [<span data-ttu-id="8f1fc-136">Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8f1fc-136">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
---
title: Copia de seguridad y restauración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230788"
---
# <a name="backing-up-and-restoring-biztalk-server"></a><span data-ttu-id="128c2-102">Realizar una copia de seguridad y una restauración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="128c2-102">Backing Up and Restoring BizTalk Server</span></span>
<span data-ttu-id="128c2-103">Si se produce un error de hardware, es esencial tener una buena copia de seguridad de las bases de datos y de los componentes de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="128c2-103">In the event of hardware failure, having a good backup of your BizTalk Server databases and components is essential.</span></span> <span data-ttu-id="128c2-104">Una buena copia de seguridad le permitirá recuperar la información en la que la pérdida de datos será mínima o ninguna.</span><span class="sxs-lookup"><span data-stu-id="128c2-104">A good backup will enable you to recover with little or no data loss.</span></span> <span data-ttu-id="128c2-105">El modo de restaurar BizTalk Server depende de los componentes que se han instalado en el sistema en el que ha ocurrido el error.</span><span class="sxs-lookup"><span data-stu-id="128c2-105">How you restore BizTalk Server depends on which components were installed on the system where hardware failure occurred.</span></span> <span data-ttu-id="128c2-106">En esta guía se tratan los siguientes escenarios de error de hardware:</span><span class="sxs-lookup"><span data-stu-id="128c2-106">This guide covers the following hardware failure scenarios:</span></span>  
  
 <span data-ttu-id="128c2-107">**Error de hardware en el equipo que ejecuta BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="128c2-107">**Hardware failure in the computer running BizTalk Server**</span></span>  
  
 <span data-ttu-id="128c2-108">Un error de hardware en el equipo que ejecuta BizTalk Server puede hacer que se interrumpa la actividad del sistema o disminuya el rendimiento, si el grupo de BizTalk no se ha diseñado para obtener alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="128c2-108">A hardware failure in the computer running BizTalk Server may cause system downtime or degraded performance if the BizTalk group is not designed for high availability.</span></span> <span data-ttu-id="128c2-109">Para obtener más información sobre cómo crear un grupo de BizTalk de alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).</span><span class="sxs-lookup"><span data-stu-id="128c2-109">For more information about how to create a highly available BizTalk group, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
 <span data-ttu-id="128c2-110">Para asegurarse de que puede sustituir un equipo que ejecuta BizTalk Server después de que se produzca un error de hardware, debe realizar una copia de seguridad de los componentes de BizTalk Server en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="128c2-110">To ensure that you can replace a computer running BizTalk Server after a hardware failure, you must back up the BizTalk Server components on that computer.</span></span> <span data-ttu-id="128c2-111">Para obtener más información acerca de cómo realizar copias de y restaurar un equipo que ejecuta BizTalk Server, vea [realizar una copia de seguridad de un equipo ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) y [recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="128c2-111">For more information about how to back up and restore a computer running BizTalk Server, see [Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) and [Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="128c2-112">**Error de hardware en el equipo que ejecuta SQL Server**</span><span class="sxs-lookup"><span data-stu-id="128c2-112">**Hardware failure in the computer running SQL Server**</span></span>  
  
 <span data-ttu-id="128c2-113">Puede minimizar el riesgo de que se produzca un error de hardware en un equipo que ejecuta SQL Server mediante la utilización de organización por clústeres de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="128c2-113">You can minimize the risk of a hardware failure in a computer running SQL Server by using SQL Server clustering.</span></span> <span data-ttu-id="128c2-114">Incluso cuando se utiliza la organización por clústeres de SQL Server, puede haber situaciones en las que se produzca un error irrecuperable en los servidores SQL Server que contienen las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="128c2-114">Even when using SQL Server clustering, however, there may be situations when the SQL server(s) containing the BizTalk Server databases experiences an unrecoverable hardware failure.</span></span> <span data-ttu-id="128c2-115">Por ejemplo, todos los niveles de los datos se han visto afectados por un error.</span><span class="sxs-lookup"><span data-stu-id="128c2-115">For example, the entire data tier suffered a failure.</span></span> <span data-ttu-id="128c2-116">En estas situaciones, debe reactivar el grupo de BizTalk mediante la restauración del conjunto de bases de datos de las que se ha realizado una copia de seguridad más reciente.</span><span class="sxs-lookup"><span data-stu-id="128c2-116">In these situations, you must revive the BizTalk group by restoring the most recent set of backed up databases.</span></span>  
  
 <span data-ttu-id="128c2-117">Para obtener más información acerca de cómo proporcionar tolerancia a errores para las bases de datos de BizTalk Server, vea [proporcionar una alta disponibilidad para bases de datos de BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="128c2-117">For more information about providing fault tolerance for the BizTalk Server databases, see [Providing High Availability for BizTalk Server Databases](../core/providing-high-availability-for-biztalk-server-databases.md).</span></span> <span data-ttu-id="128c2-118">En el caso de un error grave de SQL Server donde se ha producido un tiempo de inactividad, debe seguir las instrucciones en [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="128c2-118">In the case of a catastrophic SQL Server failure where downtime has occurred, you should follow the instructions in [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="128c2-119">En caso de que se produzca un error de hardware en un equipo en el que se ha instalado SQL Server y BizTalk Server, debe restaurar las bases de datos de BizTalk Server y, a continuación, recuperar sus componentes.</span><span class="sxs-lookup"><span data-stu-id="128c2-119">If you experience a hardware failure on a computer where both SQL Server and BizTalk Server are installed, you should restore the BizTalk Server databases, and then recover the BizTalk Server components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="128c2-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="128c2-120">In This Section</span></span>  
  
-   [<span data-ttu-id="128c2-121">Lista de comprobación: Copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="128c2-121">Checklist: Backup and Restore</span></span>](../core/checklist-backup-and-restore.md)  
  
-   [<span data-ttu-id="128c2-122">Prácticas recomendadas para la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="128c2-122">Best Practices for Backup and Restore</span></span>](../core/best-practices-for-backup-and-restore.md)  
  
-   [<span data-ttu-id="128c2-123">Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="128c2-123">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="128c2-124">Recuperación ante desastres para equipos que ejecutan BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="128c2-124">Disaster Recovery for Computers Running BizTalk Server</span></span>](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [<span data-ttu-id="128c2-125">Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="128c2-125">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [<span data-ttu-id="128c2-126">Recuperar un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="128c2-126">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
---
title: Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a><span data-ttu-id="1662f-102">Realizar una copia de seguridad y restaurar las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1662f-102">Backing Up and Restoring the BizTalk Server Databases</span></span>
<span data-ttu-id="1662f-103">En esta sección se proporciona información acerca de cómo realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1662f-103">This section provides information about how to back up and restore the BizTalk Server databases.</span></span> <span data-ttu-id="1662f-104">Debería seguir los procedimientos de esta sección para garantizar la posibilidad de restaurar un entorno de BizTalk Server coherente en el caso de que se produzca un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="1662f-104">You should follow the procedures in this section to ensure your ability to restore a consistent BizTalk Server environment in the event of a hardware failure.</span></span> <span data-ttu-id="1662f-105">BizTalk Server lleva a cabo transacciones distribuidas en las bases de datos, de modo que resulta extremadamente importante realizar una copia de seguridad y una restauración ulterior de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1662f-105">BizTalk Server performs distributed transactions across databases, so it is critical that you back up and then restore all databases.</span></span>  
  
 <span data-ttu-id="1662f-106">BizTalk Server requiere un proceso de copia de seguridad personalizado que utiliza copias de seguridad de registros y de bases de datos completas junto con marcas de registros de carácter transaccional.</span><span class="sxs-lookup"><span data-stu-id="1662f-106">BizTalk Server requires a customized backup process that uses full database backups and log backups in conjunction with transactional log marking.</span></span> <span data-ttu-id="1662f-107">Para obtener información acerca de este proceso, consulte [transacciones marcadas y copias de seguridad completas, copias de seguridad del registro](../core/marked-transactions-full-backups-and-log-backups.md).</span><span class="sxs-lookup"><span data-stu-id="1662f-107">For information about this process, see [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1662f-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1662f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="1662f-109">Lista de comprobación: Copia de seguridad y restaurar bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1662f-109">Checklist: Back Up and Restore BizTalk Server Databases</span></span>](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="1662f-110">Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos</span><span class="sxs-lookup"><span data-stu-id="1662f-110">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [<span data-ttu-id="1662f-111">Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1662f-111">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="1662f-112">Copia de seguridad y restauración de BAM</span><span class="sxs-lookup"><span data-stu-id="1662f-112">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
-   [<span data-ttu-id="1662f-113">Resolver la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="1662f-113">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)  
  
-   [<span data-ttu-id="1662f-114">Información avanzada sobre la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="1662f-114">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
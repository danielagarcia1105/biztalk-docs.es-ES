---
title: Restauración de la producción de una copia de seguridad semiactiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66177cd1f6f10e252a71d2875b4079e660125719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971365"
---
# <a name="restoring-production-from-a-warm-backup"></a><span data-ttu-id="b5f75-102">Restauración de la producción de una copia de seguridad semiactiva</span><span class="sxs-lookup"><span data-stu-id="b5f75-102">Restoring Production from a Warm Backup</span></span>
<span data-ttu-id="b5f75-103">Si se convierte en el sistema de origen no confiable, es posible restaurar las bases de datos del destino al origen.</span><span class="sxs-lookup"><span data-stu-id="b5f75-103">If the source system becomes unreliable, it is possible to restore the databases from the destination to the source.</span></span> <span data-ttu-id="b5f75-104">Realice el procedimiento siguiente para restaurar las bases de datos desde el destino al origen.</span><span class="sxs-lookup"><span data-stu-id="b5f75-104">Perform the following procedure to restore databases from the destination to the source.</span></span>  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a><span data-ttu-id="b5f75-105">Para restaurar las bases de datos del destino al origen siguen estos pasos</span><span class="sxs-lookup"><span data-stu-id="b5f75-105">To restore the databases from the destination to the source follow these steps</span></span>  
  
1. <span data-ttu-id="b5f75-106">Deshabilitar todos los trabajos de copia de seguridad en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-106">Disable all backup jobs on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
2. <span data-ttu-id="b5f75-107">Espere a todos los trabajos de completa en la recuperación de desastres (DR) de destino de restauración [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-107">Wait for all restore jobs to complete on the destination disaster recovery (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
3. <span data-ttu-id="b5f75-108">Deshabilitar todos los trabajos de restauración en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-108">Disable all restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
4. <span data-ttu-id="b5f75-109">Restaurar todas las bases de datos con STOPATMARK en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-109">Restore all databases with STOPATMARK on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
5. <span data-ttu-id="b5f75-110">Todos los detenga [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services en todos los servidores BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b5f75-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services on all BizTalk servers.</span></span>  
  
6. <span data-ttu-id="b5f75-111">Todos los quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionadas con bases de datos en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-111">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
7. <span data-ttu-id="b5f75-112">Copia de seguridad (completa) todas las bases de datos en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-112">Back up (full) all databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
8. <span data-ttu-id="b5f75-113">Restaurar (completa) todos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos de copia de seguridad en el paso 7 en el origen (producción) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-113">Restore (full) all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases backed up in step 7 to the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
9. <span data-ttu-id="b5f75-114">Reinicie todos los servidores de BizTalk, incluido el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="b5f75-114">Restart all BizTalk servers including the master secret server.</span></span>  
  
10. <span data-ttu-id="b5f75-115">Todos los quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-relacionadas con bases de datos en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-115">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
11. <span data-ttu-id="b5f75-116">Habilitar trabajos de copia de seguridad en el origen de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-116">Enable backup jobs on the source [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
12. <span data-ttu-id="b5f75-117">Habilitar trabajos de restauración en el destino (recuperación ante desastres) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="b5f75-117">Enable restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f75-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5f75-118">See Also</span></span>  
 [<span data-ttu-id="b5f75-119">Información avanzada acerca de la copia de seguridad y Restore2</span><span class="sxs-lookup"><span data-stu-id="b5f75-119">Advanced Information About Backup and Restore2</span></span>](../technical-guides/advanced-information-about-backup-and-restore2.md)
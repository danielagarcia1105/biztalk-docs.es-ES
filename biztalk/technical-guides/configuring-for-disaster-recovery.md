---
title: "Configuración de recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3899b27324fa00e0b5c630c7be4433f65a917a1b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="b7d9f-102">Configuración de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="b7d9f-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="b7d9f-103">La característica de trasvase de registros de BizTalk Server extiende la copia de seguridad existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajo.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-103">The BizTalk Server Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> <span data-ttu-id="b7d9f-104">Trasvase de registros de BizTalk Server elimina la necesidad de restaurar de forma manual una serie de conjuntos de copia de seguridad generados por el trabajo de copia de seguridad y reduce el tiempo de inactividad en caso de un error del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-104">BizTalk Server Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> <span data-ttu-id="b7d9f-105">Trasvase de registros de BizTalk Server es un componente esencial para ver los procedimientos de recuperación ante desastres de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-105">BizTalk Server Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7d9f-106">Cada equipo de la aplicación debe tener una copia de seguridad documentado y restaurar el plan de recuperación ante desastres que complementa los conceptos proporcionados en este tema.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="b7d9f-107">El plan general debería tratar todo el sistema, incluidas las aplicaciones y los componentes del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="b7d9f-108">Realizar una operación de recuperación ante desastres es muy similar a realizar manualmente una restauración de un grupo de BizTalk a un nuevo conjunto de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="b7d9f-109">La diferencia principal radica en dicho registro de BizTalk Server aplica de trasvase de registros continuamente en el sitio de recuperación ante desastres, guardar muchos pasos manuales.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-109">The primary difference is that BizTalk Server log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="b7d9f-110">Por lo tanto, solo el último conjunto de registros se debe restaurar manualmente cuando BizTalk Server se implementa el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-110">Therefore, only the last set of logs must be restored manually when BizTalk Server log shipping is implemented.</span></span> <span data-ttu-id="b7d9f-111">En caso contrario, la última copia de seguridad completa seguida de todas las copias de seguridad del registro desde la última copia de seguridad que se restaura manualmente.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> <span data-ttu-id="b7d9f-112">Registro de BizTalk Server envío reduce el esfuerzo necesario para hacerlo manualmente, lo que acelera la restauración del sitio de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-112">BizTalk Server log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="b7d9f-113">Esta sección contiene recomendaciones de configuración de producción para facilitar el proceso de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7d9f-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7d9f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="b7d9f-115">Preparar el sitio de recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="b7d9f-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="b7d9f-116">Roles y cuentas de usuario de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="b7d9f-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="b7d9f-117">Configuración del trasvase de registros de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b7d9f-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7d9f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d9f-118">See Also</span></span>  
 [<span data-ttu-id="b7d9f-119">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="b7d9f-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)
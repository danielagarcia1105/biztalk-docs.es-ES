---
title: Mediante la recuperación ante desastres de trasvase de registros de servidor BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2ded5686cc81b1cc3b629601b142a19c3b7b193
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023386"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a><span data-ttu-id="d74cd-102">Uso de recuperación ante desastres de trasvase de registros de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d74cd-102">Using BizTalk Server Log Shipping for Disaster Recovery</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d74cd-103"> implementa la base de datos en espera capacidades mediante el uso de la base de datos de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="d74cd-103"> implements database standby capabilities through the use of database log shipping.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d74cd-104"> el trasvase de registros automatiza la copia de seguridad y restauración de archivos de registro de transacciones y la base de datos, lo que permite a un servidor en espera reanudar el procesamiento de base de datos en caso de que se produce un error en el servidor de base de datos de producción.</span><span class="sxs-lookup"><span data-stu-id="d74cd-104"> log shipping automates the backup and restore of database and transaction log files, allowing a standby server to resume database processing in the event that the production database server fails.</span></span>  
  
## <a name="how-log-shipping-works"></a><span data-ttu-id="d74cd-105">Cómo funciona de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="d74cd-105">How Log Shipping Works</span></span>  
 <span data-ttu-id="d74cd-106">El [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] utilizados por los trabajos del agente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de trasvase de registros a sincronizar datos entre el servidor de origen utilizados en la producción y el servidor de destino que se usa como un servidor en espera cada 15 minutos de forma predeterminada (es decir, cada vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server).</span><span class="sxs-lookup"><span data-stu-id="d74cd-106">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for log shipping synchronize data between the source server used in production and the destination server used as a standby every 15 minutes by default (every time that the Backup BizTalk Server job runs).</span></span>  
  
## <a name="using-log-shipping-for-disaster-recovery"></a><span data-ttu-id="d74cd-107">Uso de recuperación ante desastres de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="d74cd-107">Using Log Shipping for Disaster Recovery</span></span>  
 <span data-ttu-id="d74cd-108">Haga lo siguiente al usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros para la recuperación ante desastres:</span><span class="sxs-lookup"><span data-stu-id="d74cd-108">Do the following when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping for disaster recovery:</span></span>  
  
- <span data-ttu-id="d74cd-109">Siga los pasos descritos en el tema [lista de comprobación: aumento de disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) para aumentar la disponibilidad de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="d74cd-109">Follow the steps in the topic [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) to increase availability of a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery.</span></span>  
  
- <span data-ttu-id="d74cd-110">Compruebe que los servidores de recuperación ante desastres tienen la capacidad para administrar la carga de producción.</span><span class="sxs-lookup"><span data-stu-id="d74cd-110">Verify that the disaster recovery servers have the capacity to handle production load.</span></span>  
  
   <span data-ttu-id="d74cd-111">Asegúrese de que los servidores en espera tienen el mismos o similares recursos disponibles (CPU/memoria/disco) como los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="d74cd-111">Ensure that the standby servers have the same or similar resources available (CPU/memory/disk) as the production servers.</span></span>  
  
- <span data-ttu-id="d74cd-112">Asegúrese de que los detalles de la rutina de recuperación ante desastres están bien documentados.</span><span class="sxs-lookup"><span data-stu-id="d74cd-112">Ensure that the specifics of your disaster recovery routine are well documented.</span></span>  
  
   <span data-ttu-id="d74cd-113">Documente todos los pasos de la preparación de la recuperación ante desastres y la implementación en detalle.</span><span class="sxs-lookup"><span data-stu-id="d74cd-113">Document every step of your disaster recovery preparation and implementation in detail.</span></span> <span data-ttu-id="d74cd-114">Ante desastres rara vez huelgas cuando sea conveniente por lo que se suponen que las partes responsables de implementar el procedimiento de recuperación ante desastres están comenzando a su primer día de trabajo y a realizar esto por primera vez.</span><span class="sxs-lookup"><span data-stu-id="d74cd-114">Disaster seldom strikes when it is convenient so assume that the parties responsible for implementing the disaster recovery procedure are starting their first day of work and will be doing this for the first time.</span></span>  
  
- <span data-ttu-id="d74cd-115">Como parte de la prueba, práctica conmutación por error normal para el sitio de recuperación ante desastres, especialmente como nuevo de BizTalk se colocan las aplicaciones en producción.</span><span class="sxs-lookup"><span data-stu-id="d74cd-115">As part of regular testing, practice failover to the disaster recovery site, especially as new BizTalk applications are put in production.</span></span>  
  
   <span data-ttu-id="d74cd-116">Realizar las pruebas como parte de las pruebas y el mantenimiento para asegurarse de que puede realizar sin problemas normal de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="d74cd-116">Perform failover testing as a part of regular testing and maintenance to ensure that it can be performed smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74cd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d74cd-117">See Also</span></span>  
 [<span data-ttu-id="d74cd-118">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="d74cd-118">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)
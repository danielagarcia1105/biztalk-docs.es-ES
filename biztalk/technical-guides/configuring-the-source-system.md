---
title: Configuración del sistema de origen | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 722dd52c-1eea-453c-9a36-9b8d9cf19350
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87cf66470ff2d05f4446fbcb81eb2a533064d3f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024370"
---
# <a name="configuring-the-source-system"></a><span data-ttu-id="a2a20-102">Configuración del sistema de origen</span><span class="sxs-lookup"><span data-stu-id="a2a20-102">Configuring the Source System</span></span>
<span data-ttu-id="a2a20-103">Para los fines de trasvase de registros de servidor BizTalk Server, no importa si el sistema de origen se encuentra en una sola [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia o si se distribuye entre varias instancias que se hospedan en un clúster de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a2a20-103">For the purposes of BizTalk Server log shipping, it does not matter if the source system is located on a single [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance or if it is distributed among multiple instances hosted in a Windows Server cluster.</span></span> <span data-ttu-id="a2a20-104">No hay ninguna consideración adicional que no eran necesarios para ejecutar correctamente el trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a2a20-104">There are no additional considerations other than those required to successfully run the Backup BizTalk Server job.</span></span> <span data-ttu-id="a2a20-105">Para configurar este trabajo, consulte [cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154072) (<http://go.microsoft.com/fwlink/?LinkID=154072>) en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a2a20-105">To configure this job, see [How to Configure the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkID=154072) (<http://go.microsoft.com/fwlink/?LinkID=154072>) in BizTalk Server Help.</span></span> <span data-ttu-id="a2a20-106">Después de haber configurado el trabajo de copia de seguridad de BizTalk Server, continúe con el tema [cómo configurar el sistema de destino](../technical-guides/how-to-configure-the-destination-system.md).</span><span class="sxs-lookup"><span data-stu-id="a2a20-106">After you have configured the Backup BizTalk Server Job, proceed to the topic [How to Configure the Destination System](../technical-guides/how-to-configure-the-destination-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a20-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2a20-107">See Also</span></span>  
 [<span data-ttu-id="a2a20-108">Configuración del trasvase de registros de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a2a20-108">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)
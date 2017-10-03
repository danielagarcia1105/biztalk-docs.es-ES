---
title: "Lista de comprobación: Supervisión de servidores SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5dea6db0-5347-497c-b07d-6a339e409f0a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cd47efb3bf9417c3733212b8f45946a2f13fa19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-sql-servers"></a><span data-ttu-id="afa3c-102">Lista de comprobación: Supervisar los servidores SQL</span><span class="sxs-lookup"><span data-stu-id="afa3c-102">Checklist: Monitoring SQL Servers</span></span>
<span data-ttu-id="afa3c-103">Este tema describe los pasos que deben seguirse para supervisar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en uno de producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="afa3c-103">This topic describes the steps that should be followed to monitor [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="afa3c-104">Tarea</span><span class="sxs-lookup"><span data-stu-id="afa3c-104">Task</span></span>|<span data-ttu-id="afa3c-105">Referencia</span><span class="sxs-lookup"><span data-stu-id="afa3c-105">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="afa3c-106">Instalar Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack para Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="afa3c-106">Install the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for Operations Manager 2007</span></span>|<span data-ttu-id="afa3c-107">[Módulo de administración de supervisión de SQL Server](http://go.microsoft.com/fwlink/?linkid=109858) (http://go.microsoft.com/fwlink/?linkid=109858)</span><span class="sxs-lookup"><span data-stu-id="afa3c-107">[SQL Server Monitoring Management Pack](http://go.microsoft.com/fwlink/?linkid=109858) (http://go.microsoft.com/fwlink/?linkid=109858)</span></span>|  
|<span data-ttu-id="afa3c-108">Designar la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos como críticas en el módulo de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afa3c-108">Designate the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases as critical in the SQL Server Management Pack.</span></span>|[<span data-ttu-id="afa3c-109">Cómo marcar bases de datos de BizTalk Server para supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="afa3c-109">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)|  
|<span data-ttu-id="afa3c-110">Asegúrese de que se supervisan los equipos SQL server.</span><span class="sxs-lookup"><span data-stu-id="afa3c-110">Ensure that the SQL server machines are monitored.</span></span>|[<span data-ttu-id="afa3c-111">Supervisión de trabajos del Agente SQL Server y bases de datos</span><span class="sxs-lookup"><span data-stu-id="afa3c-111">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)|  
|<span data-ttu-id="afa3c-112">Asegúrese de que se supervisan los trabajos del Agente SQL de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="afa3c-112">Ensure that the BizTalk SQL Agent jobs are monitored.</span></span>|[<span data-ttu-id="afa3c-113">Supervisión de trabajos del Agente SQL Server y bases de datos</span><span class="sxs-lookup"><span data-stu-id="afa3c-113">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)|
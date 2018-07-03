---
title: 'Lista de comprobación: Supervisión de servidores SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dea6db0-5347-497c-b07d-6a339e409f0a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8835af94ec16d344cd85c0321731ac4150451acf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993397"
---
# <a name="checklist-monitoring-sql-servers"></a><span data-ttu-id="a955a-102">Lista de comprobación: Supervisión de servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="a955a-102">Checklist: Monitoring SQL Servers</span></span>
<span data-ttu-id="a955a-103">En este tema se describe los pasos que se deben seguir para supervisar [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="a955a-103">This topic describes the steps that should be followed to monitor [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  


|                                                                       <span data-ttu-id="a955a-104">Tarea</span><span class="sxs-lookup"><span data-stu-id="a955a-104">Task</span></span>                                                                        |                                                                        <span data-ttu-id="a955a-105">Referencia</span><span class="sxs-lookup"><span data-stu-id="a955a-105">Reference</span></span>                                                                        |
|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|   <span data-ttu-id="a955a-106">Instalar Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack para Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="a955a-106">Install the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for Operations Manager 2007</span></span>    |        <span data-ttu-id="a955a-107">[Módulo de administración de supervisión de SQL Server](http://go.microsoft.com/fwlink/?linkid=109858) (<http://go.microsoft.com/fwlink/?linkid=109858>)</span><span class="sxs-lookup"><span data-stu-id="a955a-107">[SQL Server Monitoring Management Pack](http://go.microsoft.com/fwlink/?linkid=109858) (<http://go.microsoft.com/fwlink/?linkid=109858>)</span></span>         |
| <span data-ttu-id="a955a-108">Designar la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] bases de datos como críticas en el módulo de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a955a-108">Designate the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases as critical in the SQL Server Management Pack.</span></span> | [<span data-ttu-id="a955a-109">Cómo marcar las bases de datos de BizTalk Server para la supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="a955a-109">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md) |
|                                                <span data-ttu-id="a955a-110">Asegúrese de que se supervisan las máquinas SQL server.</span><span class="sxs-lookup"><span data-stu-id="a955a-110">Ensure that the SQL server machines are monitored.</span></span>                                                 |                 [<span data-ttu-id="a955a-111">Supervisión de las bases de datos y trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a955a-111">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)                 |
|                                               <span data-ttu-id="a955a-112">Asegúrese de que se supervisan los trabajos del Agente SQL de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a955a-112">Ensure that the BizTalk SQL Agent jobs are monitored.</span></span>                                               |                 [<span data-ttu-id="a955a-113">Supervisión de las bases de datos y trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="a955a-113">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)                 |


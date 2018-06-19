---
title: Supervisar el rendimiento de SQL Server | Documentos de Microsoft
description: Supervisar las bases de datos de BizTalk Server mediante herramientas de rendimiento, Monitor de actividad y la recopilación de datos
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4f9db738298ec2a242350faae3ba5bc9da1c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007901"
---
# <a name="monitor-sql-server-performance"></a><span data-ttu-id="1b427-103">Supervisar el rendimiento de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b427-103">Monitor SQL Server Performance</span></span>
<span data-ttu-id="1b427-104">SQL Server proporciona varias herramientas para supervisar los eventos de SQL Server y para optimizar el diseño físico de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1b427-104">SQL Server provides several tools for monitoring events in SQL Server and for tuning the physical database design.</span></span> <span data-ttu-id="1b427-105">[Herramientas para la supervisión de rendimiento y optimización](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describe estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="1b427-105">[Tools for Performance Monitoring and Tuning](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describes these tools.</span></span> 
  
<span data-ttu-id="1b427-106">BizTalk Server es un proceso intensivo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1b427-106">BizTalk Server is a database-intensive process.</span></span> <span data-ttu-id="1b427-107">al solucionar problemas de rendimiento de BizTalk Server, puede ser beneficioso comprobar el rendimiento de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b427-107">when troubleshooting BizTalk Server performance issues, it can be beneficial to also check the SQL Server performance.</span></span> <span data-ttu-id="1b427-108">Pueden ayudar las herramientas siguientes.</span><span class="sxs-lookup"><span data-stu-id="1b427-108">The following tools can help.</span></span>  
  
## <a name="sql-server-activity-monitor"></a><span data-ttu-id="1b427-109">Monitor de actividad SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b427-109">SQL Server Activity Monitor</span></span>  
<span data-ttu-id="1b427-110">Monitor de actividad de SQL Server proporciona información acerca de los procesos de SQL Server y cómo estos procesos afectan a la instancia actual de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b427-110">SQL Server Activity Monitor provides information about SQL Server processes and how these processes affect the current instance of SQL Server.</span></span> <span data-ttu-id="1b427-111">Para obtener más información, consulte [Monitor de actividad](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), y [Cómo: abrir el Monitor de actividad (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio).</span><span class="sxs-lookup"><span data-stu-id="1b427-111">For more information, see [Activity Monitor](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), and [How to: Open Activity Monitor (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio).</span></span> 
  
## <a name="sql-serverdata-collection"></a><span data-ttu-id="1b427-112">Colección de registrando ServerData SQL</span><span class="sxs-lookup"><span data-stu-id="1b427-112">SQL ServerData Collection</span></span>  
<span data-ttu-id="1b427-113">SQL Server proporciona un recopilador de datos que puede usar para obtener y guardar los datos recopilados de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="1b427-113">SQL Server provides a data collector that you can use to obtain and save data that is gathered from several sources.</span></span> <span data-ttu-id="1b427-114">El recopilador de datos permite usar contenedores de recopilación de datos, lo que permite determinar el ámbito y la frecuencia de recopilación de datos en un equipo que ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b427-114">The data collector enables you to use data collection containers, which enable you to determine the scope and frequency of data collection on a computer that is running SQL Server.</span></span> <span data-ttu-id="1b427-115">Vea [la recopilación de datos](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).</span><span class="sxs-lookup"><span data-stu-id="1b427-115">See [Data Collection](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b427-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b427-116">See Also</span></span>  
 [<span data-ttu-id="1b427-117">Optimización del rendimiento de la base de datos</span><span class="sxs-lookup"><span data-stu-id="1b427-117">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
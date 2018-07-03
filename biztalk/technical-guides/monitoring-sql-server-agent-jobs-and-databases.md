---
title: Supervisión de trabajos del Agente SQL Server y bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a0b770ded2bef9ccf28a763f63f053c0b3c89e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024314"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a><span data-ttu-id="4a853-102">Supervisar bases de datos y trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a853-102">Monitoring SQL Server Agent Jobs and Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4a853-103"> incluye varios [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente que realizan funciones importantes para mantener los servidores operativos y en buen estado.</span><span class="sxs-lookup"><span data-stu-id="4a853-103"> includes multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="4a853-104">Por ello, debe supervisar el estado de funcionamiento de estos trabajos y garantizar que no se producen errores en su ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a853-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span> <span data-ttu-id="4a853-105">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración contiene reglas para supervisar elementos tales como bases de datos SQL y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="4a853-105">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack contains rules for monitoring items such as SQL databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="4a853-106">Debe configurar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración de supervisión completa de todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="4a853-106">You should configure the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for comprehensive monitoring of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="4a853-107">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración incluye dos reglas deshabilitadas para supervisar el estado de dos de lo más importante BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente:</span><span class="sxs-lookup"><span data-stu-id="4a853-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack includes two disabled rules for monitoring the health of two of the most important BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs:</span></span>  
  
- <span data-ttu-id="4a853-108">Error crítico: Error en un trabajo de agente SQL Server de BizTalk - Backup BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4a853-108">Critical Error: A BizTalk SQL Server Agent job failed - Backup BizTalk Server</span></span>  
  
- <span data-ttu-id="4a853-109">Error crítico: Error de un trabajo del Agente SQL Server de BizTalk: realiza el seguimiento de la copia del mensaje</span><span class="sxs-lookup"><span data-stu-id="4a853-109">Critical Error: A BizTalk SQL Server Agent job failed – Tracked Message Copy</span></span>  
  
  <span data-ttu-id="4a853-110">Para supervisar todos los BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, debe habilitar estas reglas y crear reglas adicionales para otros trabajos que desea supervisar mediante el proceso siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a853-110">To monitor all BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack, you must enable these rules and create additional rules for other jobs that you want to monitor using the following process.</span></span>  
  
- <span data-ttu-id="4a853-111">En la consola de administrador de Operations Manager, cree una copia de cualquiera de las dos reglas anteriores en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] CRS agrupar y cambiar el nombre de la regla de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="4a853-111">In the Operations Manager Administrator console, create a copy of either of the two preceding rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Core Rule group, and rename the rule appropriately.</span></span>  
  
- <span data-ttu-id="4a853-112">En la sección de criterios de la regla, cambie la comparación de comodín para el parámetro 1 adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="4a853-112">In the criteria section for the rule, change the wildcard comparison for Parameter 1 appropriately.</span></span>  
  
- <span data-ttu-id="4a853-113">En algunos casos, los nombres de los trabajos son dependientes de nombres de base de datos que crea el usuario, por ejemplo, el nombre de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a853-113">In some cases, job names are dependent on database names that the user creates, for example, the name of the MessageBox database.</span></span>  
  
- <span data-ttu-id="4a853-114">La regla puede estar dirigida a un trabajo asociado con un único cuadro de mensajes o todos los cuadros de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a853-114">Your rule can be targeted either towards a job associated with a single MessageBox or all MessageBoxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a853-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a853-115">See Also</span></span>  
 [<span data-ttu-id="4a853-116">Cómo iniciar al Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a853-116">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)
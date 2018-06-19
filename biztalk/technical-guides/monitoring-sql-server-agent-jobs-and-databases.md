---
title: Supervisión de trabajos del Agente SQL Server y bases de datos | Documentos de Microsoft
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
ms.openlocfilehash: f6c9991e7ebd61c72bbeb6a090b0497244da63e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299204"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a><span data-ttu-id="0ca03-102">Supervisar bases de datos y trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ca03-102">Monitoring SQL Server Agent Jobs and Databases</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0ca03-103">incluye varios [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente que realizan funciones importantes para mantener los servidores operativos y en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0ca03-103"> includes multiple [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="0ca03-104">Por ello, debe supervisar el estado de funcionamiento de estos trabajos y garantizar que no se producen errores en su ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ca03-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span> <span data-ttu-id="0ca03-105">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración contiene reglas para supervisar elementos tales como bases de datos SQL y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="0ca03-105">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack contains rules for monitoring items such as SQL databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="0ca03-106">Debe configurar el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración para una supervisión completa de todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente.</span><span class="sxs-lookup"><span data-stu-id="0ca03-106">You should configure the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack for comprehensive monitoring of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="0ca03-107">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración incluye dos reglas deshabilitadas para supervisar el estado de dos de lo más importante BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente:</span><span class="sxs-lookup"><span data-stu-id="0ca03-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack includes two disabled rules for monitoring the health of two of the most important BizTalk [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs:</span></span>  
  
-   <span data-ttu-id="0ca03-108">Error crítico: Un trabajo del Agente SQL Server de BizTalk no se pudo: copia de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0ca03-108">Critical Error: A BizTalk SQL Server Agent job failed - Backup BizTalk Server</span></span>  
  
-   <span data-ttu-id="0ca03-109">Error crítico: Error en un trabajo de agente SQL Server de BizTalk: realiza el seguimiento de copia del mensaje</span><span class="sxs-lookup"><span data-stu-id="0ca03-109">Critical Error: A BizTalk SQL Server Agent job failed – Tracked Message Copy</span></span>  
  
 <span data-ttu-id="0ca03-110">Para supervisar todos los BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente desde la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, debe habilitar estas reglas y cree reglas adicionales para otros trabajos que desea supervisar mediante el proceso siguiente.</span><span class="sxs-lookup"><span data-stu-id="0ca03-110">To monitor all BizTalk Server [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack, you must enable these rules and create additional rules for other jobs that you want to monitor using the following process.</span></span>  
  
-   <span data-ttu-id="0ca03-111">En la consola de administrador de Operations Manager, cree una copia de cualquiera de las dos reglas anteriores en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reglas principales de agrupar y cambiar el nombre de la regla de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="0ca03-111">In the Operations Manager Administrator console, create a copy of either of the two preceding rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Core Rule group, and rename the rule appropriately.</span></span>  
  
-   <span data-ttu-id="0ca03-112">En la sección de criterios de la regla, cambiar la comparación de comodín para el parámetro 1 correctamente.</span><span class="sxs-lookup"><span data-stu-id="0ca03-112">In the criteria section for the rule, change the wildcard comparison for Parameter 1 appropriately.</span></span>  
  
-   <span data-ttu-id="0ca03-113">En algunos casos, los nombres de los trabajos son dependientes de nombres de base de datos creados por el usuario, por ejemplo, el nombre de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ca03-113">In some cases, job names are dependent on database names that the user creates, for example, the name of the MessageBox database.</span></span>  
  
-   <span data-ttu-id="0ca03-114">La regla se puede destinar a un trabajo asociado con un único cuadro de mensajes o todos los cuadros de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ca03-114">Your rule can be targeted either towards a job associated with a single MessageBox or all MessageBoxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca03-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ca03-115">See Also</span></span>  
 [<span data-ttu-id="0ca03-116">Cómo iniciar al Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ca03-116">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)
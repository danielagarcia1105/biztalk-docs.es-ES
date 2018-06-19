---
title: Supervisión de trabajos del Agente SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489e9e8e8b5bf5b00125036d71ff5fa0f37f3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298964"
---
# <a name="monitoring-sql-server-agent-jobs"></a><span data-ttu-id="96f61-102">Supervisión de trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="96f61-102">Monitoring SQL Server Agent Jobs</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="96f61-103">incluye varios trabajos del Agente SQL Server que realizan funciones importantes para mantener los servidores operativos y en buen estado.</span><span class="sxs-lookup"><span data-stu-id="96f61-103"> includes multiple SQL Server Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="96f61-104">Por ello, debe supervisar el estado de funcionamiento de estos trabajos y garantizar que no se producen errores en su ejecución.</span><span class="sxs-lookup"><span data-stu-id="96f61-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span>  
  
## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a><span data-ttu-id="96f61-105">Directrices para supervisar los trabajos del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="96f61-105">Guidelines for Monitoring the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="96f61-106">Siguientes son directrices para la supervisión de los trabajos:</span><span class="sxs-lookup"><span data-stu-id="96f61-106">Following are guidelines for monitoring the jobs:</span></span>  
  
-   <span data-ttu-id="96f61-107">**Compruebe que está ejecutando el servicio Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="96f61-107">**Verify that the SQL Server Agent service is running**</span></span>  
  
-   <span data-ttu-id="96f61-108">**Compruebe que los trabajos de agente SQL Server instalados por BizTalk Server están habilitado y ejecutándose correctamente**</span><span class="sxs-lookup"><span data-stu-id="96f61-108">**Verify that the SQL Server Agent jobs installed by BizTalk Server are enabled and running successfully**</span></span>  
  
     <span data-ttu-id="96f61-109">La [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos del Agente SQL Server son cruciales: si no es así, se verá afectado el rendimiento del sistema con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="96f61-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server Agent jobs are crucial: if they are not running, system performance will degrade over time.</span></span>  
  
-   <span data-ttu-id="96f61-110">**Compruebe que se completan los trabajos del Agente SQL Server de BizTalk Server de manera oportuna**</span><span class="sxs-lookup"><span data-stu-id="96f61-110">**Verify that the BizTalk Server SQL Server Agent jobs are completing in a timely manner**</span></span>  
  
     <span data-ttu-id="96f61-111">Configura Microsoft System Center Operations Manager para supervisar los trabajos.</span><span class="sxs-lookup"><span data-stu-id="96f61-111">Set up Microsoft System Center Operations Manager to monitor the jobs.</span></span>  
  
     <span data-ttu-id="96f61-112">Debe tener en cuenta las programaciones que son específicas de determinados trabajos:</span><span class="sxs-lookup"><span data-stu-id="96f61-112">You should be aware of schedules that are particular to certain jobs:</span></span>  
  
    -   <span data-ttu-id="96f61-113">El trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb se ejecuta sin interrupción de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96f61-113">The MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job runs continuously by default.</span></span> <span data-ttu-id="96f61-114">Software de supervisión debe tener esta programación en cuenta y no generan advertencias.</span><span class="sxs-lookup"><span data-stu-id="96f61-114">Monitoring software should take this schedule into account and not produce warnings.</span></span>  
  
    -   <span data-ttu-id="96f61-115">El trabajo MessageBox_Message_Cleanup_BizTalkMsgBoxDb no está habilitado o programado, pero se inicia el trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb cada 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="96f61-115">The MessageBox_Message_Cleanup_BizTalkMsgBoxDb job is not enabled or scheduled, but it is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job every 10 seconds.</span></span> <span data-ttu-id="96f61-116">Por lo tanto, este trabajo debe no ser habilitado, programado o iniciar de forma manual.</span><span class="sxs-lookup"><span data-stu-id="96f61-116">Therefore, this job should not be enabled, scheduled, or manually started.</span></span>  
  
-   <span data-ttu-id="96f61-117">**Compruebe que el tipo de inicio del servicio Agente SQL Server está configurado correctamente**</span><span class="sxs-lookup"><span data-stu-id="96f61-117">**Verify that the Startup type of the SQL Server Agent service is configured correctly**</span></span>  
  
     <span data-ttu-id="96f61-118">Compruebe que el servicio Agente SQL Server está configurado con un **Startuptype** de **automática** a menos que el servicio Agente SQL Server está configurado como un recurso de clúster en un clúster de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="96f61-118">Verify that the SQL Server Agent service is configured with a **Startuptype** of **Automatic** unless the SQL Server Agent service is configured as a cluster resource on a Windows Server cluster.</span></span> <span data-ttu-id="96f61-119">Si el servicio Agente SQL Server está configurado como un recurso de clúster, debe configurar el **Startuptype** como **Manual** puesto que el servicio se administrarán con el servicio de Cluster Server.</span><span class="sxs-lookup"><span data-stu-id="96f61-119">If the SQL Server Agent service is configured as a cluster resource, then you should configure the **Startuptype** as **Manual** since the service will be managed by the Cluster service.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="96f61-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="96f61-120">Additional Resources</span></span>  
  
-   <span data-ttu-id="96f61-121">Para obtener más información acerca de cómo supervisar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trabajos del Agente SQL, consulte [trabajos del agente de supervisión de SQL Server y bases de datos](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).</span><span class="sxs-lookup"><span data-stu-id="96f61-121">For more information about monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Agent jobs, see [Monitoring SQL Server Agent Jobs and Databases](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).</span></span>  
  
-   <span data-ttu-id="96f61-122">Para obtener más información sobre los trabajos del Agente SQL Server que se incluyen con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vea ["Estructura de base de datos y trabajos"](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451).</span><span class="sxs-lookup"><span data-stu-id="96f61-122">For more information about the SQL Server Agent jobs that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] see ["Database Structure and Jobs"](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451).</span></span>
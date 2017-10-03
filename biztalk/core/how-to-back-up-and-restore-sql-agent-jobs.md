---
title: "Cómo realizar copias de y restaurar trabajos del Agente SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a><span data-ttu-id="9e684-102">Cómo realizar copias de seguridad y restaurar trabajos del Agente SQL</span><span class="sxs-lookup"><span data-stu-id="9e684-102">How to Back Up and Restore SQL Agent Jobs</span></span>
<span data-ttu-id="9e684-103">En este tema se describe cómo crear una copia de seguridad de los trabajos del Agente SQL Server y restaurarlos.</span><span class="sxs-lookup"><span data-stu-id="9e684-103">This topic describes how to back up and restore SQL Server Agent Jobs.</span></span> <span data-ttu-id="9e684-104">Debe crear copia de seguridad de los trabajos SQL después de configurarlos.</span><span class="sxs-lookup"><span data-stu-id="9e684-104">You should back up your SQL jobs after you configure them.</span></span>  
  
## <a name="biztalk-server-jobs"></a><span data-ttu-id="9e684-105">Trabajos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9e684-105">BizTalk Server Jobs</span></span>  
 <span data-ttu-id="9e684-106">Los siguientes trabajos del Agente SQL Server están asociados a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e684-106">The following SQL Server Agent jobs are associated with BizTalk Server.</span></span> <span data-ttu-id="9e684-107">Los trabajos instalados en cada servidor son diferentes según las características instaladas y configuradas.</span><span class="sxs-lookup"><span data-stu-id="9e684-107">The jobs installed on each server are different depending on which features are installed and configured.</span></span> <span data-ttu-id="9e684-108">La mayoría de estos trabajos se crea durante la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e684-108">Most of these jobs are created during BizTalk Server setup.</span></span> <span data-ttu-id="9e684-109">Algunos se crean al configurar el envío de registro.</span><span class="sxs-lookup"><span data-stu-id="9e684-109">Several are created when configuring log shipping.</span></span>  
  
-   <span data-ttu-id="9e684-110">Copia de seguridad de BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="9e684-110">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="9e684-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="9e684-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
-   <span data-ttu-id="9e684-112">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="9e684-112">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
-   <span data-ttu-id="9e684-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="9e684-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
-   <span data-ttu-id="9e684-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="9e684-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="9e684-122">Envío de registro BTS - Obtener historial de copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="9e684-122">BTS Log Shipping Get Backup History</span></span>  
  
-   <span data-ttu-id="9e684-123">Envío de registro BTS - Restaurar base de datos</span><span class="sxs-lookup"><span data-stu-id="9e684-123">BTS Log Shipping Restore Database</span></span>  
  
-   <span data-ttu-id="9e684-124">Envío de registro BTS - Restaurar en marca</span><span class="sxs-lookup"><span data-stu-id="9e684-124">BTS Log Shipping Restore To Mark</span></span>  
  
## <a name="back-up-a-job-using-a-script"></a><span data-ttu-id="9e684-125">Un trabajo de copia de seguridad mediante un script</span><span class="sxs-lookup"><span data-stu-id="9e684-125">Back up a job using a script</span></span>  
  
1.  <span data-ttu-id="9e684-126">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="9e684-126">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="9e684-127">Expanda **Agente SQL Server** y **Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="9e684-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="9e684-128">Haga clic en el trabajo que desea crear un script para copia de seguridad y, a continuación, seleccione **incluir trabajo como**.</span><span class="sxs-lookup"><span data-stu-id="9e684-128">Right-click the job you want to create a backup script for, and then select **Script Job as**.</span></span>  
  
4.  <span data-ttu-id="9e684-129">Seleccione **CREATE To** o **DROP To**, a continuación, seleccione **nueva ventana del Editor de consultas**, **archivo**, o **Portapapeles** Para seleccionar un destino para la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="9e684-129">Select **CREATE To** or **DROP To**, then select **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="9e684-130">Normalmente, el destino es un archivo con un **.sql** extensión.</span><span class="sxs-lookup"><span data-stu-id="9e684-130">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="9e684-131">Repita este procedimiento en el paso 3 para cada trabajo que desee incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="9e684-131">Repeat this procedure from Step 3 for each job you want to script.</span></span> <span data-ttu-id="9e684-132">Consulte la lista de trabajos relacionados con BizTalk Server para determinar qué trabajos debe incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="9e684-132">Refer to the list of BizTalk Server related jobs to determine which jobs you need to script.</span></span>  
  
     <span data-ttu-id="9e684-133">Como mínimo, debe realizar una copia de la **copia de seguridad de BizTalk Server (BizTalkMgmtDb)** tras la configuración del trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e684-133">At a minimum, you should back up the **Backup BizTalk Server (BizTalkMgmtDb)** job after it is configured.</span></span>  
  
## <a name="restore-a-job-from-a-script"></a><span data-ttu-id="9e684-134">Un trabajo de restauración de una secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="9e684-134">Restore a job from a script</span></span>  
  
1.  <span data-ttu-id="9e684-135">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="9e684-135">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="9e684-136">En el **archivo** menú, **abiertos** el archivo que contiene el trabajo con scripts.</span><span class="sxs-lookup"><span data-stu-id="9e684-136">On the **File** menu, **Open** the file containing the scripted job.</span></span>  
  
3.  <span data-ttu-id="9e684-137">Ejecute el script para crear el trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e684-137">Execute the script to create the job.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e684-138">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9e684-138">Next Steps</span></span>  
 [<span data-ttu-id="9e684-139">Cómo realizar copias de y restaurar inicios de sesión SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e684-139">How to Back Up and Restore SQL Server Logins</span></span>](../core/how-to-back-up-and-restore-sql-server-logins.md)
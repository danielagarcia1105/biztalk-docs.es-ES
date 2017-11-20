---
title: Procedimientos almacenados del servicio de Bus de eventos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-event-bus-service-stored-procedures"></a><span data-ttu-id="ee325-102">Procedimientos almacenados del servicio de bus de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="ee325-102">BAM Event Bus Service Stored Procedures</span></span>
<span data-ttu-id="ee325-103">Los siguientes procedimientos almacenados se utilizan para administrar el servicio de bus de eventos BAM:</span><span class="sxs-lookup"><span data-stu-id="ee325-103">You use the following stored procedures to manage the BAM Event Bus service:</span></span>  
  
-   <span data-ttu-id="ee325-104">Para pausar el servicio de bus de eventos BAM, ejecute el procedimiento almacenado TDDS_BlockTDDS en una transacción de la base de datos de BAM (pero sin confirmar la transacción).</span><span class="sxs-lookup"><span data-stu-id="ee325-104">To pause the BAM Event Bus service, execute the TDDS_BlockTDDS stored procedure within a transaction (without committing the transaction) on the BAM database.</span></span> <span data-ttu-id="ee325-105">Para reanudar el servicio de bus de eventos BAM, confirme la transacción TDDS_BlockTDDS.</span><span class="sxs-lookup"><span data-stu-id="ee325-105">To resume the BAM Event Bus service, commit the TDDS_BlockTDDS transaction.</span></span>  
  
-   <span data-ttu-id="ee325-106">Para habilitar el servicio de bus de eventos BAM en varios equipos, determine los hosts que se van a utilizar en el proceso de seguimiento y, a continuación, una esos equipos al host de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ee325-106">To enable the BAM Event Bus service on multiple computers, identify which host(s) to use for tracking, and then join those computers to the tracking host.</span></span>  
  
-   <span data-ttu-id="ee325-107">Para configurar un intervalo de latido y un tiempo de espera de sesión, utilice el procedimiento almacenado TDDS_UpdateSettings.</span><span class="sxs-lookup"><span data-stu-id="ee325-107">To set up a session time-out and heartbeat interval, use the TDDS_UpdateSettings stored procedure.</span></span> <span data-ttu-id="ee325-108">solo los miembros del grupo BTS_ADMIN_USERS tienen permiso para ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ee325-108">Only members of the BTS_ADMIN_USERS group have permission to execute this stored procedure.</span></span>  
  
     <span data-ttu-id="ee325-109">El procedimiento almacenado TDDS_UpdateSettings consta de los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="ee325-109">The TDDS_UpdateSettings stored procedure has the following parameters:</span></span>  
  
    -   <span data-ttu-id="ee325-110">@RefreshIntervalint. Definido como superior a 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="ee325-110">@RefreshInterval int. Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="ee325-111">@SqlCommandTimeoutint. Definido como inferior a RefreshInterval.</span><span class="sxs-lookup"><span data-stu-id="ee325-111">@SqlCommandTimeout int. Set to less than RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="ee325-112">@SessionTimeoutint. Definido como superior al doble de RefreshInterval.</span><span class="sxs-lookup"><span data-stu-id="ee325-112">@SessionTimeout int. Set to greater than two times the RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="ee325-113">@EventLoggingIntervalnvarchar(16).</span><span class="sxs-lookup"><span data-stu-id="ee325-113">@EventLoggingInterval nvarchar(16).</span></span> <span data-ttu-id="ee325-114">Definido como superior a 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="ee325-114">Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="ee325-115">@RetryCountint. Establece en mayor que 60 segundos</span><span class="sxs-lookup"><span data-stu-id="ee325-115">@RetryCount int. Set to greater than 60 seconds</span></span>  
  
    -   <span data-ttu-id="ee325-116">@ThreadPerSessionint. Este parámetro es obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ee325-116">@ThreadPerSession int. This parameter is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee325-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee325-117">See Also</span></span>  
 [<span data-ttu-id="ee325-118">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="ee325-118">Managing BAM</span></span>](../core/managing-bam.md)
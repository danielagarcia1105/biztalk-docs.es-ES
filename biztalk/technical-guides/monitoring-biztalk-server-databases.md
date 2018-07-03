---
title: Supervisión de bases de datos de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fee5015-e818-459b-aeeb-a084ef355600
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3cb759bf377cfe77f1e346a94fca739b8532a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002133"
---
# <a name="monitoring-biztalk-server-databases"></a><span data-ttu-id="5ba70-102">Supervisión de las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5ba70-102">Monitoring BizTalk Server Databases</span></span>
<span data-ttu-id="5ba70-103">Puede ejecutar el trabajo del Agente SQL de supervisar BizTalk Server para identificar los problemas conocidos de las bases de datos de administración, el cuadro de mensaje o DTA.</span><span class="sxs-lookup"><span data-stu-id="5ba70-103">You can run the Monitor BizTalk Server SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="5ba70-104">El trabajo se crea al configurar un grupo de BizTalk en la consola de administración de BizTalk Server o al actualizar la versión anterior de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5ba70-104">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
## <a name="the-monitor-biztalk-server-job"></a><span data-ttu-id="5ba70-105">El trabajo del Monitor de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5ba70-105">The Monitor BizTalk Server Job</span></span>  
 <span data-ttu-id="5ba70-106">El trabajo Supervisar BizTalk Server busca los siguientes problemas en la administración, el cuadro de mensaje y las bases de datos DTA:</span><span class="sxs-lookup"><span data-stu-id="5ba70-106">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ba70-107">El trabajo Supervisar BizTalk Server solo busca los problemas.</span><span class="sxs-lookup"><span data-stu-id="5ba70-107">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="5ba70-108">No arregla los problemas que encuentra.</span><span class="sxs-lookup"><span data-stu-id="5ba70-108">It does not fix the issues found.</span></span>  
  
- <span data-ttu-id="5ba70-109">Mensajes sin referencias</span><span class="sxs-lookup"><span data-stu-id="5ba70-109">Messages without any references</span></span>  
  
- <span data-ttu-id="5ba70-110">Mensajes sin números de referencia</span><span class="sxs-lookup"><span data-stu-id="5ba70-110">Messages without reference counts</span></span>  
  
- <span data-ttu-id="5ba70-111">Mensajes con número de referencia menor que 0</span><span class="sxs-lookup"><span data-stu-id="5ba70-111">Messages with reference count less than 0</span></span>  
  
- <span data-ttu-id="5ba70-112">Referencias de mensajes sin filas de colas de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ba70-112">Message references without spool rows</span></span>  
  
- <span data-ttu-id="5ba70-113">Referencias de mensaje sin instancias</span><span class="sxs-lookup"><span data-stu-id="5ba70-113">Message references without instances</span></span>  
  
- <span data-ttu-id="5ba70-114">Estado de instancia sin instancias</span><span class="sxs-lookup"><span data-stu-id="5ba70-114">Instance state without instances</span></span>  
  
- <span data-ttu-id="5ba70-115">Suscripciones de instancia sin instancias correspondientes</span><span class="sxs-lookup"><span data-stu-id="5ba70-115">Instance subscriptions without corresponding instances</span></span>  
  
- <span data-ttu-id="5ba70-116">Instancias de servicio DTA huérfano</span><span class="sxs-lookup"><span data-stu-id="5ba70-116">Orphaned DTA service instances</span></span>  
  
- <span data-ttu-id="5ba70-117">Excepciones de instancia de servicio DTA huérfano</span><span class="sxs-lookup"><span data-stu-id="5ba70-117">Orphaned DTA service instance exceptions</span></span>  
  
- <span data-ttu-id="5ba70-118">TDDS no se está ejecutando en cualquier instancia de host cuando está habilitada la opción de seguimiento global</span><span class="sxs-lookup"><span data-stu-id="5ba70-118">TDDS is not running on any host instance when global tracking option is enabled</span></span>  
  
  <span data-ttu-id="5ba70-119">El trabajo Supervisar BizTalk Server está configurado y automatizado para ejecutarse una vez a la semana.</span><span class="sxs-lookup"><span data-stu-id="5ba70-119">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="5ba70-120">Puesto que el trabajo es computacionalmente intensivo, se recomienda programarlo para que se ejecutan durante períodos de tiempo de inactividad o de poco tráfico.</span><span class="sxs-lookup"><span data-stu-id="5ba70-120">Since the job is computationally intensive, we recommended that you schedule it to run during periods of downtime or low traffic.</span></span>  
  <span data-ttu-id="5ba70-121">El trabajo se produce un error si encuentra algún problema; la cadena de error devuelta contiene el número de los problemas encontrados.</span><span class="sxs-lookup"><span data-stu-id="5ba70-121">The job fails if it encounters any issues; the error string returned contains the number of issues found.</span></span> <span data-ttu-id="5ba70-122">Si no, se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ba70-122">Else, it runs successfully.</span></span> <span data-ttu-id="5ba70-123">Puede ver los detalles en el historial del trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ba70-123">You can see the details in the job history.</span></span> <span data-ttu-id="5ba70-124">Si se ejecuta el trabajo con privilegios de administrador, la cadena de error se registrará en el historial de trabajos y el registro de aplicación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ba70-124">If you run the job with Administrator privileges, the error string will be logged to both the job history and the SQL Server Application log.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ba70-125">Error de este trabajo no necesariamente constituye un problema crítico, pero en su lugar un problema que se debe investigar y dirigirse como parte del mantenimiento regular de las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5ba70-125">Failure of this job does not necessarily constitute a critical issue, but rather an issue that should be investigated and addressed as part of regular maintenance of the BizTalk Server databases.</span></span> <span data-ttu-id="5ba70-126">Este trabajo no tiene éxito por diseño, en caso de que detecta uno de los problemas mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ba70-126">This job fails by design in the event it discovers one of the issues listed above.</span></span>
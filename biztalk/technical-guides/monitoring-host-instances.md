---
title: Supervisión de instancias de Host | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41dd0e01aa1e28862a3e99cfc767b3dd6ddec3c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008597"
---
# <a name="monitoring-host-instances"></a><span data-ttu-id="27e3f-102">Supervisión de instancias de Host</span><span class="sxs-lookup"><span data-stu-id="27e3f-102">Monitoring Host Instances</span></span>
<span data-ttu-id="27e3f-103">Este tema describe supervisión instancias de host de BizTalk mediante Microsoft System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="27e3f-103">This topic describes monitoring BizTalk host instances using Microsoft System Center Operations Manager.</span></span>  
  
## <a name="using-threshold-rules-to-monitor-health"></a><span data-ttu-id="27e3f-104">Uso de reglas de umbral para supervisar el estado</span><span class="sxs-lookup"><span data-stu-id="27e3f-104">Using Threshold Rules to Monitor Health</span></span>  
 <span data-ttu-id="27e3f-105">El módulo de administración de BizTalk Server incorpora reglas de umbral de rendimiento que proporcionan una vista completa del estado de los hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="27e3f-105">The BizTalk Server Management Pack incorporates performance threshold rules that provide a comprehensive view of the health of the BizTalk hosts.</span></span> <span data-ttu-id="27e3f-106">Se proporcionan dos tipos distintos de reglas de umbral:</span><span class="sxs-lookup"><span data-stu-id="27e3f-106">Two different types of threshold rules are provided:</span></span>  
  
-   <span data-ttu-id="27e3f-107">Reglas que se aplican genéricamente (por ejemplo, para todos los hosts de BizTalk y a todas las bases de datos de cuadro de mensajes).</span><span class="sxs-lookup"><span data-stu-id="27e3f-107">Rules that apply generically (for example, to all BizTalk hosts and to all MessageBox databases).</span></span>  
  
-   <span data-ttu-id="27e3f-108">Reglas que son específicas de un host de BizTalk determinado.</span><span class="sxs-lookup"><span data-stu-id="27e3f-108">Rules that are specific to a particular BizTalk host.</span></span>  
  
 <span data-ttu-id="27e3f-109">Las reglas genéricas supervisan todos los hosts de BizTalk tomando como base un umbral común.</span><span class="sxs-lookup"><span data-stu-id="27e3f-109">Generic rules monitor all the BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="27e3f-110">Por ejemplo, la regla de Monitor HostQ Size supervisa las colas de trabajo de todos los hosts de BizTalk tomando como base un umbral común.</span><span class="sxs-lookup"><span data-stu-id="27e3f-110">For example, the rule Monitor HostQ Size monitors the work queues of all BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="27e3f-111">Si hay tres hosts diferentes, la misma regla supervisa sus colas de trabajo y alertas se producen cuando cualquiera de las colas de trabajo de host cruza el umbral común.</span><span class="sxs-lookup"><span data-stu-id="27e3f-111">If there are three different hosts, all their work queues are monitored by the same rule, and alerts occur when any of the host work queues cross the common threshold.</span></span>  
  
 <span data-ttu-id="27e3f-112">Reglas de específico del host de BizTalk le permiten configurar varios umbrales para distintos hosts.</span><span class="sxs-lookup"><span data-stu-id="27e3f-112">BizTalk host-specific rules enable you to configure different thresholds for different hosts.</span></span> <span data-ttu-id="27e3f-113">Por ejemplo, la regla Monitor HostQ Size – BizTalkServerApplication es una regla específica de host que supervisa la cola de trabajo del host BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="27e3f-113">For example, the rule Monitor HostQ Size – BizTalkServerApplication is a host-specific rule that monitors the work queue of the BizTalkServerApplication host.</span></span> <span data-ttu-id="27e3f-114">En este ejemplo puede definir un proveedor concreto de Operations Manager para la instancia de contador de rendimiento específicos y usar ese proveedor en la regla de umbral.</span><span class="sxs-lookup"><span data-stu-id="27e3f-114">In this example you can define a specific Operations Manager provider for the particular performance counter instance and use that provider in the threshold rule.</span></span> <span data-ttu-id="27e3f-115">Dado que estas reglas son específicos del host, debe definir reglas específicas para cada host recién creado.</span><span class="sxs-lookup"><span data-stu-id="27e3f-115">Because these rules are host-specific, you must define rules specific to each newly created host.</span></span>  
  
 <span data-ttu-id="27e3f-116">Las reglas de específico del host de BizTalk se proporcionan como reglas de plantilla para crear reglas que son aplicables en su entorno.</span><span class="sxs-lookup"><span data-stu-id="27e3f-116">BizTalk host-specific rules are provided as template rules for creating rules that are applicable in your environment.</span></span> <span data-ttu-id="27e3f-117">Todas las reglas de supervisión de umbral están deshabilitadas de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="27e3f-117">All threshold monitoring rules are disabled by default:</span></span>  
  
-   <span data-ttu-id="27e3f-118">Debe configurar las reglas genéricas con valores de umbral específicos para su entorno.</span><span class="sxs-lookup"><span data-stu-id="27e3f-118">You should configure generic rules with threshold values specific to your environment.</span></span>  
  
-   <span data-ttu-id="27e3f-119">Debe crear reglas de específico del host de BizTalk en función de los umbrales adecuados y reglas de plantilla.</span><span class="sxs-lookup"><span data-stu-id="27e3f-119">You should create BizTalk host-specific rules based on the template rules and appropriate thresholds.</span></span>  
  
## <a name="monitoring-biztalk-host-instances"></a><span data-ttu-id="27e3f-120">Supervisar instancias de Host de BizTalk</span><span class="sxs-lookup"><span data-stu-id="27e3f-120">Monitoring BizTalk Host Instances</span></span>  
 <span data-ttu-id="27e3f-121">Las reglas dirigidas a hosts específicos de BizTalk son más flexibles desde la perspectiva de supervisión.</span><span class="sxs-lookup"><span data-stu-id="27e3f-121">Rules that target specific BizTalk hosts are more flexible from a monitoring perspective.</span></span> <span data-ttu-id="27e3f-122">Todas las reglas de supervisión de umbral para el host de BizTalkServerApplication proporcionado en el módulo de administración de BizTalk Server son reglas de plantilla.</span><span class="sxs-lookup"><span data-stu-id="27e3f-122">All threshold monitoring rules for the BizTalkServerApplication host provided in the BizTalk Server Management pack are template rules.</span></span> <span data-ttu-id="27e3f-123">Para usar estas reglas, debe usar la consola de administrador de Operations Manager para:</span><span class="sxs-lookup"><span data-stu-id="27e3f-123">In order to use these rules, you should use the Operations Manager Administrator console to:</span></span>  
  
-   <span data-ttu-id="27e3f-124">Crear una copia de la regla de plantilla en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de reglas y cambie su nombre.</span><span class="sxs-lookup"><span data-stu-id="27e3f-124">Create a copy of the template rule in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rule group and rename it.</span></span>  
  
-   <span data-ttu-id="27e3f-125">Crear un nuevo proveedor de Operations Manager para la instancia del contador de rendimiento específico del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="27e3f-125">Create a new Operations Manager provider for the BizTalk host-specific performance counter instance.</span></span>  
  
-   <span data-ttu-id="27e3f-126">Modificar el proveedor de Operations Manager utilizado la regla y haga que señale al nuevo.</span><span class="sxs-lookup"><span data-stu-id="27e3f-126">Modify the Operations Manager provider used by the rule and point it to the new one.</span></span>  
  
 <span data-ttu-id="27e3f-127">Suponga que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación tiene un host de BizTalk ReceiveHost y que desea supervisar el tamaño de la cola de Host para este host.</span><span class="sxs-lookup"><span data-stu-id="27e3f-127">Suppose your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation has a BizTalk host ReceiveHost and you want to monitor the Host Queue size for this host.</span></span> <span data-ttu-id="27e3f-128">En este caso, debe crear un proveedor de Operations Manager basado en la instancia de ReceiveHost del contador de rendimiento para el tamaño de la cola del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="27e3f-128">In this case, you should create a Operations Manager provider based on the ReceiveHost instance of the performance counter for the queue size for the BizTalk host.</span></span> <span data-ttu-id="27e3f-129">También debe establecer el valor del umbral en la regla de modo que sea adecuado para su entorno.</span><span class="sxs-lookup"><span data-stu-id="27e3f-129">You should also set the threshold value in the rule appropriately for your environment.</span></span>  
  
 <span data-ttu-id="27e3f-130">Si usa reglas de umbral específico del host de supervisión, debe deshabilitar las reglas de supervisión genéricas.</span><span class="sxs-lookup"><span data-stu-id="27e3f-130">If you are using host-specific threshold monitoring rules, you should disable generic monitoring rules.</span></span> <span data-ttu-id="27e3f-131">De este modo se evitan las alertas redundantes.</span><span class="sxs-lookup"><span data-stu-id="27e3f-131">This prevents redundant alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e3f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e3f-132">See Also</span></span>  
 [<span data-ttu-id="27e3f-133">Supervisión de BizTalk Server con System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="27e3f-133">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)
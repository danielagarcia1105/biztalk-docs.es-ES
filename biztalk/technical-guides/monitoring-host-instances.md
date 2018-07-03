---
title: Supervisión de instancias de Host | Microsoft Docs
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
ms.openlocfilehash: 91ad5ec158466db6716b515fe3d34ae76c4cde0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003341"
---
# <a name="monitoring-host-instances"></a><span data-ttu-id="af40b-102">Supervisión de instancias de Host</span><span class="sxs-lookup"><span data-stu-id="af40b-102">Monitoring Host Instances</span></span>
<span data-ttu-id="af40b-103">Este tema describe la supervisión de las instancias de host de BizTalk mediante Microsoft System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="af40b-103">This topic describes monitoring BizTalk host instances using Microsoft System Center Operations Manager.</span></span>  
  
## <a name="using-threshold-rules-to-monitor-health"></a><span data-ttu-id="af40b-104">Uso de reglas de umbral para supervisar el estado</span><span class="sxs-lookup"><span data-stu-id="af40b-104">Using Threshold Rules to Monitor Health</span></span>  
 <span data-ttu-id="af40b-105">El módulo de administración de BizTalk Server incorpora reglas de umbral de rendimiento que proporcionan una visión completa del estado de los hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="af40b-105">The BizTalk Server Management Pack incorporates performance threshold rules that provide a comprehensive view of the health of the BizTalk hosts.</span></span> <span data-ttu-id="af40b-106">Se proporcionan dos tipos distintos de reglas de umbral:</span><span class="sxs-lookup"><span data-stu-id="af40b-106">Two different types of threshold rules are provided:</span></span>  
  
- <span data-ttu-id="af40b-107">Reglas que se aplican de forma genérica (por ejemplo, para todos los hosts de BizTalk y a todas las bases de datos de cuadro de mensajes).</span><span class="sxs-lookup"><span data-stu-id="af40b-107">Rules that apply generically (for example, to all BizTalk hosts and to all MessageBox databases).</span></span>  
  
- <span data-ttu-id="af40b-108">Reglas que son específicas de un determinado host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="af40b-108">Rules that are specific to a particular BizTalk host.</span></span>  
  
  <span data-ttu-id="af40b-109">Las reglas genéricas supervisan todos los hosts de BizTalk según un umbral común.</span><span class="sxs-lookup"><span data-stu-id="af40b-109">Generic rules monitor all the BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="af40b-110">Por ejemplo, la regla de Monitor HostQ Size supervisa las colas de trabajo de todos los hosts de BizTalk según un umbral común.</span><span class="sxs-lookup"><span data-stu-id="af40b-110">For example, the rule Monitor HostQ Size monitors the work queues of all BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="af40b-111">Si hay tres hosts diferentes, la misma regla supervisa todas las colas de trabajo y las alertas se producen cuando cualquiera de las colas de trabajo de host cruza el umbral común.</span><span class="sxs-lookup"><span data-stu-id="af40b-111">If there are three different hosts, all their work queues are monitored by the same rule, and alerts occur when any of the host work queues cross the common threshold.</span></span>  
  
  <span data-ttu-id="af40b-112">Reglas específicas del host de BizTalk le permiten configurar varios umbrales para distintos hosts.</span><span class="sxs-lookup"><span data-stu-id="af40b-112">BizTalk host-specific rules enable you to configure different thresholds for different hosts.</span></span> <span data-ttu-id="af40b-113">Por ejemplo, la regla de Monitor HostQ Size – BizTalkServerApplication es una regla de host específico que supervisa la cola de trabajo del host BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="af40b-113">For example, the rule Monitor HostQ Size – BizTalkServerApplication is a host-specific rule that monitors the work queue of the BizTalkServerApplication host.</span></span> <span data-ttu-id="af40b-114">En este ejemplo puede definir un proveedor específico de Operations Manager para la instancia de contador de rendimiento determinado y usar ese proveedor en la regla de umbral.</span><span class="sxs-lookup"><span data-stu-id="af40b-114">In this example you can define a specific Operations Manager provider for the particular performance counter instance and use that provider in the threshold rule.</span></span> <span data-ttu-id="af40b-115">Dado que estas reglas son específicos del host, debe definir reglas específicas para cada host recién creado.</span><span class="sxs-lookup"><span data-stu-id="af40b-115">Because these rules are host-specific, you must define rules specific to each newly created host.</span></span>  
  
  <span data-ttu-id="af40b-116">Reglas específicas del host de BizTalk se proporcionan como reglas de plantilla para crear reglas que son aplicables en su entorno.</span><span class="sxs-lookup"><span data-stu-id="af40b-116">BizTalk host-specific rules are provided as template rules for creating rules that are applicable in your environment.</span></span> <span data-ttu-id="af40b-117">Todas las reglas de supervisión de umbral están deshabilitadas de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="af40b-117">All threshold monitoring rules are disabled by default:</span></span>  
  
- <span data-ttu-id="af40b-118">Debe configurar las reglas genéricas con valores de umbral específicos para su entorno.</span><span class="sxs-lookup"><span data-stu-id="af40b-118">You should configure generic rules with threshold values specific to your environment.</span></span>  
  
- <span data-ttu-id="af40b-119">Debe crear reglas de específico del host de BizTalk según las reglas de plantilla y los umbrales apropiados.</span><span class="sxs-lookup"><span data-stu-id="af40b-119">You should create BizTalk host-specific rules based on the template rules and appropriate thresholds.</span></span>  
  
## <a name="monitoring-biztalk-host-instances"></a><span data-ttu-id="af40b-120">Supervisión de instancias de Host de BizTalk</span><span class="sxs-lookup"><span data-stu-id="af40b-120">Monitoring BizTalk Host Instances</span></span>  
 <span data-ttu-id="af40b-121">Las reglas dirigidas a hosts específicos de BizTalk son más flexibles desde una perspectiva de supervisión.</span><span class="sxs-lookup"><span data-stu-id="af40b-121">Rules that target specific BizTalk hosts are more flexible from a monitoring perspective.</span></span> <span data-ttu-id="af40b-122">Todas las reglas de supervisión de umbral para el host de BizTalkServerApplication proporcionado en el módulo de administración de BizTalk Server son reglas de plantilla.</span><span class="sxs-lookup"><span data-stu-id="af40b-122">All threshold monitoring rules for the BizTalkServerApplication host provided in the BizTalk Server Management pack are template rules.</span></span> <span data-ttu-id="af40b-123">Para poder usar estas reglas, debe usar la consola de administrador de Operations Manager para:</span><span class="sxs-lookup"><span data-stu-id="af40b-123">In order to use these rules, you should use the Operations Manager Administrator console to:</span></span>  
  
- <span data-ttu-id="af40b-124">Crear una copia de la regla de plantilla en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de reglas y cambie su nombre.</span><span class="sxs-lookup"><span data-stu-id="af40b-124">Create a copy of the template rule in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rule group and rename it.</span></span>  
  
- <span data-ttu-id="af40b-125">Crear un nuevo proveedor de Operations Manager para la instancia del contador de rendimiento específicos de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="af40b-125">Create a new Operations Manager provider for the BizTalk host-specific performance counter instance.</span></span>  
  
- <span data-ttu-id="af40b-126">Modificar el proveedor de Operations Manager utilizado la regla y haga que señale al nuevo.</span><span class="sxs-lookup"><span data-stu-id="af40b-126">Modify the Operations Manager provider used by the rule and point it to the new one.</span></span>  
  
  <span data-ttu-id="af40b-127">Supongamos que su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación tiene un host de BizTalk denominado ReceiveHost y que desea supervisar el tamaño de cola de Host para este host.</span><span class="sxs-lookup"><span data-stu-id="af40b-127">Suppose your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation has a BizTalk host ReceiveHost and you want to monitor the Host Queue size for this host.</span></span> <span data-ttu-id="af40b-128">En este caso, debe crear un proveedor de Operations Manager basado en la instancia de ReceiveHost del contador de rendimiento para el tamaño de la cola del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="af40b-128">In this case, you should create a Operations Manager provider based on the ReceiveHost instance of the performance counter for the queue size for the BizTalk host.</span></span> <span data-ttu-id="af40b-129">También debe establecer el valor del umbral en la regla de modo que sea adecuado para su entorno.</span><span class="sxs-lookup"><span data-stu-id="af40b-129">You should also set the threshold value in the rule appropriately for your environment.</span></span>  
  
  <span data-ttu-id="af40b-130">Si usa reglas de supervisión de umbral específico del host, debe deshabilitar las reglas de supervisión genéricas.</span><span class="sxs-lookup"><span data-stu-id="af40b-130">If you are using host-specific threshold monitoring rules, you should disable generic monitoring rules.</span></span> <span data-ttu-id="af40b-131">De este modo se evitan las alertas redundantes.</span><span class="sxs-lookup"><span data-stu-id="af40b-131">This prevents redundant alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af40b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="af40b-132">See Also</span></span>  
 [<span data-ttu-id="af40b-133">Supervisión de BizTalk Server con System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="af40b-133">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)
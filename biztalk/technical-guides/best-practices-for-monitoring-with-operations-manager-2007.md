---
title: Procedimientos recomendados para la supervisión con Operations Manager 2007 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d099ba9ea60fd8f553d4eaf2011e93a054f59e68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018711"
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a><span data-ttu-id="b67fb-102">Procedimientos recomendados para la supervisión con Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="b67fb-102">Best Practices for Monitoring with Operations Manager 2007</span></span>
<span data-ttu-id="b67fb-103">Respetar las prácticas recomendadas descritas en este tema para supervisar de forma eficaz las aplicaciones mediante Operations Manager 2007.</span><span class="sxs-lookup"><span data-stu-id="b67fb-103">Adhere to the best practices listed in this topic to effectively monitor your applications using Operations Manager 2007.</span></span>  
  
 <span data-ttu-id="b67fb-104">**Instalar módulos de administración adicionales para una cobertura más completa**</span><span class="sxs-lookup"><span data-stu-id="b67fb-104">**Install additional management packs for more complete coverage**</span></span>  
  
- <span data-ttu-id="b67fb-105">Para ayudar a garantizar que Operations Manager 2007 supervisa las aplicaciones clave en su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, debe instalar los módulos de administración siguientes:</span><span class="sxs-lookup"><span data-stu-id="b67fb-105">To help ensure that Operations Manager 2007 monitors the key applications in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, you should install the following management packs:</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b67fb-106"> (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b67fb-106"> (required)</span></span>  
  
  - <span data-ttu-id="b67fb-107">Sistema operativo de servidor de Windows (opcional)</span><span class="sxs-lookup"><span data-stu-id="b67fb-107">Windows Server Operating System (optional)</span></span>  
  
  - <span data-ttu-id="b67fb-108">Clúster de conmutación por error de servidor de Microsoft Windows (si los clústeres son utilizado, opcional)</span><span class="sxs-lookup"><span data-stu-id="b67fb-108">Microsoft Windows Server Failover Cluster (if clusters are used, optional)</span></span>  
  
  - <span data-ttu-id="b67fb-109">Supervisión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b67fb-109">SQL Server Monitoring</span></span>  
  
  - <span data-ttu-id="b67fb-110">Internet Information Services 7</span><span class="sxs-lookup"><span data-stu-id="b67fb-110">Internet Information Services 7</span></span>  
  
  - <span data-ttu-id="b67fb-111">Message Queue Server (MSMQ) 5.0 (opcional)</span><span class="sxs-lookup"><span data-stu-id="b67fb-111">Message Queuing (MSMQ) 5.0 (optional)</span></span>  
  
  <span data-ttu-id="b67fb-112">**Revisar y priorizar las alertas por día**</span><span class="sxs-lookup"><span data-stu-id="b67fb-112">**Review and prioritize alerts on a daily basis**</span></span>  
  
- <span data-ttu-id="b67fb-113">Al revisar las alertas y establecer prioridades entre ellas a diario, se contribuye a la resolución de los problemas de una forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="b67fb-113">Reviewing and prioritizing alerts on a daily basis helps to ensure that issues are resolved in a timely manner.</span></span>  
  
  <span data-ttu-id="b67fb-114">**Compruebe que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunica con el servidor de Operations Manager 2007.**</span><span class="sxs-lookup"><span data-stu-id="b67fb-114">**Verify that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is communicating with the Operations Manager 2007 server.**</span></span>  
  
- <span data-ttu-id="b67fb-115">Si se produce un error de comunicación entre los servidores que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la infraestructura de supervisión, no recibirá las alertas.</span><span class="sxs-lookup"><span data-stu-id="b67fb-115">If communication fails between the servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the monitoring infrastructure, you will not receive alerts.</span></span>  
  
  <span data-ttu-id="b67fb-116">**Habilitar y deshabilitar las reglas según sea necesario**</span><span class="sxs-lookup"><span data-stu-id="b67fb-116">**Enable and disable rules as necessary**</span></span>  
  
- <span data-ttu-id="b67fb-117">De forma predeterminada, algunas de las reglas en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b67fb-117">By default, some of the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack are disabled.</span></span> <span data-ttu-id="b67fb-118">Las reglas deshabilitadas son de los siguientes tipos: reglas que necesitan personalización, reglas que se utilizan como plantillas y reglas para la supervisión adicional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] eventos.</span><span class="sxs-lookup"><span data-stu-id="b67fb-118">These disabled rules are of the following types: rules needing customization, rules that serve as templates, and rules for monitoring additional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] events.</span></span> <span data-ttu-id="b67fb-119">Asegúrese de que las reglas pertinentes su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b67fb-119">Make sure the relevant rules for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment are enabled.</span></span>  
  
  <span data-ttu-id="b67fb-120">**Personalización de reglas según sea necesario para su entorno**</span><span class="sxs-lookup"><span data-stu-id="b67fb-120">**Customize rules as necessary for your environment**</span></span>  
  
- <span data-ttu-id="b67fb-121">Debería personalizar las reglas del paquete de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para obtener un mejor ajuste a su implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b67fb-121">You should customize the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack to suit your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span> <span data-ttu-id="b67fb-122">Algunas reglas requieren umbrales de supervisión y los umbrales de tiempo que se definen mejor según específica de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación.</span><span class="sxs-lookup"><span data-stu-id="b67fb-122">Some rules require monitoring thresholds or time thresholds that are best defined based on your specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
  <span data-ttu-id="b67fb-123">**Crear reglas adicionales según sea necesario, según las reglas incluidas en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración**</span><span class="sxs-lookup"><span data-stu-id="b67fb-123">**Create additional rules as necessary, based on the rules included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack**</span></span>  
  
- <span data-ttu-id="b67fb-124">Las reglas se proporcionan para su uso como plantillas para los artefactos que cree, como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts.</span><span class="sxs-lookup"><span data-stu-id="b67fb-124">Rules are provided for use as templates for artifacts that you create, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span> <span data-ttu-id="b67fb-125">Debería usar estas reglas de plantilla como referencia al crear reglas de artefactos específicos como:</span><span class="sxs-lookup"><span data-stu-id="b67fb-125">You should use these template rules as a reference when creating artifact-specific rules such as:</span></span>  
  
  -   <span data-ttu-id="b67fb-126">Reglas de host específico, por ejemplo, supervisión de la cola de host y supervisión de limitación de host</span><span class="sxs-lookup"><span data-stu-id="b67fb-126">Host-specific rules, for example, host queue monitoring, and host throttling monitoring</span></span>  
  
  -   <span data-ttu-id="b67fb-127">Reglas específicas de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="b67fb-127">MessageBox-specific rules</span></span>  
  
  -   <span data-ttu-id="b67fb-128">Reglas para componentes adicionales de terceros (por ejemplo, la del adaptador de MQSeries)</span><span class="sxs-lookup"><span data-stu-id="b67fb-128">Rules for additional third party components, for example, MQSeries adapter</span></span>  
  
  <span data-ttu-id="b67fb-129">**Todos los supervisar componentes relacionados con el servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="b67fb-129">**Monitor all the BizTalk Server related components**</span></span>  
  
  <span data-ttu-id="b67fb-130">Los componentes de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluyen entorno que se debe supervisar para asegurarse de que se están ejecutando, pero no está limitado necesariamente a:</span><span class="sxs-lookup"><span data-stu-id="b67fb-130">The components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that you should monitor to ensure that they are running include, but are not necessarily limited to:</span></span>  
  
- <span data-ttu-id="b67fb-131">Instancias de host de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b67fb-131">BizTalk Host instances</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="b67fb-132"> Trabajos del agente instalados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b67fb-132"> Agent jobs installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="b67fb-133">Los servicios personalizados desarrollados para la solución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b67fb-133">Any custom services developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="b67fb-134">Estado de las bases de datos personalizados desarrollados para la solución de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b67fb-134">Status of any custom databases developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="b67fb-135">Todas las entradas de registro de eventos personalizado relevantes para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno</span><span class="sxs-lookup"><span data-stu-id="b67fb-135">Any custom event log entries relevant to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67fb-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b67fb-136">See Also</span></span>  
 [<span data-ttu-id="b67fb-137">Supervisión de BizTalk Server con System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="b67fb-137">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)
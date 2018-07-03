---
title: Supervisión de BizTalk Server con System Center Operations Manager 2007 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cee8275-bbd0-435f-ac54-07f582190538
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 380af93ccba2671e3ffa3e6377c049eaf23dcd67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995821"
---
# <a name="monitoring-biztalk-server-with-system-center-operations-manager-2007"></a><span data-ttu-id="59ff9-102">Supervisión de BizTalk Server con System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="59ff9-102">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>
<span data-ttu-id="59ff9-103">Supervisar las aplicaciones de BizTalk y la infraestructura con Microsoft System Center Operations Manager (Operations Manager) es el método preferido de supervisión.</span><span class="sxs-lookup"><span data-stu-id="59ff9-103">Monitoring your BizTalk applications and infrastructure with Microsoft System Center Operations Manager (Operations Manager) is the preferred monitoring approach.</span></span> <span data-ttu-id="59ff9-104">Los módulos de administración de Microsoft BizTalk Server para Operations Manager proporcionan supervisión proactiva y reactiva de equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59ff9-104">The Microsoft BizTalk Server management packs for Operations Manager provide proactive and reactive monitoring of computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="59ff9-105">Estos módulos de administración proporcionan numerosas reglas integradas y personalizables para permitir la supervisión integral y automatizada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59ff9-105">These management packs provide dozens of built-in, customizable rules to allow for comprehensive and automated monitoring of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="59ff9-106">El siguiente módulo de administración de BizTalk Server está disponible para su uso con Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="59ff9-106">The following BizTalk Server management pack is available for use with Operations Manager:</span></span>  
  
- <span data-ttu-id="59ff9-107">[El módulo de administración de supervisión de BizTalk Server 2010](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span><span class="sxs-lookup"><span data-stu-id="59ff9-107">[BizTalk Server 2010 Monitoring Management Pack](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span></span>  
  
  <span data-ttu-id="59ff9-108">Esta sección de la Guía de operaciones incluye información general, mejores prácticas, las listas de comprobación y procedimientos que puede usar para ayudar a implementar una estrategia de supervisión basada en Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="59ff9-108">This section of the operations guide includes background information, best practices, checklists, and procedures that you can use to assist in implementing a monitoring strategy based on Operations Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59ff9-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="59ff9-109">In This Section</span></span>  
  
-   [<span data-ttu-id="59ff9-110">Procedimientos recomendados para la supervisión con Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="59ff9-110">Best Practices for Monitoring with Operations Manager 2007</span></span>](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)  
  
-   [<span data-ttu-id="59ff9-111">Limitación de supervisión mediante reglas de umbral de rendimiento</span><span class="sxs-lookup"><span data-stu-id="59ff9-111">Monitoring Throttling Using Performance Threshold Rules</span></span>](../technical-guides/monitoring-throttling-using-performance-threshold-rules.md)  
  
-   [<span data-ttu-id="59ff9-112">Supervisión de servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="59ff9-112">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)  
  
-   [<span data-ttu-id="59ff9-113">Supervisión de aplicaciones e instancias de host</span><span class="sxs-lookup"><span data-stu-id="59ff9-113">Monitoring Applications and Host Instances</span></span>](../technical-guides/monitoring-applications-and-host-instances.md)
---
title: "Optimizar el uso de recursos mediante la limitación de Host | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-resource-usage-through-host-throttling"></a><span data-ttu-id="377da-102">Optimizar el uso de recursos mediante la limitación de host</span><span class="sxs-lookup"><span data-stu-id="377da-102">Optimizing Resource Usage Through Host Throttling</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="377da-103">hace uso de diferentes tecnologías de Microsoft, cada uno de los cuales puede consumir una parte importante de la memoria, disco y recursos de CPU disponibles en el servidor BizTalk server y SQL server que contiene las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="377da-103"> makes use of several different Microsoft technologies, each of which can consume a significant portion of the memory, disk, and CPU resources available on the BizTalk server and the SQL server that contains the BizTalk Server databases.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="377da-104">emplea un mecanismo de limitación para ayudar a administrar el uso de recursos disponibles para minimizar la contención de uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="377da-104"> employs a throttling mechanism to help manage the use of available resources to minimize resource use contention.</span></span> <span data-ttu-id="377da-105">En este tema se describe el diseño de este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="377da-105">This topic discusses the design of this mechanism.</span></span> <span data-ttu-id="377da-106">Para obtener información sobre cómo ajustar los valores de limitación, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span><span class="sxs-lookup"><span data-stu-id="377da-106">For information on how to adjust the throttling values, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="377da-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="377da-107">In This Section</span></span>  
  
-   [<span data-ttu-id="377da-108">¿Qué es la limitación de Host?</span><span class="sxs-lookup"><span data-stu-id="377da-108">What Is Host Throttling?</span></span>](../core/what-is-host-throttling.md)  
  
-   [<span data-ttu-id="377da-109">Cómo BizTalk Server incorpora la limitación de Host</span><span class="sxs-lookup"><span data-stu-id="377da-109">How BizTalk Server Implements Host Throttling</span></span>](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [<span data-ttu-id="377da-110">Contadores de rendimiento de limitación de host</span><span class="sxs-lookup"><span data-stu-id="377da-110">Host Throttling Performance Counters</span></span>](../core/host-throttling-performance-counters.md)  
  
-   [<span data-ttu-id="377da-111">Recomendaciones de diseño de limitación</span><span class="sxs-lookup"><span data-stu-id="377da-111">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)
---
title: Consideraciones de rendimiento para la publicación de eventos BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- publishing, BAM
- BAM, publishing
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 5a99e61a-a3d9-47fd-a933-2297f79817a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebab873c94c0ae17abf9938883662ca8777cef36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264428"
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="e7d04-102">Consideraciones de rendimiento para la publicación de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="e7d04-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="e7d04-103">BAM admite dos formas de publicación de eventos empresariales:</span><span class="sxs-lookup"><span data-stu-id="e7d04-103">BAM supports two forms of business event publishing:</span></span>  
  
-   <span data-ttu-id="e7d04-104">Sincrónica</span><span class="sxs-lookup"><span data-stu-id="e7d04-104">Synchronous</span></span>  
  
-   <span data-ttu-id="e7d04-105">Asincrónica</span><span class="sxs-lookup"><span data-stu-id="e7d04-105">Asynchronous</span></span>  
  
 <span data-ttu-id="e7d04-106">En el siguiente diagrama se ilustran los dos modelos.</span><span class="sxs-lookup"><span data-stu-id="e7d04-106">The following diagram illustrates the two models.</span></span>  
  
 ![](../core/media/bam-topologies.gif "bam_topologies")  
<span data-ttu-id="e7d04-107">Topologías de BAM</span><span class="sxs-lookup"><span data-stu-id="e7d04-107">BAM Topologies</span></span>  
  
 <span data-ttu-id="e7d04-108">El enfoque sincrónico es mucho más sencillo para la administración y utilización del código, mientras que el enfoque asíncrono le permite un rendimiento mejor.</span><span class="sxs-lookup"><span data-stu-id="e7d04-108">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7d04-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e7d04-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e7d04-110">Seguimiento de eventos empresariales sincrónico</span><span class="sxs-lookup"><span data-stu-id="e7d04-110">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="e7d04-111">Seguimiento de eventos empresariales asíncronos</span><span class="sxs-lookup"><span data-stu-id="e7d04-111">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)
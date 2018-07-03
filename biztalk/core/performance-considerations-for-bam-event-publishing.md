---
title: Consideraciones de rendimiento para la publicación de eventos BAM | Microsoft Docs
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
ms.openlocfilehash: c031f9a3325eda9cbcf865eaf72d1d9e100616c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997541"
---
# <a name="performance-considerations-for-bam-event-publishing"></a><span data-ttu-id="4390f-102">Consideraciones de rendimiento para la publicación de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="4390f-102">Performance Considerations for BAM Event Publishing</span></span>
<span data-ttu-id="4390f-103">BAM admite dos formas de publicación de eventos empresariales:</span><span class="sxs-lookup"><span data-stu-id="4390f-103">BAM supports two forms of business event publishing:</span></span>  
  
- <span data-ttu-id="4390f-104">Sincrónica</span><span class="sxs-lookup"><span data-stu-id="4390f-104">Synchronous</span></span>  
  
- <span data-ttu-id="4390f-105">Asincrónica</span><span class="sxs-lookup"><span data-stu-id="4390f-105">Asynchronous</span></span>  
  
  <span data-ttu-id="4390f-106">En el siguiente diagrama se ilustran los dos modelos.</span><span class="sxs-lookup"><span data-stu-id="4390f-106">The following diagram illustrates the two models.</span></span>  
  
  <span data-ttu-id="4390f-107">![](../core/media/bam-topologies.gif "bam_topologies")</span><span class="sxs-lookup"><span data-stu-id="4390f-107">![](../core/media/bam-topologies.gif "bam_topologies")</span></span>  
  <span data-ttu-id="4390f-108">Topologías de BAM</span><span class="sxs-lookup"><span data-stu-id="4390f-108">BAM Topologies</span></span>  
  
  <span data-ttu-id="4390f-109">El enfoque sincrónico es mucho más sencillo para la administración y utilización del código, mientras que el enfoque asíncrono le permite un rendimiento mejor.</span><span class="sxs-lookup"><span data-stu-id="4390f-109">The synchronous approach is much simpler for management and using from code, while the asynchronous approach allows for better performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4390f-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4390f-110">In This Section</span></span>  
  
-   [<span data-ttu-id="4390f-111">Seguimiento sincrónico de eventos empresariales</span><span class="sxs-lookup"><span data-stu-id="4390f-111">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)  
  
-   [<span data-ttu-id="4390f-112">Seguimiento asincrónico de eventos empresariales</span><span class="sxs-lookup"><span data-stu-id="4390f-112">Asynchronous Business Event Tracking</span></span>](../core/asynchronous-business-event-tracking.md)
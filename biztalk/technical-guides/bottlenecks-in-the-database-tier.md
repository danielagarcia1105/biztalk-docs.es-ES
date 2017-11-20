---
title: Cuellos de botella en el nivel de base de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55b37393-32dc-4717-bf62-48588c23dd78
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b741f1ffcd68f7a5c739731e5aa9a1db55be34c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bottlenecks-in-the-database-tier"></a><span data-ttu-id="bb8c8-102">Cuellos de botella en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="bb8c8-102">Bottlenecks in the Database Tier</span></span>
<span data-ttu-id="bb8c8-103">Esta sección explica cómo identificar cuellos de botella en la base de datos BizTalk MessageBox, base de datos de seguimiento y base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="bb8c8-103">This section explains how to identify bottlenecks in the BizTalk MessageBox database, Tracking database, and BAM Primary Import database.</span></span> <span data-ttu-id="bb8c8-104">También se explica cómo evitar la contención de disco.</span><span class="sxs-lookup"><span data-stu-id="bb8c8-104">It also explains how to avoid disk contention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb8c8-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bb8c8-105">In This Section</span></span>  
  
-   [<span data-ttu-id="bb8c8-106">Cómo identificar cuellos de botella en el cuadro de mensajes Database1</span><span class="sxs-lookup"><span data-stu-id="bb8c8-106">How to Identify Bottlenecks in the MessageBox Database1</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)  
  
-   [<span data-ttu-id="bb8c8-107">Cómo identificar cuellos de botella en la base de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bb8c8-107">How to Identify Bottlenecks in the Tracking Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)  
  
-   [<span data-ttu-id="bb8c8-108">Cómo identificar cuellos de botella en la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="bb8c8-108">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-bam-primary-import-database.md)  
  
-   [<span data-ttu-id="bb8c8-109">Cómo evitar Contention2 de disco</span><span class="sxs-lookup"><span data-stu-id="bb8c8-109">How to Avoid Disk Contention2</span></span>](../technical-guides/how-to-avoid-disk-contention2.md)
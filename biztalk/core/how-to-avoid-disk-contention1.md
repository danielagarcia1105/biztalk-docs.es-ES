---
title: "Cómo evitar disco Contention1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a><span data-ttu-id="59e10-102">Cómo evitar la contención del disco</span><span class="sxs-lookup"><span data-stu-id="59e10-102">How to Avoid Disk Contention</span></span>
<span data-ttu-id="59e10-103">BizTalk Server está diseñado como un sistema permanente donde, en el caso de escenarios de alto rendimiento, el cuadro de mensajes puede sufrir contenciones severas.</span><span class="sxs-lookup"><span data-stu-id="59e10-103">BizTalk Server is designed as a persistent system whereby, for high throughput scenarios, the MessageBox can experience severe contention.</span></span> <span data-ttu-id="59e10-104">Esta contención puede verse agravada por discos lentos.</span><span class="sxs-lookup"><span data-stu-id="59e10-104">This contention can be aggravated by slow disks.</span></span> <span data-ttu-id="59e10-105">Si los discos son lentos (bajo % de tiempo de inactividad del disco), pueden provocar que SQL mantenga los bloqueos durante más tiempo (tiempos de espera de bloqueos altos) y, por tanto, que crezcan las tablas (cola de impresión y de aplicación) del cuadro de mensajes. Esto ocasiona que la base de datos se inunde y se vea limitada, con lo que el rendimiento global sostenible será inferior.</span><span class="sxs-lookup"><span data-stu-id="59e10-105">If the disks are slow (low % Disk Idle Time), this can cause SQL to hold onto locks longer (high Lock Wait Time and high Lock Timeouts) which can cause the MessageBox tables (Spool and Application Queues) to grow, causing database bloat and throttling ultimately resulting in lower overall sustainable throughput.</span></span>  
  
 <span data-ttu-id="59e10-106">Para evitar la contención del disco, se recomienda que realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59e10-106">To avoid disk contention, it is recommended that you do the following:</span></span>  
  
-   <span data-ttu-id="59e10-107">Use discos de alta velocidad (varios ejes).</span><span class="sxs-lookup"><span data-stu-id="59e10-107">Use of high speed (multiple spindles) disks.</span></span>  
  
-   <span data-ttu-id="59e10-108">Cuando sea posible, implemente las bases de datos en una SAN de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="59e10-108">If possible, deploy the databases on a high speed SAN.</span></span> <span data-ttu-id="59e10-109">Si hay varias bases de datos que comparten los mismos discos, se recomienda configurarlos en discos dedicados independientes.</span><span class="sxs-lookup"><span data-stu-id="59e10-109">If multiple databases are sharing the same disks it is recommended to configure them on separate dedicated disks.</span></span> <span data-ttu-id="59e10-110">Además, es aconsejable separar los archivos MDF y LDF para la base de datos del cuadro de mensajes en diferentes discos.</span><span class="sxs-lookup"><span data-stu-id="59e10-110">In addition it is recommended to separate the MDF and LDF files for the MessageBox database onto separate disks.</span></span>  
  
-   <span data-ttu-id="59e10-111">En caso de que SQL necesite de la CPU, considere la posibilidad de separar la base de datos del cuadro de mensajes en un servidor dedicado que sea independiente de las bases de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="59e10-111">If SQL is starved for CPU, consider separating the MessageBox database onto a dedicated server that is separate from the Tracking databases.</span></span>  
  
-   <span data-ttu-id="59e10-112">Después de configurar un servidor dedicado para la base de datos de cuadro de mensajes, considere la posibilidad de escalar verticalmente mediante la actualización de la CPU y la adición de más CPU.</span><span class="sxs-lookup"><span data-stu-id="59e10-112">After setting up a dedicated server for the MessageBox database, consider scaling up by upgrading the CPU’s and/or adding more CPU’s.</span></span> <span data-ttu-id="59e10-113">Supervise la unidad local en el servidor de SQL Server como los registros de MSDTC se guardan en la unidad local (C:\WINDOWS\system32\Msdtc).</span><span class="sxs-lookup"><span data-stu-id="59e10-113">Monitor the local drive on the SQL-Server as the MSDTC logs are saved on the local drive (C:\WINDOWS\system32\Msdtc).</span></span>  
  
-   <span data-ttu-id="59e10-114">Si hay contención en la unidad local debido al archivo de paginación o al registro MSDTC, intente moverlos a una unidad independiente.</span><span class="sxs-lookup"><span data-stu-id="59e10-114">If there is contention on the local drive due to the PageFile or MSDTC log, try moving the PageFile and/or the MSDTC log to a separate drive.</span></span>
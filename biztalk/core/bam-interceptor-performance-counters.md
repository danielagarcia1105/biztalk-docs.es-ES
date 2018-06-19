---
title: Contadores de rendimiento del Interceptor de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230500"
---
# <a name="bam-interceptor-performance-counters"></a><span data-ttu-id="27eb4-102">Contadores de rendimiento del interceptor de BAM</span><span class="sxs-lookup"><span data-stu-id="27eb4-102">BAM Interceptor Performance Counters</span></span>
<span data-ttu-id="27eb4-103">Los contadores de rendimiento permiten controlar aspectos específicos del trabajo llevado a cabo por los interceptores de BAM.</span><span class="sxs-lookup"><span data-stu-id="27eb4-103">Performance counters allow you to monitor specific aspects of work performed by the BAM interceptors.</span></span> <span data-ttu-id="27eb4-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="27eb4-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="27eb4-105">La tabla siguiente enumera los contadores de rendimiento disponibles para los interceptores de BAM.</span><span class="sxs-lookup"><span data-stu-id="27eb4-105">The following table lists the performance counters available for the BAM interceptors.</span></span> <span data-ttu-id="27eb4-106">La categoría de los contadores de rendimiento es “Interceptor de BAM”.</span><span class="sxs-lookup"><span data-stu-id="27eb4-106">The performance counters category is “BAM Interceptor.”</span></span>  
  
|<span data-ttu-id="27eb4-107">Contador</span><span class="sxs-lookup"><span data-stu-id="27eb4-107">Counter</span></span>|<span data-ttu-id="27eb4-108">Description</span><span class="sxs-lookup"><span data-stu-id="27eb4-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27eb4-109">Promedio de Promedio de eventos de BAM con error por vaciado</span><span class="sxs-lookup"><span data-stu-id="27eb4-109">Avg. Failed BAM Events/Flush Avg</span></span>|<span data-ttu-id="27eb4-110">Promedio de eventos BAM con errores que se han producido durante un vaciado de datos en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="27eb4-110">The average number of failed BAM events that occurred during a flush of data to the Primary Import database.</span></span>|  
|<span data-ttu-id="27eb4-111">Promedio de eventos BAM correctos por vaciado</span><span class="sxs-lookup"><span data-stu-id="27eb4-111">Successful BAM Events/Flush</span></span>|<span data-ttu-id="27eb4-112">Promedio de eventos BAM correctos que se han producido durante un vaciado de datos en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="27eb4-112">The average number of successful BAM events that occurred during a data flush to the Primary Import database.</span></span> <span data-ttu-id="27eb4-113">Es posible que los eventos no se almacenen en la base de datos si se revierte la transacción.</span><span class="sxs-lookup"><span data-stu-id="27eb4-113">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
|<span data-ttu-id="27eb4-114">Promedio de Segundos de extracción por evento de BAM</span><span class="sxs-lookup"><span data-stu-id="27eb4-114">Avg. Extraction sec/BAM Event</span></span>|<span data-ttu-id="27eb4-115">Promedio de tiempo empleado en la extracción de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="27eb4-115">The average amount of time spent extracting BAM events.</span></span>|  
|<span data-ttu-id="27eb4-116">Promedio de Segundos de vaciado por evento de BAM</span><span class="sxs-lookup"><span data-stu-id="27eb4-116">Avg. Flush sec/BAM Event</span></span>|<span data-ttu-id="27eb4-117">Promedio de tiempo empleado en el vaciado de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="27eb4-117">The average amount of time spent flushing BAM events.</span></span>|  
|<span data-ttu-id="27eb4-118">Total de eventos BAM con errores durante el vaciado</span><span class="sxs-lookup"><span data-stu-id="27eb4-118">Total Failed BAM Events During Flush</span></span>|<span data-ttu-id="27eb4-119">Número total de eventos BAM con errores que se han producido durante el vaciado de los datos.</span><span class="sxs-lookup"><span data-stu-id="27eb4-119">The total number of failed BAM events that occurred during the data flush</span></span>|  
|<span data-ttu-id="27eb4-120">Total de eventos BAM correctos durante el vaciado</span><span class="sxs-lookup"><span data-stu-id="27eb4-120">Total Successful BAM Events During Flush</span></span>|<span data-ttu-id="27eb4-121">Número total de eventos BAM correctos que se han vaciado en la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="27eb4-121">The total number of successful BAM events flushed to the Primary Import database.</span></span> <span data-ttu-id="27eb4-122">Es posible que los eventos no se almacenen en la base de datos si se revierte la transacción.</span><span class="sxs-lookup"><span data-stu-id="27eb4-122">The events may not be persisted to the database if the transaction is rolled back.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27eb4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="27eb4-123">See Also</span></span>  
 [<span data-ttu-id="27eb4-124">Contadores de rendimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="27eb4-124">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)
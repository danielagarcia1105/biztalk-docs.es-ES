---
title: "Dimensión de tiempo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418afdc5b7507aba9a564628341c10495b2a740a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="time-dimension"></a><span data-ttu-id="1aac1-102">Dimensión de tiempo</span><span class="sxs-lookup"><span data-stu-id="1aac1-102">Time Dimension</span></span>
<span data-ttu-id="1aac1-103">La dimensión de tiempo permite crear agregaciones con respecto al tiempo.</span><span class="sxs-lookup"><span data-stu-id="1aac1-103">The time dimension allows aggregations to be created with respect to time.</span></span> <span data-ttu-id="1aac1-104">Por ejemplo, puede usar una dimensión de tiempo para crear la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="1aac1-104">For example a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="1aac1-105">Year</span><span class="sxs-lookup"><span data-stu-id="1aac1-105">Year</span></span>|<span data-ttu-id="1aac1-106">Month</span><span class="sxs-lookup"><span data-stu-id="1aac1-106">Month</span></span>|<span data-ttu-id="1aac1-107">Count</span><span class="sxs-lookup"><span data-stu-id="1aac1-107">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="1aac1-108">2003</span><span class="sxs-lookup"><span data-stu-id="1aac1-108">2003</span></span>|<span data-ttu-id="1aac1-109">January</span><span class="sxs-lookup"><span data-stu-id="1aac1-109">January</span></span>|<span data-ttu-id="1aac1-110">120</span><span class="sxs-lookup"><span data-stu-id="1aac1-110">120</span></span>|  
||<span data-ttu-id="1aac1-111">February</span><span class="sxs-lookup"><span data-stu-id="1aac1-111">February</span></span>|<span data-ttu-id="1aac1-112">230</span><span class="sxs-lookup"><span data-stu-id="1aac1-112">230</span></span>|  
||<span data-ttu-id="1aac1-113">March</span><span class="sxs-lookup"><span data-stu-id="1aac1-113">March</span></span>|<span data-ttu-id="1aac1-114">350</span><span class="sxs-lookup"><span data-stu-id="1aac1-114">350</span></span>|  
||<span data-ttu-id="1aac1-115">April</span><span class="sxs-lookup"><span data-stu-id="1aac1-115">April</span></span>|<span data-ttu-id="1aac1-116">280</span><span class="sxs-lookup"><span data-stu-id="1aac1-116">280</span></span>|  
  
 <span data-ttu-id="1aac1-117">La dimensión de tiempo puede combinarse con cualquier otra dimensión.</span><span class="sxs-lookup"><span data-stu-id="1aac1-117">The time dimension can be combined with any other dimension.</span></span> <span data-ttu-id="1aac1-118">Por ejemplo, puede usar la dimensión de tiempo en filas y la dimensión de datos en columnas para crear la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="1aac1-118">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|||<span data-ttu-id="1aac1-119">Raquetas de tenis</span><span class="sxs-lookup"><span data-stu-id="1aac1-119">Tennis racquets</span></span>|<span data-ttu-id="1aac1-120">Balones de fútbol</span><span class="sxs-lookup"><span data-stu-id="1aac1-120">Soccer balls</span></span>|  
|------|------|---------------------|------------------|  
||<span data-ttu-id="1aac1-121">January</span><span class="sxs-lookup"><span data-stu-id="1aac1-121">January</span></span>|<span data-ttu-id="1aac1-122">50</span><span class="sxs-lookup"><span data-stu-id="1aac1-122">50</span></span>|<span data-ttu-id="1aac1-123">70</span><span class="sxs-lookup"><span data-stu-id="1aac1-123">70</span></span>|  
||<span data-ttu-id="1aac1-124">February</span><span class="sxs-lookup"><span data-stu-id="1aac1-124">February</span></span>|<span data-ttu-id="1aac1-125">120</span><span class="sxs-lookup"><span data-stu-id="1aac1-125">120</span></span>|<span data-ttu-id="1aac1-126">110</span><span class="sxs-lookup"><span data-stu-id="1aac1-126">110</span></span>|  
||<span data-ttu-id="1aac1-127">March</span><span class="sxs-lookup"><span data-stu-id="1aac1-127">March</span></span>|<span data-ttu-id="1aac1-128">300</span><span class="sxs-lookup"><span data-stu-id="1aac1-128">300</span></span>|<span data-ttu-id="1aac1-129">50</span><span class="sxs-lookup"><span data-stu-id="1aac1-129">50</span></span>|  
||<span data-ttu-id="1aac1-130">April</span><span class="sxs-lookup"><span data-stu-id="1aac1-130">April</span></span>|<span data-ttu-id="1aac1-131">220</span><span class="sxs-lookup"><span data-stu-id="1aac1-131">220</span></span>|<span data-ttu-id="1aac1-132">60</span><span class="sxs-lookup"><span data-stu-id="1aac1-132">60</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1aac1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aac1-133">See Also</span></span>  
 <span data-ttu-id="1aac1-134">[Dimensión de rango numérico](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="1aac1-134">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 <span data-ttu-id="1aac1-135">[Dimensión de progreso](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="1aac1-135">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="1aac1-136">[Dimensión de datos](../core/data-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="1aac1-136">[Data Dimension](../core/data-dimension.md) </span></span>  
 [<span data-ttu-id="1aac1-137">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="1aac1-137">Defining Dimensions</span></span>](../core/defining-dimensions.md)
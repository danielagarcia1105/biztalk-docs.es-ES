---
title: "Dimensión de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-dimension"></a><span data-ttu-id="6bd83-102">Dimensión de datos</span><span class="sxs-lookup"><span data-stu-id="6bd83-102">Data Dimension</span></span>
<span data-ttu-id="6bd83-103">La definición de una dimensión de datos permite usar el valor de ciertos elementos de texto de la actividad de BAM en filas o columnas.</span><span class="sxs-lookup"><span data-stu-id="6bd83-103">Defining a data dimension allows the value of some text items in the BAM activity to be used on rows or columns.</span></span> <span data-ttu-id="6bd83-104">Por ejemplo, puede usarse una dimensión de datos llamada Productos para crear la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bd83-104">For example a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="6bd83-105">Product</span><span class="sxs-lookup"><span data-stu-id="6bd83-105">Product</span></span>|<span data-ttu-id="6bd83-106">Count</span><span class="sxs-lookup"><span data-stu-id="6bd83-106">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="6bd83-107">Raquetas de tenis</span><span class="sxs-lookup"><span data-stu-id="6bd83-107">Tennis racquets</span></span>|<span data-ttu-id="6bd83-108">100</span><span class="sxs-lookup"><span data-stu-id="6bd83-108">100</span></span>|  
|<span data-ttu-id="6bd83-109">Balones de fútbol</span><span class="sxs-lookup"><span data-stu-id="6bd83-109">Soccer balls</span></span>|<span data-ttu-id="6bd83-110">200</span><span class="sxs-lookup"><span data-stu-id="6bd83-110">200</span></span>|  
  
 <span data-ttu-id="6bd83-111">Asimismo, es posible definir más de una dimensión de datos en el Asistente para vistas de BAM.</span><span class="sxs-lookup"><span data-stu-id="6bd83-111">Also, more than one data dimension can be defined in the BAM view wizard.</span></span> <span data-ttu-id="6bd83-112">Por ejemplo, definir una dimensión de datos llamada **ubicación** con niveles para **estado** y **City** puede usarse para crear la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bd83-112">For example, defining a data dimension named **Location** with levels for **State** and **City** can be used to create the following table:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="6bd83-113">California</span><span class="sxs-lookup"><span data-stu-id="6bd83-113">California</span></span>||<span data-ttu-id="6bd83-114">Washington</span><span class="sxs-lookup"><span data-stu-id="6bd83-114">Washington</span></span>|  
||<span data-ttu-id="6bd83-115">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="6bd83-115">Los Angeles</span></span>|<span data-ttu-id="6bd83-116">San Francisco</span><span class="sxs-lookup"><span data-stu-id="6bd83-116">San Francisco</span></span>|<span data-ttu-id="6bd83-117">Seattle</span><span class="sxs-lookup"><span data-stu-id="6bd83-117">Seattle</span></span>|  
|<span data-ttu-id="6bd83-118">Raquetas de tenis</span><span class="sxs-lookup"><span data-stu-id="6bd83-118">Tennis racquets</span></span>|<span data-ttu-id="6bd83-119">50</span><span class="sxs-lookup"><span data-stu-id="6bd83-119">50</span></span>|<span data-ttu-id="6bd83-120">20</span><span class="sxs-lookup"><span data-stu-id="6bd83-120">20</span></span>|<span data-ttu-id="6bd83-121">30</span><span class="sxs-lookup"><span data-stu-id="6bd83-121">30</span></span>|  
|<span data-ttu-id="6bd83-122">Balones de fútbol</span><span class="sxs-lookup"><span data-stu-id="6bd83-122">Soccer balls</span></span>|<span data-ttu-id="6bd83-123">130</span><span class="sxs-lookup"><span data-stu-id="6bd83-123">130</span></span>|<span data-ttu-id="6bd83-124">50</span><span class="sxs-lookup"><span data-stu-id="6bd83-124">50</span></span>|<span data-ttu-id="6bd83-125">20</span><span class="sxs-lookup"><span data-stu-id="6bd83-125">20</span></span>|  
  
 <span data-ttu-id="6bd83-126">En esta tabla se usó la dimensión Producto para las filas y la dimensión Ubicación para las columnas.</span><span class="sxs-lookup"><span data-stu-id="6bd83-126">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd83-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bd83-127">See Also</span></span>  
 <span data-ttu-id="6bd83-128">[Dimensión de tiempo](../core/time-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6bd83-128">[Time Dimension](../core/time-dimension.md) </span></span>  
 <span data-ttu-id="6bd83-129">[Dimensión de progreso](../core/progress-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6bd83-129">[Progress Dimension](../core/progress-dimension.md) </span></span>  
 <span data-ttu-id="6bd83-130">[Dimensión de rango numérico](../core/numeric-range-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6bd83-130">[Numeric Range Dimension](../core/numeric-range-dimension.md) </span></span>  
 [<span data-ttu-id="6bd83-131">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="6bd83-131">Defining Dimensions</span></span>](../core/defining-dimensions.md)
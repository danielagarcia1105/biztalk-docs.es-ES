---
title: Functoids científicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0311b7dc-1955-45af-b858-681faccc939b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7a181f200948335aab0ffa2a06d43d38408afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977420"
---
# <a name="scientific-functoids"></a><span data-ttu-id="079bc-102">Functoids científicos</span><span class="sxs-lookup"><span data-stu-id="079bc-102">Scientific Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="079bc-103">Información general</span><span class="sxs-lookup"><span data-stu-id="079bc-103">Overview</span></span>
<span data-ttu-id="079bc-104">**Científicos** functoids se utilizan para realizar una serie de cálculos trigonométricos, logarítmicos y exponenciales estándar.</span><span class="sxs-lookup"><span data-stu-id="079bc-104">**Scientific** functoids are used to perform a variety of standard trigonometric, logarithmic, and exponential calculations.</span></span>  

 <span data-ttu-id="079bc-105">Con la excepción de la **logaritmo en una base especificada** y **X ^ Y** functoids, que toman dos parámetros de entrada, el **científica** todos los functoids toman un único parámetro.</span><span class="sxs-lookup"><span data-stu-id="079bc-105">With the exception of the **Base-Specified Logarithm** and **X^Y** functoids, which each take two input parameters, the **Scientific** functoids all take a single parameter.</span></span>  

 <span data-ttu-id="079bc-106">Las cuatro operaciones trigonométricas **científica** functoids (**arco tangente**, **coseno**, **seno**, y **tangente**) todos utilizan radianes en vez de grados como unidades para sus parámetros de salida o entrada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="079bc-106">The four trigonometric **Scientific** functoids (**Arc Tangent**, **Cosine**, **Sine**, and **Tangent**) all use radians rather than degrees as the units for their relevant input or output parameters.</span></span> <span data-ttu-id="079bc-107">Una en radianes es una unidad de medida de ángulos, de forma que hay 2π radianes en un círculo.</span><span class="sxs-lookup"><span data-stu-id="079bc-107">A radian is a unit of measure of angles, such that there are 2π radians in a circle.</span></span> <span data-ttu-id="079bc-108">Así pues:</span><span class="sxs-lookup"><span data-stu-id="079bc-108">It follows that:</span></span>  

- <span data-ttu-id="079bc-109">2π radianes es igual a 360 grados</span><span class="sxs-lookup"><span data-stu-id="079bc-109">2π radians equals 360 degrees</span></span>  

- <span data-ttu-id="079bc-110">1 radianes = π/180 grados</span><span class="sxs-lookup"><span data-stu-id="079bc-110">1 radian = 180/π degrees</span></span>  

- <span data-ttu-id="079bc-111">1 grado = 180/π radianes</span><span class="sxs-lookup"><span data-stu-id="079bc-111">1 degree = π/180 radians</span></span>  

  <span data-ttu-id="079bc-112">Si los mensajes de instancia de entrada o salida utilizan grados como unidad de medida de ángulos, deberá usar un **matemáticos** functoid junto con un trigonométrico **científica** functoid para lograr el resultado correcto.</span><span class="sxs-lookup"><span data-stu-id="079bc-112">If your input or output instance messages use degrees as their unit of measure for angles, you will need to use a **Mathematical** functoid in conjunction with a trigonometric **Scientific** functoid to achieve the correct result.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="079bc-113">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="079bc-113">Available functoids</span></span>  
 <span data-ttu-id="079bc-114">El **científica** functoids son:</span><span class="sxs-lookup"><span data-stu-id="079bc-114">The **Scientific** functoids are:</span></span> 

* <span data-ttu-id="079bc-115">10^n</span><span class="sxs-lookup"><span data-stu-id="079bc-115">10^n</span></span>
* <span data-ttu-id="079bc-116">Arco tangente</span><span class="sxs-lookup"><span data-stu-id="079bc-116">Arc Tangent</span></span>
* <span data-ttu-id="079bc-117">Logaritmo en una base de datos especificada</span><span class="sxs-lookup"><span data-stu-id="079bc-117">Base-Specified Logarithm</span></span>
* <span data-ttu-id="079bc-118">Logaritmo común</span><span class="sxs-lookup"><span data-stu-id="079bc-118">Common Logarithm</span></span>
* <span data-ttu-id="079bc-119">Coseno</span><span class="sxs-lookup"><span data-stu-id="079bc-119">Cosine</span></span>
* <span data-ttu-id="079bc-120">Función exponencial natural</span><span class="sxs-lookup"><span data-stu-id="079bc-120">Natural Exponential Function</span></span>
* <span data-ttu-id="079bc-121">Logaritmo natural</span><span class="sxs-lookup"><span data-stu-id="079bc-121">Natural Logarithm</span></span>
* <span data-ttu-id="079bc-122">Seno</span><span class="sxs-lookup"><span data-stu-id="079bc-122">Sine</span></span>
* <span data-ttu-id="079bc-123">Tangente</span><span class="sxs-lookup"><span data-stu-id="079bc-123">Tangent</span></span>
* <span data-ttu-id="079bc-124">X^Y</span><span class="sxs-lookup"><span data-stu-id="079bc-124">X^Y</span></span>

## <a name="see-also"></a><span data-ttu-id="079bc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="079bc-125">See Also</span></span>  
- [<span data-ttu-id="079bc-126">Cómo agregar Functoids básicos a una asignación</span><span class="sxs-lookup"><span data-stu-id="079bc-126">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="079bc-127">**Referencia a Functoids científicos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="079bc-127">**Scientific Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

---
title: "Ejemplo de cálculo de deshidratación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ff231b630a5848494c45cd8d4d05f89e764eb41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-dehydration-calculation"></a><span data-ttu-id="db750-102">Ejemplo de cálculo de deshidratación</span><span class="sxs-lookup"><span data-stu-id="db750-102">Sample Dehydration Calculation</span></span>
<span data-ttu-id="db750-103">A continuación, se muestra un ejemplo del cálculo, utilizando bytes privados, para determinar si BizTalk se deshidratará o no.</span><span class="sxs-lookup"><span data-stu-id="db750-103">Here is an example of a sample calculation, using private bytes, to determine if BizTalk will dehydrate or not.</span></span> <span data-ttu-id="db750-104">Usa los valores configurados predeterminados y algunos ejemplos de valores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="db750-104">It uses the default configured values, and some example run-time values.</span></span>  
  
 <span data-ttu-id="db750-105">Presuponga los valores siguientes para las propiedades de deshidratación:</span><span class="sxs-lookup"><span data-stu-id="db750-105">Assume the following values for the dehydration properties:</span></span>  
  
-   <span data-ttu-id="db750-106">**TimeBlocked** = 60 (ejemplo de tiempo bloqueado en segundos)</span><span class="sxs-lookup"><span data-stu-id="db750-106">**TimeBlocked** = 60 (example time blocked in seconds)</span></span>  
  
-   <span data-ttu-id="db750-107">**WaitingHistory** = 90 (historial de ejemplo espera en segundos)</span><span class="sxs-lookup"><span data-stu-id="db750-107">**WaitingHistory** = 90 (example waiting history in seconds)</span></span>  
  
-   <span data-ttu-id="db750-108">**ActualPrivateBytes** = 250 (ejemplo del valor de bytes privados)</span><span class="sxs-lookup"><span data-stu-id="db750-108">**ActualPrivateBytes** = 250 (example value for private bytes)</span></span>  
  
-   <span data-ttu-id="db750-109">**OptimalUsage** = 50 (valor de configuración predeterminado)</span><span class="sxs-lookup"><span data-stu-id="db750-109">**OptimalUsage** = 50 (default configuration value)</span></span>  
  
-   <span data-ttu-id="db750-110">**MaximalUsage** = 350 (valor de configuración predeterminado)</span><span class="sxs-lookup"><span data-stu-id="db750-110">**MaximalUsage** = 350 (default configuration value)</span></span>  
  
 <span data-ttu-id="db750-111">Puesto que la **ActualPrivateBytes** están comprendidos entre **OptimalUsage** y **MaximalUsage**, alpha se calcula como:</span><span class="sxs-lookup"><span data-stu-id="db750-111">Since the **ActualPrivateBytes** are between **OptimalUsage** and **MaximalUsage**, alpha is calculated as:</span></span>  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 <span data-ttu-id="db750-112">A continuación, calcula el **TestThreshold** como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="db750-112">Then you calculate the **TestThreshold** as follows:</span></span>  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 <span data-ttu-id="db750-113">Por último, se toma la decisión sobre si deshidratar o no:</span><span class="sxs-lookup"><span data-stu-id="db750-113">And finally, make the decision to dehydrate or not:</span></span>  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 <span data-ttu-id="db750-114">Mediante este ejemplo, se puede establecer que la orquestación no se deshidratará en este momento.</span><span class="sxs-lookup"><span data-stu-id="db750-114">Using this example, you can determine that the orchestration will not be dehydrated at this time.</span></span>
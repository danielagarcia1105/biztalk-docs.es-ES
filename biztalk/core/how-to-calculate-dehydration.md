---
title: Cómo calcular la deshidratación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db413cfef1e49f1f3177d8a9f578c94f5a2a1a28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998149"
---
# <a name="how-to-calculate-dehydration"></a><span data-ttu-id="60672-102">Cómo calcular la deshidratación</span><span class="sxs-lookup"><span data-stu-id="60672-102">How to Calculate Dehydration</span></span>
<span data-ttu-id="60672-103">Para calcular la deshidratación, use las propiedades configuradas y determinados valores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60672-103">To calculate dehydration, you use the configured properties and certain run-time values.</span></span> <span data-ttu-id="60672-104">En el ejemplo siguiente se muestra cómo calcular un escenario de deshidratación hipotético.</span><span class="sxs-lookup"><span data-stu-id="60672-104">The following example demonstrates how to calculate a hypothetical dehydration scenario.</span></span>  
  
### <a name="to-calculate-dehydration"></a><span data-ttu-id="60672-105">Para calcular la deshidratación</span><span class="sxs-lookup"><span data-stu-id="60672-105">To calculate dehydration</span></span>  
  
1. <span data-ttu-id="60672-106">Permita que alfa represente un factor entre 0 y 1 que mida la sobrecarga de la memoria.</span><span class="sxs-lookup"><span data-stu-id="60672-106">Let alpha represent a factor between 0 and 1 that measures memory stress.</span></span>  <span data-ttu-id="60672-107">En la práctica, alfa tiene un componente para cada uno de los tres criterios de limitación de la memoria (propiedades de deshidratación); en este ejemplo, se indican como alpha(virtual), alpha(private) y alpha(physical).</span><span class="sxs-lookup"><span data-stu-id="60672-107">In practice, alpha has a component for each of the three memory throttling criteria (dehydration properties); in this example we denote them as alpha(virtual), alpha(private) and alpha(physical).</span></span> <span data-ttu-id="60672-108">Defina lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60672-108">Define the following:</span></span>  
  
   ```  
   IF ActualPrivateBytes < OptimalUsage  
      alpha(private) = 1  
   ELSE IF ActualPrivateBytes > MaximalUsage  
      alpha(private) = 0  
   ELSE  
      alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="60672-109">OptimalUsage y MaximalUsage tienen valores predeterminados para cada propiedad de deshidratación.</span><span class="sxs-lookup"><span data-stu-id="60672-109">OptimalUsage and MaximalUsage have default values for each dehydration property.</span></span> <span data-ttu-id="60672-110">Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="60672-110">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="60672-111">Para obtener más información, consulte [propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md).</span><span class="sxs-lookup"><span data-stu-id="60672-111">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
2. <span data-ttu-id="60672-112">Defina los otros componentes alfa de forma similar.</span><span class="sxs-lookup"><span data-stu-id="60672-112">Define the other alpha components analogously.</span></span> <span data-ttu-id="60672-113">Defina lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60672-113">Define the following:</span></span>  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. <span data-ttu-id="60672-114">A continuación, defina TestThreshold (TestThreshold, MinThreshold y MaxThreshold se definen en segundos):</span><span class="sxs-lookup"><span data-stu-id="60672-114">Then define TestThreshold (TestThreshold, MinThreshold, and MaxThreshold are defined in seconds):</span></span>  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="60672-115">Valor predeterminado de MinThreshold = 1.</span><span class="sxs-lookup"><span data-stu-id="60672-115">MinThreshold default value = 1.</span></span> <span data-ttu-id="60672-116">Valor predeterminado de MaxThreshold = 1800.</span><span class="sxs-lookup"><span data-stu-id="60672-116">MaxThreshold default value = 1800.</span></span> <span data-ttu-id="60672-117">Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="60672-117">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="60672-118">Para obtener más información, consulte [propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md).</span><span class="sxs-lookup"><span data-stu-id="60672-118">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
4. <span data-ttu-id="60672-119">A continuación, defina TimeBlocked y EstimatedTime:</span><span class="sxs-lookup"><span data-stu-id="60672-119">Then define TimeBlocked and EstimatedTime:</span></span>  
  
   -   <span data-ttu-id="60672-120">TimeBlocked = tiempo real que se ha esperado a que se satisficiera esta suscripción</span><span class="sxs-lookup"><span data-stu-id="60672-120">TimeBlocked = actual time we have been waiting for this subscription to be satisfied</span></span>  
  
   -   <span data-ttu-id="60672-121">EstimatedTime = tiempo estimado que esta orquestación permanecerá inactiva (por ejemplo, tiempo de espera restante en la escucha)</span><span class="sxs-lookup"><span data-stu-id="60672-121">EstimatedTime = estimated time that this orchestration will remain idle (e.g. remaining timeout on the listen)</span></span>  
  
   <span data-ttu-id="60672-122">La decisión sobre si se debe deshidratar es el resultado la siguiente condición booleana (true = deshidratar):</span><span class="sxs-lookup"><span data-stu-id="60672-122">The decision whether to dehydrate is the result of the following Boolean condition (true = dehydrate):</span></span>  
  
-   <span data-ttu-id="60672-123">Deshidratar = (EstimatedTime > TestThreshold OR TimeBlocked > (2\* TestThreshold))</span><span class="sxs-lookup"><span data-stu-id="60672-123">Dehydrate = (EstimatedTime > TestThreshold OR TimeBlocked > (2\* TestThreshold))</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60672-124">El tiempo estimado es el tiempo restante hasta que termina el retraso (si se retrasa 5 minutos y han pasado 2 minutos, TimeBlocked=120 segundos, EstimatedTime=180 segundos).</span><span class="sxs-lookup"><span data-stu-id="60672-124">Estimated time is the time remaining until the delay is ended (if delayed for 5 minutes and 2 minutes has passed, TimeBlocked=120 seconds, EstimatedTime=180 seconds).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60672-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="60672-125">See Also</span></span>  
 <span data-ttu-id="60672-126">[Propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md) </span><span class="sxs-lookup"><span data-stu-id="60672-126">[Dehydration Default Properties](../core/dehydration-default-properties.md) </span></span>  
 [<span data-ttu-id="60672-127">BTSNTSvc.exe.config (archivo)</span><span class="sxs-lookup"><span data-stu-id="60672-127">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)
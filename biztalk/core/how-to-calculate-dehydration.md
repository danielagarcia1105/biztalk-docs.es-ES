---
title: "Cómo calcular la deshidratación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a327695099ec575f2a13ccb75b4152e4a7de1af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-calculate-dehydration"></a><span data-ttu-id="fb124-102">Cómo calcular la deshidratación</span><span class="sxs-lookup"><span data-stu-id="fb124-102">How to Calculate Dehydration</span></span>
<span data-ttu-id="fb124-103">Para calcular la deshidratación, use las propiedades configuradas y determinados valores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb124-103">To calculate dehydration, you use the configured properties and certain run-time values.</span></span> <span data-ttu-id="fb124-104">En el ejemplo siguiente se muestra cómo calcular un escenario de deshidratación hipotético.</span><span class="sxs-lookup"><span data-stu-id="fb124-104">The following example demonstrates how to calculate a hypothetical dehydration scenario.</span></span>  
  
### <a name="to-calculate-dehydration"></a><span data-ttu-id="fb124-105">Para calcular la deshidratación</span><span class="sxs-lookup"><span data-stu-id="fb124-105">To calculate dehydration</span></span>  
  
1.  <span data-ttu-id="fb124-106">Permita que alfa represente un factor entre 0 y 1 que mida la sobrecarga de la memoria.</span><span class="sxs-lookup"><span data-stu-id="fb124-106">Let alpha represent a factor between 0 and 1 that measures memory stress.</span></span>  <span data-ttu-id="fb124-107">En la práctica, alfa tiene un componente para cada uno de los tres criterios de limitación de la memoria (propiedades de deshidratación); en este ejemplo, se indican como alpha(virtual), alpha(private) y alpha(physical).</span><span class="sxs-lookup"><span data-stu-id="fb124-107">In practice, alpha has a component for each of the three memory throttling criteria (dehydration properties); in this example we denote them as alpha(virtual), alpha(private) and alpha(physical).</span></span> <span data-ttu-id="fb124-108">Defina lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb124-108">Define the following:</span></span>  
  
    ```  
    IF ActualPrivateBytes < OptimalUsage  
       alpha(private) = 1  
    ELSE IF ActualPrivateBytes > MaximalUsage  
       alpha(private) = 0  
    ELSE  
       alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fb124-109">OptimalUsage y MaximalUsage tienen valores predeterminados para cada propiedad de deshidratación.</span><span class="sxs-lookup"><span data-stu-id="fb124-109">OptimalUsage and MaximalUsage have default values for each dehydration property.</span></span> <span data-ttu-id="fb124-110">Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="fb124-110">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="fb124-111">Para obtener más información, consulte [propiedades de deshidratación predeterminado](../core/dehydration-default-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fb124-111">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
2.  <span data-ttu-id="fb124-112">Defina los otros componentes alfa de forma similar.</span><span class="sxs-lookup"><span data-stu-id="fb124-112">Define the other alpha components analogously.</span></span> <span data-ttu-id="fb124-113">Defina lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb124-113">Define the following:</span></span>  
  
    ```  
    alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
    where alpha(…) = 1 whenever IsActive=false for that given memory unit  
    ```  
  
3.  <span data-ttu-id="fb124-114">A continuación, defina TestThreshold (TestThreshold, MinThreshold y MaxThreshold se definen en segundos):</span><span class="sxs-lookup"><span data-stu-id="fb124-114">Then define TestThreshold (TestThreshold, MinThreshold, and MaxThreshold are defined in seconds):</span></span>  
  
    ```  
    TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fb124-115">Valor predeterminado de MinThreshold = 1.</span><span class="sxs-lookup"><span data-stu-id="fb124-115">MinThreshold default value = 1.</span></span> <span data-ttu-id="fb124-116">Valor predeterminado de MaxThreshold = 1800.</span><span class="sxs-lookup"><span data-stu-id="fb124-116">MaxThreshold default value = 1800.</span></span> <span data-ttu-id="fb124-117">Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="fb124-117">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="fb124-118">Para obtener más información, consulte [propiedades de deshidratación predeterminado](../core/dehydration-default-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fb124-118">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
4.  <span data-ttu-id="fb124-119">A continuación, defina TimeBlocked y EstimatedTime:</span><span class="sxs-lookup"><span data-stu-id="fb124-119">Then define TimeBlocked and EstimatedTime:</span></span>  
  
    -   <span data-ttu-id="fb124-120">TimeBlocked = tiempo real que se ha esperado a que se satisficiera esta suscripción</span><span class="sxs-lookup"><span data-stu-id="fb124-120">TimeBlocked = actual time we have been waiting for this subscription to be satisfied</span></span>  
  
    -   <span data-ttu-id="fb124-121">EstimatedTime = tiempo estimado que esta orquestación permanecerá inactiva (por ejemplo, tiempo de espera restante en la escucha)</span><span class="sxs-lookup"><span data-stu-id="fb124-121">EstimatedTime = estimated time that this orchestration will remain idle (e.g. remaining timeout on the listen)</span></span>  
  
 <span data-ttu-id="fb124-122">La decisión sobre si se debe deshidratar es el resultado la siguiente condición booleana (true = deshidratar):</span><span class="sxs-lookup"><span data-stu-id="fb124-122">The decision whether to dehydrate is the result of the following Boolean condition (true = dehydrate):</span></span>  
  
-   <span data-ttu-id="fb124-123">Deshidratar = (EstimatedTime > TestThreshold OR TimeBlocked > (2* TestThreshold))</span><span class="sxs-lookup"><span data-stu-id="fb124-123">Dehydrate = (EstimatedTime > TestThreshold OR TimeBlocked > (2* TestThreshold))</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb124-124">El tiempo estimado es el tiempo restante hasta que termina el retraso (si se retrasa 5 minutos y han pasado 2 minutos, TimeBlocked=120 segundos, EstimatedTime=180 segundos).</span><span class="sxs-lookup"><span data-stu-id="fb124-124">Estimated time is the time remaining until the delay is ended (if delayed for 5 minutes and 2 minutes has passed, TimeBlocked=120 seconds, EstimatedTime=180 seconds).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb124-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb124-125">See Also</span></span>  
 <span data-ttu-id="fb124-126">[Propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fb124-126">[Dehydration Default Properties](../core/dehydration-default-properties.md) </span></span>  
 [<span data-ttu-id="fb124-127">Archivo BTSNTSvc.exe.config</span><span class="sxs-lookup"><span data-stu-id="fb124-127">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)
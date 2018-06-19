---
title: Orquestación deshidratación y rehidratación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7cee568cda6c869ede94e28bce441462c0c7cdc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710619"
---
# <a name="orchestration-dehydration-and-rehydration"></a><span data-ttu-id="d9d31-102">Deshidratación y rehidratación de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d9d31-102">Orchestration Dehydration and Rehydration</span></span>
<span data-ttu-id="d9d31-103">Cuando se ejecutan a la vez muchos procesos empresariales de larga duración, la memoria y el rendimiento se convierten en problemas potenciales.</span><span class="sxs-lookup"><span data-stu-id="d9d31-103">When many long-running business processes are running at the same time, memory and performance are potential issues.</span></span> <span data-ttu-id="d9d31-104">El motor de la orquestación aborda estos problemas mediante la "deshidratación" y la "rehidratación" de las instancias de orquestación.</span><span class="sxs-lookup"><span data-stu-id="d9d31-104">The orchestration engine addresses these issues by "dehydrating" and "rehydrating" orchestration instances.</span></span>  
  
 <span data-ttu-id="d9d31-105">La deshidratación es el proceso de serializar el estado de una orquestación en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d9d31-105">Dehydration is the process of serializing the state of an orchestration into a SQL Server database.</span></span> <span data-ttu-id="d9d31-106">Rehidratación es el proceso inverso: deserializar el último estado de ejecución de una orquestación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d9d31-106">Rehydration is the reverse of this process: deserializing the last running state of an orchestration from the database.</span></span> <span data-ttu-id="d9d31-107">La deshidratación se utiliza para minimizar el uso de recursos de sistema al reducir el número de las orquestaciones de las que a la vez se tiene que crear la instancia en memoria.</span><span class="sxs-lookup"><span data-stu-id="d9d31-107">Dehydration is used to minimize the use of system resources by reducing the number of orchestrations that have to be instantiated in memory at one time.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="d9d31-108">Deshidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-108">Dehydration</span></span>  
 <span data-ttu-id="d9d31-109">La orquestación puede determinar que una instancia de orquestación ha estado inactiva durante un período relativamente grande.</span><span class="sxs-lookup"><span data-stu-id="d9d31-109">The orchestration engine might determine that an orchestration instance has been idle for a relatively long period of time.</span></span> <span data-ttu-id="d9d31-110">Calcula umbrales para determinar el tiempo que esperará para que tengan lugar varias acciones y, si dichos umbrales se superan, deshidrata la instancia.</span><span class="sxs-lookup"><span data-stu-id="d9d31-110">It calculates thresholds to determine how long it will wait for various actions to take place, and if those thresholds are exceeded, it dehydrates the instance.</span></span> <span data-ttu-id="d9d31-111">Esto puede producirse en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="d9d31-111">This can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="d9d31-112">Si la orquestación espera la recepción de un mensaje y el tiempo de espera es superior al umbral determinado por el motor.</span><span class="sxs-lookup"><span data-stu-id="d9d31-112">When the orchestration is waiting to receive a message, and the wait is longer than a threshold determined by the engine.</span></span>  
  
-   <span data-ttu-id="d9d31-113">Cuando la orquestación "escucha" para un mensaje, como ocurre cuando se usa un **escuchar** forma y ninguna bifurcación se desencadena antes de un umbral determinado por el motor.</span><span class="sxs-lookup"><span data-stu-id="d9d31-113">When the orchestration is "listening" for a message, as it does when you use a **Listen** shape, and no branch is triggered before a threshold determined by the engine.</span></span> <span data-ttu-id="d9d31-114">La única excepción a esto es cuando la **escuchar** forma contiene una activación de recepción.</span><span class="sxs-lookup"><span data-stu-id="d9d31-114">The only exception to this is when the **Listen** shape contains an activation receive.</span></span>  
  
-   <span data-ttu-id="d9d31-115">Si un retraso en la orquestación es mayor que el umbral determinado por el motor.</span><span class="sxs-lookup"><span data-stu-id="d9d31-115">When a delay in the orchestration is longer than a threshold determined by the engine.</span></span>  
  
 <span data-ttu-id="d9d31-116">El motor deshidrata la instancia; para ello, guarda el estado de la instancia y libera la memoria que ésta necesita.</span><span class="sxs-lookup"><span data-stu-id="d9d31-116">The engine dehydrates the instance by saving the state, and frees up the memory required by the instance.</span></span> <span data-ttu-id="d9d31-117">Mediante la deshidratación de instancias de orquestación latentes, el motor permite un gran número de procesos empresariales de larga ejecución para ejecutar simultáneamente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="d9d31-117">By dehydrating dormant orchestration instances, the engine makes it possible for a large number of long-running business processes to run concurrently on the same computer.</span></span>  
  
 <span data-ttu-id="d9d31-118">Se pueden establecer 12 propiedades para configurar el funcionamiento de la deshidratación en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d9d31-118">You can set 12 properties to configure how dehydration works in BizTalk Server.</span></span> <span data-ttu-id="d9d31-119">Los temas de esta sección enumeran y describen las propiedades y sus valores predeterminados, y explican el modo en que los distintos valores afectan al comportamiento de la deshidratación.</span><span class="sxs-lookup"><span data-stu-id="d9d31-119">The topics in this section list and describe these properties and their default values, and discuss how various values affect dehydration behavior.</span></span>  
  
## <a name="rehydration"></a><span data-ttu-id="d9d31-120">Rehidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-120">Rehydration</span></span>  
 <span data-ttu-id="d9d31-121">El motor de orquestaciones se inicia para rehidratar una instancia de orquestación mediante la recepción de un mensaje o el vencimiento de un tiempo de espera especificado en una forma Retraso.</span><span class="sxs-lookup"><span data-stu-id="d9d31-121">The orchestration engine can be triggered to rehydrate an orchestration instance by the receipt of a message or by the expiration of a time-out specified in a Delay shape.</span></span> <span data-ttu-id="d9d31-122">Después carga la instancia de orquestación guardada en la memoria, restaura su estado y la ejecuta desde el punto en que se interrumpió.</span><span class="sxs-lookup"><span data-stu-id="d9d31-122">It then loads the saved orchestration instance into memory, restores its state, and runs it from the point where it left off.</span></span> <span data-ttu-id="d9d31-123">Para obtener más información sobre el uso de formas en orquestaciones, consulte [formas de orquestación](../core/orchestration-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="d9d31-123">For more information about using shapes in orchestrations, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
 <span data-ttu-id="d9d31-124">Una orquestación se puede configurar para que se ejecute en más de un servidor.</span><span class="sxs-lookup"><span data-stu-id="d9d31-124">An orchestration can be configured to run on more than one server.</span></span> <span data-ttu-id="d9d31-125">Después de que una instancia de orquestación se haya deshidratado, puede rehidratarse en cualquiera de estos servidores.</span><span class="sxs-lookup"><span data-stu-id="d9d31-125">After an orchestration instance has been dehydrated, it can be rehydrated on any of these servers.</span></span> <span data-ttu-id="d9d31-126">Si un servidor deja de funcionar, el motor continúa ejecutando la orquestación en un servidor diferente desde su estado anterior.</span><span class="sxs-lookup"><span data-stu-id="d9d31-126">If one server goes down, the engine continues to run the orchestration on a different server, continuing from its previous state.</span></span> <span data-ttu-id="d9d31-127">El motor también aprovecha esta característica para implementar el equilibrio de carga entre los servidores.</span><span class="sxs-lookup"><span data-stu-id="d9d31-127">The engine also takes advantage of this feature to implement load balancing across servers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d9d31-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d9d31-128">Next steps</span></span>
  
-   [<span data-ttu-id="d9d31-129">Propiedades predeterminadas de deshidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-129">Dehydration Default Properties</span></span>](../core/dehydration-default-properties.md)  
  
-   [<span data-ttu-id="d9d31-130">Cómo calcular la deshidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-130">How to Calculate Dehydration</span></span>](../core/how-to-calculate-dehydration.md)  
  
-   [<span data-ttu-id="d9d31-131">Ejemplo de cálculo de deshidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-131">Sample Dehydration Calculation</span></span>](../core/sample-dehydration-calculation.md)  
  
-   [<span data-ttu-id="d9d31-132">Contadores de rendimiento de deshidratación de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="d9d31-132">Orchestration Dehydration Performance Counters</span></span>](../core/orchestration-dehydration-performance-counters.md)  
  
-   [<span data-ttu-id="d9d31-133">BTSNTSvc.exe.config (archivo)</span><span class="sxs-lookup"><span data-stu-id="d9d31-133">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)  
  
-   [<span data-ttu-id="d9d31-134">Otras actividades que pueden afectar al comportamiento de deshidratación</span><span class="sxs-lookup"><span data-stu-id="d9d31-134">Other Activities That Can Affect Dehydration Behavior</span></span>](../core/other-activities-that-can-affect-dehydration-behavior.md)
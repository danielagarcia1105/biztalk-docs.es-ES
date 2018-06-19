---
title: Persistencia y el motor de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, persistence
- persistence
- orchestration engine, serialization
ms.assetid: 088230ef-13b3-440b-9875-6449f29dd5c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9e1c8b158d313681a6e1374a586ca957b1aa15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264932"
---
# <a name="persistence-and-the-orchestration-engine"></a><span data-ttu-id="b8f70-102">Persistencia y el motor de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="b8f70-102">Persistence and the Orchestration Engine</span></span>
<span data-ttu-id="b8f70-103">La persistencia de los estados, su administración y restauración constituyen la base de muchas de las funcionalidades fundamentales del motor de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="b8f70-103">State persistence, its management and restoration form the basis of a lot of fundamental functionalities of the orchestration engine.</span></span> <span data-ttu-id="b8f70-104">En particular, la persistencia es crítica para el funcionamiento correcto de:</span><span class="sxs-lookup"><span data-stu-id="b8f70-104">In particular, persistence is critical to the correct functioning of:</span></span>  
  
-   <span data-ttu-id="b8f70-105">Deshidratación y rehidratación</span><span class="sxs-lookup"><span data-stu-id="b8f70-105">Dehydration and rehydration</span></span>  
  
-   <span data-ttu-id="b8f70-106">Ejecución agnóstica del equipo y rehidratación</span><span class="sxs-lookup"><span data-stu-id="b8f70-106">Machine agnostic execution and rehydration</span></span>  
  
-   <span data-ttu-id="b8f70-107">Modelo de compensación</span><span class="sxs-lookup"><span data-stu-id="b8f70-107">Compensation model</span></span>  
  
-   <span data-ttu-id="b8f70-108">Cierre controlado del sistema</span><span class="sxs-lookup"><span data-stu-id="b8f70-108">Controlled System Shutdown</span></span>  
  
-   <span data-ttu-id="b8f70-109">Recuperación</span><span class="sxs-lookup"><span data-stu-id="b8f70-109">Recovery</span></span>  
  
 <span data-ttu-id="b8f70-110">El motor de orquestaciones guarda toda la información de estado de las instancias de orquestación en ejecución en varios puntos en el almacenamiento persistente, de modo que las instancias se puedan restaurar posteriormente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b8f70-110">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be completely restored in memory.</span></span> <span data-ttu-id="b8f70-111">El estado incluye:</span><span class="sxs-lookup"><span data-stu-id="b8f70-111">The state includes:</span></span>  
  
-   <span data-ttu-id="b8f70-112">El estado interno del motor, incluido su progreso actual</span><span class="sxs-lookup"><span data-stu-id="b8f70-112">The internal state of the engine, including its current progress.</span></span>  
  
-   <span data-ttu-id="b8f70-113">El estado de cualquier componente .NET que mantenga información de estado y que utilice la orquestación</span><span class="sxs-lookup"><span data-stu-id="b8f70-113">The state of any .NET components that maintain state information and are being used by the orchestration.</span></span>  
  
-   <span data-ttu-id="b8f70-114">Valores de variables y mensajes</span><span class="sxs-lookup"><span data-stu-id="b8f70-114">Message and variable values.</span></span>  
  
## <a name="persistence-points"></a><span data-ttu-id="b8f70-115">Puntos de persistencia</span><span class="sxs-lookup"><span data-stu-id="b8f70-115">Persistence Points</span></span>  
 <span data-ttu-id="b8f70-116">El motor de orquestaciones guarda el estado de una instancia de orquestación en ejecución en varios puntos.</span><span class="sxs-lookup"><span data-stu-id="b8f70-116">The orchestration engine saves the state of a running orchestration instance at various points.</span></span> <span data-ttu-id="b8f70-117">Si la instancia de orquestación se debe rehidratar, iniciar a partir de un cierre controlado o recuperar desde un cierre inesperado, ésta se ejecutará desde el último punto de persistencia como si nada hubiera ocurrido.</span><span class="sxs-lookup"><span data-stu-id="b8f70-117">If it needs to rehydrate the orchestration instance, start up from a controlled shutdown, or recover from an unexpected shutdown, it will run the orchestration instance from the last persistence point, as though nothing else had occurred.</span></span> <span data-ttu-id="b8f70-118">Por ejemplo, si se recibe un mensaje pero se produce un cierre inesperado antes de que se pueda guardar el estado, el motor no registrará que se ha recibido el mensaje y lo volverá a recibir después de reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="b8f70-118">For example, if a message is received but there is an unexpected shutdown before state can be saved, the engine will not record that it has received the message, and will receive it again upon restarting.</span></span> <span data-ttu-id="b8f70-119">El motor guardará el estado de una orquestación cuando se produzcan las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="b8f70-119">The engine will save the state of an orchestration in the following circumstances:</span></span>  
  
-   <span data-ttu-id="b8f70-120">Se alcanza el final de un ámbito transaccional.</span><span class="sxs-lookup"><span data-stu-id="b8f70-120">The end of a transactional scope is reached.</span></span>  
  
    -   <span data-ttu-id="b8f70-121">El motor guarda el estado al final de un ámbito transaccional de modo que el punto desde el que se debe reanudar la orquestación esté definido de forma no ambigua y que, por tanto, se pueda llevar a cabo correctamente dicha compensación si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b8f70-121">The engine saves state at the end of a transactional scope so that the point at which the orchestration should resume is defined unambiguously, and so that compensation can be carried out correctly if necessary.</span></span>  
  
    -   <span data-ttu-id="b8f70-122">La orquestación seguirá ejecutándose desde el final del ámbito si la persistencia es correcta; en caso contrario, se invocará el controlador de excepción apropiado.</span><span class="sxs-lookup"><span data-stu-id="b8f70-122">The orchestration will continue to run from the end of the scope if persistence was successful; otherwise, the appropriate exception handler will be invoked.</span></span>  
  
    -   <span data-ttu-id="b8f70-123">Si el ámbito es transaccional y atómico, el motor guardará el estado al final del ámbito atómico cuando realice la confirmación.</span><span class="sxs-lookup"><span data-stu-id="b8f70-123">If the scope is transactional and atomic, the engine will save state at the end of the atomic scope when it commits.</span></span>  
  
    -   <span data-ttu-id="b8f70-124">Si el ámbito es transaccional y de larga ejecución, el motor generará una nueva transacción y almacenará el estado completo de tiempo de ejecución cuando se complete el ámbito.</span><span class="sxs-lookup"><span data-stu-id="b8f70-124">If the scope is transactional and long-running, the engine will generate a new transaction and persist the complete state of the runtime when the scope completes.</span></span>  
  
-   <span data-ttu-id="b8f70-125">Se alcanza un punto de interrupción de depuración.</span><span class="sxs-lookup"><span data-stu-id="b8f70-125">A debugging breakpoint is reached.</span></span>  
  
-   <span data-ttu-id="b8f70-126">Se envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b8f70-126">A message is sent.</span></span> <span data-ttu-id="b8f70-127">La única excepción a esto es cuando se envía un mensaje desde un ámbito de transacción atómica.</span><span class="sxs-lookup"><span data-stu-id="b8f70-127">The only exception to this is when a message is sent from within an atomic transaction scope.</span></span>  
  
-   <span data-ttu-id="b8f70-128">La orquestación inicia otra orquestación de forma asincrónica, al igual que con la **Iniciar orquestación** forma.</span><span class="sxs-lookup"><span data-stu-id="b8f70-128">The orchestration starts another orchestration asynchronously, as with the **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="b8f70-129">La instancia de orquestación se suspende.</span><span class="sxs-lookup"><span data-stu-id="b8f70-129">The orchestration instance is suspended.</span></span>  
  
-   <span data-ttu-id="b8f70-130">Cuando se solicita el cierre del motor de orquestaciones, éste intenta guardar la información de control y el estado actual de todas las instancias de orquestación en ejecución, de modo que pueda reanudar la ejecución de dichas instancias cuando se vuelva a iniciar.</span><span class="sxs-lookup"><span data-stu-id="b8f70-130">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="b8f70-131">Si el motor no consigue guardar el estado actual, reanudará la instancia de orquestación desde el último punto de persistencia que se haya producido antes del cierre.</span><span class="sxs-lookup"><span data-stu-id="b8f70-131">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="b8f70-132">Esto se aplica al cierre del sistema de manera controlada, así como a la terminación anormal.</span><span class="sxs-lookup"><span data-stu-id="b8f70-132">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
-   <span data-ttu-id="b8f70-133">El motor determina que la instancia se debe deshidratar.</span><span class="sxs-lookup"><span data-stu-id="b8f70-133">The engine determines that the instance should be dehydrated.</span></span>  
  
-   <span data-ttu-id="b8f70-134">La instancia de orquestación se finaliza.</span><span class="sxs-lookup"><span data-stu-id="b8f70-134">The orchestration instance is finished.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="b8f70-135">Serialización</span><span class="sxs-lookup"><span data-stu-id="b8f70-135">Serialization</span></span>  
 <span data-ttu-id="b8f70-136">Todas las instancias de objetos a las que la orquestación haga referencia de forma directa o indirecta (como a través de otros objetos) deben ser serializables para que se pueda almacenar de forma persistente el estado de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="b8f70-136">All object instances that your orchestration refers to directly or indirectly (as through other objects) must be serializable for your orchestration state to be persisted.</span></span> <span data-ttu-id="b8f70-137">Hay dos excepciones:</span><span class="sxs-lookup"><span data-stu-id="b8f70-137">There are two exceptions:</span></span>  
  
-   <span data-ttu-id="b8f70-138">Puede haber un objeto no serializable declarado dentro de una transacción atómica.</span><span class="sxs-lookup"><span data-stu-id="b8f70-138">You can have a nonserializable object declared inside an atomic transaction.</span></span> <span data-ttu-id="b8f70-139">Esto es posible porque los ámbitos atómicos no contienen puntos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="b8f70-139">You can do this because atomic scopes do not contain persistence points.</span></span>  
  
-   <span data-ttu-id="b8f70-140">System.Xml.XmlDocument no es una clase serializable; se considera un caso especial y se puede utilizar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="b8f70-140">System.Xml.XmlDocument is not a serializable class; it is handled as a special case and can be used anywhere.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b8f70-141">Un objeto .NET debe estar marcado como serializable para que se pueda almacenar de forma persistente.</span><span class="sxs-lookup"><span data-stu-id="b8f70-141">In order for a .NET object to be persisted, it must be marked as serializable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8f70-142">Los objetos COM no se pueden almacenar de forma persistente con procedimientos de serialización .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="b8f70-142">COM objects cannot be persisted using standard .NET serialization procedures.</span></span> <span data-ttu-id="b8f70-143">Si desea llamar un objeto COM fuera de una transacción atómica, debe incluir el objeto COM en un objeto .NET que sea .NET serializable, además de saber cómo almacenarlo de forma persistente y cómo restaurar el estado del objeto COM.</span><span class="sxs-lookup"><span data-stu-id="b8f70-143">If you want to call a COM object outside of an atomic transaction, you must wrap the COM object in a .NET object that is .NET serializable and knows how to persist and restore the state of the COM object.</span></span>  
  
## <a name="system-shutdown"></a><span data-ttu-id="b8f70-144">Cierre del sistema</span><span class="sxs-lookup"><span data-stu-id="b8f70-144">System Shutdown</span></span>  
 <span data-ttu-id="b8f70-145">Cuando se solicita el cierre del motor de orquestaciones, éste intenta guardar la información de control y el estado actual de todas las instancias de orquestación en ejecución, de modo que pueda reanudar la ejecución de dichas instancias cuando se vuelva a iniciar.</span><span class="sxs-lookup"><span data-stu-id="b8f70-145">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="b8f70-146">Si el motor no consigue guardar el estado actual, reanudará la instancia de orquestación desde el último punto de persistencia que se haya producido antes del cierre.</span><span class="sxs-lookup"><span data-stu-id="b8f70-146">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="b8f70-147">Esto se aplica al cierre del sistema de manera controlada, así como a la terminación anormal.</span><span class="sxs-lookup"><span data-stu-id="b8f70-147">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
## <a name="recovery"></a><span data-ttu-id="b8f70-148">Recuperación</span><span class="sxs-lookup"><span data-stu-id="b8f70-148">Recovery</span></span>  
 <span data-ttu-id="b8f70-149">El motor guarda periódicamente la información de estado de una instancia de orquestación en el almacenamiento persistente y guarda también el estado en caso de cierre del sistema.</span><span class="sxs-lookup"><span data-stu-id="b8f70-149">The engine regularly saves to persistent storage the state information of an orchestration instance, and it also saves state in the event of a system shutdown.</span></span>  
  
 <span data-ttu-id="b8f70-150">Cuando por cualquier motivo se produce un error anormal en una instancia de orquestación, la instancia se puede recuperar desde el último estado guardado y puede seguir ejecutándose como si no se hubiera producido ninguna interrupción.</span><span class="sxs-lookup"><span data-stu-id="b8f70-150">When an orchestration instance fails abnormally for whatever reason, the instance can be recovered from the last persisted state, and it can continue to run as if there were no interruption.</span></span> <span data-ttu-id="b8f70-151">Esto ocurre aunque el servidor original en el que se ejecuta la instancia se quede sin servicio por algún motivo; la instancia puede simplemente reanudar la ejecución en un equipo distinto.</span><span class="sxs-lookup"><span data-stu-id="b8f70-151">This is true even if the original server that the instance ran on goes out of service for some reason; the instance can simply resume running on a separate machine.</span></span> <span data-ttu-id="b8f70-152">Debido a este modelo de recuperación de varios servidores, ya no necesitará más la organización por clústeres.</span><span class="sxs-lookup"><span data-stu-id="b8f70-152">Because of this multi-server recovery model, you no longer need clustering.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f70-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8f70-153">See Also</span></span>  
 [<span data-ttu-id="b8f70-154">Orquestación deshidratación y rehidratación</span><span class="sxs-lookup"><span data-stu-id="b8f70-154">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)
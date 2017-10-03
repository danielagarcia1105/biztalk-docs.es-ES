---
title: "Formas de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-shapes"></a><span data-ttu-id="f4163-102">Formas de orquestación</span><span class="sxs-lookup"><span data-stu-id="f4163-102">Orchestration Shapes</span></span>
<span data-ttu-id="f4163-103">El Diseñador de orquestaciones es una herramienta visual para crear orquestaciones</span><span class="sxs-lookup"><span data-stu-id="f4163-103">Orchestration Designer is a visual tool for creating orchestrations.</span></span> <span data-ttu-id="f4163-104">Proporciona varias formas que puede situar en la superficie de diseño como representaciones visuales de acciones subyacentes y pueden serle útiles a la hora de diseñar e implementar eficientemente una orquestación.</span><span class="sxs-lookup"><span data-stu-id="f4163-104">It provides several shapes that you can place on the design surface as visual representations of underlying actions, and they can help you to efficiently design and implement an orchestration.</span></span>  
  
 <span data-ttu-id="f4163-105">**Acción de configuración incompleta**</span><span class="sxs-lookup"><span data-stu-id="f4163-105">**Insufficient Configuration Action**</span></span>  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  <span data-ttu-id="f4163-106">La acción de configuración incompleta se muestra en el Diseñador de orquestaciones cuando este detecta que la forma asociada no está completamente configurada.</span><span class="sxs-lookup"><span data-stu-id="f4163-106">The Insufficient Configuration Action is displayed in the Orchestration designer when the Orchestration Designer detects that the associated shape is not completely configured.</span></span> <span data-ttu-id="f4163-107">Si una forma de una orquestación no está completamente configurada, la orquestación asociada no se compilará.</span><span class="sxs-lookup"><span data-stu-id="f4163-107">If a shape in an Orchestration is not completely configured then the associated Orchestration will not compile.</span></span>  
  
 <span data-ttu-id="f4163-108">En la siguiente tabla se enumeran las formas disponibles junto a una breve descripción de la función de cada una.</span><span class="sxs-lookup"><span data-stu-id="f4163-108">The following table lists the available shapes, along with a brief description of the function of each shape.</span></span>  
  
|<span data-ttu-id="f4163-109">Forma</span><span class="sxs-lookup"><span data-stu-id="f4163-109">Shape</span></span>|<span data-ttu-id="f4163-110">Nombre de la forma</span><span class="sxs-lookup"><span data-stu-id="f4163-110">Shape Name</span></span>|<span data-ttu-id="f4163-111">Finalidad</span><span class="sxs-lookup"><span data-stu-id="f4163-111">Purpose</span></span>|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|<span data-ttu-id="f4163-112">**Orquestación de llamada**</span><span class="sxs-lookup"><span data-stu-id="f4163-112">**Call Orchestration**</span></span>|<span data-ttu-id="f4163-113">Permite que su orquestación llame a otra orquestación de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="f4163-113">Enables your orchestration to call another orchestration synchronously.</span></span>|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|<span data-ttu-id="f4163-114">**Reglas de llamada**</span><span class="sxs-lookup"><span data-stu-id="f4163-114">**Call Rules**</span></span>|<span data-ttu-id="f4163-115">Permite crear una directiva de reglas de negocios para ejecutarla en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f4163-115">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|<span data-ttu-id="f4163-116">**Compensar**</span><span class="sxs-lookup"><span data-stu-id="f4163-116">**Compensate**</span></span>|<span data-ttu-id="f4163-117">Permite llamar a código para deshacer o compensar operaciones ya realizadas por la orquestación cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="f4163-117">Enables you to call code to undo or compensate for operations already performed by the orchestration when an error occurs.</span></span>|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|<span data-ttu-id="f4163-118">**Forma construir mensaje**</span><span class="sxs-lookup"><span data-stu-id="f4163-118">**Construct Message**</span></span>|<span data-ttu-id="f4163-119">Permite construir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4163-119">Enables you to construct a message.</span></span>|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|<span data-ttu-id="f4163-120">**Decidir**</span><span class="sxs-lookup"><span data-stu-id="f4163-120">**Decide**</span></span>|<span data-ttu-id="f4163-121">Permite que su orquestación se ramifique de forma condicional.</span><span class="sxs-lookup"><span data-stu-id="f4163-121">Enables you to conditionally branch in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|<span data-ttu-id="f4163-122">**Retraso**</span><span class="sxs-lookup"><span data-stu-id="f4163-122">**Delay**</span></span>|<span data-ttu-id="f4163-123">Permite generar retrasos en la orquestación en función de un intervalo de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f4163-123">Enables you to build delays in your orchestration based on a time-out interval.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="f4163-124">**Expresión**</span><span class="sxs-lookup"><span data-stu-id="f4163-124">**Expression**</span></span>|<span data-ttu-id="f4163-125">Permite asignar valores a variables o realizar llamadas .NET.</span><span class="sxs-lookup"><span data-stu-id="f4163-125">Enables you to assign values to variables or make .NET calls.</span></span>|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|<span data-ttu-id="f4163-126">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="f4163-126">**Group**</span></span>|<span data-ttu-id="f4163-127">Permite agrupar operaciones en una unidad única que puede contraerse o expandirse para mayor facilidad visual.</span><span class="sxs-lookup"><span data-stu-id="f4163-127">Enables you to group operations into a single collapsible and expandable unit for visual convenience.</span></span>|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|<span data-ttu-id="f4163-128">**Escuchar**</span><span class="sxs-lookup"><span data-stu-id="f4163-128">**Listen**</span></span>|<span data-ttu-id="f4163-129">Permite que la orquestación se ramifique de forma condicional según los mensajes recibidos o el vencimiento de un período de espera.</span><span class="sxs-lookup"><span data-stu-id="f4163-129">Enables your orchestration to conditionally branch depending on messages received or the expiration of a timeout period.</span></span>|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|<span data-ttu-id="f4163-130">**Bucle**</span><span class="sxs-lookup"><span data-stu-id="f4163-130">**Loop**</span></span>|<span data-ttu-id="f4163-131">Permite que la orquestación se ejecute en bucle hasta que se cumpla una condición.</span><span class="sxs-lookup"><span data-stu-id="f4163-131">Enables your orchestration to loop until a condition is met.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="f4163-132">**Asignación de mensajes**</span><span class="sxs-lookup"><span data-stu-id="f4163-132">**Message Assignment**</span></span>|<span data-ttu-id="f4163-133">Permite asignar valores de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4163-133">Enables you to assign message values.</span></span>|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|<span data-ttu-id="f4163-134">**Acciones paralelas**</span><span class="sxs-lookup"><span data-stu-id="f4163-134">**Parallel Actions**</span></span>|<span data-ttu-id="f4163-135">Permite que la orquestación lleve a cabo dos o más operaciones independientemente del resto.</span><span class="sxs-lookup"><span data-stu-id="f4163-135">Enables your orchestration to perform two or more operations independently of each other.</span></span>|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|<span data-ttu-id="f4163-136">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="f4163-136">**Port**</span></span>|<span data-ttu-id="f4163-137">Define dónde y cómo se transmiten los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f4163-137">Defines where and how messages are transmitted.</span></span>|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|<span data-ttu-id="f4163-138">**Recepción**</span><span class="sxs-lookup"><span data-stu-id="f4163-138">**Receive**</span></span>|<span data-ttu-id="f4163-139">Permite que su orquestación reciba un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4163-139">Enables you to receive a message in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|<span data-ttu-id="f4163-140">**Vínculo de función**</span><span class="sxs-lookup"><span data-stu-id="f4163-140">**Role Link**</span></span>|<span data-ttu-id="f4163-141">Permite crear una colección de puertos que se comunican con el mismo socio comercial lógico, quizá mediante diferentes transportes o extremos.</span><span class="sxs-lookup"><span data-stu-id="f4163-141">Enables you to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints.</span></span>|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|<span data-ttu-id="f4163-142">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="f4163-142">**Scope**</span></span>|<span data-ttu-id="f4163-143">Proporciona un marco de trabajo para transacciones y control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="f4163-143">Provides a framework for transactions and exception handling.</span></span>|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|<span data-ttu-id="f4163-144">**Enviar**</span><span class="sxs-lookup"><span data-stu-id="f4163-144">**Send**</span></span>|<span data-ttu-id="f4163-145">Permite enviar un mensaje desde la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f4163-145">Enables you to send a message from your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|<span data-ttu-id="f4163-146">**Iniciar orquestación**</span><span class="sxs-lookup"><span data-stu-id="f4163-146">**Start Orchestration**</span></span>|<span data-ttu-id="f4163-147">Permite que su orquestación llame a otra orquestación de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f4163-147">Enables your orchestration to call another orchestration asynchronously.</span></span>|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|<span data-ttu-id="f4163-148">**Suspender**</span><span class="sxs-lookup"><span data-stu-id="f4163-148">**Suspend**</span></span>|<span data-ttu-id="f4163-149">Suspende la operación de la orquestación para permitir la intervención en caso de que se produzca alguna condición de error.</span><span class="sxs-lookup"><span data-stu-id="f4163-149">Suspends the operation of your orchestration to enable intervention in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|<span data-ttu-id="f4163-150">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="f4163-150">**Terminate**</span></span>|<span data-ttu-id="f4163-151">Permite finalizar inmediatamente la operación de la orquestación por si se produjera alguna condición de error.</span><span class="sxs-lookup"><span data-stu-id="f4163-151">Enables you to immediately end the operation of your orchestration in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|<span data-ttu-id="f4163-152">**Iniciar excepción**</span><span class="sxs-lookup"><span data-stu-id="f4163-152">**Throw Exception**</span></span>|<span data-ttu-id="f4163-153">Permite iniciar una excepción de forma explícita en caso de error.</span><span class="sxs-lookup"><span data-stu-id="f4163-153">Enables you to explicitly throw an exception in the event of an error.</span></span>|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|<span data-ttu-id="f4163-154">**Transformar**</span><span class="sxs-lookup"><span data-stu-id="f4163-154">**Transform**</span></span>|<span data-ttu-id="f4163-155">Permite asignar los campos de mensajes ya existentes a nuevos mensajes.</span><span class="sxs-lookup"><span data-stu-id="f4163-155">Enables you to map the fields from existing messages into new messages.</span></span>|
---
title: "Tarea 3: Configurar el envío y recepción formas2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="618a8-102">Tarea 3: Configurar el envío y recepción formas</span><span class="sxs-lookup"><span data-stu-id="618a8-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="618a8-103">Utilice este procedimiento para configurar las formas de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="618a8-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="618a8-104">Para configurar las formas de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="618a8-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="618a8-105">Arrastre las formas de envío y recepción del cuadro de herramientas al centro de la orquestación en el siguiente orden.</span><span class="sxs-lookup"><span data-stu-id="618a8-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="618a8-106">Establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="618a8-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="618a8-107">Forma</span><span class="sxs-lookup"><span data-stu-id="618a8-107">Shape</span></span>|<span data-ttu-id="618a8-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-108">Name</span></span>|<span data-ttu-id="618a8-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="618a8-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="618a8-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="618a8-110">Receive1</span></span>|<span data-ttu-id="618a8-111">Activate</span><span class="sxs-lookup"><span data-stu-id="618a8-111">Activate</span></span>|<span data-ttu-id="618a8-112">True</span><span class="sxs-lookup"><span data-stu-id="618a8-112">True</span></span>|  
    ||<span data-ttu-id="618a8-113">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-113">Message</span></span>|<span data-ttu-id="618a8-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="618a8-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-115">Name</span></span>|<span data-ttu-id="618a8-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="618a8-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="618a8-117">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-117">Operation</span></span>|<span data-ttu-id="618a8-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="618a8-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="618a8-119">Send1</span><span class="sxs-lookup"><span data-stu-id="618a8-119">Send1</span></span>|<span data-ttu-id="618a8-120">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-120">Message</span></span>|<span data-ttu-id="618a8-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="618a8-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-122">Name</span></span>|<span data-ttu-id="618a8-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="618a8-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="618a8-124">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-124">Operation</span></span>|<span data-ttu-id="618a8-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="618a8-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="618a8-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="618a8-126">Receive2</span></span>|<span data-ttu-id="618a8-127">Activate</span><span class="sxs-lookup"><span data-stu-id="618a8-127">Activate</span></span>|<span data-ttu-id="618a8-128">False</span><span class="sxs-lookup"><span data-stu-id="618a8-128">False</span></span>|  
    ||<span data-ttu-id="618a8-129">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-129">Message</span></span>|<span data-ttu-id="618a8-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="618a8-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-131">Name</span></span>|<span data-ttu-id="618a8-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="618a8-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="618a8-133">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-133">Operation</span></span>|<span data-ttu-id="618a8-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="618a8-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="618a8-135">Send2</span><span class="sxs-lookup"><span data-stu-id="618a8-135">Send2</span></span>|<span data-ttu-id="618a8-136">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-136">Message</span></span>|<span data-ttu-id="618a8-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="618a8-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-138">Name</span></span>|<span data-ttu-id="618a8-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="618a8-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="618a8-140">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-140">Operation</span></span>|<span data-ttu-id="618a8-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="618a8-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="618a8-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="618a8-142">Receive3</span></span>|<span data-ttu-id="618a8-143">Activate</span><span class="sxs-lookup"><span data-stu-id="618a8-143">Activate</span></span>|<span data-ttu-id="618a8-144">False</span><span class="sxs-lookup"><span data-stu-id="618a8-144">False</span></span>|  
    ||<span data-ttu-id="618a8-145">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-145">Message</span></span>|<span data-ttu-id="618a8-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="618a8-147">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-147">Name</span></span>|<span data-ttu-id="618a8-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="618a8-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="618a8-149">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-149">Operation</span></span>|<span data-ttu-id="618a8-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="618a8-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="618a8-151">Send3</span><span class="sxs-lookup"><span data-stu-id="618a8-151">Send3</span></span>|<span data-ttu-id="618a8-152">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-152">Message</span></span>|<span data-ttu-id="618a8-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="618a8-154">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-154">Name</span></span>|<span data-ttu-id="618a8-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="618a8-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="618a8-156">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-156">Operation</span></span>|<span data-ttu-id="618a8-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="618a8-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="618a8-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="618a8-158">Receive4</span></span>|<span data-ttu-id="618a8-159">Activate</span><span class="sxs-lookup"><span data-stu-id="618a8-159">Activate</span></span>|<span data-ttu-id="618a8-160">False</span><span class="sxs-lookup"><span data-stu-id="618a8-160">False</span></span>|  
    ||<span data-ttu-id="618a8-161">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-161">Message</span></span>|<span data-ttu-id="618a8-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="618a8-163">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-163">Name</span></span>|<span data-ttu-id="618a8-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="618a8-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="618a8-165">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-165">Operation</span></span>|<span data-ttu-id="618a8-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="618a8-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="618a8-167">Send4</span><span class="sxs-lookup"><span data-stu-id="618a8-167">Send4</span></span>|<span data-ttu-id="618a8-168">de mensaje</span><span class="sxs-lookup"><span data-stu-id="618a8-168">Message</span></span>|<span data-ttu-id="618a8-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="618a8-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="618a8-170">Nombre</span><span class="sxs-lookup"><span data-stu-id="618a8-170">Name</span></span>|<span data-ttu-id="618a8-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="618a8-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="618a8-172">Operación</span><span class="sxs-lookup"><span data-stu-id="618a8-172">Operation</span></span>|<span data-ttu-id="618a8-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="618a8-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="618a8-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="618a8-174">See Also</span></span>  
 <span data-ttu-id="618a8-175">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="618a8-175">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="618a8-176">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="618a8-176">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="618a8-177">[Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="618a8-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="618a8-178">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="618a8-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)
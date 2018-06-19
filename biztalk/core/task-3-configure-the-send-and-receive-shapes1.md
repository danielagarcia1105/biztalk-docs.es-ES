---
title: 'Tarea 3: Configurar el envío y recepción formas1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e258d22-755b-48a4-9f9e-e9398f6b68b1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c730cc6bc5cb11c27152613f331bda6b15be390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278820"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="a7135-102">Tarea 3: Configurar el envío y recepción formas</span><span class="sxs-lookup"><span data-stu-id="a7135-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="a7135-103">Utilice este procedimiento para configurar las formas de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="a7135-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="a7135-104">Para configurar las formas de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="a7135-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="a7135-105">Arrastre las formas de envío y recepción del cuadro de herramientas al centro de la orquestación en el siguiente orden.</span><span class="sxs-lookup"><span data-stu-id="a7135-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="a7135-106">Establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7135-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="a7135-107">Forma</span><span class="sxs-lookup"><span data-stu-id="a7135-107">Shape</span></span>|<span data-ttu-id="a7135-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-108">Name</span></span>|<span data-ttu-id="a7135-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="a7135-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="a7135-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="a7135-110">Receive1</span></span>|<span data-ttu-id="a7135-111">Activate</span><span class="sxs-lookup"><span data-stu-id="a7135-111">Activate</span></span>|<span data-ttu-id="a7135-112">True</span><span class="sxs-lookup"><span data-stu-id="a7135-112">True</span></span>|  
    ||<span data-ttu-id="a7135-113">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-113">Message</span></span>|<span data-ttu-id="a7135-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="a7135-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-115">Name</span></span>|<span data-ttu-id="a7135-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="a7135-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="a7135-117">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-117">Operation</span></span>|<span data-ttu-id="a7135-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="a7135-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="a7135-119">Send1</span><span class="sxs-lookup"><span data-stu-id="a7135-119">Send1</span></span>|<span data-ttu-id="a7135-120">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-120">Message</span></span>|<span data-ttu-id="a7135-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="a7135-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-122">Name</span></span>|<span data-ttu-id="a7135-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="a7135-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="a7135-124">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-124">Operation</span></span>|<span data-ttu-id="a7135-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="a7135-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="a7135-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="a7135-126">Receive2</span></span>|<span data-ttu-id="a7135-127">Activate</span><span class="sxs-lookup"><span data-stu-id="a7135-127">Activate</span></span>|<span data-ttu-id="a7135-128">False</span><span class="sxs-lookup"><span data-stu-id="a7135-128">False</span></span>|  
    ||<span data-ttu-id="a7135-129">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-129">Message</span></span>|<span data-ttu-id="a7135-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="a7135-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-131">Name</span></span>|<span data-ttu-id="a7135-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="a7135-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="a7135-133">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-133">Operation</span></span>|<span data-ttu-id="a7135-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="a7135-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="a7135-135">Send2</span><span class="sxs-lookup"><span data-stu-id="a7135-135">Send2</span></span>|<span data-ttu-id="a7135-136">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-136">Message</span></span>|<span data-ttu-id="a7135-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="a7135-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-138">Name</span></span>|<span data-ttu-id="a7135-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="a7135-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="a7135-140">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-140">Operation</span></span>|<span data-ttu-id="a7135-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="a7135-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="a7135-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="a7135-142">Receive3</span></span>|<span data-ttu-id="a7135-143">Activate</span><span class="sxs-lookup"><span data-stu-id="a7135-143">Activate</span></span>|<span data-ttu-id="a7135-144">False</span><span class="sxs-lookup"><span data-stu-id="a7135-144">False</span></span>|  
    ||<span data-ttu-id="a7135-145">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-145">Message</span></span>|<span data-ttu-id="a7135-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="a7135-147">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-147">Name</span></span>|<span data-ttu-id="a7135-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="a7135-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="a7135-149">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-149">Operation</span></span>|<span data-ttu-id="a7135-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="a7135-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="a7135-151">Send3</span><span class="sxs-lookup"><span data-stu-id="a7135-151">Send3</span></span>|<span data-ttu-id="a7135-152">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-152">Message</span></span>|<span data-ttu-id="a7135-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="a7135-154">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-154">Name</span></span>|<span data-ttu-id="a7135-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="a7135-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="a7135-156">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-156">Operation</span></span>|<span data-ttu-id="a7135-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="a7135-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="a7135-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="a7135-158">Receive4</span></span>|<span data-ttu-id="a7135-159">Activate</span><span class="sxs-lookup"><span data-stu-id="a7135-159">Activate</span></span>|<span data-ttu-id="a7135-160">False</span><span class="sxs-lookup"><span data-stu-id="a7135-160">False</span></span>|  
    ||<span data-ttu-id="a7135-161">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-161">Message</span></span>|<span data-ttu-id="a7135-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="a7135-163">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-163">Name</span></span>|<span data-ttu-id="a7135-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="a7135-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="a7135-165">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-165">Operation</span></span>|<span data-ttu-id="a7135-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="a7135-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="a7135-167">Send4</span><span class="sxs-lookup"><span data-stu-id="a7135-167">Send4</span></span>|<span data-ttu-id="a7135-168">de mensaje</span><span class="sxs-lookup"><span data-stu-id="a7135-168">Message</span></span>|<span data-ttu-id="a7135-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a7135-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="a7135-170">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7135-170">Name</span></span>|<span data-ttu-id="a7135-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="a7135-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="a7135-172">Operación</span><span class="sxs-lookup"><span data-stu-id="a7135-172">Operation</span></span>|<span data-ttu-id="a7135-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="a7135-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7135-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7135-174">See Also</span></span>  
 <span data-ttu-id="a7135-175">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="a7135-175">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="a7135-176">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="a7135-176">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="a7135-177">[Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="a7135-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="a7135-178">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="a7135-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)
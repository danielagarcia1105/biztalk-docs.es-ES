---
title: Getworkflowevent (operación) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246612"
---
# <a name="getworkflowevent"></a><span data-ttu-id="80cad-102">GetWorkflowEvent (operación)</span><span class="sxs-lookup"><span data-stu-id="80cad-102">GetWorkflowEvent</span></span>
<span data-ttu-id="80cad-103">Inserta el nombre del evento del flujo de trabajo en curso en la pila.</span><span class="sxs-lookup"><span data-stu-id="80cad-103">Pushes the name of the current workflow event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80cad-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80cad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80cad-105">Parameters</span></span>  
 <span data-ttu-id="80cad-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80cad-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="80cad-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="80cad-107">Pushed Value</span></span>  
 <span data-ttu-id="80cad-108">Cadena que contiene el evento del flujo de trabajo en curso.</span><span class="sxs-lookup"><span data-stu-id="80cad-108">String containing the current workflow event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80cad-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80cad-109">Remarks</span></span>  
 <span data-ttu-id="80cad-110">Una instancia de flujo de trabajo puede pasar por varios estados durante el transcurso de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="80cad-110">A workflow instance can pass through several states during the course of its execution.</span></span> <span data-ttu-id="80cad-111">Por ejemplo, una instancia de flujo de trabajo puede estar inactiva o suspendida.</span><span class="sxs-lookup"><span data-stu-id="80cad-111">For example, a workflow instance may become idle, or it may be suspended.</span></span> <span data-ttu-id="80cad-112">Cada vez que la instancia de flujo de trabajo cambia de estado, emite un evento de estado de flujo de trabajo a la infraestructura de seguimiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80cad-112">Every time the workflow instance changes state, it emits a workflow status event to the runtime tracking infrastructure.</span></span> <span data-ttu-id="80cad-113">El interceptor de BAM de Windows Workflow Foundation es compatible con la mayoría de los eventos definidos por la enumeración de `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="80cad-113">The Windows Workflow Foundation BAM interceptor supports most of the events defined by the `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="80cad-114">Evento de actividad</span><span class="sxs-lookup"><span data-stu-id="80cad-114">Activity event</span></span>|<span data-ttu-id="80cad-115">Description</span><span class="sxs-lookup"><span data-stu-id="80cad-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="80cad-116">Cambiado</span><span class="sxs-lookup"><span data-stu-id="80cad-116">Changed</span></span>|<span data-ttu-id="80cad-117">Se ha producido un cambio de flujo de trabajo en la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cad-117">A workflow change has occurred on the workflow instance.</span></span>|  
|<span data-ttu-id="80cad-118">Completado</span><span class="sxs-lookup"><span data-stu-id="80cad-118">Completed</span></span>|<span data-ttu-id="80cad-119">La instancia de flujo de trabajo ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="80cad-119">The workflow instance has completed.</span></span>|  
|<span data-ttu-id="80cad-120">Creado</span><span class="sxs-lookup"><span data-stu-id="80cad-120">Created</span></span>|<span data-ttu-id="80cad-121">La instancia de flujo de trabajo se ha creado.</span><span class="sxs-lookup"><span data-stu-id="80cad-121">The workflow instance has been created.</span></span>|  
|<span data-ttu-id="80cad-122">Excepción</span><span class="sxs-lookup"><span data-stu-id="80cad-122">Exception</span></span>|<span data-ttu-id="80cad-123">Se ha producido un error no controlado.</span><span class="sxs-lookup"><span data-stu-id="80cad-123">An unhandled exception has occurred.</span></span>|  
|<span data-ttu-id="80cad-124">Idle</span><span class="sxs-lookup"><span data-stu-id="80cad-124">Idle</span></span>|<span data-ttu-id="80cad-125">La instancia del flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="80cad-125">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="80cad-126">Cargado</span><span class="sxs-lookup"><span data-stu-id="80cad-126">Loaded</span></span>|<span data-ttu-id="80cad-127">La instancia de flujo de trabajo se ha cargado en memoria.</span><span class="sxs-lookup"><span data-stu-id="80cad-127">The workflow instance has been loaded into memory.</span></span>|  
|<span data-ttu-id="80cad-128">Guardado</span><span class="sxs-lookup"><span data-stu-id="80cad-128">Persisted</span></span>|<span data-ttu-id="80cad-129">La instancia de flujo de trabajo se ha guardado.</span><span class="sxs-lookup"><span data-stu-id="80cad-129">The workflow instance has been persisted.</span></span>|  
|<span data-ttu-id="80cad-130">Reanudado</span><span class="sxs-lookup"><span data-stu-id="80cad-130">Resumed</span></span>|<span data-ttu-id="80cad-131">Se ha reanudado la ejecución de una instancia que se había detenido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="80cad-131">A previously suspended workflow instance has resumed running.</span></span>|  
|<span data-ttu-id="80cad-132">Iniciado</span><span class="sxs-lookup"><span data-stu-id="80cad-132">Started</span></span>|<span data-ttu-id="80cad-133">La instancia de flujo de trabajo se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="80cad-133">The workflow instance has been started.</span></span>|  
|<span data-ttu-id="80cad-134">Suspendida</span><span class="sxs-lookup"><span data-stu-id="80cad-134">Suspended</span></span>|<span data-ttu-id="80cad-135">La instancia de flujo de trabajo se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="80cad-135">The workflow instance has been suspended.</span></span>|  
|<span data-ttu-id="80cad-136">Finalizado</span><span class="sxs-lookup"><span data-stu-id="80cad-136">Terminated</span></span>|<span data-ttu-id="80cad-137">La instancia de flujo de trabajo se ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="80cad-137">The workflow instance has been terminated.</span></span>|  
|<span data-ttu-id="80cad-138">Descargado</span><span class="sxs-lookup"><span data-stu-id="80cad-138">Unloaded</span></span>|<span data-ttu-id="80cad-139">La instancia de flujo de trabajo se ha descargado desde memoria.</span><span class="sxs-lookup"><span data-stu-id="80cad-139">The workflow instance has been unloaded from memory.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="80cad-140">No puede usar `GetWorkflowEvent` ni `GetActivityEvent` en el mismo elemento OnEvent.</span><span class="sxs-lookup"><span data-stu-id="80cad-140">You cannot use both `GetWorkflowEvent` and `GetActivityEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80cad-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80cad-141">Example</span></span>  
 <span data-ttu-id="80cad-142">El siguiente ejemplo contiene un filtro configurado para buscar una actividad específica ("FoodAndDrinksPolicy") en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cad-142">The following sample contains a filter that is configured to find a specific activity—"FoodAndDrinksPolicy"—in a workflow.</span></span> <span data-ttu-id="80cad-143">En el ejemplo, se configura un filtro para buscar la actividad denominada "FoodAndDrinksPolicy" en un flujo de trabajo cerrado.</span><span class="sxs-lookup"><span data-stu-id="80cad-143">In the sample, a filter is configured to find the activity named "FoodAndDrinksPolicy" in a closed workflow.</span></span> <span data-ttu-id="80cad-144">Esto se realiza mediante la comparación del valor devuelto por `GetWorkflowEvent` al valor constante "Creado".</span><span class="sxs-lookup"><span data-stu-id="80cad-144">This is done by comparing the value returned by `GetWorkflowEvent` to the constant "Created".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />   
      <ic:Operation Name="Constant">  
        <ic:Argument>Created</ic:Argument>   
      </ic:Operation>  
    <ic:Operation Name="Equals" />   
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="80cad-145">Esta operación es útil para el seguimiento del período de vida de un flujo de trabajo y para la detección de excepciones o de otros problemas con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cad-145">This operation is useful for tracking the lifetime of a workflow and for detecting exceptions or other problems with the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cad-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="80cad-146">See Also</span></span>  
 [<span data-ttu-id="80cad-147">Enumeración System.Workflow.Runtime.Tracking.TrackingWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="80cad-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119568)
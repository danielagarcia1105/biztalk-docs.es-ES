---
title: Patrones de filtro de eventos comunes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef90a4533b8b12929488d3a323dae47976eace0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="common-event-filter-patterns"></a><span data-ttu-id="354a1-102">Patrones de filtro de evento comunes</span><span class="sxs-lookup"><span data-stu-id="354a1-102">Common Event Filter Patterns</span></span>
<span data-ttu-id="354a1-103">A medida que trabaje con el interceptor de BAM para Windows Workflow Foundation (WF), es probable que observe que hay un conjunto de patrones de filtro comunes que utilizará con frecuencia en los archivos de configuración del interceptor.</span><span class="sxs-lookup"><span data-stu-id="354a1-103">As you work with the BAM Interceptor for Windows Workflow Foundation (WF), you will likely notice that there are a set of common filter patterns that you will use frequently in your interceptor configuration files.</span></span> <span data-ttu-id="354a1-104">Aunque algunos de estos patrones de filtro serán exclusivos para sus aplicaciones y entornos, hay muchos patrones que se pueden usar en distintos entornos y en varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="354a1-104">While some of these filter patterns will be unique to your applications and environments, many patterns can be used across environments and in diverse applications.</span></span>  
  
 <span data-ttu-id="354a1-105">En este tema se recogen muchos de los patrones de filtro comunes que usan los archivos de configuración del interceptor escritos para aplicaciones WF.</span><span class="sxs-lookup"><span data-stu-id="354a1-105">This topic collects many of the common filter patterns used by interceptor configuration files written for WF applications.</span></span> <span data-ttu-id="354a1-106">Los patrones se agrupan según el evento de seguimiento de Windows Workflow Foundation:</span><span class="sxs-lookup"><span data-stu-id="354a1-106">Patterns are grouped by Windows Workflow Foundation tracking event:</span></span>  
  
-   <span data-ttu-id="354a1-107">Eventos de estado de actividad</span><span class="sxs-lookup"><span data-stu-id="354a1-107">Activity status events</span></span>  
  
-   <span data-ttu-id="354a1-108">Eventos de estado de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="354a1-108">Workflow status events</span></span>  
  
-   <span data-ttu-id="354a1-109">Eventos de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-109">User events</span></span>  
  
 <span data-ttu-id="354a1-110">Todos los patrones se pueden copiar en el archivo de configuración de interceptor y se pueden modificar para adaptarlos a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="354a1-110">Each pattern can be copied into your interceptor configuration file and modified to suit your application.</span></span>  
  
## <a name="activity-status-event-filter-patterns"></a><span data-ttu-id="354a1-111">Patrones de filtro de evento de estado de actividad</span><span class="sxs-lookup"><span data-stu-id="354a1-111">Activity Status Event Filter Patterns</span></span>  
 <span data-ttu-id="354a1-112">Las actividades constituyen los bloques de creación de flujos de trabajo fundamentales.</span><span class="sxs-lookup"><span data-stu-id="354a1-112">Activities are the fundamental building blocks of workflows.</span></span> <span data-ttu-id="354a1-113">Un flujo de trabajo consiste en un conjunto de actividades organizadas de forma jerárquica en una estructura de árbol.</span><span class="sxs-lookup"><span data-stu-id="354a1-113">A workflow is a set of activities that are organized hierarchically in a tree structure.</span></span> <span data-ttu-id="354a1-114">Una actividad representa una acción en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="354a1-114">An activity represents an action in a workflow.</span></span> <span data-ttu-id="354a1-115">Puede ser una acción sencilla como un retraso o una compuesta con varias actividades secundarias.</span><span class="sxs-lookup"><span data-stu-id="354a1-115">It can be a simple action such as a delay, or it can be a composite activity that consists of several child activities.</span></span>  
  
 <span data-ttu-id="354a1-116">Los filtros que se indican en esta sección filtran actividades y utilizan una o varias de las siguientes operaciones personalizadas del interceptor de BAM para WF:</span><span class="sxs-lookup"><span data-stu-id="354a1-116">The filters in this section filter activities and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="354a1-117">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="354a1-117">GetActivityName</span></span>  
  
-   <span data-ttu-id="354a1-118">GetActivityEvent (operación)</span><span class="sxs-lookup"><span data-stu-id="354a1-118">GetActivityEvent</span></span>  
  
-   <span data-ttu-id="354a1-119">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="354a1-119">GetActivityType</span></span>  
  
-   <span data-ttu-id="354a1-120">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-120">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="354a1-121">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-121">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="354a1-122">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-122">GetContextProperty</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="354a1-123">Si no se usa la operación GetActivityEvent en el filtro, éste buscará sólo eventos de actividad cerrados.</span><span class="sxs-lookup"><span data-stu-id="354a1-123">If you do not use the GetActivityEvent operation in your filter, your filter will look for Closed activity events only.</span></span>  
  
### <a name="filter-by-activity-name-closed-activity"></a><span data-ttu-id="354a1-124">Filtrar por nombre de actividad (actividad cerrada)</span><span class="sxs-lookup"><span data-stu-id="354a1-124">Filter by Activity Name (Closed Activity)</span></span>  
 <span data-ttu-id="354a1-125">Con frecuencia tendrá que filtrar los eventos de actividades cerradas por nombre de actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-125">You will frequently need to filter for closed activity events by activity name.</span></span> <span data-ttu-id="354a1-126">Esto resulta útil cuando es necesario capturar datos de una actividad específica como recibir un archivo o escribir datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="354a1-126">This is useful when you need to capture data from a specific activity such as receiving a file or writing data to a database.</span></span>  
  
 <span data-ttu-id="354a1-127">El siguiente fragmento filtra una actividad cerrada denominada "MyActivity".</span><span class="sxs-lookup"><span data-stu-id="354a1-127">The fragment below filters for a closed activity named "MyActivity".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a><span data-ttu-id="354a1-128">Filtrar por tipo de actividad (evento de actividad cerrada)</span><span class="sxs-lookup"><span data-stu-id="354a1-128">Filter by Activity Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="354a1-129">Habrá ocasiones en las que deseará filtrar una actividad por tipo en lugar de por nombre.</span><span class="sxs-lookup"><span data-stu-id="354a1-129">There will be times when you want to filter an activity by type rather than name.</span></span> <span data-ttu-id="354a1-130">Por ejemplo, es posible que desee guardar el nombre de la actividad y una marca de fecha y hora de todas las actividades en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="354a1-130">For example, you may want to save activity name and a date/time stamp for all activities in a workflow.</span></span> <span data-ttu-id="354a1-131">Para ello, use la `GetActivityType` operación.</span><span class="sxs-lookup"><span data-stu-id="354a1-131">To accomplish this, you use the `GetActivityType` operation.</span></span> <span data-ttu-id="354a1-132">`GetActivityType`Compara el tipo facilitado con el tipo base y todos los tipos derivados para determinar a su coincidencia.</span><span class="sxs-lookup"><span data-stu-id="354a1-132">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="354a1-133">La comparación con `System.Workflow.ComponentModel.Activity` coincidirá, ya que todas las actividades del flujo de trabajo deben derivarse de ella.</span><span class="sxs-lookup"><span data-stu-id="354a1-133">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a><span data-ttu-id="354a1-134">Filtrar por evento de actividad (cualquier tipo de actividad)</span><span class="sxs-lookup"><span data-stu-id="354a1-134">Filter by Activity Event (Any Activity Type)</span></span>  
 <span data-ttu-id="354a1-135">Este filtro usa la operación GetActivityEvent para encontrar actividades cerradas.</span><span class="sxs-lookup"><span data-stu-id="354a1-135">This filter uses the GetActivityEvent operation to find closed activities.</span></span> <span data-ttu-id="354a1-136">Resulta útil para capturar información acerca de todos los eventos cerrados (frente a un evento específico por nombre o tipo).</span><span class="sxs-lookup"><span data-stu-id="354a1-136">It is useful for capturing information about all closed events (versus a specific event by name or type).</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a><span data-ttu-id="354a1-137">Filtrar por nombre y tipo de actividad (evento de actividad cerrada)</span><span class="sxs-lookup"><span data-stu-id="354a1-137">Filter by Activity Name and Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="354a1-138">Puede elegir que las actividades se filtren por nombre y tipo de actividad si desea especificar el tipo exacto de la actividad (incluida la arquitectura del procesador) que le interesa encontrar.</span><span class="sxs-lookup"><span data-stu-id="354a1-138">You may choose to filter activities by activity name and activity type if you want to specify the exact type of activity (including processor architecture) that you are interested in finding.</span></span> <span data-ttu-id="354a1-139">En el siguiente ejemplo se busca "MyActivity" que deriva de `System.Workflow.ComponentModel.Activity`; puede cambiar esto a un tipo derivado para hacerlo más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="354a1-139">The sample below looks for "MyActivity" deriving from `System.Workflow.ComponentModel.Activity`; you can change this to a derived type to make it more restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a><span data-ttu-id="354a1-140">Filtrar por nombre y evento de actividad (cualquier tipo de actividad)</span><span class="sxs-lookup"><span data-stu-id="354a1-140">Filter by Activity Name and Event (Any Activity Type)</span></span>  
 <span data-ttu-id="354a1-141">Esta expresión filtra según el nombre y el evento de actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-141">This expression filters based on activity name and activity event.</span></span> <span data-ttu-id="354a1-142">Esto resulta útil si se desea capturar información para una actividad y evento específicos o cuando se capturan datos desde varios eventos de actividad para una actividad determinada.</span><span class="sxs-lookup"><span data-stu-id="354a1-142">This is useful when you want to capture information for a specific activity and event or when capturing data from more than one activity event for a given activity.</span></span> <span data-ttu-id="354a1-143">Por ejemplo, es posible que desee dos elementos OnEvent diferentes, uno para MyActivity cuando se está ejecutando y uno para cuando está cerrado, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="354a1-143">For example, you may want two different OnEvent elements, one for MyActivity when it is Executing and one for when it is Closed as shown below.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a><span data-ttu-id="354a1-144">Filtrar por tipo y evento de actividad</span><span class="sxs-lookup"><span data-stu-id="354a1-144">Filter by Activity Type and Event</span></span>  
 <span data-ttu-id="354a1-145">Este filtro resulta útil para capturar información acerca de todas las actividades que derivan de un tipo específico durante un único evento de actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-145">This filter is useful for capturing information about all activities that derive from a specific type during a single activity event.</span></span> <span data-ttu-id="354a1-146">Por ejemplo, es posible que esté interesado en realizar el seguimiento de un Id. de pedido y una marca de fecha y hora de un pedido a medida que pasa por un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="354a1-146">For example, you may be interested in tracking a purchase order ID and date/time stamp from a purchase order as it flows through a workflow.</span></span> <span data-ttu-id="354a1-147">Para ello, use la `GetActivityEvent` y `GetActivityType` operaciones.</span><span class="sxs-lookup"><span data-stu-id="354a1-147">To accomplish this, you use the `GetActivityEvent` and the `GetActivityType` operations.</span></span> <span data-ttu-id="354a1-148">`GetActivityType`Compara el tipo facilitado con el tipo base y todos los tipos derivados para determinar a su coincidencia.</span><span class="sxs-lookup"><span data-stu-id="354a1-148">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="354a1-149">La comparación con `System.Workflow.ComponentModel.Activity` coincidirá, ya que todas las actividades del flujo de trabajo deben derivarse de ella.</span><span class="sxs-lookup"><span data-stu-id="354a1-149">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a><span data-ttu-id="354a1-150">Filtrar por nombre, tipo y evento de actividad</span><span class="sxs-lookup"><span data-stu-id="354a1-150">Filter by Activity Name, Type, and Event</span></span>  
 <span data-ttu-id="354a1-151">El filtrado de una actividad por nombre, tipo y evento puede resultar útil cuando desea que califique mejor la actividad cuyo seguimiento le interesa.</span><span class="sxs-lookup"><span data-stu-id="354a1-151">Filtering an activity by name, type and event can be useful when you want to better qualify the activity you are interested in tracking.</span></span> <span data-ttu-id="354a1-152">Por ejemplo, el siguiente filtro busca la actividad cerrada "MyActivity" que tiene un tipo igual a o que deriva de `System.Workflow.ComponentModel.Activity`.</span><span class="sxs-lookup"><span data-stu-id="354a1-152">For example, the filter below looks for the closed activity "MyActivity" that has a type that is equal to or derives from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a><span data-ttu-id="354a1-153">Patrones de filtro de evento de estado de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="354a1-153">Workflow Status Event Filter Patterns</span></span>  
 <span data-ttu-id="354a1-154">Los filtros que se indican en esta sección filtran eventos de flujo de trabajo y utilizan una o varias de las siguientes operaciones personalizadas del interceptor de BAM para WF:</span><span class="sxs-lookup"><span data-stu-id="354a1-154">The filters in this section filter workflow events and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="354a1-155">GetWorkflowEvent (operación)</span><span class="sxs-lookup"><span data-stu-id="354a1-155">GetWorkflowEvent</span></span>  
  
-   <span data-ttu-id="354a1-156">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-156">GetContextProperty</span></span>  
  
### <a name="filter-by-workflow-event"></a><span data-ttu-id="354a1-157">Filtrar por evento de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="354a1-157">Filter by Workflow Event</span></span>  
 <span data-ttu-id="354a1-158">Esta expresión filtra por evento de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="354a1-158">This expression filters by workflow event.</span></span>  
  
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
  
## <a name="user-event-filter-patterns"></a><span data-ttu-id="354a1-159">Patrones de filtro de evento de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-159">User Event Filter Patterns</span></span>  
 <span data-ttu-id="354a1-160">Si la aplicación realiza el seguimiento de información personalizada con el método TrackData, puede filtrar según las características de los datos mediante una o varias operaciones de datos de usuario personalizados del interceptor de BAM para WF que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="354a1-160">If your application tracks custom information using the TrackData method, you can filter based on the characteristics of the data using one or more of the following BAM Interceptor for WF custom user data operations:</span></span>  
  
-   <span data-ttu-id="354a1-161">GetUserDataType (operación)</span><span class="sxs-lookup"><span data-stu-id="354a1-161">GetUserDataType</span></span>  
  
-   <span data-ttu-id="354a1-162">GetUserKey (operación)</span><span class="sxs-lookup"><span data-stu-id="354a1-162">GetUserKey</span></span>  
  
-   <span data-ttu-id="354a1-163">GetUserData (operación)</span><span class="sxs-lookup"><span data-stu-id="354a1-163">GetUserData</span></span>  
  
 <span data-ttu-id="354a1-164">El filtro puede combinar estas operaciones con las siguientes para crear una expresión más compleja:</span><span class="sxs-lookup"><span data-stu-id="354a1-164">The filter can combine these operations with the following to create a more complex expression:</span></span>  
  
-   <span data-ttu-id="354a1-165">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="354a1-165">GetActivityName</span></span>  
  
-   <span data-ttu-id="354a1-166">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="354a1-166">GetActivityType</span></span>  
  
-   <span data-ttu-id="354a1-167">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-167">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="354a1-168">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-168">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="354a1-169">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="354a1-169">GetContextProperty</span></span>  
  
 <span data-ttu-id="354a1-170">Si el filtro no incluye al menos una operación de datos de usuario, el filtro no será un filtro de evento de usuario y el OnEvent envolvente producirá un error (si una operación de usuario aparece en una expresión de actualización correspondiente) o se identificará como un punto de seguimiento de actividad y no de usuario.</span><span class="sxs-lookup"><span data-stu-id="354a1-170">If your filter does not include at least one user data operation, your filter will not be a user event filter and the enclosing OnEvent will cause an error (if a user operation appears in a corresponding update expression) or will be identified as an activity track point and not a user track point.</span></span>  
  
### <a name="filter-by-activity-name-and-user-data-type"></a><span data-ttu-id="354a1-171">Filtrar por nombre de actividad y tipo de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-171">Filter by Activity Name and User Data Type</span></span>  
 <span data-ttu-id="354a1-172">Con frecuencia, puede identificar un evento por nombre de actividad y tipo de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="354a1-172">Frequently you can identify an event by activity name and user data type.</span></span> <span data-ttu-id="354a1-173">La siguiente expresión filtra una actividad denominada "MyActivity" y un tipo de datos de usuario que deriva de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="354a1-173">The following expression filters for an activity named "MyActivity" and a user data type that derives from `System.Object`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a><span data-ttu-id="354a1-174">Filtrar por tipo de actividad y tipo de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-174">Filter by Activity Type and User Data Type</span></span>  
 <span data-ttu-id="354a1-175">Puede filtrar según el tipo de actividad y el tipo de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="354a1-175">You can filter based on activity type and user data type.</span></span> <span data-ttu-id="354a1-176">De este modo se consigue flexibilidad a la hora de filtrar eventos según el tipo del que derivan porque `GetActivityType` y `GetUserDataType` se comparan con el tipo especificado y todos los tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="354a1-176">This grants you the latitude to filter events based on the type the derive from because both `GetActivityType` and `GetUserDataType` compare against the type specified and all derived types.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a><span data-ttu-id="354a1-177">Filtrar por nombre de actividad, tipo de actividad y tipo de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-177">Filter by Activity Name, Activity Type, and User Data Type</span></span>  
 <span data-ttu-id="354a1-178">Este filtro restringe aún más el patrón de filtro de tipo de actividad y de tipo de datos de usuario al incluir el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-178">This filter further restricts the activity type and user data type filter pattern by including activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a><span data-ttu-id="354a1-179">Filtrar por nombre de actividad y clave del usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-179">Filter by Activity Name and User Key</span></span>  
 <span data-ttu-id="354a1-180">Si la aplicación tiene una actividad que llama a `TrackData` con una clave determinada en el tiempo de ejecución, es posible que desee filtrar por nombre de actividad y clave de usuario.</span><span class="sxs-lookup"><span data-stu-id="354a1-180">If your application has an activity that calls `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="354a1-181">Esto le habilitará para desencadenar un `OnEvent` basado en un valor de clave específico.</span><span class="sxs-lookup"><span data-stu-id="354a1-181">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="354a1-182">Por ejemplo, la aplicación podría definir varias claves y seleccionar una, de forma dinámica, en la actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-182">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="354a1-183">La siguiente expresión filtra "MyActivity" que contiene una clave de usuario denominada "ItemKey".</span><span class="sxs-lookup"><span data-stu-id="354a1-183">The expression below filters for "MyActivity" containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a><span data-ttu-id="354a1-184">Filtrar por tipo de actividad y clave de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-184">Filter by Activity Type and User Key</span></span>  
 <span data-ttu-id="354a1-185">Si la aplicación contiene varias actividades que llaman a `TrackData` con una clave determinada en el tiempo de ejecución, es posible que desee filtrar por nombre de actividad y clave de usuario.</span><span class="sxs-lookup"><span data-stu-id="354a1-185">If your application contain multiple activities that call `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="354a1-186">Esto le habilitará para desencadenar un `OnEvent` basado en un valor de clave específico.</span><span class="sxs-lookup"><span data-stu-id="354a1-186">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="354a1-187">Por ejemplo, la aplicación podría definir varias claves y seleccionar una, de forma dinámica, en la actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-187">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="354a1-188">La siguiente expresión filtra cualquier actividad que derive de `System.Workflow.ComponentModel.Activity` y que contenga una clave de usuario denominada "ItemKey".</span><span class="sxs-lookup"><span data-stu-id="354a1-188">The expression below filters for any activity deriving from `System.Workflow.ComponentModel.Activity` containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a><span data-ttu-id="354a1-189">Filtrar por nombre de actividad, tipo de actividad y clave de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-189">Filter by Activity Name, Activity Type, and User Key</span></span>  
 <span data-ttu-id="354a1-190">Este patrón de filtro refine aún más el patrón de filtro de tipo de actividad y de clave de usuario al incluir el nombre de la actividad en el filtro.</span><span class="sxs-lookup"><span data-stu-id="354a1-190">This filter pattern further refines the activity type and user key filter pattern by including the activity name in the filter.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a><span data-ttu-id="354a1-191">Filtrar por nombre de actividad, tipo de datos de usuario y clave de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-191">Filter by Activity Name, User Data Type, and User Key</span></span>  
 <span data-ttu-id="354a1-192">Este filtro resulta útil cuando se desea restringir el filtro a una actividad con un nombre y una clave de usuario específica y que derive de un tipo de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="354a1-192">This filter is useful when you want to restrict your filter to a named activity with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="354a1-193">Por ejemplo, la actividad puede llamar a TrackData mediante la clave "Item" y un valor de datos de cadena o entero según el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="354a1-193">For example, your activity may call TrackData using the key "Item" and a data value of string or integer depending upon the item type.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="354a1-194">Filtrar por tipo de actividad, tipo de datos de usuario y clave de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-194">Filter by Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="354a1-195">Este filtro resulta útil cuando se desea restringir el filtro a un tipo de actividad con una clave de usuario específica y que derive de un tipo de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="354a1-195">This filter is useful when you want to restrict your filter to an activity type with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="354a1-196">Puede ser más o menos restrictivo que el filtro que usa el nombre de actividad, el tipo de datos de usuario y la clave de usuario basados en el tipo usado.</span><span class="sxs-lookup"><span data-stu-id="354a1-196">It can be more restrictive or less restrictive than using activity name, user data type, and user key based on the type used.</span></span> <span data-ttu-id="354a1-197">Si especifica el tipo más derivado, podría ser más restrictivo; en cambio, si especifica el tipo de base raíz, podría ser menos restrictivo.</span><span class="sxs-lookup"><span data-stu-id="354a1-197">If you specify the most-derived type, it could be more restrictive; if you specify the root base type, it could be less restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="354a1-198">Filtrar por nombre de actividad, tipo de actividad, tipo de datos de usuario y clave de usuario</span><span class="sxs-lookup"><span data-stu-id="354a1-198">Filter by Activity Name, Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="354a1-199">Este filtro restringe aún más el patrón de tipo de actividad, tipo de datos de usuario y clave de usuario al agregar el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="354a1-199">This filter further restricts the activity type, user data type, and user key pattern by the addition of activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```
---
title: Elemento OnEvent del interceptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d684ac8e-61bc-410b-97a2-6fd3549e0d97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fb70b2536dbf5db5b0abc03bc194de154b4317
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257612"
---
# <a name="interceptor-onevent-element"></a><span data-ttu-id="07f8c-102">Elemento OnEvent del interceptor</span><span class="sxs-lookup"><span data-stu-id="07f8c-102">Interceptor OnEvent Element</span></span>
<span data-ttu-id="07f8c-103">El **OnEvent** elemento describe un evento real que está asignado a la actividad de BAM envolvente.</span><span class="sxs-lookup"><span data-stu-id="07f8c-103">The **OnEvent** element describes one real event that is mapped to the enclosing BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="07f8c-104">Formato</span><span class="sxs-lookup"><span data-stu-id="07f8c-104">Format</span></span>  
 <span data-ttu-id="07f8c-105">El elemento `OnEvent` contiene elementos secundarios que especifican un filtro de eventos, el Id. de correlación y, opcionalmente, los datos que se van a actualizar, los datos de referencia y un token de continuación.</span><span class="sxs-lookup"><span data-stu-id="07f8c-105">The `OnEvent` element contains child elements that specify an event filter, the correlation ID and optionally which data to update, reference data, and a continuation token.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07f8c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="07f8c-106">Attributes</span></span>  
  
|<span data-ttu-id="07f8c-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="07f8c-107">Attribute name</span></span>|<span data-ttu-id="07f8c-108">Description</span><span class="sxs-lookup"><span data-stu-id="07f8c-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="07f8c-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="07f8c-109">Name</span></span>|<span data-ttu-id="07f8c-110">Nombre de este evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="07f8c-110">User-defined name for this event.</span></span>|  
|<span data-ttu-id="07f8c-111">Source</span><span class="sxs-lookup"><span data-stu-id="07f8c-111">Source</span></span>|<span data-ttu-id="07f8c-112">Nombre del evento de origen tal como aparece en un **EventSource** elemento.</span><span class="sxs-lookup"><span data-stu-id="07f8c-112">Name of the event source as it appears in an **EventSource** element.</span></span>|  
|<span data-ttu-id="07f8c-113">IsBegin</span><span class="sxs-lookup"><span data-stu-id="07f8c-113">IsBegin</span></span>|<span data-ttu-id="07f8c-114">Valor booleano que indica si el evento es el comienzo de una nueva actividad de BAM (`true`) o no (`false`).</span><span class="sxs-lookup"><span data-stu-id="07f8c-114">Boolean value indicating whether the event is the beginning of a new BAM activity (`true`) or not (`false`).</span></span>|  
|<span data-ttu-id="07f8c-115">IsEnd</span><span class="sxs-lookup"><span data-stu-id="07f8c-115">IsEnd</span></span>|<span data-ttu-id="07f8c-116">Valor booleano que indica si el evento es el final de una nueva actividad de BAM (`true`) o no (`false`).</span><span class="sxs-lookup"><span data-stu-id="07f8c-116">Boolean value indicating whether the event is the end of a BAM activity (`true`) or not (`false`).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07f8c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07f8c-117">Child Elements</span></span>  
  
|<span data-ttu-id="07f8c-118">Estado de ejecución</span><span class="sxs-lookup"><span data-stu-id="07f8c-118">Execution status</span></span>|<span data-ttu-id="07f8c-119">Description</span><span class="sxs-lookup"><span data-stu-id="07f8c-119">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="07f8c-120">Filtro</span><span class="sxs-lookup"><span data-stu-id="07f8c-120">Filter</span></span>|<span data-ttu-id="07f8c-121">Proporciona una forma de limitar el evento de acuerdo con unos criterios específicos.</span><span class="sxs-lookup"><span data-stu-id="07f8c-121">Provides a way to limit the event to specific criteria.</span></span>|  
|<span data-ttu-id="07f8c-122">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="07f8c-122">CorrelationID</span></span>|<span data-ttu-id="07f8c-123">Especifica el Id. de correlación (el Id. de instancia de actividad).</span><span class="sxs-lookup"><span data-stu-id="07f8c-123">Specifies the correlation ID (the activity instance ID).</span></span>|  
|<span data-ttu-id="07f8c-124">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="07f8c-124">ContinuationToken</span></span>|<span data-ttu-id="07f8c-125">Especifica el token de continuación, un Id. de correlación que utilizarán eventos futuros que contribuirán a la misma instancia de actividad.</span><span class="sxs-lookup"><span data-stu-id="07f8c-125">Specifies the continuation token, a correlation ID that is used by future events that will contribute to the same activity instance.</span></span>|  
|<span data-ttu-id="07f8c-126">Update</span><span class="sxs-lookup"><span data-stu-id="07f8c-126">Update</span></span>|<span data-ttu-id="07f8c-127">Especifica los datos que se van a extraer del evento y que se van a importar a la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="07f8c-127">Specifies the data to extract from the event and import into the BAM activity.</span></span>|  
|<span data-ttu-id="07f8c-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="07f8c-128">Reference</span></span>|<span data-ttu-id="07f8c-129">Agrega una relación a una actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="07f8c-129">Adds a relationship to a BAM activity.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07f8c-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07f8c-130">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="07f8c-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07f8c-131">Example</span></span>  
 <span data-ttu-id="07f8c-132">En el ejemplo siguiente se muestra una típica **OnEvent** bloque para WF:</span><span class="sxs-lookup"><span data-stu-id="07f8c-132">The following example shows a typical **OnEvent** block for WF:</span></span>  
  
```  
<ic:OnEvent Name="BeginAct" IsBegin="true" Source="ResWF">  
  <ic:Filter>  
    <ic:Expression>  
      <wf:Operation Name="GetActivityName"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <wf:Operation Name="GetActivityEvent"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Closed</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <ic:Operation Name="And"/>  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>InstanceId</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>EventTime</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  <ic:Update DataItemName="FoodItem" Type="NVARCHAR">  
    <ic:Expression>  
      <wf:Operation Name="GetWorkflowProperty">  
        <wf:Argument>foodItem</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
 <span data-ttu-id="07f8c-133">Este ejemplo muestra el típico **OnEvent** bloque para el servicio WCF:</span><span class="sxs-lookup"><span data-stu-id="07f8c-133">This example shows a typical **OnEvent** block for WCF service:</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="AuthorizationRequestService" Source="ESCreditCardService">  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="Name" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:FirstName</wcf:Argument>  
      </wcf:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:LastName</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name ="Concatenate"/>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="07f8c-134">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07f8c-134">In This Section</span></span>  
  
-   [<span data-ttu-id="07f8c-135">Filter</span><span class="sxs-lookup"><span data-stu-id="07f8c-135">Filter</span></span>](../core/filter.md)  
  
-   [<span data-ttu-id="07f8c-136">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="07f8c-136">CorrelationID</span></span>](../core/correlationid.md)  
  
-   [<span data-ttu-id="07f8c-137">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="07f8c-137">ContinuationToken</span></span>](../core/continuationtoken.md)  
  
-   [<span data-ttu-id="07f8c-138">Referencia</span><span class="sxs-lookup"><span data-stu-id="07f8c-138">Reference</span></span>](../core/reference.md)  
  
-   [<span data-ttu-id="07f8c-139">Update</span><span class="sxs-lookup"><span data-stu-id="07f8c-139">Update</span></span>](../core/update2.md)  
  
## <a name="see-also"></a><span data-ttu-id="07f8c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="07f8c-140">See Also</span></span>  
 [<span data-ttu-id="07f8c-141">Estructura de un archivo de configuración de Interceptor</span><span class="sxs-lookup"><span data-stu-id="07f8c-141">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)
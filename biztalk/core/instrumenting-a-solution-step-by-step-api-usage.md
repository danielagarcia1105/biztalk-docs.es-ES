---
title: "Instrumentar una solución: uso de la API de paso a paso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9e027ab-1927-4905-8970-8061ac55d591
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73c59ab28c228c779fd9e6e84d836b87415d6386
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instrumenting-a-solution-step-by-step-api-usage"></a><span data-ttu-id="d14a8-102">Instrumentar una solución: uso de la API de paso a paso</span><span class="sxs-lookup"><span data-stu-id="d14a8-102">Instrumenting a Solution: Step-by-Step API Usage</span></span>
<span data-ttu-id="d14a8-103">En este tema se describe cómo instrumentar una aplicación con la clase principal de la API de BAM.</span><span class="sxs-lookup"><span data-stu-id="d14a8-103">This topic describes how to instrument an application using the key BAM API class.</span></span> <span data-ttu-id="d14a8-104">En los siguientes fragmentos de código hemos simplificado el código de ejemplo mediante el uso de constantes y con el código mínimo necesario para instrumentar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="d14a8-104">In the following code snippets we have simplified the sample code by using constants and by using the minimum code necessary to instrument an application.</span></span>  
  
 <span data-ttu-id="d14a8-105">El siguiente fragmento de código demuestra cómo crear un objeto [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) nuevo; en concreto, un objeto [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span><span class="sxs-lookup"><span data-stu-id="d14a8-105">The following code snippet demonstrates how you create a new [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object, specifically a [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span> <span data-ttu-id="d14a8-106">En este fragmento, el primer parámetro especifica la cadena de conexión al almacén de datos de la base de datos de importación principal de BAM, y el segundo parámetro indica la frecuencia con la que se escriben los eventos en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="d14a8-106">In this snippet, the first parameter specifies the connection string to the data store of the BAM Primary Import database and the second parameter specifies the frequency with which the events are written to the data store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d14a8-107">BAM solo admite conexiones a almacenes de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d14a8-107">BAM supports connections only to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] data stores.</span></span> <span data-ttu-id="d14a8-108">La cadena de conexión de ejemplo representa la cadena de conexión mínima necesaria para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="d14a8-108">The sample connection string represents the minimal connection string required to establish a connection.</span></span> <span data-ttu-id="d14a8-109">En su configuración, puede que sea necesario especificar parámetros adicionales en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="d14a8-109">Your configuration may require additional parameters to be specified in the connection string.</span></span>  
  
 <span data-ttu-id="d14a8-110">Un valor *FlushThreshold* de 0 indica que los eventos no se escriben automáticamente y que es preciso llamar al método Flush para escribir los eventos.</span><span class="sxs-lookup"><span data-stu-id="d14a8-110">A *FlushThreshold* value of 0 specifies that events are not automatically written and that you must call the Flush method to write the events.</span></span> <span data-ttu-id="d14a8-111">Un valor de 1 hace que los eventos se escriban en el momento de generarse.</span><span class="sxs-lookup"><span data-stu-id="d14a8-111">A value of one causes each event to be written when it occurs.</span></span> <span data-ttu-id="d14a8-112">Los valores mayores que 1 determinan que los eventos se escriben cuando se crea un lote de la acumulación especificada.</span><span class="sxs-lookup"><span data-stu-id="d14a8-112">Values of greater than one specify that events are written when a batch of the specified accumulation has occurred.</span></span> <span data-ttu-id="d14a8-113">Usar un valor mayor que 1 puede ser útil para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d14a8-113">Using a value of greater than one can be useful to enhance performance.</span></span>  
  
```  
// Specify the DES connection string.  
const string connBAMPIT =  
   "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
// Write the activity update data on every call.  
int flushThreshold = 1;  
// Create a DES instance  
EventStream es =   
   new DirectEventStream(connBAMPIT, flushThreshold);  
```  
  
 <span data-ttu-id="d14a8-114">Una vez creado el objeto [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) , puede comenzar la actividad e iniciar la actualización de la tabla de la actividad con los hitos y los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="d14a8-114">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object has been created, you can begin the activity and start updating the activity table with the collected milestones and data.</span></span> <span data-ttu-id="d14a8-115">Cuando se implementó la actividad de BAM, se crearon cinco tablas en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="d14a8-115">When the BAM activity was deployed, five tables were created in the BAM Primary Import database.</span></span> <span data-ttu-id="d14a8-116">Para obtener más información sobre el proceso de desarrollo, consulte [información general sobre el proceso de desarrollo de BAM](../core/overview-of-the-bam-development-process.md).</span><span class="sxs-lookup"><span data-stu-id="d14a8-116">For more information about the development process, see [Overview of the BAM Development Process](../core/overview-of-the-bam-development-process.md).</span></span>  
  
 <span data-ttu-id="d14a8-117">Al llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) , se agrega un registro a la tabla bam_ PurchaseOrder_Activity.</span><span class="sxs-lookup"><span data-stu-id="d14a8-117">Calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method adds a record to the bam_ PurchaseOrder_Activity table.</span></span> <span data-ttu-id="d14a8-118">El primer parámetro contiene el nombre de la actividad que se está actualizando, y el segundo, un identificador para esta instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-118">The first parameter contains the name of the activity being updated and the second parameter contains an identifier for this instance of the activity.</span></span> <span data-ttu-id="d14a8-119">El identificador puede ser cualquier cadena, pero debe ser único en el conjunto de registros de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-119">The identifier can be any string, but it must be unique in the record set for the activity.</span></span>  
  
 <span data-ttu-id="d14a8-120">En este momento, el registro no contiene ningún dato.</span><span class="sxs-lookup"><span data-stu-id="d14a8-120">At this point the record does not contain any data.</span></span> <span data-ttu-id="d14a8-121">El método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) actualiza el registro con los datos de los eventos capturados.</span><span class="sxs-lookup"><span data-stu-id="d14a8-121">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method updates the record with the captured event data.</span></span> <span data-ttu-id="d14a8-122">Una vez más, debe especificar una actividad y el identificador de la instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-122">Once again you specify an activity and the activity instance identifier.</span></span> <span data-ttu-id="d14a8-123">Pase los pares de nombre y valor de los elementos de datos e hitos que definió en la actividad para el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-123">You pass the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method name value pairs of data items and milestones you defined in the activity.</span></span> <span data-ttu-id="d14a8-124">Por ejemplo, en nuestra actividad se definió un hito denominado MS_Received.</span><span class="sxs-lookup"><span data-stu-id="d14a8-124">For example, our activity defined a milestone MS_Received.</span></span> <span data-ttu-id="d14a8-125">Cuando se implementó la actividad, se creó una columna en la tabla bam_ PurchaseOrder_Activity para el hito.</span><span class="sxs-lookup"><span data-stu-id="d14a8-125">When the activity was deployed, a column in the bam_ PurchaseOrder_Activity table was created for the milestone.</span></span> <span data-ttu-id="d14a8-126">La llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) especifica que el par de nombre y valor MS_Received y DateTime.UtcNow actualicen la actividad con la fecha de recepción del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d14a8-126">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method specifies the name value pair of MS_Received and DateTime.UtcNow to update the activity with received date for the purchase order.</span></span>  
  
```  
// When a purchase order is received, you call the  
// BeginActivity method in the receive application.  
// You can then capture the event data by calling   
// the UpdateActivity method.  
es.BeginActivity ("PurchaseOrder", "PO123");  
es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
```  
  
 <span data-ttu-id="d14a8-127">En este ejemplo, vamos a realizar una continuación en una segunda actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-127">In this sample we continue to a second activity.</span></span> <span data-ttu-id="d14a8-128">Para obtener más información acerca de las continuaciones, consulte [continuación de actividad](../core/activity-continuation.md).</span><span class="sxs-lookup"><span data-stu-id="d14a8-128">For more information about continuations, see [Activity Continuation](../core/activity-continuation.md).</span></span>  
  
 <span data-ttu-id="d14a8-129">Para permitir que otras aplicaciones instrumentadas actualicen la actividad PurchaseOrder, incluya una llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-129">To enable other instrumented applications to update the PurchaseOrder activity, you include a call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method.</span></span> <span data-ttu-id="d14a8-130">La llamada especifica la actividad a la que pueden contribuir otras aplicaciones, el identificador de la instancia de la actividad cuyo seguimiento se está realizando y el token de continuación que otras aplicaciones usarán para actualizar la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-130">The call specifies the activity to which other applications can contribute, the identifier for the instance of the activity being tracked, and the continuation token that other applications will use to update the activity.</span></span> <span data-ttu-id="d14a8-131">Para realizar un seguimiento del estado de la continuación, se escribe un registro en la tabla bam_ PurchaseOrder_continuations.</span><span class="sxs-lookup"><span data-stu-id="d14a8-131">A record is written to the bam_ PurchaseOrder_continuations table to track the status of the continuation.</span></span> <span data-ttu-id="d14a8-132">Si la actividad continúa en otros procesos, se escribe un registro para cada llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) con un token de continuación único.</span><span class="sxs-lookup"><span data-stu-id="d14a8-132">If the activity continues to other processes, a record is written for each call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method with a unique continuation token.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d14a8-133">Cada segmento de código en un escenario de continuación debe tener su propia llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-133">Every code segment in a continuation scenario must have its own [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method call.</span></span> <span data-ttu-id="d14a8-134">De lo contrario, se creará un registro de actividad suelto o huérfano.</span><span class="sxs-lookup"><span data-stu-id="d14a8-134">Failing to do so will result in a dangling/orphaned activity record.</span></span>  
>   
>  <span data-ttu-id="d14a8-135">Sin embargo, solo el primer segmento (que usa el identificador real de la actividad) tiene el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) ; todos los demás segmentos (que usan su propio identificador de token único) no deben llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-135">However, only the first segment (that uses the actual activity ID) has the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method; all the other segments (that use their own unique token ID) must not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span>  
  
 <span data-ttu-id="d14a8-136">Después de llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) , otros componentes pueden actualizar la actividad de pedido de compra mediante [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) , especificando el token de continuación en lugar del identificador de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-136">After the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, other components can update the purchase order activity using [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the continuation token instead of the activity ID.</span></span> <span data-ttu-id="d14a8-137">Cuando los demás componentes hayan completado sus tareas, todos ellos deben llamar a [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) con el token de continuación para informar a la infraestructura de BAM de que no se esperan más eventos.</span><span class="sxs-lookup"><span data-stu-id="d14a8-137">When the other components have completed their tasks, each of the components must call [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) with the continuation token to inform the BAM infrastructure that no more events are expected.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d14a8-138">Una vez llamado el método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) , es posible que una actividad se quede huérfana si el proceso en el que continúa no llama nunca a un método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) con el token de continuación.</span><span class="sxs-lookup"><span data-stu-id="d14a8-138">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, it is possible for an activity to become orphaned if the process in which the activity is continued never calls an [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method with the continuation token.</span></span>  
  
```  
// Continue the activity to the next process that has been  
// instrumented to handle the continuation.  
es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
```  
  
 <span data-ttu-id="d14a8-139">Por último, la actividad se finaliza con una llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) y la especificación del nombre e identificador de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d14a8-139">Finally, the activity is finalized by calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the activity name and the activity identifier.</span></span> <span data-ttu-id="d14a8-140">Si no hay ninguna continuación sin finalizar, la actividad se mueve a la tabla bam_ PurchaseOrder _completed.</span><span class="sxs-lookup"><span data-stu-id="d14a8-140">If there are no unfinished continuations, the activity is moved to the bam_ PurchaseOrder _completed table.</span></span> <span data-ttu-id="d14a8-141">Es posible que las actividades se queden huérfanas si no se pueden completar las actividades de continuación.</span><span class="sxs-lookup"><span data-stu-id="d14a8-141">It is possible for activities to become orphaned if continuation activities fail to complete.</span></span>  
  
```  
// Activity from this segment (PO submission) is completed  
es.EndActivity("PurchaseOrder", “PO123”);  
```  
  
 <span data-ttu-id="d14a8-142">Cuando la actividad continúa en otro proceso, la aplicación se instrumenta para actualizar la tabla de la actividad mediante una llamada a [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) y la especificación del nombre de actividad y el token de continuación declarados en la llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-142">When the activity continues to separate process, the application is instrumented to update the activity table by calling [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the activity name and the continuation token declared in the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d14a8-143">El proceso que controla la actividad continuada no llama al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d14a8-143">The process handling the continued activity does not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span> <span data-ttu-id="d14a8-144">El método [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) crea una instancia de la actividad mediante la creación de las tablas en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="d14a8-144">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method creates an instance of the activity by creating the tables in the BAM Primary Import database.</span></span> <span data-ttu-id="d14a8-145">El proceso en el que continúa la actividad actualiza la instancia de la actividad ya existente.</span><span class="sxs-lookup"><span data-stu-id="d14a8-145">The process to which the activity is continued is updating the instance of the already existing activity.</span></span>  
  
```  
// update when the order is approved  
es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                    DateTime.UtcNow, "T_Product", "Widget");  
  
// update when the product is ready for shipment  
es.UpdateActivity ("PurchaseOrder", “AP123”,  
                   "MS_Ready", DateTime.UtcNow);  
```  
  
 <span data-ttu-id="d14a8-146">Parte del flujo de trabajo del código de este ejemplo especifica una referencia; en este caso, un tipo específico de referencia: una actividad relacionada.</span><span class="sxs-lookup"><span data-stu-id="d14a8-146">Part of the workflow for this sample the code specifies a reference, in this case a specific type of reference - a related activity.</span></span> <span data-ttu-id="d14a8-147">Al especificar una actividad relacionada, crea un vínculo desde la actividad principal a otras actividades que interesan a un usuario que ve la actividad en el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="d14a8-147">By specifying a related activity you create a link from your primary activity to other activities that are of interest to a user viewing the activity in the BAM portal.</span></span>  
  
 <span data-ttu-id="d14a8-148">La llamada al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) escribe un registro enbam_ PurchaseOrder_ActiveRelationships que vincula las actividades.</span><span class="sxs-lookup"><span data-stu-id="d14a8-148">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) method writes a record to the bam_ PurchaseOrder_ActiveRelationships linking the activities.</span></span>  
  
```  
// These are shipped in two shipments.  
// Relates the current purchase order   
// instance to two shippings.  
// Note: only one direction  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS101”);  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS102”);  
```  
  
 <span data-ttu-id="d14a8-149">Para finalizar la actividad continuada, debe llamar al método [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) y especificar el token de continuación correspondiente a la continuación que está finalizando.</span><span class="sxs-lookup"><span data-stu-id="d14a8-149">To end the continued activity you call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the continuation token for the continuation that is ending.</span></span> <span data-ttu-id="d14a8-150">Si no hay ninguna otra continuación sin finalizar, la actividad PurchaseOrder se mueve a la tabla _completed.</span><span class="sxs-lookup"><span data-stu-id="d14a8-150">If there are no other unfinished continuations, the purchase order activity is moved to the completed table.</span></span>  
  
```  
// Activity from this segment (ApprovalProcess) is completed  
es.EndActivity("PurchaseOrder", “AP123”);  
```  
  
## <a name="complete-code-sample"></a><span data-ttu-id="d14a8-151">Ejemplo con todo el código</span><span class="sxs-lookup"><span data-stu-id="d14a8-151">Complete Code Sample</span></span>  
  
```  
//---------------------------------------------------------------------  
// File:BAMMinimalSample.cs  
//   
// Summary: Demonstrates how to instrument an application   
//using BAM APIs to track useful information.  
//  
// Sample: BAM Api Sample  
//  
//---------------------------------------------------------------------  
// This file is part of the Microsoft BizTalk Server SDK  
//  
// Copyright (c) Microsoft Corporation. All rights reserved.  
//  
// This source code is intended only as a supplement to Microsoft   
// BizTalk Server release and/or on-line documentation. See   
// these other materials for detailed information regarding Microsoft // code samples.  
//  
// THIS CODE AND INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF  
// ANY KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO // THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A   
// PARTICULAR PURPOSE.  
//---------------------------------------------------------------------  
// This sample requires that you add the     
// Microsoft.BizTalk.Bam.EventObservation.dll to the   
// references in the Visual Studio Solution.  
  
using System;  
using System.Text;  
using Microsoft.BizTalk.Bam.EventObservation;  
  
namespace EventStreamSample  
{  
  
    static void Main(string[] args)  
    {  
        //   
  // The following code would appear in a purchase order  
   // receipt application.  
        //  
  
        // Specify the DES connection string.  
        const string connBAMPIT =  
            "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
  
        // Write the activity update data on every call.  
        int flushThreshold = 1;  
  
        // Create an instance of the DirectEventStream.  
        EventStream es =   
               new DirectEventStream(connBAMPIT, flushThreshold);  
  
        // When a purchase order is received, you call the  
       // BeginActivity method in the receive application.  
  // You can then capture the event data by calling   
        // the UpdateActivity method.  
        es.BeginActivity ("PurchaseOrder", "PO123");  
        es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
  
   // Continue the activity to the next process that has been  
   // instrumented to handle the continuation.  
        es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
  
        // Activity from this segment (PO submission) is completed  
        // end activity is synonymous to IsCompleted = 1  
        es.EndActivity("PurchaseOrder", “PO123”);  
  
        //  
        // The following code would typically appear in a separate   
        // application that monitors the approval process  
        // (ApprovalProcess.exe)  
        //  
  
        // update when the order is approved  
        es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                            DateTime.UtcNow, "T_Product", "Widget");  
  
        // update when the product is ready for shipment  
        es.UpdateActivity ("PurchaseOrder", “AP123”,  
                            "MS_Ready", DateTime.UtcNow);  
  
        // These are shipped in two shipments.  
        // Relates the current purchase order  
        // instance to two shippings.  
        // Note: only one direction  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS101”);  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS102”);  
  
        // Activity from this segment (ApprovalProcess) is completed  
        es.EndActivity("PurchaseOrder", “AP123”);  
  
        // In another Shipping application, two shipments with  
            ID’s UPS101 and UPS102 will be created.  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d14a8-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="d14a8-152">See Also</span></span>  
 [<span data-ttu-id="d14a8-153">Implementar actividades BAM con secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="d14a8-153">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)
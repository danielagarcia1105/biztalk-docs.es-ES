---
title: "Cómo finalizar un adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2621e15803dd5f6e8f449de530e84df1bc1b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-an-adapter"></a><span data-ttu-id="f351d-102">Cómo finalizar un adaptador</span><span class="sxs-lookup"><span data-stu-id="f351d-102">How to Terminate an Adapter</span></span>
<span data-ttu-id="f351d-103">Los temas siguientes sirven de guía para el correcto apagado de un adaptador.</span><span class="sxs-lookup"><span data-stu-id="f351d-103">The following topics provide guidance on the proper shutdown of an adapter.</span></span>  
  
## <a name="terminating-an-adapter"></a><span data-ttu-id="f351d-104">Finalizar un adaptador</span><span class="sxs-lookup"><span data-stu-id="f351d-104">Terminating an Adapter</span></span>  
 <span data-ttu-id="f351d-105">Cuando se va a cerrar el motor de mensajería llama al método **IBTTransportControl**. **Terminar** en cada adaptador de tipo en curso.</span><span class="sxs-lookup"><span data-stu-id="f351d-105">When the Messaging Engine is shutting down it calls **IBTTransportControl**.**Terminate** on each in-process adapter.</span></span> <span data-ttu-id="f351d-106">Una vez que vuelva este método, BizTalk Server destruirá el adaptador.</span><span class="sxs-lookup"><span data-stu-id="f351d-106">After this method returns BizTalk Server will destroy the adapter.</span></span> <span data-ttu-id="f351d-107">Esto ocurre inmediatamente con los adaptadores nativos, pero en el caso de los adaptadores administrados puede llevar más tiempo debido al proceso de recolección de elementos no utilizados de .NET.</span><span class="sxs-lookup"><span data-stu-id="f351d-107">For native adapters this occurs immediately, but for managed adapters exactly when this occurs is less deterministic due to the .NET garbage-collection process.</span></span> <span data-ttu-id="f351d-108">El adaptador debe bloquear **Terminate** y realice cualquier sea necesario hasta que esté listo para ser destruido el trabajo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="f351d-108">The adapter should block in **Terminate** and do any necessary cleanup work until it is ready to be destroyed.</span></span>  
  
## <a name="terminating-isolated-receive-adapters"></a><span data-ttu-id="f351d-109">Finalizar adaptadores de recepción aislados</span><span class="sxs-lookup"><span data-stu-id="f351d-109">Terminating Isolated Receive Adapters</span></span>  
 <span data-ttu-id="f351d-110">Aisladas de recepción no tiene adaptadores de **Terminate** en las mismas llama porque no se hospedan en el servicio de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f351d-110">Isolated receive adapters do not have **Terminate** called on them because they are not hosted in the BizTalk service.</span></span> <span data-ttu-id="f351d-111">En su lugar, debe llamar a **IBTTransportProxy**. **TerminateIsolatedReceiver** para notificar al motor de mensajería que va a apagar.</span><span class="sxs-lookup"><span data-stu-id="f351d-111">Instead, they should call **IBTTransportProxy**.**TerminateIsolatedReceiver** to notify the Messaging Engine that they are about to shut down.</span></span>  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a><span data-ttu-id="f351d-112">Limpiar objetos COM mediante Marshal.ReleaseComObject</span><span class="sxs-lookup"><span data-stu-id="f351d-112">Clean Up COM Objects by Using Marshal.ReleaseComObject</span></span>  
 <span data-ttu-id="f351d-113">Cuando se escribe código administrado que usa objetos COM, Common Language Runtime (CLR), genera objetos proxy que conservan las referencias a dichos objetos COM.</span><span class="sxs-lookup"><span data-stu-id="f351d-113">When writing managed code that uses COM objects, the common language runtime (CLR) generates proxy objects that hold the references to the COM objects.</span></span> <span data-ttu-id="f351d-114">Los objetos proxy son objetos administrados y están sujetos a las reglas habituales de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f351d-114">The proxy objects are managed objects and are subject to the usual rules of garbage collection.</span></span> <span data-ttu-id="f351d-115">Existe el problema de que el recolector de elementos no utilizados solo ve la memoria asignada por los tiempos de ejecución de .NET y no es consciente del objeto COM.</span><span class="sxs-lookup"><span data-stu-id="f351d-115">A problem arises in that the garbage collector only sees memory that the .NET runtimes allocated, and is not aware of the COM object.</span></span> <span data-ttu-id="f351d-116">Los objetos proxy son pequeños, por lo que un objeto COM grande podría quedar en memoria si el recolector CLR de elementos no utilizados no tiene constancia de él.</span><span class="sxs-lookup"><span data-stu-id="f351d-116">Because the proxy objects are small, a large COM object might be left in memory because the CLR garbage collector is not aware of it.</span></span>  
  
 <span data-ttu-id="f351d-117">Para evitar este problema, libere explícitamente los objetos COM subyacentes cuando termine con ellos, especialmente cualquier **IBTTransportBatch** objetos.</span><span class="sxs-lookup"><span data-stu-id="f351d-117">To avoid this problem, explicitly release underlying COM objects when you are finished with them, particularly any **IBTTransportBatch** objects.</span></span> <span data-ttu-id="f351d-118">Para ello, al llamar a **Marshal**. **ReleaseComObject**.</span><span class="sxs-lookup"><span data-stu-id="f351d-118">You do this by calling **Marshal**.**ReleaseComObject**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f351d-119">**ReleaseComObject** devuelve el número de referencias restantes y solo libera el objeto COM cuando dicho valor es cero.</span><span class="sxs-lookup"><span data-stu-id="f351d-119">**ReleaseComObject** returns the number of remaining references and only releases the COM object when this returned value is zero.</span></span> <span data-ttu-id="f351d-120">A menudo **ReleaseComObject** se llama en un bucle para asegurarse de que se libera el objeto.</span><span class="sxs-lookup"><span data-stu-id="f351d-120">Often **ReleaseComObject** is called in a loop to ensure that the object is released.</span></span> <span data-ttu-id="f351d-121">Una vez que completa, debe llamar a **SuppressFinalize** en este objeto porque no hay nada que finalizar.</span><span class="sxs-lookup"><span data-stu-id="f351d-121">After that is complete, you should call **SuppressFinalize** on this object because there is nothing to finalize.</span></span> <span data-ttu-id="f351d-122">El último paso consiste en comprobar si el objeto es realmente un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="f351d-122">One last step is to check whether this really is a COM object.</span></span>  
  
 <span data-ttu-id="f351d-123">El código siguiente muestra el proceso que se acaba de describir:</span><span class="sxs-lookup"><span data-stu-id="f351d-123">The following code shows the process descrjbed above:</span></span>  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 <span data-ttu-id="f351d-124">Liberar de forma explícita el **IBTTransportBatch** objeto devuelto desde **GetBatch** puede realizar una mejora considerable del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f351d-124">Explicitly releasing the **IBTTransportBatch** object returned from **GetBatch** can make a significant improvement to performance.</span></span>  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a><span data-ttu-id="f351d-125">Usar siempre Terminate al cerrar un adaptador</span><span class="sxs-lookup"><span data-stu-id="f351d-125">Always Use Terminate When Closing an Adapter</span></span>  
 <span data-ttu-id="f351d-126">Para que BizTalk Server reconozca su código como un adaptador, debe implementar una interfaz denominada **IBTTransportControl**.</span><span class="sxs-lookup"><span data-stu-id="f351d-126">For BizTalk Server to recognize your code as an adapter, you must implement an interface called **IBTTransportControl**.</span></span> <span data-ttu-id="f351d-127">Esa interfaz regula el modo en que BizTalk Server se comunica con su adaptador, y se define de este modo:</span><span class="sxs-lookup"><span data-stu-id="f351d-127">This interface defines how BizTalk Server communicates with your adapter, and is defined as follows:</span></span>  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 <span data-ttu-id="f351d-128">La interfaz contiene dos métodos, **inicializar** y **Terminate**.</span><span class="sxs-lookup"><span data-stu-id="f351d-128">The interface contains two methods, **Initialize** and **Terminate**.</span></span>  
  
### <a name="initialize"></a><span data-ttu-id="f351d-129">Inicializar</span><span class="sxs-lookup"><span data-stu-id="f351d-129">Initialize</span></span>  
 <span data-ttu-id="f351d-130">BizTalk Server llama a la **inicializar** método tras cargar el ensamblado del adaptador.</span><span class="sxs-lookup"><span data-stu-id="f351d-130">BizTalk Server calls the **Initialize** method after it loads the adapter assembly.</span></span> <span data-ttu-id="f351d-131">Hace esto con el fin de pasar el proxy de transporte (el principal componente de BizTalk Server) al adaptador.</span><span class="sxs-lookup"><span data-stu-id="f351d-131">It does this to pass the transport proxy (the main handle to BizTalk Server) to the adapter.</span></span> <span data-ttu-id="f351d-132">La implementación de **inicializar** simplemente almacena el proxy de transporte en una variable miembro.</span><span class="sxs-lookup"><span data-stu-id="f351d-132">The implementation of **Initialize** simply stores the transport proxy in a member variable.</span></span>  
  
### <a name="terminate"></a><span data-ttu-id="f351d-133">Finalizar</span><span class="sxs-lookup"><span data-stu-id="f351d-133">Terminate</span></span>  
 <span data-ttu-id="f351d-134">BizTalk Server llama a la **Terminate** método de cierre del servicio para dar tiempo al adaptador para finalizar la ejecución de todos los lotes.</span><span class="sxs-lookup"><span data-stu-id="f351d-134">BizTalk Server calls the **Terminate** method on service shutdown to give the adapter time to finish the execution of all batches.</span></span> <span data-ttu-id="f351d-135">Esto hace que la implementación de la **Terminate** método mucho más compleja.</span><span class="sxs-lookup"><span data-stu-id="f351d-135">This makes the implementation of the **Terminate** method much more involved.</span></span>  
  
 <span data-ttu-id="f351d-136">El adaptador no debe devolver desde una **Terminate** llamadas hasta que se complete cualquier trabajo pendiente tiene.</span><span class="sxs-lookup"><span data-stu-id="f351d-136">The adapter should not return from a **Terminate** call until any pending work it has is complete.</span></span> <span data-ttu-id="f351d-137">Cuando BizTalk Server llama **Terminate**, el adaptador debería intentar detener todas sus tareas actuales y no iniciar ninguna nueva.</span><span class="sxs-lookup"><span data-stu-id="f351d-137">When BizTalk Server calls **Terminate**, the adapter should try to stop all its current tasks and not start any new ones.</span></span>  
  
 <span data-ttu-id="f351d-138">Dado que **Terminate** se llama como parte del cierre del servicio, el Administrador de control de servicios finaliza el proceso si el adaptador de bloquearse en **Terminate**.</span><span class="sxs-lookup"><span data-stu-id="f351d-138">Because **Terminate** is called as part of the service shutdown, the service control manager ends the process if the adapter perpetually blocks in **Terminate**.</span></span> <span data-ttu-id="f351d-139">En ese caso, verá la advertencia del Administrador de control de servicios cuando éste detenga el servicio de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f351d-139">In this case, you see the warning from the service control manager as it stops the BizTalk Server service.</span></span> <span data-ttu-id="f351d-140">Si es posible, no finalice el adaptador de este modo prematuro.</span><span class="sxs-lookup"><span data-stu-id="f351d-140">If possible, avoid terminating the adapter prematurely like this.</span></span> <span data-ttu-id="f351d-141">Si el adaptador no realiza correctamente el proceso de finalización y aún tiene subprocesos en ejecución cuando el proceso comienza a finalizar, puede que a veces vea un mensaje de infracción de acceso de BizTalk Server al apagar.</span><span class="sxs-lookup"><span data-stu-id="f351d-141">If the adapter does not handle the termination process appropriately, and still has threads running when the process starts to shut down, then you may occasionally see an access violation from BizTalk Server on shutdown.</span></span>  
  
 <span data-ttu-id="f351d-142">Dada la naturaleza asíncrona de la interfaz con BizTalk Server, es probable que bajo la carga aún haya muchos lotes y por tanto subprocesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f351d-142">Because of the asynchronous nature of the interface to BizTalk Server, it is likely that under load there will be many batches and therefore threads still being executed.</span></span> <span data-ttu-id="f351d-143">El **Terminate** llamada debe implementarse para esperar la finalización de cada lote se ha ejecutado correctamente el adaptador en BizTalk Server antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f351d-143">The **Terminate** call should be implemented to wait on the conclusion of every batch the adapter has successfully executed on BizTalk Server before proceeding.</span></span> <span data-ttu-id="f351d-144">La conclusión del lote se señaliza mediante la **BatchComplete** devolución de llamada de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f351d-144">The conclusion of the batch is signaled by the **BatchComplete** callback from BizTalk Server.</span></span> <span data-ttu-id="f351d-145">El **Terminate** debe esperar la llamada cada pendientes **BatchComplete** que se produzca.</span><span class="sxs-lookup"><span data-stu-id="f351d-145">The **Terminate** call should wait on every pending **BatchComplete** to happen.</span></span> <span data-ttu-id="f351d-146">No obstante, el lote debe ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="f351d-146">However, the execution of the batch must be successful.</span></span> <span data-ttu-id="f351d-147">Es decir, la llamada a **IBTTransportBatch**::**realiza** no producirá un error.</span><span class="sxs-lookup"><span data-stu-id="f351d-147">That is, the call to **IBTTransportBatch**::**Done** must not fail.</span></span> <span data-ttu-id="f351d-148">Si la llamada a **IBTTransportBatch**::**realiza** se produce un error, no hay ninguna devolución de llamada de lote.</span><span class="sxs-lookup"><span data-stu-id="f351d-148">If the call to **IBTTransportBatch**::**Done** fails, there is no batch callback.</span></span>  
  
 <span data-ttu-id="f351d-149">Una vez comprendido que debe agregar código de sincronización a su adaptador, la implementación es bastante sencilla.</span><span class="sxs-lookup"><span data-stu-id="f351d-149">After you realize that you have to add synchronization code to your adapter, the implementation is fairly straightforward.</span></span>  
  
 <span data-ttu-id="f351d-150">Una estrategia sencilla consiste en implementar un objeto de sincronización compuesta con **escriba** y **deje** métodos para los subprocesos de trabajo y un **finalizar** método que se bloquee mientras un subproceso está aún dentro de la ejecución protegida.</span><span class="sxs-lookup"><span data-stu-id="f351d-150">One simple approach is to implement a compound synchronization object with **enter** and **leave** methods for the worker threads and a **terminate** method that blocks while a thread is still within the protected execution.</span></span> <span data-ttu-id="f351d-151">(A propósito, la solución es muy similar a la estructura de varios lectores, solo escritor familiar donde los subprocesos de trabajo pueden considerarse como lectores y **finalizar** método como el sistema de escritura.)</span><span class="sxs-lookup"><span data-stu-id="f351d-151">(Incidentally, the solution is very similar to the familiar multiple-reader, single-writer structure where the worker threads can be thought of as readers and the **terminate** method as the writer.)</span></span>  
  
 <span data-ttu-id="f351d-152">El **finalizar** método es como sigue:</span><span class="sxs-lookup"><span data-stu-id="f351d-152">The **terminate** method is as follows:</span></span>  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 <span data-ttu-id="f351d-153">Para cada subproceso de trabajo:</span><span class="sxs-lookup"><span data-stu-id="f351d-153">For each worker thread:</span></span>  
  
```  
If (!this.control.Enter())  
return; // we can’t enter because Terminate has been called  
try  
{  
//  create and fill batch  
batch.Done();  
}  
catch (Exception)  
{  
//  we are not expecting a callback  
This.control.Leave();  
}  
```  
  
 <span data-ttu-id="f351d-154">En la devolución de llamada de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="f351d-154">In the callback from BizTalk Server:</span></span>  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f351d-155">se distribuye con el código de ejemplo ControlledTermination.cs en el ejemplo de adaptador Base, que muestra el mecanismo de sincronización que se describen aquí.</span><span class="sxs-lookup"><span data-stu-id="f351d-155"> ships with sample code ControlledTermination.cs in the Base Adapter sample, showing the synchronization mechanism described here.</span></span>
---
title: "Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de eco | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da34bca28f073babac4907b7d408d0642a234e2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a><span data-ttu-id="9abf9-102">Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="9abf9-102">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="9abf9-103">![Paso 8 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="9abf9-103">![Step 8 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="9abf9-104">**Tiempo en completarse:** 45 minutos</span><span class="sxs-lookup"><span data-stu-id="9abf9-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="9abf9-105">En este paso, implementará la capacidad del adaptador de eco entrante.</span><span class="sxs-lookup"><span data-stu-id="9abf9-105">In this step, you implement the inbound capability of the echo adapter.</span></span> <span data-ttu-id="9abf9-106">Esta capacidad permite que el adaptador realizar escuchas de datos o eventos del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9abf9-106">This capability allows the adapter to listen for data or events from the target system.</span></span> <span data-ttu-id="9abf9-107">Según la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], solo debe implementar la `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz, cuando el adaptador es compatible con la capacidad de entrada.</span><span class="sxs-lookup"><span data-stu-id="9abf9-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you only need to implement the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, when your adapter supports inbound capability.</span></span> <span data-ttu-id="9abf9-108">El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente la clase derivada denominada EchoAdpterInboundHandler para usted.</span><span class="sxs-lookup"><span data-stu-id="9abf9-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdpterInboundHandler for you.</span></span>  
  
 <span data-ttu-id="9abf9-109">En la siguiente sección, se actualiza la clase EchoAdpterInboundHandler para obtener una mejor comprensión acerca de cómo implementar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abf9-109">In the following section, you update the EchoAdpterInboundHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="9abf9-110">Cuando haya completado este paso, tendrá un controlador de entrada de trabajo para el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="9abf9-110">When you complete this step, you have a working inbound handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9abf9-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9abf9-111">Prerequisites</span></span>  
 <span data-ttu-id="9abf9-112">Antes de comenzar este paso, debe haber completado correctamente [paso 7: implementar el controlador de salida sincrónica para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9abf9-112">Before you begin this step, you must have successfully completed [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="9abf9-113">Un conocimiento básico de `Microsoft.ServiceModel.Channels.Common.IInboundHandler` también es útil.</span><span class="sxs-lookup"><span data-stu-id="9abf9-113">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is also helpful.</span></span>  
  
## <a name="the-iinboundhandler-interface"></a><span data-ttu-id="9abf9-114">La interfaz de IInboundHandler</span><span class="sxs-lookup"><span data-stu-id="9abf9-114">The IInboundHandler Interface</span></span>  
 <span data-ttu-id="9abf9-115">El `Microsoft.ServiceModel.Channels.Common.IInboundHandler` se define como:</span><span class="sxs-lookup"><span data-stu-id="9abf9-115">The `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is defined as:</span></span>  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="9abf9-116">Las descripciones de método son:</span><span class="sxs-lookup"><span data-stu-id="9abf9-116">The method descriptions are:</span></span>  
  
|<span data-ttu-id="9abf9-117">Método</span><span class="sxs-lookup"><span data-stu-id="9abf9-117">Method</span></span>|<span data-ttu-id="9abf9-118">Description</span><span class="sxs-lookup"><span data-stu-id="9abf9-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9abf9-119">StartListener</span><span class="sxs-lookup"><span data-stu-id="9abf9-119">StartListener</span></span>|<span data-ttu-id="9abf9-120">Empieza a escuchar los mensajes con las acciones proporcionadas de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="9abf9-120">Starts listening to messages with the provided WS-Addressing Actions.</span></span> <span data-ttu-id="9abf9-121">Si no se especifica ninguno, escucha a todos o las acciones de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9abf9-121">If none is specified, it listens to all or the default actions.</span></span>|  
|<span data-ttu-id="9abf9-122">StopListener</span><span class="sxs-lookup"><span data-stu-id="9abf9-122">StopListener</span></span>|<span data-ttu-id="9abf9-123">Detiene la escucha.</span><span class="sxs-lookup"><span data-stu-id="9abf9-123">Stops listening.</span></span>|  
|<span data-ttu-id="9abf9-124">TryReceive</span><span class="sxs-lookup"><span data-stu-id="9abf9-124">TryReceive</span></span>|<span data-ttu-id="9abf9-125">Intenta recibir un mensaje entrante desde el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9abf9-125">Tries to receive an inbound message from the target system.</span></span>|  
|<span data-ttu-id="9abf9-126">WaitForMessage</span><span class="sxs-lookup"><span data-stu-id="9abf9-126">WaitForMessage</span></span>|<span data-ttu-id="9abf9-127">Espera un mensaje WCF entrante desde el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9abf9-127">Waits for an inbound WCF message from the target system.</span></span>|  
  
 <span data-ttu-id="9abf9-128">Para obtener más detalles sobre la descripción de los parámetros de cada método, consulte la documentación en el `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abf9-128">For more details on the description for each method parameters, see the documentation on the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface.</span></span>  
  
## <a name="implementing-the-echoadpterinboundhandler"></a><span data-ttu-id="9abf9-129">Implementar el EchoAdpterInboundHandler</span><span class="sxs-lookup"><span data-stu-id="9abf9-129">Implementing the EchoAdpterInboundHandler</span></span>  
 <span data-ttu-id="9abf9-130">El adaptador de eco utiliza el `System.IO.FileSystemWatcher` para simular el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9abf9-130">The echo adapter uses the `System.IO.FileSystemWatcher` to simulate the target system.</span></span> <span data-ttu-id="9abf9-131">A continuación, implementa cada método dentro de la `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz, StartListener, StopListener, TryReceive y WaitForMessage.</span><span class="sxs-lookup"><span data-stu-id="9abf9-131">In the following, you implement each method within the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, StartListener, StopListener, TryReceive and WaitForMessage.</span></span>  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a><span data-ttu-id="9abf9-132">Para implementar la interfaz de IInboundHandler en la clase EchoAdpterInboundHandler</span><span class="sxs-lookup"><span data-stu-id="9abf9-132">To implement IInboundHandler interface in the EchoAdpterInboundHandler class</span></span>  
  
1.  <span data-ttu-id="9abf9-133">En el Explorador de soluciones, haga doble clic en el **EchoAdapterInboundHandler.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="9abf9-133">In Solution Explorer, double-click the **EchoAdapterInboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="9abf9-134">En el editor de Visual Studio, agregue las líneas siguientes al conjunto existente de directivas using.</span><span class="sxs-lookup"><span data-stu-id="9abf9-134">In the Visual Studio editor, add the following lines to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  <span data-ttu-id="9abf9-135">Ahora agregue las variables de nivel de clase a la clase EchoAdapterInboundHandler.</span><span class="sxs-lookup"><span data-stu-id="9abf9-135">Now add class level variables to the EchoAdapterInboundHandler class.</span></span> <span data-ttu-id="9abf9-136">Estas variables se utilizan para supervisar el sistema de archivos para la actividad de archivo.</span><span class="sxs-lookup"><span data-stu-id="9abf9-136">These variables are used to monitor the file system for file activity.</span></span> <span data-ttu-id="9abf9-137">Copie las declaraciones a continuación en la clase antes del constructor.</span><span class="sxs-lookup"><span data-stu-id="9abf9-137">Copy the declarations below into the class before the constructor.</span></span>  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  <span data-ttu-id="9abf9-138">Dentro del método de constructor EchoAdapterInboundHandler, agregue el código siguiente para inicializar el archivo viendo la infraestructura y para capturar la supervisión de la ruta de acceso y el filtro.</span><span class="sxs-lookup"><span data-stu-id="9abf9-138">Inside the EchoAdapterInboundHandler constructor method, add the following code to initialize the file watching infrastructure and to capture the monitoring path and filter.</span></span>  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  <span data-ttu-id="9abf9-139">Ahora, agregue el código siguiente a la **StartListener** método.</span><span class="sxs-lookup"><span data-stu-id="9abf9-139">Now add the following code to the **StartListener** method.</span></span> <span data-ttu-id="9abf9-140">El código implementa la lógica para comprobar los parámetros e iniciar la supervisión de la actividad de archivo.</span><span class="sxs-lookup"><span data-stu-id="9abf9-140">The code implements logic to verify parameters and start monitoring for file activity.</span></span>  
  
    ```csharp  
    // if no actions are provided, log an error in the trace log  
    // and throw an exception  
    if (actions.Length == 0)  
    {  
        EchoAdapterUtilities.Trace.Trace(TraceEventType.Error, "http://echoadapterv2/startlistener/noactions", "No operation actions were received for listener to do specific processing.", this);  
        throw new AdapterException("Unable to receive any actions for inbound handler to start listening.");  
    }  
  
    inboundQueue = new Queue<Message>();  
    foreach (string action in actions)  
    {  
        // for the OnReceiveEcho action listen for a new file created event  
        if ("Echo/OnReceiveEcho".Equals(action))  
        {  
            if (inboundWatcher == null)  
            {  
                inboundWatcher = new FileSystemWatcher(path);  
                inboundWatcher.Filter = filter;  
                // Begin monitoring  
                inboundWatcher.EnableRaisingEvents = true;  
            }  
            inboundWatcher.Created += new FileSystemEventHandler(FileMonitor_Created);  
            EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/startlistener", "Listening for file created event for " + filter + " in path " + path, this);  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="9abf9-141">Continuar agregando una implementación para el **StopListener** método.</span><span class="sxs-lookup"><span data-stu-id="9abf9-141">Continue by adding an implementation for the **StopListener** method.</span></span>  
  
    ```csharp  
    if (inboundWatcher != null)  
    {  
        // End monitoring  
        inboundWatcher.EnableRaisingEvents = false;  
        inboundWatcher = null;  
    }  
    lock (inboundQueueSynchronizationLock)  
    {  
        inboundQueue.Clear();  
        inboundQueue = null;  
    }  
    ```  
  
7.  <span data-ttu-id="9abf9-142">Ahora proporciona una implementación para el **TryReveive** método.</span><span class="sxs-lookup"><span data-stu-id="9abf9-142">Now provide an implementation for the **TryReveive** method.</span></span> <span data-ttu-id="9abf9-143">Este método recupera el archivo más reciente reciben un mensaje de la cola interna si está disponible.</span><span class="sxs-lookup"><span data-stu-id="9abf9-143">This method retrieves the most recent file receive message from the internal queue if one is available.</span></span>  
  
    ```csharp  
    reply = new EchoAdapterInboundReply();  
    message = null;  
    TimeoutHelper timeoutHelper = new TimeoutHelper(timeout);  
    while (true)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (inboundQueue == null)  
            {  
                //listener has been closed  
                return false;  
            }  
            if (inboundQueue.Count != 0)  
            {  
                message = inboundQueue.Dequeue();  
                if (message != null)  
                {  
                    return true;  
                }  
            }  
        }  
        if (timeoutHelper.IsExpired)  
        {  
            return false;  
        }  
        //wait for sometime, and check again  
        System.Threading.Thread.Sleep(500);  
    }  
    ```  
  
8.  <span data-ttu-id="9abf9-144">Continuar agregando una implementación para el **WaitForMessage** método.</span><span class="sxs-lookup"><span data-stu-id="9abf9-144">Continue by adding an implementation for the **WaitForMessage** method.</span></span>  
  
    ```csharp  
    while (inboundQueue.Count == 0) { };  
    Message msg = inboundQueue.Peek();  
    if (msg != null)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
    ```  
  
9. <span data-ttu-id="9abf9-145">Proporcionar ahora la devolución de llamada para el Monitor de archivos.</span><span class="sxs-lookup"><span data-stu-id="9abf9-145">Now supply the callback for the file watcher.</span></span> <span data-ttu-id="9abf9-146">Para ello, agregue el nuevo método **FileMonitor_Created** a la **EchoAdapterInboundAdapter** clase.</span><span class="sxs-lookup"><span data-stu-id="9abf9-146">To do so, add the new method **FileMonitor_Created** to the **EchoAdapterInboundAdapter** class.</span></span>  
  
    ```csharp  
    private void FileMonitor_Created(object sender, FileSystemEventArgs e)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (e.ChangeType == WatcherChangeTypes.Created)  
            {  
                // wait for file to close - should do this in a better manner  
                System.Threading.Thread.Sleep(500);  
                try  
                {  
                    EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/FileMonitorCreated", "File " + e.FullPath + " created.", this);  
                    FileInfo fileInfo = new FileInfo(e.FullPath);  
                    // Create WCF message to send to the inbound service  
                    // that is listening for messages from adapter  
                    String xmlData = String.Format(@"<OnReceiveEcho xmlns=""{0}""><path>{1}</path><length>{2}</length></OnReceiveEcho>", EchoAdapter.SERVICENAMESPACE, e.FullPath, fileInfo.Length);  
                    // set action string  
                    XmlReader reader = XmlReader.Create(new StringReader(xmlData));  
                    // create WCF message  
                    Message requestMessage = Message.CreateMessage(MessageVersion.Default  
                                , "Echo/OnReceiveEcho"  
                                , reader);  
                    requestMessage.Headers.To = new Uri(path);  
                    inboundQueue.Enqueue(requestMessage);  
                }  
                catch (Exception ex)  
                {  
                    String message = String.Format("An exception was thrown while trying to open file {1}.", e.FullPath);  
                    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Error, "http://echoadapterv2/FileMonitorCreated", message, this, ex);  
                    throw new AdapterException(message, ex);  
                }  
            }  
        }  
    }  
    ```  
  
10. <span data-ttu-id="9abf9-147">Ahora debe quitar la **NotImplementedException** las excepciones producidas por interno **EchoAdapterInboundReply** clase.</span><span class="sxs-lookup"><span data-stu-id="9abf9-147">Now you must remove the **NotImplementedException** exceptions thrown by the internal **EchoAdapterInboundReply** class.</span></span> <span data-ttu-id="9abf9-148">Para ello, elimine la instrucción siguiente de la **anular** y **respuesta** métodos.</span><span class="sxs-lookup"><span data-stu-id="9abf9-148">To do this, delete the following statement from the **Abort** and **Reply** methods.</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="9abf9-149">Su **anular** y **respuesta** métodos deben ser similares al siguiente.</span><span class="sxs-lookup"><span data-stu-id="9abf9-149">Your **Abort** and **Reply** methods should be similar to the following.</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Abort the inbound reply call  
    /// </summary>  
    public override void Abort()  
    {  
    }  
  
    /// <summary>  
    /// Reply message implemented  
    /// </summary>  
    public override void Reply(System.ServiceModel.Channels.Message message  
        , TimeSpan timeout)  
    {  
    }  
    ```  
  
11. <span data-ttu-id="9abf9-150">Para completar la implementación para el controlador de entrada, agregue la siguiente clase al **EchoAdapterOutboundHandler.cs**.</span><span class="sxs-lookup"><span data-stu-id="9abf9-150">To complete the implementation for the inbound handler, add the following class to **EchoAdapterOutboundHandler.cs**.</span></span> <span data-ttu-id="9abf9-151">Esta clase proporciona compatibilidad de tiempo de espera para la implementación del controlador de entrada.</span><span class="sxs-lookup"><span data-stu-id="9abf9-151">This class provides timeout support for the inbound handler implementation.</span></span>  
  
    ```csharp  
    /// <summary>  
    /// Utility class containing helper functions for measuring timeout   
    /// </summary>  
    class TimeoutHelper  
    {  
        private TimeSpan timeout;  
        private DateTime creationTime;  
        private Boolean isInfinite;  
  
        /// <summary>  
        /// Constructor  
        /// </summary>  
        /// <param name="timeout"></param>  
        public TimeoutHelper(TimeSpan timeout)  
        {  
            this.creationTime = DateTime.Now;  
            this.timeout = timeout;  
            if (timeout.Equals(Infinite)) this.isInfinite = true;  
        }  
  
        /// <summary>  
        /// Value of infinite timespan  
        /// </summary>  
        public static TimeSpan Infinite  
        {  
            get { return TimeSpan.MaxValue; }  
        }  
  
        /// <summary>  
        /// Value indicating remaining timeout  
        /// </summary>  
        public TimeSpan RemainingTimeout  
        {  
            get  
            {  
                if (this.isInfinite) return Infinite;  
                return this.timeout.Subtract(DateTime.Now.Subtract(this.creationTime));  
            }  
        }  
  
        /// <summary>  
        /// Get remaining timeout value and throw an exception if the timeout  
        /// has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        /// <returns></returns>  
        public TimeSpan GetRemainingTimeoutAndThrowIfExpired(String exceptionMessage)  
        {  
            if (this.isInfinite) return Infinite;  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
            return RemainingTimeout;  
        }  
  
        /// <summary>  
        /// Throw an exception if the timeout has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        public void ThrowIfTimeoutExpired(String exceptionMessage)  
        {  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
  
        }  
  
        /// <summary>  
        /// Value indicating whether timeout has expired.  
        /// </summary>  
        public Boolean IsExpired  
        {  
            get  
            {  
                if (this.isInfinite) return false;  
                return RemainingTimeout < TimeSpan.Zero;  
            }  
        }  
    }  
    ```  
  
12. <span data-ttu-id="9abf9-152">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="9abf9-152">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
13. <span data-ttu-id="9abf9-153">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="9abf9-153">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="9abf9-154">Debe compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="9abf9-154">It should compile without errors.</span></span> <span data-ttu-id="9abf9-155">Si no es así, asegúrese de que ha seguido todos los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9abf9-155">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9abf9-156">Ya ha guardado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="9abf9-156">You saved your work.</span></span> <span data-ttu-id="9abf9-157">Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 9: compilar e implementar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9abf9-157">You can safely close Visual Studio at this time or go to the next step, [Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9abf9-158">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="9abf9-158">What Did I Just Do?</span></span>  
 <span data-ttu-id="9abf9-159">En este paso del tutorial de eco adaptador, se proporciona una implementación para el controlador de entrada.</span><span class="sxs-lookup"><span data-stu-id="9abf9-159">In this step of the Echo Adapter tutorial, you provided an implementation for the Inbound Handler.</span></span> <span data-ttu-id="9abf9-160">Esta implementación proporciona archivo viendo capacidades para el adaptador de eco mediante el **FileSystemWatcher** clase de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9abf9-160">This implementation provides file watching capabilities for the Echo Adapter using the **FileSystemWatcher** class of the .NET Framework.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9abf9-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9abf9-161">Next Steps</span></span>  
 <span data-ttu-id="9abf9-162">En el paso siguiente, se implementa el adaptador.</span><span class="sxs-lookup"><span data-stu-id="9abf9-162">In the next step, you deploy the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abf9-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="9abf9-163">See Also</span></span>  
 <span data-ttu-id="9abf9-164">[Paso 9: Compilar e implementar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="9abf9-164">[Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="9abf9-165">Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="9abf9-165">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)
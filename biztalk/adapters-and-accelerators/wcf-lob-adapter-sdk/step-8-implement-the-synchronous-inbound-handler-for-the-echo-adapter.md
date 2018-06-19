---
title: 'Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da34bca28f073babac4907b7d408d0642a234e2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226636"
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a>Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de eco
![Paso 8 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 **Tiempo en completarse:** 45 minutos  
  
 En este paso, implementará la capacidad del adaptador de eco entrante. Esta capacidad permite que el adaptador realizar escuchas de datos o eventos del sistema de destino. Según la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], solo debe implementar la `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz, cuando el adaptador es compatible con la capacidad de entrada. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente la clase derivada denominada EchoAdpterInboundHandler para usted.  
  
 En la siguiente sección, se actualiza la clase EchoAdpterInboundHandler para obtener una mejor comprensión acerca de cómo implementar esta interfaz. Cuando haya completado este paso, tendrá un controlador de entrada de trabajo para el adaptador de eco.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 7: implementar el controlador de salida sincrónica para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md). Un conocimiento básico de `Microsoft.ServiceModel.Channels.Common.IInboundHandler` también es útil.  
  
## <a name="the-iinboundhandler-interface"></a>La interfaz de IInboundHandler  
 El `Microsoft.ServiceModel.Channels.Common.IInboundHandler` se define como:  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 Las descripciones de método son:  
  
|Método|Description|  
|------------|-----------------|  
|StartListener|Empieza a escuchar los mensajes con las acciones proporcionadas de WS-Addressing. Si no se especifica ninguno, escucha a todos o las acciones de forma predeterminada.|  
|StopListener|Detiene la escucha.|  
|TryReceive|Intenta recibir un mensaje entrante desde el sistema de destino.|  
|WaitForMessage|Espera un mensaje WCF entrante desde el sistema de destino.|  
  
 Para obtener más detalles sobre la descripción de los parámetros de cada método, consulte la documentación en el `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz.  
  
## <a name="implementing-the-echoadpterinboundhandler"></a>Implementar el EchoAdpterInboundHandler  
 El adaptador de eco utiliza el `System.IO.FileSystemWatcher` para simular el sistema de destino. A continuación, implementa cada método dentro de la `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz, StartListener, StopListener, TryReceive y WaitForMessage.  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a>Para implementar la interfaz de IInboundHandler en la clase EchoAdpterInboundHandler  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterInboundHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, agregue las líneas siguientes al conjunto existente de directivas using.  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  Ahora agregue las variables de nivel de clase a la clase EchoAdapterInboundHandler. Estas variables se utilizan para supervisar el sistema de archivos para la actividad de archivo. Copie las declaraciones a continuación en la clase antes del constructor.  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  Dentro del método de constructor EchoAdapterInboundHandler, agregue el código siguiente para inicializar el archivo viendo la infraestructura y para capturar la supervisión de la ruta de acceso y el filtro.  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  Ahora, agregue el código siguiente a la **StartListener** método. El código implementa la lógica para comprobar los parámetros e iniciar la supervisión de la actividad de archivo.  
  
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
  
6.  Continuar agregando una implementación para el **StopListener** método.  
  
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
  
7.  Ahora proporciona una implementación para el **TryReveive** método. Este método recupera el archivo más reciente reciben un mensaje de la cola interna si está disponible.  
  
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
  
8.  Continuar agregando una implementación para el **WaitForMessage** método.  
  
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
  
9. Proporcionar ahora la devolución de llamada para el Monitor de archivos. Para ello, agregue el nuevo método **FileMonitor_Created** a la **EchoAdapterInboundAdapter** clase.  
  
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
  
10. Ahora debe quitar la **NotImplementedException** las excepciones producidas por interno **EchoAdapterInboundReply** clase. Para ello, elimine la instrucción siguiente de la **anular** y **respuesta** métodos.  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     Su **anular** y **respuesta** métodos deben ser similares al siguiente.  
  
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
  
11. Para completar la implementación para el controlador de entrada, agregue la siguiente clase al **EchoAdapterOutboundHandler.cs**. Esta clase proporciona compatibilidad de tiempo de espera para la implementación del controlador de entrada.  
  
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
  
12. En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
13. En el menú **Compilar** , haga clic en **Compilar solución**. Debe compilar sin errores. Si no es así, asegúrese de que ha seguido todos los pasos anteriores.  
  
> [!NOTE]
>  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 9: compilar e implementar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso del tutorial de eco adaptador, se proporciona una implementación para el controlador de entrada. Esta implementación proporciona archivo viendo capacidades para el adaptador de eco mediante el **FileSystemWatcher** clase de .NET Framework.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el paso siguiente, se implementa el adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Paso 9: Compilar e implementar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)   
 [Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)
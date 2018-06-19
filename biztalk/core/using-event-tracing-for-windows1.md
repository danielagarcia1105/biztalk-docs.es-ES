---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: cce9ad685bc4b0bc8a0d97e0645573c5e2db1cf5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975570"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="b6057-101">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="b6057-101">Using Event Tracing for Windows</span></span>
<span data-ttu-id="b6057-102">Microsoft BizTalk Adapter para TIBCO Rendezvous registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="b6057-102">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="b6057-103">Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b6057-103">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="b6057-104">Cuando se activa ETW, crea un archivo \*.etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b6057-104">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="b6057-105">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="b6057-105">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="b6057-106">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="b6057-106">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="b6057-107">Por ejemplo, la aplicación tracerpt.exe convertirá el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.</span><span class="sxs-lookup"><span data-stu-id="b6057-107">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="b6057-108">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="b6057-108">ETW Components</span></span>  
 <span data-ttu-id="b6057-109">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="b6057-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="b6057-110">**Aplicación del controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="b6057-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="b6057-111">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="b6057-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="b6057-112">Esto garantiza que las llamadas de BTATIBCO RendezvousTrace puedan localizar tracelog.exe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="b6057-112">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="b6057-113">De forma predeterminada, BTATIBCO RendezvousTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="b6057-113">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6057-114">tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO RendezvousTrace.</span><span class="sxs-lookup"><span data-stu-id="b6057-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="b6057-115">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="b6057-115">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="b6057-116">**Aplicación de consumidor**: lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="b6057-116">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="b6057-117">Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="b6057-117">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="b6057-118">Normalmente esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b6057-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="b6057-119">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<tiempo Real\> = -rt.</span><span class="sxs-lookup"><span data-stu-id="b6057-119">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
-   <span data-ttu-id="b6057-120">**Proveedor**: proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="b6057-120">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="b6057-121">BizTalk Adapter para TIBCO Rendezvous incluye tres proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="b6057-121">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="b6057-122">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="b6057-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="b6057-123">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="b6057-123">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="b6057-124">BizTalk Adapter para TIBCO Rendezvous tiene tres proveedores.</span><span class="sxs-lookup"><span data-stu-id="b6057-124">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="b6057-125">Esto le permite registrar diferentes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="b6057-125">This lets you log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="b6057-126">**Proveedor de registro de receptor**: el \<elemento Trace\> conmutador **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="b6057-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="b6057-127">Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6057-127">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
-   <span data-ttu-id="b6057-128">**Proveedor de registro de transmisor**: el \<elemento Trace\> conmutador **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="b6057-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="b6057-129">Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6057-129">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="b6057-130">**Proveedor de registro de administración:** el \<elemento Trace\> conmutador **-administración**.</span><span class="sxs-lookup"><span data-stu-id="b6057-130">**Management Logging Provider—** the \<Trace element\> switch is **-management**.</span></span>  
  
     <span data-ttu-id="b6057-131">Use **-administración**para recibir cualquier mensaje del registro que se generaron durante la exploración del sistema del servidor.</span><span class="sxs-lookup"><span data-stu-id="b6057-131">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="b6057-132">Comando BTATIBCORVTrace</span><span class="sxs-lookup"><span data-stu-id="b6057-132">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="b6057-133">Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Rendezvous, BTATIBCORVTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="b6057-133">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="b6057-134">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="b6057-134">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="b6057-135">Dónde:  **\<elemento Trace\>**  (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="b6057-135">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="b6057-136">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="b6057-136">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="b6057-137">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="b6057-137">**-transmitter**</span></span>  
  
-   <span data-ttu-id="b6057-138">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="b6057-138">**-receiver**</span></span>  
  
-   <span data-ttu-id="b6057-139">**-administración**</span><span class="sxs-lookup"><span data-stu-id="b6057-139">**-management**</span></span>  
  
-   <span data-ttu-id="b6057-140">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="b6057-140">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="b6057-141">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="b6057-141">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="b6057-142">**-cir** es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="b6057-142">**-cir** is a circular file.</span></span> <span data-ttu-id="b6057-143">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="b6057-143">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="b6057-144">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="b6057-144">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="b6057-145">**-seq** es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="b6057-145">**-seq** is a sequential file.</span></span> <span data-ttu-id="b6057-146">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="b6057-146">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="b6057-147">**-rt**: activar el modo de tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b6057-147">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="b6057-148">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6057-148">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="b6057-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6057-149">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6057-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6057-150">See Also</span></span>  
 [<span data-ttu-id="b6057-151">Solución de problemas de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="b6057-151">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)
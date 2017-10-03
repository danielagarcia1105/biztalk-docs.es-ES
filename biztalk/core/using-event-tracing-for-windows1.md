---
title: Uso de seguimiento de eventos para Windows1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- Management Logging Provider
- consumer application
- Event Tracing for Windows
- BTATIBCORVTrace command
ms.assetid: 9e0418e2-7938-4202-83b7-555a90348904
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b51ca273e63ce93ee1ce94a66d0d14a97f807767
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="9761b-102">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="9761b-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="9761b-103">Microsoft BizTalk Adapter para TIBCO Rendezvous registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="9761b-103">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="9761b-104">Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="9761b-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="9761b-105">Cuando se activa ETW, crea un archivo *.etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9761b-105">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="9761b-106">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="9761b-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="9761b-107">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="9761b-107">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="9761b-108">Por ejemplo, la aplicación tracerpt.exe convertirá el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.</span><span class="sxs-lookup"><span data-stu-id="9761b-108">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="9761b-109">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="9761b-109">ETW Components</span></span>  
 <span data-ttu-id="9761b-110">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="9761b-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="9761b-111">**Aplicación del controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="9761b-111">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="9761b-112">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="9761b-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="9761b-113">Esto garantiza que las llamadas de BTATIBCO RendezvousTrace puedan localizar tracelog.exe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9761b-113">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="9761b-114">De forma predeterminada, BTATIBCO RendezvousTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="9761b-114">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9761b-115">tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO RendezvousTrace.</span><span class="sxs-lookup"><span data-stu-id="9761b-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="9761b-116">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="9761b-116">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="9761b-117">**Aplicación de consumidor**: lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="9761b-117">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="9761b-118">Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="9761b-118">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="9761b-119">Normalmente esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9761b-119">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="9761b-120">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<tiempo Real > = -rt.</span><span class="sxs-lookup"><span data-stu-id="9761b-120">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time> = -rt.</span></span>  
  
-   <span data-ttu-id="9761b-121">**Proveedor**: proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="9761b-121">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="9761b-122">BizTalk Adapter para TIBCO Rendezvous incluye tres proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="9761b-122">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="9761b-123">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="9761b-123">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="9761b-124">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="9761b-124">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="9761b-125">BizTalk Adapter para TIBCO Rendezvous tiene tres proveedores.</span><span class="sxs-lookup"><span data-stu-id="9761b-125">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="9761b-126">Esto le permite registrar diferentes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="9761b-126">This lets you log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="9761b-127">**Proveedor de registro de receptor**: el \<elemento de seguimiento > es el conmutador **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="9761b-127">**Receiver Logging Provider**: The \<Trace element> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="9761b-128">Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9761b-128">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
-   <span data-ttu-id="9761b-129">**Proveedor de registro de transmisor**: el \<elemento de seguimiento > es el conmutador **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="9761b-129">**Transmitter Logging Provider**: the \<Trace element> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="9761b-130">Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9761b-130">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="9761b-131">**Proveedor de registro de administración:**el \<elemento de seguimiento > es el conmutador **-administración**.</span><span class="sxs-lookup"><span data-stu-id="9761b-131">**Management Logging Provider—**the \<Trace element> switch is **-management**.</span></span>  
  
     <span data-ttu-id="9761b-132">Use **-administración**para recibir cualquier mensaje del registro que se generaron durante la exploración del sistema del servidor.</span><span class="sxs-lookup"><span data-stu-id="9761b-132">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="9761b-133">Comando BTATIBCORVTrace</span><span class="sxs-lookup"><span data-stu-id="9761b-133">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="9761b-134">Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Rendezvous, BTATIBCORVTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="9761b-134">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="9761b-135">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="9761b-135">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="9761b-136">Dónde:  **\<elemento Trace >** (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="9761b-136">Where: **\<Trace element>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="9761b-137">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="9761b-137">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="9761b-138">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="9761b-138">**-transmitter**</span></span>  
  
-   <span data-ttu-id="9761b-139">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="9761b-139">**-receiver**</span></span>  
  
-   <span data-ttu-id="9761b-140">**-administración**</span><span class="sxs-lookup"><span data-stu-id="9761b-140">**-management**</span></span>  
  
-   <span data-ttu-id="9761b-141">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="9761b-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="9761b-142">**-cir \<MB >**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="9761b-142">**-cir \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="9761b-143">**-cir** es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="9761b-143">**-cir** is a circular file.</span></span> <span data-ttu-id="9761b-144">**\<MB >**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="9761b-144">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="9761b-145">**-seq \<MB >**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="9761b-145">**-seq \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="9761b-146">**-seq** es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="9761b-146">**-seq** is a sequential file.</span></span> <span data-ttu-id="9761b-147">**\<MB >**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="9761b-147">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="9761b-148">**-rt**: activar el modo de tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9761b-148">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="9761b-149">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9761b-149">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="9761b-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9761b-150">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="9761b-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="9761b-151">See Also</span></span>  
 [<span data-ttu-id="9761b-152">Solución de problemas de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="9761b-152">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)
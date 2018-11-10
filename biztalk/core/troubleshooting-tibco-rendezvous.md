---
title: Solución de problemas de TIBCO Rendezvous | Microsoft Docs
description: Usar el seguimiento de eventos de Windows para troubl = esdhoot Microsoft BizTalk Adapter para TIBCO Rendezvous en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b7bc3ab-16fa-4e91-8730-9431473b2fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c9f80b2d5426c6a967f9fe57d923971d1fa305
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752400"
---
# <a name="troubleshoot-tibco-rendezvous"></a><span data-ttu-id="7d7cf-103">Solución de problemas de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="7d7cf-103">Troubleshoot TIBCO Rendezvous</span></span>
  
## <a name="use-event-tracing-for-windows"></a><span data-ttu-id="7d7cf-104">Usar seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="7d7cf-104">Use Event Tracing for Windows</span></span>
<span data-ttu-id="7d7cf-105">Microsoft BizTalk Adapter para TIBCO Rendezvous registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-105">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="7d7cf-106">Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="7d7cf-106">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="7d7cf-107">Cuando se activa ETW, crea un \*archivo .etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-107">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="7d7cf-108">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-108">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="7d7cf-109">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-109">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="7d7cf-110">Por ejemplo, la aplicación tracerpt.exe convertirá el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-110">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="7d7cf-111">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="7d7cf-111">ETW Components</span></span>  
 <span data-ttu-id="7d7cf-112">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="7d7cf-112">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="7d7cf-113">**Aplicación de controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="7d7cf-113">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="7d7cf-114">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-114">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="7d7cf-115">Esto garantiza que las llamadas de BTATIBCO RendezvousTrace puedan localizar tracelog.exe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-115">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="7d7cf-116">De forma predeterminada, BTATIBCO RendezvousTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-116">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d7cf-117">tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO RendezvousTrace.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-117">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="7d7cf-118">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-118">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="7d7cf-119">**Aplicación de consumidor**: lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-119">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="7d7cf-120">Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="7d7cf-121">Normalmente esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-121">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="7d7cf-122">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<en tiempo Real\> = -rt.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="7d7cf-123">**Proveedor**: proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-123">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="7d7cf-124">BizTalk Adapter para TIBCO Rendezvous incluye tres proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-124">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="7d7cf-125">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="7d7cf-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="7d7cf-126">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="7d7cf-127">BizTalk Adapter para TIBCO Rendezvous tiene tres proveedores.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-127">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="7d7cf-128">Esto le permite registrar diferentes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="7d7cf-128">This lets you log different kinds of messages:</span></span>  
  
- <span data-ttu-id="7d7cf-129">**Proveedor de registro de receptor**: el \<elemento Trace\> modificador es **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="7d7cf-130">Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-130">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
- <span data-ttu-id="7d7cf-131">**Proveedor de registro de transmisor**: el \<elemento Trace\> modificador es **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-131">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="7d7cf-132">Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="7d7cf-133"><strong>Proveedor de registro de administración:</strong>el \<elemento Trace\> modificador es **-administración**.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-133"><strong>Management Logging Provider—</strong>the \<Trace element\> switch is **-management**.</span></span>  
  
   <span data-ttu-id="7d7cf-134">Use **-administración**para recibir cualquier mensaje del registro que se generaron durante la exploración del sistema del servidor.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-134">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="7d7cf-135">Comando BTATIBCORVTrace</span><span class="sxs-lookup"><span data-stu-id="7d7cf-135">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="7d7cf-136">Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Rendezvous, BTATIBCORVTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-136">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="7d7cf-137">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="7d7cf-137">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="7d7cf-138">Dónde: **\<elemento Trace\>** (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-138">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="7d7cf-139">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="7d7cf-139">Its options are as follows:</span></span>  
  
- <span data-ttu-id="7d7cf-140">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="7d7cf-140">**-transmitter**</span></span>  
  
- <span data-ttu-id="7d7cf-141">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="7d7cf-141">**-receiver**</span></span>  
  
- <span data-ttu-id="7d7cf-142">**-administración**</span><span class="sxs-lookup"><span data-stu-id="7d7cf-142">**-management**</span></span>  
  
- <span data-ttu-id="7d7cf-143">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-143">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="7d7cf-144">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-144">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="7d7cf-145">**-cir** es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-145">**-cir** is a circular file.</span></span> <span data-ttu-id="7d7cf-146">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-146">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="7d7cf-147">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-147">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="7d7cf-148">**-seq** es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-148">**-seq** is a sequential file.</span></span> <span data-ttu-id="7d7cf-149">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-149">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="7d7cf-150">**-rt**: activar el modo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="7d7cf-150">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="7d7cf-151">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7d7cf-151">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="7d7cf-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d7cf-152">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
## <a name="see-more"></a><span data-ttu-id="7d7cf-153">Ver más</span><span class="sxs-lookup"><span data-stu-id="7d7cf-153">See more</span></span>
[<span data-ttu-id="7d7cf-154">Controlar excepciones</span><span class="sxs-lookup"><span data-stu-id="7d7cf-154">Handle exceptions</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="7d7cf-155">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7d7cf-155">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)  
[<span data-ttu-id="7d7cf-156">Arquitectura</span><span class="sxs-lookup"><span data-stu-id="7d7cf-156">Architecture</span></span>](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)
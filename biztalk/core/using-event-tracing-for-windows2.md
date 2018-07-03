---
title: Uso de seguimiento de eventos para Windows2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f022035dd432e818c02289246a2d3a43849557
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980781"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="b08d4-102">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="b08d4-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="b08d4-103">Microsoft BizTalk Adapter para JD Edwards OneWorld registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="b08d4-103">Microsoft BizTalk Adapter for JD Edwards OneWorld logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="b08d4-104">Puede ver mensajes de seguimiento adicionales mediante la herramienta Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b08d4-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="b08d4-105">Cuando se activa ETW, crea un archivo \*.etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b08d4-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="b08d4-106">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="b08d4-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="b08d4-107">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl: por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="b08d4-107">To do this, you must have a consumer application available to interpret the \*.etl file: for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="b08d4-108">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="b08d4-108">ETW Components</span></span>  
 <span data-ttu-id="b08d4-109">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="b08d4-109">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="b08d4-110">**Aplicación de controlador.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-110">**Controller application.**</span></span> <span data-ttu-id="b08d4-111">Activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="b08d4-111">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="b08d4-112">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="b08d4-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="b08d4-113">Esto garantiza que las llamadas de BTAJDEdwardsOneWorldTrace pueden localizar tracelog.exe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="b08d4-113">This ensures that BTAJDEdwardsOneWorldTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="b08d4-114">De forma predeterminada, BTAJDEdwardsOneWorldTrace busca en la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="b08d4-114">By default, BTAJDEdwardsOneWorldTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b08d4-115">tracelog.exe está disponible en Microsoft SDK y es compatible con los comandos proporcionados por BizTalk Adapter para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="b08d4-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="b08d4-116">Para usar logman.exe consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="b08d4-116">To use logman.exe refer to the logman documentation.</span></span>  
  
- <span data-ttu-id="b08d4-117">**Aplicación de consumidor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-117">**Consumer application.**</span></span> <span data-ttu-id="b08d4-118">Lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="b08d4-118">Reads logged events.</span></span>  
  
   <span data-ttu-id="b08d4-119">Para que la aplicación de consumidor pueda leer el evento en el archivo .etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="b08d4-119">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="b08d4-120">Normalmente, esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b08d4-120">Normally this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="b08d4-121">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción en tiempo real,  **\<en tiempo Real\> = -rt**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-121">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
- <span data-ttu-id="b08d4-122">**Proveedor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-122">**Provider.**</span></span> <span data-ttu-id="b08d4-123">Proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="b08d4-123">Provides the event.</span></span>  
  
  <span data-ttu-id="b08d4-124">El Adaptador de BizTalk para J.D. Edwards OneWorld incluye cinco proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="b08d4-124">BizTalk Adapter for JD Edwards OneWorld includes five different providers.</span></span> <span data-ttu-id="b08d4-125">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="b08d4-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="b08d4-126">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="b08d4-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="b08d4-127">BizTalk Adapter para JD Edwards OneWorld tiene cinco proveedores, que permiten registrar diferentes clases de mensajes:</span><span class="sxs-lookup"><span data-stu-id="b08d4-127">BizTalk Adapter for JD Edwards OneWorld has five providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="b08d4-128">**Proveedor de registro de receptor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-128">**Receiver Logging Provider.**</span></span> <span data-ttu-id="b08d4-129">El \<elemento Trace\> modificador es **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-129">The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="b08d4-130">**Proveedor CastDetails de receptor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-130">**Receiver CastDetails Provider.**</span></span> <span data-ttu-id="b08d4-131">El \<elemento Trace\> modificador es **- castDetailsReceive**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-131">The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
- <span data-ttu-id="b08d4-132">**Proveedor de registro de transmisor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-132">**Transmitter Logging Provider.**</span></span> <span data-ttu-id="b08d4-133">El \<elemento Trace\> modificador es **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-133">The \<Trace element\> switch is **-transmitter**.</span></span>  
  
- <span data-ttu-id="b08d4-134">**Proveedor CastDetails de transmisor.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-134">**Transmitter CastDetails Provider.**</span></span> <span data-ttu-id="b08d4-135">El \<elemento Trace\> modificador es **- castDetailsTransmit**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-135">The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
- <span data-ttu-id="b08d4-136">**Proveedor de registro de administración.**</span><span class="sxs-lookup"><span data-stu-id="b08d4-136">**Management Logging Provider.**</span></span> <span data-ttu-id="b08d4-137">El \<elemento Trace\> modificador es **-administración**.</span><span class="sxs-lookup"><span data-stu-id="b08d4-137">The \<Trace element\> switch is **-management**.</span></span>  
  
  <span data-ttu-id="b08d4-138">Comando BTAJDEOneWorldTrace</span><span class="sxs-lookup"><span data-stu-id="b08d4-138">BTAJDEOneWorldTrace Command</span></span>  
  
  <span data-ttu-id="b08d4-139">Para usar ETW, ejecute el adaptador de BizTalk para el comando de JD Edwards OneWorld, BTAJDEOneWorldTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="b08d4-139">To use ETW, run the BizTalk Adapter for JD Edwards OneWorld command, BTAJDEOneWorldTrace.cmd.</span></span> <span data-ttu-id="b08d4-140">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="b08d4-140">You use this command as follows:</span></span>  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="b08d4-141">Donde:</span><span class="sxs-lookup"><span data-stu-id="b08d4-141">Where:</span></span>  
  
- <span data-ttu-id="b08d4-142">**\<Elemento Trace\>**  (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="b08d4-142">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
- <span data-ttu-id="b08d4-143">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="b08d4-143">Its options are:</span></span>  
  
  -   <span data-ttu-id="b08d4-144">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="b08d4-144">**-castDetailsTransmit**</span></span>  
  
  -   <span data-ttu-id="b08d4-145">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="b08d4-145">**-transmitter**</span></span>  
  
  -   <span data-ttu-id="b08d4-146">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="b08d4-146">**-castDetailsReceive**</span></span>  
  
  -   <span data-ttu-id="b08d4-147">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="b08d4-147">**-receiver**</span></span>  
  
  -   <span data-ttu-id="b08d4-148">**-administración**</span><span class="sxs-lookup"><span data-stu-id="b08d4-148">**-management**</span></span>  
  
  -   <span data-ttu-id="b08d4-149">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="b08d4-149">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
  -   <span data-ttu-id="b08d4-150">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="b08d4-150">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="b08d4-151">-cir es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="b08d4-151">-cir is a circular file.</span></span> <span data-ttu-id="b08d4-152">\<MB\>: tamaño en meg.</span><span class="sxs-lookup"><span data-stu-id="b08d4-152">\<MB\>: Size in meg.</span></span>  
  
  -   <span data-ttu-id="b08d4-153">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="b08d4-153">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="b08d4-154">-seq es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="b08d4-154">-seq is a sequential file.</span></span> <span data-ttu-id="b08d4-155">\<MB\>: tamaño en meg.</span><span class="sxs-lookup"><span data-stu-id="b08d4-155">\<MB\>: Size in meg.</span></span>  
  
  -   <span data-ttu-id="b08d4-156">**-rt**: activar el modo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b08d4-156">**-rt**: Set the real time mode on.</span></span>  
  
  -   <span data-ttu-id="b08d4-157">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b08d4-157">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="b08d4-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b08d4-158">For example:</span></span>  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="b08d4-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="b08d4-159">See Also</span></span>  
 [<span data-ttu-id="b08d4-160">Solución de problemas de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="b08d4-160">Troubleshooting JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)
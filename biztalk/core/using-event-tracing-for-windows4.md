---
title: Uso de seguimiento de eventos para Windows4 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75f5a62f2ae243c6fd3eabc5d40f99136471ad30
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752330"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="70e27-102">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="70e27-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="70e27-103">El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne registra mensajes de error, advertencia e información en el visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="70e27-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="70e27-104">Puede ver mensajes de seguimiento adicionales mediante la herramienta Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="70e27-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="70e27-105">Cuando se activa ETW, crea un \*archivo .etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="70e27-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="70e27-106">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="70e27-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="70e27-107">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl; por ejemplo, tracerpt.exe o tracedmp.ex.</span><span class="sxs-lookup"><span data-stu-id="70e27-107">To do this, you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.ex.</span></span> <span data-ttu-id="70e27-108">La aplicación tracept.exe convierte el \*.etl en dos archivos de texto: summary.txt y dumpfile.csv.</span><span class="sxs-lookup"><span data-stu-id="70e27-108">The tracept.exe application converts the \*.etl into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="70e27-109">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="70e27-109">ETW Components</span></span>  
 <span data-ttu-id="70e27-110">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="70e27-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="70e27-111">**Aplicación de controlador**.</span><span class="sxs-lookup"><span data-stu-id="70e27-111">**Controller application**.</span></span> <span data-ttu-id="70e27-112">Activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="70e27-112">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="70e27-113">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="70e27-113">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="70e27-114">De este modo se asegurará de que las llamadas BTAJDEEnterpriseOneTrace puedan localizar tracelog.exe en su sistema.</span><span class="sxs-lookup"><span data-stu-id="70e27-114">This ensures that BTAJDEEnterpriseOneTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="70e27-115">De forma predeterminada, BTAJDEEnterpriseOneTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="70e27-115">By default, BTAJDEEnterpriseOneTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70e27-116">tracelog.exe está disponible desde Microsoft SDK y es compatible con los comandos que proporciona el Adaptador de BizTalk para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="70e27-116">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by  BizTalk Adapter  for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="70e27-117">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="70e27-117">To use logman.exe, refer to the logman documentation.</span></span>  
  
- <span data-ttu-id="70e27-118">**Aplicación de consumidor**.</span><span class="sxs-lookup"><span data-stu-id="70e27-118">**Consumer application**.</span></span> <span data-ttu-id="70e27-119">Lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="70e27-119">Reads logged events.</span></span> <span data-ttu-id="70e27-120">Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="70e27-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="70e27-121">Normalmente, esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="70e27-121">Normally this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="70e27-122">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción en tiempo real,  **\<en tiempo Real\> = -rt**.</span><span class="sxs-lookup"><span data-stu-id="70e27-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
- <span data-ttu-id="70e27-123">**Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="70e27-123">**Provider**.</span></span> <span data-ttu-id="70e27-124">Se usa para proporcionar el evento.</span><span class="sxs-lookup"><span data-stu-id="70e27-124">Used to provide the event.</span></span> <span data-ttu-id="70e27-125">El Adaptador de BizTalk para JD Edwards EnterpriseOne incluye tres proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="70e27-125">BizTalk Adapter for JD Edwards EnterpriseOne includes three different providers.</span></span> <span data-ttu-id="70e27-126">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="70e27-126">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="70e27-127">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="70e27-127">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="70e27-128">El Adaptador de BizTalk para JD Edwards EnterpriseOne incluye tres proveedores diferentes, lo cual le permite registrar diferentes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="70e27-128">BizTalk Adapter  for JD Edwards EnterpriseOne contains three providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="70e27-129">**Proveedor de registro de receptor**: el \<elemento Trace\> modificador es **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="70e27-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span> <span data-ttu-id="70e27-130">Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70e27-130">Use **-receiver** to get any messages from the log that were received by the adapter at run time.</span></span>  
  
- <span data-ttu-id="70e27-131">**Proveedor de registro de transmisor**: el \<elemento Trace\> modificador es **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="70e27-131">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span> <span data-ttu-id="70e27-132">Use **-transmisor** para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70e27-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="70e27-133">**Proveedor de registro de administración**: el \<elemento Trace\> modificador es **-administración** Use **-administración** para recibir cualquier mensaje del registro que se generaron durante la exploración del sistema del servidor.</span><span class="sxs-lookup"><span data-stu-id="70e27-133">**Management Logging Provider**: The \<Trace element\> switch is **-management** Use **-management** to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
### <a name="btajdeenterpriseonetrace-command"></a><span data-ttu-id="70e27-134">Comando BTAJDEEnterpriseOneTrace</span><span class="sxs-lookup"><span data-stu-id="70e27-134">BTAJDEEnterpriseOneTrace Command</span></span>  
 <span data-ttu-id="70e27-135">Para usar ETW, ejecute el adaptador de BizTalk para JD Edwards EnterpriseOne comando, **BTAJDEEnterpriseOneTrace.cmd**.</span><span class="sxs-lookup"><span data-stu-id="70e27-135">To use ETW, run the BizTalk Adapter for JD Edwards EnterpriseOne command, **BTAJDEEnterpriseOneTrace.cmd**.</span></span> <span data-ttu-id="70e27-136">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="70e27-136">You use this command as follows:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 <span data-ttu-id="70e27-137">Dónde: **\<elemento Trace\>** (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="70e27-137">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="70e27-138">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="70e27-138">Its options are:</span></span>  
  
- <span data-ttu-id="70e27-139">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="70e27-139">**-transmitter**</span></span>  
  
- <span data-ttu-id="70e27-140">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="70e27-140">**-receiver**</span></span>  
  
- <span data-ttu-id="70e27-141">**-administración**</span><span class="sxs-lookup"><span data-stu-id="70e27-141">**-management**</span></span>  
  
- <span data-ttu-id="70e27-142">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="70e27-142">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="70e27-143">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="70e27-143">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="70e27-144">-cir es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="70e27-144">-cir is a circular file.</span></span> <span data-ttu-id="70e27-145">\<MB\>: tamaño en meg.</span><span class="sxs-lookup"><span data-stu-id="70e27-145">\<MB\>: Size in meg.</span></span>  
  
- <span data-ttu-id="70e27-146">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="70e27-146">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="70e27-147">-seq es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="70e27-147">-seq is a sequential file.</span></span> <span data-ttu-id="70e27-148">\<MB\>: tamaño en meg.</span><span class="sxs-lookup"><span data-stu-id="70e27-148">\<MB\>: Size in meg.</span></span>  
  
- <span data-ttu-id="70e27-149">**-rt**: activar el modo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="70e27-149">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="70e27-150">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="70e27-150">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="70e27-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70e27-151">For example:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="70e27-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="70e27-152">See Also</span></span>  
 [<span data-ttu-id="70e27-153">Solución de problemas de JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="70e27-153">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)
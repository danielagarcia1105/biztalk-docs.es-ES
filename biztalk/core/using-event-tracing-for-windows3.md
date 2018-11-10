---
title: Uso de seguimiento de eventos para Windows3 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d3b1869252b934d1f996f5021c1aa5cf888b19
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752836"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="716a6-102">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="716a6-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="716a6-103">Microsoft BizTalk Adapter para TIBCO Enterprise Message Service registra los mensajes de error, de advertencia e informativos en el Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="716a6-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="716a6-104">Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="716a6-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="716a6-105">Cuando se activa ETW, crea un \*archivo .etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="716a6-105">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="716a6-106">Este archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="716a6-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="716a6-107">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="716a6-107">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="716a6-108">Por ejemplo, la aplicación tracerpt.exe convierte el \*archivo .etl en dos archivos de texto: summary.txt y dumpfile.csv.</span><span class="sxs-lookup"><span data-stu-id="716a6-108">For example, the tracerpt.exe application converts the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="716a6-109">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="716a6-109">ETW Components</span></span>  
 <span data-ttu-id="716a6-110">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="716a6-110">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="716a6-111">**Aplicación de controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="716a6-111">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="716a6-112">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="716a6-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="716a6-113">Esto garantiza que las llamadas de BTATIBCO EMSTrace pueden localizar tracelog.exe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="716a6-113">This makes sure that BTATIBCO EMSTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="716a6-114">De forma predeterminada, BTATIBCO EMSTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="716a6-114">By default, BTATIBCO EMSTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="716a6-115">tracelog.exe está disponible en el Microsoft SDK y es compatible con los comandos proporcionados por Microsoft BizTalk Adapter para TIBCO Enterprise Message Service.</span><span class="sxs-lookup"><span data-stu-id="716a6-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="716a6-116">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="716a6-116">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="716a6-117">**Aplicación de consumidor**: lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="716a6-117">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="716a6-118">Para que la aplicación de consumidor pueda leer el evento en el archivo etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="716a6-118">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="716a6-119">Normalmente esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="716a6-119">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="716a6-120">Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<en tiempo Real\> = -rt.</span><span class="sxs-lookup"><span data-stu-id="716a6-120">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="716a6-121">**Proveedor**: proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="716a6-121">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="716a6-122">BizTalk Adapter para TIBCO Enterprise Message Service incluye tres proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="716a6-122">BizTalk Adapter for TIBCO Enterprise Message Service includes three different providers.</span></span> <span data-ttu-id="716a6-123">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="716a6-123">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="716a6-124">Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="716a6-124">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="716a6-125">BizTalk Adapter para TIBCO Enterprise Message Service tiene proveedores que permiten registrar diferentes clases de mensajes:</span><span class="sxs-lookup"><span data-stu-id="716a6-125">BizTalk Adapter for TIBCO Enterprise Message Service has providers that enable you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="716a6-126">**Proveedor de registro de receptor**: el \<elemento Trace\> modificador es **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="716a6-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
   <span data-ttu-id="716a6-127">Use **-receptor** para recibir cualquier mensaje del registro que se han recibido por el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="716a6-127">Use **-receiver** to obtain any messages from the log that were received by the adapter at run time.</span></span>  
  
- <span data-ttu-id="716a6-128">**Proveedor de registro de transmisor**: el \<elemento Trace\> modificador es **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="716a6-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="716a6-129">Use **-transmisor**para recibir cualquier mensaje del registro que haya transmitido el adaptador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="716a6-129">Use **-transmitter**to obtain any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
### <a name="btatibcoemstrace-command"></a><span data-ttu-id="716a6-130">Comando BTATIBCOEMSTrace</span><span class="sxs-lookup"><span data-stu-id="716a6-130">BTATIBCOEMSTrace Command</span></span>  
 <span data-ttu-id="716a6-131">Para usar ETW, ejecute el adaptador de BizTalk para el comando de TIBCO Enterprise Message Service, BTATIBCOEMSTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="716a6-131">To use ETW, run the BizTalk Adapter for TIBCO Enterprise Message Service command, BTATIBCOEMSTrace.cmd.</span></span> <span data-ttu-id="716a6-132">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="716a6-132">You use this command as follows:</span></span>  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="716a6-133">Donde:</span><span class="sxs-lookup"><span data-stu-id="716a6-133">Where:</span></span>  
  
- <span data-ttu-id="716a6-134">**\<Elemento Trace\>**  (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="716a6-134">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
  <span data-ttu-id="716a6-135">Sus opciones son:</span><span class="sxs-lookup"><span data-stu-id="716a6-135">Its options are as follows:</span></span>  
  
- <span data-ttu-id="716a6-136">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="716a6-136">**-transmitter**</span></span>  
  
- <span data-ttu-id="716a6-137">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="716a6-137">**-receiver**</span></span>  
  
- <span data-ttu-id="716a6-138">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="716a6-138">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="716a6-139">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="716a6-139">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="716a6-140">**-cir** es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="716a6-140">**-cir** is a circular file.</span></span> <span data-ttu-id="716a6-141">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="716a6-141">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="716a6-142">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="716a6-142">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="716a6-143">**-seq** es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="716a6-143">**-seq** is a sequential file.</span></span> <span data-ttu-id="716a6-144">**\<MB\>**: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="716a6-144">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="716a6-145">**-rt**: activar el modo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="716a6-145">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="716a6-146">**Archivo de registro**: nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="716a6-146">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="716a6-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="716a6-147">For example:</span></span>  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="716a6-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="716a6-148">See Also</span></span>  
 [<span data-ttu-id="716a6-149">Solución de problemas de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="716a6-149">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)
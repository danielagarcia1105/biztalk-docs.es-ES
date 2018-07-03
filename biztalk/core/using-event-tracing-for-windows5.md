---
title: Uso de seguimiento de eventos para Windows5 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fa744d7182f6238d71765afac2411b60974b5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000037"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="712dc-102">Uso de seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="712dc-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="712dc-103">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise registra mensajes de error, advertencia e información en el visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="712dc-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="712dc-104">Puede ver mensajes de seguimiento adicionales mediante la herramienta de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="712dc-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="712dc-105">Cuando está habilitado ETW, crea un archivo \*.etl para recibir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="712dc-105">When ETW is enabled, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="712dc-106">El archivo está en formato binario y se debe convertir para poder leerse.</span><span class="sxs-lookup"><span data-stu-id="712dc-106">The file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="712dc-107">Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl; por ejemplo, tracerpt.exe o tracedmp.exe.</span><span class="sxs-lookup"><span data-stu-id="712dc-107">To do this you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="712dc-108">Componentes de ETW</span><span class="sxs-lookup"><span data-stu-id="712dc-108">ETW Components</span></span>  
 <span data-ttu-id="712dc-109">Seguimiento de eventos para Windows tiene tres componentes:</span><span class="sxs-lookup"><span data-stu-id="712dc-109">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="712dc-110">**Aplicación de controlador**: activa y desactiva un proveedor (por ejemplo, tracelog.exe o logman.exe).</span><span class="sxs-lookup"><span data-stu-id="712dc-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="712dc-111">Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="712dc-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="712dc-112">De este modo se asegurará de que las llamadas `BTAPeopleSoftTrace` puedan localizar tracelog.exe en su sistema.</span><span class="sxs-lookup"><span data-stu-id="712dc-112">This makes sure that `BTAPeopleSoftTrace` calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="712dc-113">De forma predeterminada, BTAPeopleSoftTrace busca la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="712dc-113">By default, BTAPeopleSoftTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="712dc-114">tracelog.exe está disponible desde Microsoft SDK y es compatible con los comandos que proporciona el Adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="712dc-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="712dc-115">Para usar logman.exe, consulte la documentación de logman.</span><span class="sxs-lookup"><span data-stu-id="712dc-115">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="712dc-116">**Aplicación de consumidor**: lee eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="712dc-116">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="712dc-117">Para que la aplicación de consumidor pueda leer el evento en el archivo .etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="712dc-117">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="712dc-118">Normalmente esto se realiza cuando el controlador desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="712dc-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="712dc-119">Para usar el consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción de tiempo real, \<en tiempo Real\> = -rt.</span><span class="sxs-lookup"><span data-stu-id="712dc-119">To use the consumer without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="712dc-120">**Proveedor:** proporciona el evento.</span><span class="sxs-lookup"><span data-stu-id="712dc-120">**Provider:** Provides the event.</span></span>  
  
   <span data-ttu-id="712dc-121">El Adaptador de BizTalk para PeopleSoft Enterprise tiene cinco proveedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="712dc-121">BizTalk Adapter for PeopleSoft Enterprise has five different providers.</span></span> <span data-ttu-id="712dc-122">Están registrados en el Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="712dc-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="712dc-123">Para encontrar los proveedores registrados en el **root\WMI\EventTrace** ruta de acceso, puede usar herramientas tales como WMI CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="712dc-123">To find the registered providers in the **root\WMI\EventTrace** path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="712dc-124">El Adaptador de BizTalk para PeopleSoft Enterprise incluye cinco proveedores, lo cual le permite registrar diferentes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="712dc-124">BizTalk Adapter for PeopleSoft Enterprise has five providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="712dc-125">**Proveedor de registro de receptor**: el \<elemento Trace\> modificador es **-receptor**.</span><span class="sxs-lookup"><span data-stu-id="712dc-125">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="712dc-126">**Proveedor CastDetails de receptor**: el \<elemento Trace\> modificador es **- castDetailsReceive**.</span><span class="sxs-lookup"><span data-stu-id="712dc-126">**Receiver CastDetails Provider**: The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
- <span data-ttu-id="712dc-127">**Proveedor de registro de transmisor**: el \<elemento Trace\> modificador es **-transmisor**.</span><span class="sxs-lookup"><span data-stu-id="712dc-127">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span>  
  
- <span data-ttu-id="712dc-128">**Proveedor CastDetails de transmisor**: el \<elemento Trace\> modificador es **- castDetailsTransmit**.</span><span class="sxs-lookup"><span data-stu-id="712dc-128">**Transmitter CastDetails Provider**: The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
- <span data-ttu-id="712dc-129">**Proveedor de registro de administración**: el \<elemento Trace\> modificador es **-administración**.</span><span class="sxs-lookup"><span data-stu-id="712dc-129">**Management Logging Provider**: The \<Trace element\> switch is **-management**.</span></span>  
  
## <a name="btapeoplesofttrace-command"></a><span data-ttu-id="712dc-130">Comando BTAPeopleSoftTrace</span><span class="sxs-lookup"><span data-stu-id="712dc-130">BTAPeopleSoftTrace Command</span></span>  
 <span data-ttu-id="712dc-131">Para usar ETW, ejecute el comando adaptador **BTAPeopleSoftTrace.cmd**.</span><span class="sxs-lookup"><span data-stu-id="712dc-131">To use ETW, run the adapter command, **BTAPeopleSoftTrace.cmd**.</span></span> <span data-ttu-id="712dc-132">Use este comando como sigue:</span><span class="sxs-lookup"><span data-stu-id="712dc-132">You use this command as follows:</span></span>  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="712dc-133">Donde:</span><span class="sxs-lookup"><span data-stu-id="712dc-133">Where:</span></span>  
  
- <span data-ttu-id="712dc-134">\<Elemento Trace\> (obligatorio) es el tipo de proveedor.</span><span class="sxs-lookup"><span data-stu-id="712dc-134">\<Trace element\> (required) is the kind of provider.</span></span>  
  
   <span data-ttu-id="712dc-135">Las opciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="712dc-135">Options are as follows:</span></span>  
  
  -   <span data-ttu-id="712dc-136">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="712dc-136">**-castDetailsTransmit**</span></span>  
  
  -   <span data-ttu-id="712dc-137">**-transmisor**</span><span class="sxs-lookup"><span data-stu-id="712dc-137">**-transmitter**</span></span>  
  
  -   <span data-ttu-id="712dc-138">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="712dc-138">**-castDetailsReceive**</span></span>  
  
  -   <span data-ttu-id="712dc-139">**-receptor**</span><span class="sxs-lookup"><span data-stu-id="712dc-139">**-receiver**</span></span>  
  
  -   <span data-ttu-id="712dc-140">**-administración**</span><span class="sxs-lookup"><span data-stu-id="712dc-140">**-management**</span></span>  
  
  -   <span data-ttu-id="712dc-141">**-iniciar, - detener**: activar o desactivar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="712dc-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="712dc-142">**-cir \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="712dc-142">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="712dc-143">-cir es un archivo circular.</span><span class="sxs-lookup"><span data-stu-id="712dc-143">-cir is a circular file.</span></span> <span data-ttu-id="712dc-144">\<MB\>: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="712dc-144">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="712dc-145">**-seq \<MB\>**: tamaño y tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="712dc-145">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="712dc-146">-seq es un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="712dc-146">-seq is a sequential file.</span></span> <span data-ttu-id="712dc-147">\<MB\>: tamaño en megabytes.</span><span class="sxs-lookup"><span data-stu-id="712dc-147">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="712dc-148">**-rt**: activar el modo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="712dc-148">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="712dc-149">**Archivo de registro**: nombre del archivo de registro (C:\rtlog.etl es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="712dc-149">**Logfile**: Name of the log file (C:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="712dc-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="712dc-150">For example:</span></span>  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="712dc-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="712dc-151">See Also</span></span>  
 [<span data-ttu-id="712dc-152">Solución de problemas de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="712dc-152">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)
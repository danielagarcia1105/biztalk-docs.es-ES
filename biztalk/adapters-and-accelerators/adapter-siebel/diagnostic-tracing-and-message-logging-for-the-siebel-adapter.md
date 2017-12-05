---
title: "Seguimiento de diagnóstico y el registro de mensajes para el adaptador de Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6b27dd6d169c9ea7e5012be3e03329e6888522
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a><span data-ttu-id="3ad6b-102">Seguimiento de diagnóstico y registro de mensajes para el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="3ad6b-102">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>
<span data-ttu-id="3ad6b-103">Los clientes de adaptador pueden habilitar el seguimiento de diagnóstico diagnosticar eficazmente los problemas que se producen durante el uso de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-103">Adapter clients can enable diagnostic tracing to effectively diagnose problems encountered while using the adapters.</span></span> <span data-ttu-id="3ad6b-104">Los clientes de adaptador pueden activar el seguimiento en tres niveles diferentes:</span><span class="sxs-lookup"><span data-stu-id="3ad6b-104">Adapter clients can activate tracing at three different levels:</span></span>  
  
-   <span data-ttu-id="3ad6b-105">Entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="3ad6b-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="3ad6b-106">En el adaptador</span><span class="sxs-lookup"><span data-stu-id="3ad6b-106">Within the adapter</span></span>  
  
-   <span data-ttu-id="3ad6b-107">Entre el adaptador y la aplicación de línea de negocio (LOB)</span><span class="sxs-lookup"><span data-stu-id="3ad6b-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
 <span data-ttu-id="3ad6b-108">Esta sección proporciona información acerca de cómo activar el seguimiento en estos niveles.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="3ad6b-109">Seguimiento entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="3ad6b-109">Tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="3ad6b-110">Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="3ad6b-111">Seguimiento de WCF se usa para realizar el seguimiento de la entrada XML que llega desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-111">WCF tracing is used to trace the input XMLs coming from the adapter client using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="3ad6b-112">No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="3ad6b-113">Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="3ad6b-114">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="3ad6b-115">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-115">**Tracing at design-time**.</span></span> <span data-ttu-id="3ad6b-116">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ad6b-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="3ad6b-117">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ad6b-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="3ad6b-118">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="3ad6b-119">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-119">**Tracing at run-time**.</span></span> <span data-ttu-id="3ad6b-120">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="3ad6b-121">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="3ad6b-122">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="3ad6b-123">Para habilitar el seguimiento de WCF, debe agregar el extracto siguiente dentro de la `<configuration>` etiqueta:</span><span class="sxs-lookup"><span data-stu-id="3ad6b-123">To enable WCF tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>
  
```  
<system.diagnostics>  
    <sources>  
      <source name ="System.ServiceModel" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.ServiceModel.MessageLogging"   
              switchValue="Verbose, ActivityTracing">          
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.Runtime.Serialization" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
   </sources>  
   <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"                
           traceOutputOptions="LogicalOperationStack"   
           initializeData="C:\log\WCFTrace.svclog" />  
   </sharedListeners>  
   <trace autoflush="true" />  
  </system.diagnostics>  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  </system.serviceModel>  
```  
  
 <span data-ttu-id="3ad6b-124">Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="3ad6b-125">[Seguimiento de WCF](https://msdn.microsoft.com/library/ms730342.aspx) proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-125">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more info.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="3ad6b-126">Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="3ad6b-127">Vea [las prácticas recomendadas para proteger el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="3ad6b-127">See [Best practices to secure the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span></span> 
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="3ad6b-128">Seguimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="3ad6b-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="3ad6b-129">Los adaptadores de BizTalk Adapter Pack registrar diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias e información.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-129">The adapters in the BizTalk Adapter Pack log different categories of useful information to the trace file such as errors, warnings, and information.</span></span> <span data-ttu-id="3ad6b-130">Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="3ad6b-131">Puede activar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-131">You can activate [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="3ad6b-132">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="3ad6b-133">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-133">**Tracing at design-time**.</span></span> <span data-ttu-id="3ad6b-134">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ad6b-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="3ad6b-135">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ad6b-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="3ad6b-136">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="3ad6b-137">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-137">**Tracing at run-time**.</span></span> <span data-ttu-id="3ad6b-138">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="3ad6b-139">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="3ad6b-140">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="3ad6b-141">Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el adaptador de seguimiento, debe agregar el extracto siguiente dentro de la `<configuration>` etiqueta:</span><span class="sxs-lookup"><span data-stu-id="3ad6b-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Siebel" switchValue="Information">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"   
   traceOutputOptions="LogicalOperationStack"   
          initializeData="C:\log\AdapterTrace.svclog" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="3ad6b-142">Esto debería guardar los seguimientos WCF en C:\log\AdapterTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-142">This would save the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="3ad6b-143">Seguimiento entre el adaptador y la aplicación de LOB</span><span class="sxs-lookup"><span data-stu-id="3ad6b-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="3ad6b-144">Debe habilitar el seguimiento para la comunicación entre el adaptador y la aplicación de LOB para diagnosticar problemas de que sospecha dentro de la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-144">You must enable tracing for communication between the adapter and the LOB application to diagnose issues you suspect within the LOB application.</span></span> <span data-ttu-id="3ad6b-145">Adaptadores también dependen de LOB seguimiento (lado del cliente/servidor) para obtener acceso a esta información.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-145">Adapters also depend on LOB tracing (client/server side) to get access to this information.</span></span> <span data-ttu-id="3ad6b-146">Las características específicas de activar el seguimiento de LOB se excluyen de este documento.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-146">The specifics of turning on LOB tracing are excluded from this document.</span></span>  
  
 <span data-ttu-id="3ad6b-147">Además, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona una propiedad de enlace (**LogData**), que si se establece en **True** y si el nivel de seguimiento se establece en **detallado**, [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] registra el flujo de información entre el adaptador y el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-147">Additionally, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides a binding property (**LogData**), which if set to **True** and if the trace level is set to **Verbose**, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] logs the information flow between the adapter and the Siebel system.</span></span> <span data-ttu-id="3ad6b-148">Esta información se registra junto con los seguimientos de adaptador en el mismo archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-148">This information is logged along with the adapter traces in the same trace file.</span></span>  
  
 <span data-ttu-id="3ad6b-149">Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3ad6b-149">For more information about this binding property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="3ad6b-150">Ver los seguimientos</span><span class="sxs-lookup"><span data-stu-id="3ad6b-150">Viewing the Traces</span></span>  
 <span data-ttu-id="3ad6b-151">Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="3ad6b-152">Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx).</span><span class="sxs-lookup"><span data-stu-id="3ad6b-152">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="3ad6b-153">Configuración del seguimiento de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3ad6b-153">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="3ad6b-154">La consola de administración de BizTalk le permite configurar diversas opciones de seguimiento para elementos tales como puertos de envío, puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-154">The BizTalk Administration Console enables you to configure various tracking options for things such as send ports, receive ports.</span></span> <span data-ttu-id="3ad6b-155">El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada/salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-155">The tracking configuration settings enable you to track inbound/outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="3ad6b-156">Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte [administrar artefactos](../../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="3ad6b-156">For more information about configuring tracking for BizTalk applications, see [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
<span data-ttu-id="3ad6b-157">También puede utilizar el concentrador de grupo a [ver realiza el seguimiento de mensajes y datos de la instancia](../../core/viewing-tracked-message-and-instance-data.md), que incluye una lista de comprobación de seguimiento y los procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="3ad6b-157">You can also use Group Hub to [Viewing Tracked Message and Instance Data](../../core/viewing-tracked-message-and-instance-data.md), including a tracking checklist, and best practices.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ad6b-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ad6b-158">See Also</span></span>  
[<span data-ttu-id="3ad6b-159">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="3ad6b-159">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
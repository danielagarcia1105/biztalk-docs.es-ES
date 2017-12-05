---
title: "Seguimiento de diagnóstico y el registro de mensajes en el adaptador de SQL | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae089d91a245fe6b261a0b0b8f92f7f52a4d4af
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a><span data-ttu-id="62aef-102">Seguimiento de diagnóstico y el registro de mensajes en el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="62aef-102">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>
<span data-ttu-id="62aef-103">Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="62aef-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="62aef-104">Los clientes de adaptador pueden activar el seguimiento de diagnóstico en dos niveles:</span><span class="sxs-lookup"><span data-stu-id="62aef-104">Adapter clients can activate diagnostic tracing at two levels:</span></span>  
  
-   <span data-ttu-id="62aef-105">Entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="62aef-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="62aef-106">En el adaptador</span><span class="sxs-lookup"><span data-stu-id="62aef-106">Within the adapter</span></span>  
  
 <span data-ttu-id="62aef-107">Esta sección proporciona información acerca de cómo activar el seguimiento en estos niveles.</span><span class="sxs-lookup"><span data-stu-id="62aef-107">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="62aef-108">Seguimiento entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="62aef-108">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="62aef-109">Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="62aef-109">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="62aef-110">Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización.</span><span class="sxs-lookup"><span data-stu-id="62aef-110">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="62aef-111">No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="62aef-111">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="62aef-112">Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="62aef-112">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="62aef-113">Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="62aef-113">Also, you can enable tracing both at design time and run time.</span></span>  
  
-   <span data-ttu-id="62aef-114">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="62aef-114">**Tracing at design time**.</span></span> <span data-ttu-id="62aef-115">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62aef-115">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="62aef-116">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62aef-116">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="62aef-117">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="62aef-117">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="62aef-118">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="62aef-118">**Tracing at run time**.</span></span> <span data-ttu-id="62aef-119">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="62aef-119">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="62aef-120">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="62aef-120">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="62aef-121">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="62aef-121">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="62aef-122">Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="62aef-122">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="62aef-123">Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="62aef-123">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="62aef-124">Para obtener más información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).</span><span class="sxs-lookup"><span data-stu-id="62aef-124">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="62aef-125">Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="62aef-125">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="62aef-126">Para obtener recomendaciones vea [las prácticas recomendadas para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="62aef-126">For recommendations see [Best practices to secure the SQL adapter](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span></span>
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="62aef-127">Seguimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="62aef-127">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="62aef-128">Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="62aef-128">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="62aef-129">Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="62aef-129">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="62aef-130">Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="62aef-130">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="62aef-131">Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="62aef-131">Also, you can enable tracing both at design time and run time.</span></span>  
  
-   <span data-ttu-id="62aef-132">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="62aef-132">**Tracing at design time**.</span></span> <span data-ttu-id="62aef-133">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62aef-133">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="62aef-134">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62aef-134">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="62aef-135">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="62aef-135">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="62aef-136">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="62aef-136">**Tracing at run time**.</span></span> <span data-ttu-id="62aef-137">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="62aef-137">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="62aef-138">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="62aef-138">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="62aef-139">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="62aef-139">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="62aef-140">Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="62aef-140">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Sql" switchValue="Information">  
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
  
 <span data-ttu-id="62aef-141">Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="62aef-141">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="62aef-142">Ver los seguimientos</span><span class="sxs-lookup"><span data-stu-id="62aef-142">Viewing the Traces</span></span>  
 <span data-ttu-id="62aef-143">Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="62aef-143">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="62aef-144">Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y problemas](https://msdn.microsoft.com/library/aa751795.aspx).</span><span class="sxs-lookup"><span data-stu-id="62aef-144">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="62aef-145">Configuración del seguimiento de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="62aef-145">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="62aef-146">La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="62aef-146">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="62aef-147">El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="62aef-147">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="62aef-148">Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte la [administrar artefactos](../../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="62aef-148">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="62aef-149">También puede usar el estado y el seguimiento de actividad (HAT) para ver los datos históricos o controlados.</span><span class="sxs-lookup"><span data-stu-id="62aef-149">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="62aef-150">Para obtener más información, consulte [ver históricos y realiza el seguimiento de datos](../../core/viewing-historical-and-tracked-data.md).</span><span class="sxs-lookup"><span data-stu-id="62aef-150">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62aef-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="62aef-151">See Also</span></span>  
 [<span data-ttu-id="62aef-152">Solucionar problemas del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="62aef-152">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
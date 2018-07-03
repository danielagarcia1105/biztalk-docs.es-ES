---
title: Seguimiento de diagnóstico y registro de mensajes en el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fbcdac66c40a4b1d9c2b35d2f8268a63c8bd0e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968157"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a><span data-ttu-id="474f3-102">Seguimiento de diagnóstico y registro de mensajes en el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="474f3-102">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>
<span data-ttu-id="474f3-103">Seguimiento de diagnóstico le ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="474f3-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="474f3-104">Los clientes del adaptador pueden activar el seguimiento de diagnóstico en dos niveles:</span><span class="sxs-lookup"><span data-stu-id="474f3-104">Adapter clients can activate diagnostic tracing at two levels:</span></span>  
  
- <span data-ttu-id="474f3-105">Entre el cliente del adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="474f3-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="474f3-106">En el adaptador</span><span class="sxs-lookup"><span data-stu-id="474f3-106">Within the adapter</span></span>  
  
  <span data-ttu-id="474f3-107">Esta sección proporciona información sobre cómo activar el seguimiento en estos niveles.</span><span class="sxs-lookup"><span data-stu-id="474f3-107">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="474f3-108">Seguimiento entre el cliente del adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="474f3-108">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="474f3-109">Los clientes del adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente del adaptador y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="474f3-109">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="474f3-110">Seguimiento de WCF se usa para realizar un seguimiento de la que procede el cliente del adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="474f3-110">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="474f3-111">No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente del adaptador.</span><span class="sxs-lookup"><span data-stu-id="474f3-111">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="474f3-112">Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="474f3-112">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="474f3-113">Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="474f3-113">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="474f3-114">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="474f3-114">**Tracing at design time**.</span></span> <span data-ttu-id="474f3-115">La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="474f3-115">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="474f3-116">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="474f3-116">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="474f3-117">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="474f3-117">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="474f3-118">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="474f3-118">**Tracing at run time**.</span></span> <span data-ttu-id="474f3-119">Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.</span><span class="sxs-lookup"><span data-stu-id="474f3-119">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="474f3-120">Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="474f3-120">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="474f3-121">Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="474f3-121">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="474f3-122">Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="474f3-122">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="474f3-123">Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="474f3-123">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="474f3-124">Para obtener más información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).</span><span class="sxs-lookup"><span data-stu-id="474f3-124">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="474f3-125">Asegúrese de que mitigar posibles amenazas de seguridad de exponer los datos empresariales confidenciales mediante la habilitación del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="474f3-125">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="474f3-126">Para obtener recomendaciones vea [procedimientos recomendados para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="474f3-126">For recommendations see [Best practices to secure the SQL adapter](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span></span>
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="474f3-127">Seguimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="474f3-127">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="474f3-128">Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento, como errores, advertencias y mensajes de información.</span><span class="sxs-lookup"><span data-stu-id="474f3-128">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="474f3-129">Dicha información es útil comprender el flujo del proceso del adaptador y diagnosticar problemas con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="474f3-129">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="474f3-130">Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y seguimiento de adaptador para aplicaciones de BizTalk y WCF del servicio de aplicaciones de modelo mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="474f3-130">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="474f3-131">Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="474f3-131">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="474f3-132">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="474f3-132">**Tracing at design time**.</span></span> <span data-ttu-id="474f3-133">La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="474f3-133">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="474f3-134">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="474f3-134">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="474f3-135">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="474f3-135">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="474f3-136">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="474f3-136">**Tracing at run time**.</span></span> <span data-ttu-id="474f3-137">Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.</span><span class="sxs-lookup"><span data-stu-id="474f3-137">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="474f3-138">Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="474f3-138">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="474f3-139">Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="474f3-139">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="474f3-140">Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="474f3-140">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="474f3-141">Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="474f3-141">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="474f3-142">Ver los seguimientos</span><span class="sxs-lookup"><span data-stu-id="474f3-142">Viewing the Traces</span></span>  
 <span data-ttu-id="474f3-143">Puede usar la herramienta Service Trace Viewer de Windows Communication Foundation (WCF) para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="474f3-143">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="474f3-144">Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver seguimientos correlacionados y problemas](https://msdn.microsoft.com/library/aa751795.aspx).</span><span class="sxs-lookup"><span data-stu-id="474f3-144">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="474f3-145">Configuración del seguimiento de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="474f3-145">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="474f3-146">La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos como puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="474f3-146">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="474f3-147">Seguimiento de lo valores de configuración permiten realizar un seguimiento de los datos de eventos de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="474f3-147">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="474f3-148">Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte el [administrar artefactos](../../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="474f3-148">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="474f3-149">También puede utilizar el estado y el seguimiento de actividad (HAT) para ver los datos históricos o controlados.</span><span class="sxs-lookup"><span data-stu-id="474f3-149">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="474f3-150">Para obtener más información, consulte [ver históricos y datos de seguimiento](../../core/viewing-historical-and-tracked-data.md).</span><span class="sxs-lookup"><span data-stu-id="474f3-150">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="474f3-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="474f3-151">See Also</span></span>  
 [<span data-ttu-id="474f3-152">Solucionar problemas del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="474f3-152">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
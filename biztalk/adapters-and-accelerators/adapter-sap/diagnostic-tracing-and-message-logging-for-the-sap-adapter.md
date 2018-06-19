---
title: Seguimiento de diagnóstico y el registro de mensajes para el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and adapter
- tracing, within the adapter
- tracing, between the adapter and the LOB application
- troubleshooting, tracing and logging
ms.assetid: 5c60af54-896d-4873-acbf-32fbcd051ee2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb5565141521c08e295a9d5cee88406c16df7de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007180"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a><span data-ttu-id="9e243-102">Seguimiento de diagnóstico y registro de mensajes para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="9e243-102">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>
<span data-ttu-id="9e243-103">Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="9e243-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="9e243-104">Los clientes de adaptador pueden activar el seguimiento de diagnóstico en tres niveles:</span><span class="sxs-lookup"><span data-stu-id="9e243-104">Adapter clients can activate diagnostic tracing at three levels:</span></span>  
  
-   <span data-ttu-id="9e243-105">Entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="9e243-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="9e243-106">En el adaptador</span><span class="sxs-lookup"><span data-stu-id="9e243-106">Within the adapter</span></span>  
  
-   <span data-ttu-id="9e243-107">Entre el adaptador y la aplicación de línea de negocio (LOB)</span><span class="sxs-lookup"><span data-stu-id="9e243-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
 <span data-ttu-id="9e243-108">Esta sección proporciona información acerca de cómo activar el seguimiento en estos niveles.</span><span class="sxs-lookup"><span data-stu-id="9e243-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="9e243-109">Seguimiento entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="9e243-109">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="9e243-110">Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="9e243-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="9e243-111">Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización.</span><span class="sxs-lookup"><span data-stu-id="9e243-111">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="9e243-112">No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="9e243-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="9e243-113">Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e243-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="9e243-114">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e243-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="9e243-115">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="9e243-115">**Tracing at design-time**.</span></span> <span data-ttu-id="9e243-116">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e243-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="9e243-117">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e243-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="9e243-118">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="9e243-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="9e243-119">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="9e243-119">**Tracing at run-time**.</span></span> <span data-ttu-id="9e243-120">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="9e243-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="9e243-121">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e243-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="9e243-122">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e243-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="9e243-123">Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9e243-123">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="9e243-124">Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="9e243-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="9e243-125">Para obtener más información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e243-125">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="9e243-126">Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e243-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="9e243-127">Para obtener recomendaciones vea [las prácticas recomendadas para proteger el adaptador SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9e243-127">For recommendations see [Best practices to secure the SAP adapter](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md).</span></span>  
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="9e243-128">Seguimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="9e243-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="9e243-129">Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="9e243-129">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="9e243-130">Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="9e243-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="9e243-131">Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e243-131">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="9e243-132">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e243-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="9e243-133">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="9e243-133">**Tracing at design-time**.</span></span> <span data-ttu-id="9e243-134">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e243-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="9e243-135">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e243-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="9e243-136">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="9e243-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="9e243-137">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="9e243-137">**Tracing at run-time**.</span></span> <span data-ttu-id="9e243-138">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="9e243-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="9e243-139">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e243-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="9e243-140">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e243-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="9e243-141">Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9e243-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.SAP" switchValue="Information">  
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
  
 <span data-ttu-id="9e243-142">Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="9e243-142">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="9e243-143">Seguimiento entre el adaptador y la aplicación de LOB</span><span class="sxs-lookup"><span data-stu-id="9e243-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="9e243-144">Para diagnosticar problemas que sospecha que están relacionados con la aplicación de LOB, debe habilitar el seguimiento para la comunicación entre el adaptador y la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="9e243-144">To diagnose issues that you suspect are related to the LOB application, you must enable tracing for communication between the adapter and the LOB application.</span></span> <span data-ttu-id="9e243-145">Adaptadores también dependen de LOB seguimiento (lado del cliente/servidor) para tener acceso a esta información.</span><span class="sxs-lookup"><span data-stu-id="9e243-145">Adapters also depend on LOB tracing (client/server side) to access this information.</span></span> <span data-ttu-id="9e243-146">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes de adaptador activar el seguimiento en el sistema SAP especificando el parámetro "RfcSdkTrace" en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e243-146">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enables adapter clients to turn on tracing within the SAP system by specifying the "RfcSdkTrace" parameter in the connection URI.</span></span> <span data-ttu-id="9e243-147">Debe especificar este parámetro para habilitar la RFC SDK al flujo de información de seguimiento en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="9e243-147">You must specify this parameter to enable the RFC SDK to trace information flow within the SAP system.</span></span> <span data-ttu-id="9e243-148">Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="9e243-148">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="9e243-149">Además, también puede crear una variable de entorno RFC_TRACE que establece el nivel de seguimiento de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="9e243-149">Additionally, you can also create an RFC_TRACE environment variable that sets the level of tracing for the RFC SDK.</span></span> <span data-ttu-id="9e243-150">RFC_TRACE es una variable de entorno definida por SAP y se usa el SDK de RFC.</span><span class="sxs-lookup"><span data-stu-id="9e243-150">RFC_TRACE is an environment variable defined by SAP and is used by the RFC SDK.</span></span> <span data-ttu-id="9e243-151">Si esta variable no está definida o se establece en 0, el nivel de seguimiento de RFC SDK es mínimo.</span><span class="sxs-lookup"><span data-stu-id="9e243-151">If this variable is not defined or is set to 0, the RFC SDK tracing level is bare minimum.</span></span> <span data-ttu-id="9e243-152">Si la variable se establece en 1 o 2, más se detalla el nivel de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e243-152">If the variable is set to 1 or 2, the tracing level is more detailed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e243-153">Independientemente de si se establece la variable de entorno RFC_TRACE, está habilitado el seguimiento de RFC SDK *sólo* si el parámetro "RfcSdkTrace" se establece en true en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e243-153">Irrespective of whether the RFC_TRACE environment variable is set, the RFC SDK tracing is enabled *only* if the "RfcSdkTrace" parameter is set to true in the connection URI.</span></span> <span data-ttu-id="9e243-154">El valor de esta variable de entorno únicamente controla el nivel de seguimiento de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="9e243-154">The value of this environment variable solely governs the level of RFC SDK tracing.</span></span> <span data-ttu-id="9e243-155">Si RfcSdkTrace se establece en true, el mensaje de seguimientos entre el adaptador y el sistema SAP se copian en la carpeta "system32" en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9e243-155">If RfcSdkTrace is set to true, the message traces between the adapter and the SAP system are copied to the “system32” folder on your computer.</span></span> <span data-ttu-id="9e243-156">Para guardar los seguimientos de RFC SDK en alguna otra ubicación, puede establecer la variable de entorno RFC_TRACE_DIR.</span><span class="sxs-lookup"><span data-stu-id="9e243-156">To save the RFC SDK traces to some other location, you can set the RFC_TRACE_DIR environment variable.</span></span> <span data-ttu-id="9e243-157">Para obtener más información acerca de estas variables de entorno, consulte la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="9e243-157">For more information about these environment variables refer to the SAP documentation.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="9e243-158">Ver los seguimientos</span><span class="sxs-lookup"><span data-stu-id="9e243-158">Viewing the Traces</span></span>  
 <span data-ttu-id="9e243-159">Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="9e243-159">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="9e243-160">Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y problemas](https://msdn.microsoft.com/library/aa751795.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e243-160">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="9e243-161">Configuración del seguimiento de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9e243-161">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="9e243-162">La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e243-162">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="9e243-163">El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="9e243-163">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="9e243-164">Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte la [administrar artefactos](../../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="9e243-164">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="9e243-165">También puede usar el estado y el seguimiento de actividad (HAT) para ver los datos históricos o controlados.</span><span class="sxs-lookup"><span data-stu-id="9e243-165">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="9e243-166">Para obtener más información, consulte [ver históricos y realiza el seguimiento de datos](../../core/viewing-historical-and-tracked-data.md).</span><span class="sxs-lookup"><span data-stu-id="9e243-166">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="9e243-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e243-167">See Also</span></span>  
[<span data-ttu-id="9e243-168">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="9e243-168">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
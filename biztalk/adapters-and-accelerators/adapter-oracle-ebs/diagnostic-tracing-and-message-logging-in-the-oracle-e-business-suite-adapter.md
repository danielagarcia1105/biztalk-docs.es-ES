---
title: Seguimiento de diagnóstico y el registro de mensajes en el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de2444cecbd661e9af4457f5f19c7e929d1c9c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007149"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="92285-102">Seguimiento de diagnóstico y el registro de mensajes en el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="92285-102">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="92285-103">Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="92285-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="92285-104">Este tema proporciona información acerca de los tres tipos siguientes de la traza compatibles con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="92285-104">This topic provides information about the following three types of tracing supported with [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="92285-105">Seguimiento de servidor de Oracle con un identificador de cliente</span><span class="sxs-lookup"><span data-stu-id="92285-105">Oracle server-side tracing using a client identifier</span></span>
  
-   <span data-ttu-id="92285-106">Seguimiento de WCF entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="92285-106">WCF tracing between the adapter client and the adapter</span></span>
  
-   <span data-ttu-id="92285-107">Seguimiento de WCF en el adaptador</span><span class="sxs-lookup"><span data-stu-id="92285-107">WCF tracing within the adapter</span></span>
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a><span data-ttu-id="92285-108">Con un identificador de cliente seguimiento de servidor de Oracle</span><span class="sxs-lookup"><span data-stu-id="92285-108">Oracle server side tracing using a client identifier</span></span>  
 <span data-ttu-id="92285-109">Oracle permite realizar un seguimiento del servidor para las operaciones realizadas por las aplicaciones cliente en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="92285-109">Oracle allows you to perform server-side tracing for the operations performed by client applications on the Oracle database.</span></span> <span data-ttu-id="92285-110">Dado que las solicitudes de las aplicaciones cliente se pueden enrutar a las sesiones de base de datos diferente, es difícil realizar un seguimiento del origen de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="92285-110">Because requests from client applications can be routed to different database sessions, it becomes difficult to trace the origin of the request.</span></span> <span data-ttu-id="92285-111">Sin embargo, Oracle facilita el seguimiento de la aplicación de extremo a extremo mediante identificadores de cliente.</span><span class="sxs-lookup"><span data-stu-id="92285-111">However, Oracle facilitates end-to-end application tracing using client identifiers.</span></span> 
 
 <span data-ttu-id="92285-112">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el `OracleConnectionClientId` enlaza la propiedad que le permite especificar el identificador de cliente en el tiempo de diseño para la conexión utilizada por el adaptador para conectar con Oracle.</span><span class="sxs-lookup"><span data-stu-id="92285-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the `OracleConnectionClientId` binding property that allows you to specify the client identifier at the design time for the connection used by the adapter to connect to Oracle.</span></span> <span data-ttu-id="92285-113">El identificador de cliente del adaptador le ayuda a en el seguimiento selectivo de las operaciones realizadas por el cliente de adaptador en Oracle y también permite filtrar y ver los seguimientos de servidor de Oracle basados en el identificador de cliente.</span><span class="sxs-lookup"><span data-stu-id="92285-113">The adapter client identifier helps you in selective tracing of the operations performed by the adapter client on Oracle, and also allows you to filter and view the Oracle server traces based on the client identifier.</span></span> <span data-ttu-id="92285-114">Para obtener información acerca de cómo se puede habilitar el seguimiento de los identificadores de cliente de Oracle, vea [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746).</span><span class="sxs-lookup"><span data-stu-id="92285-114">For information about how you can enable tracing for client identifiers in Oracle, see [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746).</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="92285-115">Seguimiento de WCF entre el cliente de adaptador y el adaptador</span><span class="sxs-lookup"><span data-stu-id="92285-115">WCF tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="92285-116">Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador.</span><span class="sxs-lookup"><span data-stu-id="92285-116">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="92285-117">Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización.</span><span class="sxs-lookup"><span data-stu-id="92285-117">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="92285-118">No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador.</span><span class="sxs-lookup"><span data-stu-id="92285-118">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="92285-119">Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="92285-119">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="92285-120">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="92285-120">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="92285-121">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="92285-121">**Tracing at design-time**.</span></span> <span data-ttu-id="92285-122">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92285-122">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="92285-123">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92285-123">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="92285-124">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="92285-124">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="92285-125">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="92285-125">**Tracing at run-time**.</span></span> <span data-ttu-id="92285-126">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="92285-126">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="92285-127">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="92285-127">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="92285-128">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="92285-128">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="92285-129">Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta:</span><span class="sxs-lookup"><span data-stu-id="92285-129">To enable WCF tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
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
  
 <span data-ttu-id="92285-130">Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="92285-130">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="92285-131">[Seguimiento de WCF](https://msdn.microsoft.com/library/ms730342.aspx) proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="92285-131">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more information.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="92285-132">Asegúrese de que mitigar posibles amenazas de seguridad de exponer los datos empresariales confidenciales que pueden producirse cuando la habilitación del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="92285-132">Make sure you mitigate potential security threats of exposing sensitive business data that can be caused when enabling tracing.</span></span> <span data-ttu-id="92285-133">Para obtener recomendaciones, consulte el [prácticas recomendadas para el mensaje y seguimiento de datos de instancia](../../core/best-practices-for-message-and-instance-data-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="92285-133">For recommendations, see the [Best Practices for Message and Instance Data Tracking](../../core/best-practices-for-message-and-instance-data-tracking.md).</span></span>  
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="92285-134">Seguimiento de WCF en el adaptador</span><span class="sxs-lookup"><span data-stu-id="92285-134">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="92285-135">Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="92285-135">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="92285-136">Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="92285-136">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="92285-137">Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes.</span><span class="sxs-lookup"><span data-stu-id="92285-137">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="92285-138">Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="92285-138">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="92285-139">**Seguimiento en tiempo de diseño**.</span><span class="sxs-lookup"><span data-stu-id="92285-139">**Tracing at design-time**.</span></span> <span data-ttu-id="92285-140">Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92285-140">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="92285-141">Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92285-141">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="92285-142">Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="92285-142">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="92285-143">**Seguimiento en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="92285-143">**Tracing at run-time**.</span></span> <span data-ttu-id="92285-144">Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="92285-144">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="92285-145">Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], este archivo está disponible normalmente en \<unidad de instalación\>: \Program [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92285-145">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], this file is available typically under \<installation drive\>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="92285-146">Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="92285-146">For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="92285-147">Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.</span><span class="sxs-lookup"><span data-stu-id="92285-147">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="92285-148">Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta:</span><span class="sxs-lookup"><span data-stu-id="92285-148">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.OracleEBS" switchValue="Information">  
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
  
 <span data-ttu-id="92285-149">Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.</span><span class="sxs-lookup"><span data-stu-id="92285-149">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="92285-150">Ver los seguimientos</span><span class="sxs-lookup"><span data-stu-id="92285-150">Viewing the traces</span></span>  
 <span data-ttu-id="92285-151">Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="92285-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="92285-152">[Con Service Trace Viewer para ver los seguimientos correlacionados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx) proporcionan más detalles acerca de esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="92285-152">[Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx) provides more details on this tool.</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="92285-153">Configuración del seguimiento de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="92285-153">Configuring tracking for BizTalk applications</span></span>  
 <span data-ttu-id="92285-154">La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="92285-154">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="92285-155">El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="92285-155">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="92285-156">Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte [administración y los artefactos de seguimiento](../../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="92285-156">For more information about configuring tracking for BizTalk applications, see [Managing and tracking your artifacts](../../core/managing-artifacts.md).</span></span>  
  
 <span data-ttu-id="92285-157">También puede utilizar el concentrador de grupo a [ver datos de instancias y mensajes de seguimiento](../../core/viewing-tracked-message-and-instance-data.md), incluyendo los procedimientos recomendados, guardar las consultas de seguimiento y mucho más.</span><span class="sxs-lookup"><span data-stu-id="92285-157">You can also use Group Hub to [view tracked message and instance data](../../core/viewing-tracked-message-and-instance-data.md), including best practices, saving tracking queries, and more.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92285-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="92285-158">See Also</span></span>  
[<span data-ttu-id="92285-159">Solucionar problemas del adaptador</span><span class="sxs-lookup"><span data-stu-id="92285-159">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
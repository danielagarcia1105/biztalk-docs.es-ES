---
title: "Seguimiento de diagnóstico y el registro de mensajes para el adaptador SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and adapter
- tracing, within the adapter
- tracing, between the adapter and the LOB application
- troubleshooting, tracing and logging
ms.assetid: 5c60af54-896d-4873-acbf-32fbcd051ee2
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aab9debbc619d2524063c1228c63745c6481d42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a>Seguimiento de diagnóstico y registro de mensajes para el adaptador SAP
Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores. Los clientes de adaptador pueden activar el seguimiento de diagnóstico en tres niveles:  
  
-   Entre el cliente de adaptador y el adaptador  
  
-   En el adaptador  
  
-   Entre el adaptador y la aplicación de línea de negocio (LOB)  
  
 Esta sección proporciona información acerca de cómo activar el seguimiento en estos niveles.  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento entre el cliente de adaptador y el adaptador  
 Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador. Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación >*: \Program Visual Studio  *\<versión >*\Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], este archivo está disponible normalmente en \<unidad de instalación >: \Program [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
  \<system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  \</system.serviceModel>  
```  
  
 Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog. Para obtener más información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx). 
  
> [!IMPORTANT]
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento. Para obtener recomendaciones vea [las prácticas recomendadas para proteger el adaptador SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md).  
  
## <a name="tracing-within-the-adapter"></a>Seguimiento del adaptador  
 Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos. Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador. Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación >*: \Program Visual Studio  *\<versión >*\Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], este archivo está disponible normalmente en \<unidad de instalación >: \Program [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
```  
  
 Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>Seguimiento entre el adaptador y la aplicación de LOB  
 Para diagnosticar problemas que sospecha que están relacionados con la aplicación de LOB, debe habilitar el seguimiento para la comunicación entre el adaptador y la aplicación de LOB. Adaptadores también dependen de LOB seguimiento (lado del cliente/servidor) para tener acceso a esta información. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] permite a los clientes de adaptador activar el seguimiento en el sistema SAP especificando el parámetro "RfcSdkTrace" en el URI de conexión. Debe especificar este parámetro para habilitar la RFC SDK al flujo de información de seguimiento en el sistema SAP. Para obtener más información sobre el URI de conexión, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
 Además, también puede crear una variable de entorno RFC_TRACE que establece el nivel de seguimiento de RFC SDK. RFC_TRACE es una variable de entorno definida por SAP y se usa el SDK de RFC. Si esta variable no está definida o se establece en 0, el nivel de seguimiento de RFC SDK es mínimo. Si la variable se establece en 1 o 2, más se detalla el nivel de seguimiento.  
  
> [!NOTE]
>  Independientemente de si se establece la variable de entorno RFC_TRACE, está habilitado el seguimiento de RFC SDK *sólo* si el parámetro "RfcSdkTrace" se establece en true en el URI de conexión. El valor de esta variable de entorno únicamente controla el nivel de seguimiento de RFC SDK. Si RfcSdkTrace se establece en true, el mensaje de seguimientos entre el adaptador y el sistema SAP se copian en la carpeta "system32" en el equipo. Para guardar los seguimientos de RFC SDK en alguna otra ubicación, puede establecer la variable de entorno RFC_TRACE_DIR. Para obtener más información acerca de estas variables de entorno, consulte la documentación de SAP.  
  
## <a name="viewing-the-traces"></a>Ver los seguimientos  
 Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos. Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y problemas](https://msdn.microsoft.com/library/aa751795.aspx).
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción. El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte la [administrar artefactos](../../core/managing-artifacts.md).
  
 También puede usar el estado y el seguimiento de actividad (HAT) para ver los datos históricos o controlados. Para obtener más información, consulte [ver históricos y realiza el seguimiento de datos](../../core/viewing-historical-and-tracked-data.md).
 
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
---
title: Seguimiento de diagnóstico y el registro de mensajes para el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6b27dd6d169c9ea7e5012be3e03329e6888522
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006533"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a>Seguimiento de diagnóstico y registro de mensajes para el adaptador de Siebel
Los clientes de adaptador pueden habilitar el seguimiento de diagnóstico diagnosticar eficazmente los problemas que se producen durante el uso de los adaptadores. Los clientes de adaptador pueden activar el seguimiento en tres niveles diferentes:  
  
-   Entre el cliente de adaptador y el adaptador  
  
-   En el adaptador  
  
-   Entre el adaptador y la aplicación de línea de negocio (LOB)  
  
 Esta sección proporciona información acerca de cómo activar el seguimiento en estos niveles.  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento entre el cliente de adaptador y el adaptador  
 Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador. Seguimiento de WCF se usa para realizar el seguimiento de la entrada XML que llega desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar el seguimiento de WCF, debe agregar el extracto siguiente dentro de la `<configuration>` etiqueta:
  
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
  
 Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog. [Seguimiento de WCF](https://msdn.microsoft.com/library/ms730342.aspx) proporciona más información.
  
> [!IMPORTANT]
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento. Vea [las prácticas recomendadas para proteger el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md) 
  
## <a name="tracing-within-the-adapter"></a>Seguimiento del adaptador  
 Los adaptadores de BizTalk Adapter Pack registrar diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias e información. Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador. Puede activar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el adaptador de seguimiento, debe agregar el extracto siguiente dentro de la `<configuration>` etiqueta:  
  
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
  
 Esto debería guardar los seguimientos WCF en C:\log\AdapterTrace.svclog.  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>Seguimiento entre el adaptador y la aplicación de LOB  
 Debe habilitar el seguimiento para la comunicación entre el adaptador y la aplicación de LOB para diagnosticar problemas de que sospecha dentro de la aplicación de LOB. Adaptadores también dependen de LOB seguimiento (lado del cliente/servidor) para obtener acceso a esta información. Las características específicas de activar el seguimiento de LOB se excluyen de este documento.  
  
 Además, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona una propiedad de enlace (**LogData**), que si se establece en **True** y si el nivel de seguimiento se establece en **detallado**, [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] registra el flujo de información entre el adaptador y el sistema Siebel. Esta información se registra junto con los seguimientos de adaptador en el mismo archivo de seguimiento.  
  
 Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  
  
## <a name="viewing-the-traces"></a>Ver los seguimientos  
 Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos. Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver los seguimientos correlacionados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx).  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk le permite configurar diversas opciones de seguimiento para elementos tales como puertos de envío, puertos de recepción. El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada/salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte [administrar artefactos](../../core/managing-artifacts.md).
  
También puede utilizar el concentrador de grupo a [ver realiza el seguimiento de mensajes y datos de la instancia](../../core/viewing-tracked-message-and-instance-data.md), que incluye una lista de comprobación de seguimiento y los procedimientos recomendados.
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
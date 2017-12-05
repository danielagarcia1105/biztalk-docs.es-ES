---
title: "Seguimiento de diagnóstico y el registro de mensajes en el adaptador de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de2444cecbd661e9af4457f5f19c7e929d1c9c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a>Seguimiento de diagnóstico y el registro de mensajes en el adaptador de Oracle E-Business Suite
Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores. Este tema proporciona información acerca de los tres tipos siguientes de la traza compatibles con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   Seguimiento de servidor de Oracle con un identificador de cliente
  
-   Seguimiento de WCF entre el cliente de adaptador y el adaptador
  
-   Seguimiento de WCF en el adaptador
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a>Con un identificador de cliente seguimiento de servidor de Oracle  
 Oracle permite realizar un seguimiento del servidor para las operaciones realizadas por las aplicaciones cliente en la base de datos de Oracle. Dado que las solicitudes de las aplicaciones cliente se pueden enrutar a las sesiones de base de datos diferente, es difícil realizar un seguimiento del origen de la solicitud. Sin embargo, Oracle facilita el seguimiento de la aplicación de extremo a extremo mediante identificadores de cliente. 
 
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el `OracleConnectionClientId` enlaza la propiedad que le permite especificar el identificador de cliente en el tiempo de diseño para la conexión utilizada por el adaptador para conectar con Oracle. El identificador de cliente del adaptador le ayuda a en el seguimiento selectivo de las operaciones realizadas por el cliente de adaptador en Oracle y también permite filtrar y ver los seguimientos de servidor de Oracle basados en el identificador de cliente. Para obtener información acerca de cómo se puede habilitar el seguimiento de los identificadores de cliente de Oracle, vea [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746).  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento de WCF entre el cliente de adaptador y el adaptador  
 Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador. Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta:  
  
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
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer los datos empresariales confidenciales que pueden producirse cuando la habilitación del seguimiento. Para obtener recomendaciones, consulte el [prácticas recomendadas para el mensaje y seguimiento de datos de instancia](../../core/best-practices-for-message-and-instance-data-tracking.md).  
  
## <a name="wcf-tracing-within-the-adapter"></a>Seguimiento de WCF en el adaptador  
 Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos. Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador. Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>*\Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], este archivo está disponible normalmente en \<unidad de instalación\>: \Program [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
 Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta:  
  
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
  
 Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.  
  
## <a name="viewing-the-traces"></a>Ver los seguimientos  
 Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos. [Con Service Trace Viewer para ver los seguimientos correlacionados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx) proporcionan más detalles acerca de esta herramienta.  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción. El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte [administración y los artefactos de seguimiento](../../core/managing-artifacts.md).  
  
 También puede utilizar el concentrador de grupo a [ver datos de instancias y mensajes de seguimiento](../../core/viewing-tracked-message-and-instance-data.md), incluyendo los procedimientos recomendados, guardar las consultas de seguimiento y mucho más.
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
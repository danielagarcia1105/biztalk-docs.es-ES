---
title: Seguimiento de diagnóstico y registro de mensajes en el adaptador de Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: 00bf78bcc7c6589889691de7ec6c20621f1883ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985957"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a>Seguimiento de diagnóstico y registro de mensajes en el adaptador de Oracle E-Business Suite
Seguimiento de diagnóstico le ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores. En este tema se proporciona información acerca de los tres tipos siguientes de la traza compatible con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   Seguimiento de servidor de Oracle con un identificador de cliente
  
-   Seguimiento entre el cliente del adaptador y el adaptador de WCF
  
-   Seguimiento de WCF dentro del adaptador
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a>Con un identificador de cliente seguimiento de servidor de Oracle  
 Oracle permite realizar el seguimiento del lado servidor para las operaciones realizadas por las aplicaciones cliente en la base de datos de Oracle. Dado que las solicitudes de las aplicaciones cliente pueden enrutarse a las sesiones de base de datos diferente, resulta difícil realizar un seguimiento del origen de la solicitud. Sin embargo, facilita el seguimiento de la aplicación de extremo a otro con los identificadores de cliente Oracle. 
 
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone el `OracleConnectionClientId` enlaza la propiedad que le permite especificar el identificador de cliente en el tiempo de diseño para la conexión utilizada por el adaptador para conectarse a Oracle. El identificador de cliente de adaptador le ayuda en el seguimiento selectivo de las operaciones realizadas por el cliente del adaptador de Oracle y también le permite filtrar y ver los seguimientos del servidor de Oracle en función del identificador de cliente. Para obtener información acerca de cómo puede habilitar el seguimiento para los identificadores de cliente de Oracle, vea [ http://go.microsoft.com/fwlink/p/?LinkId=135746 ](http://go.microsoft.com/fwlink/p/?LinkId=135746).  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento entre el cliente del adaptador y el adaptador de WCF  
 Los clientes del adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente del adaptador y el adaptador. Seguimiento de WCF se usa para realizar un seguimiento de la que procede el cliente del adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización XML de entrada. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente del adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
- **Seguimiento en tiempo de diseño**. La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.  
  
- **Seguimiento en tiempo de ejecución**. Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.  
  
  - Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.  
  
  - Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.  
  
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
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer los datos empresariales confidenciales que se pueden producir cuando la habilitación del seguimiento. Para obtener recomendaciones, consulte el [prácticas recomendadas para el mensaje y seguimiento de datos de instancia](../../core/best-practices-for-message-and-instance-data-tracking.md).  
  
## <a name="wcf-tracing-within-the-adapter"></a>Seguimiento de WCF dentro del adaptador  
 Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento, como errores, advertencias y mensajes de información. Dicha información es útil comprender el flujo del proceso del adaptador y diagnosticar problemas con el adaptador. Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y seguimiento de adaptador para aplicaciones de BizTalk y WCF del servicio de aplicaciones de modelo mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
- **Seguimiento en tiempo de diseño**. La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.  
  
- **Seguimiento en tiempo de ejecución**. Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.  
  
  - Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.  
  
  - Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.  
  
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
 Puede usar la herramienta Service Trace Viewer de Windows Communication Foundation (WCF) para ver los seguimientos. [Uso de Service Trace Viewer para ver seguimientos correlacionados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx) proporciona más detalles sobre esta herramienta.  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos como puertos de envío y puertos de recepción. Seguimiento de lo valores de configuración permiten realizar un seguimiento de los datos de eventos de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte [administración y seguimiento de los artefactos](../../core/managing-artifacts.md).  
  
 También puede utilizar el concentrador de grupo a [ver datos de instancias y mensajes de seguimiento](../../core/viewing-tracked-message-and-instance-data.md), incluidos los procedimientos recomendados, guardar las consultas de seguimiento y mucho más.
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
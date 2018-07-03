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
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a>Seguimiento de diagnóstico y registro de mensajes en el adaptador de SQL
Seguimiento de diagnóstico le ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores. Los clientes del adaptador pueden activar el seguimiento de diagnóstico en dos niveles:  
  
- Entre el cliente del adaptador y el adaptador  
  
- En el adaptador  
  
  Esta sección proporciona información sobre cómo activar el seguimiento en estos niveles.  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento entre el cliente del adaptador y el adaptador  
 Los clientes del adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente del adaptador y el adaptador. Seguimiento de WCF se usa para realizar un seguimiento de la que procede el cliente del adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización XML de entrada. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente del adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.  
  
- **Seguimiento en tiempo de diseño**. La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.  
  
- **Seguimiento en tiempo de ejecución**. Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.  
  
  - Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.  
  
  - Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.  
  
  Para habilitar el seguimiento de WCF, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.  
  
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
  
 Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog. Para obtener más información acerca del seguimiento de WCF, vea [seguimiento](https://msdn.microsoft.com/library/ms730342.aspx).  
  
> [!IMPORTANT]
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer los datos empresariales confidenciales mediante la habilitación del seguimiento. Para obtener recomendaciones vea [procedimientos recomendados para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).
  
## <a name="tracing-within-the-adapter"></a>Seguimiento del adaptador  
 Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento, como errores, advertencias y mensajes de información. Dicha información es útil comprender el flujo del proceso del adaptador y diagnosticar problemas con el adaptador. Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y seguimiento de adaptador para aplicaciones de BizTalk y WCF del servicio de aplicaciones de modelo mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento tanto en tiempo de diseño y tiempo de ejecución.  
  
- **Seguimiento en tiempo de diseño**. La experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el fragmento al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Files\Microsoft Visual Studio  *\<versión\>* \Common7\IDE.  
  
- **Seguimiento en tiempo de ejecución**. Para el seguimiento de tiempo de ejecución, debe agregar el extracto dependiendo de la aplicación que usa.  
  
  - Para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación, debe agregar el fragmento al archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program Files\Microsoft BizTalk Server.  
  
  - Para una aplicación .NET de modelo de servicio WCF, debe agregar el fragmento al archivo app.config del proyecto.  
  
  Para habilitar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y el seguimiento del adaptador, agregue el siguiente extracto dentro de la `<configuration>` etiqueta.  
  
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
  
 Esto guarda los seguimientos WCF en C:\log\AdapterTrace.svclog.  
  
## <a name="viewing-the-traces"></a>Ver los seguimientos  
 Puede usar la herramienta Service Trace Viewer de Windows Communication Foundation (WCF) para ver los seguimientos. Para obtener más información acerca de la herramienta, consulte [utilizando Service Trace Viewer para ver seguimientos correlacionados y problemas](https://msdn.microsoft.com/library/aa751795.aspx).
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos como puertos de envío y puertos de recepción. Seguimiento de lo valores de configuración permiten realizar un seguimiento de los datos de eventos de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. Para obtener más información acerca de cómo configurar el seguimiento de las aplicaciones de BizTalk, consulte el [administrar artefactos](../../core/managing-artifacts.md).
  
 También puede utilizar el estado y el seguimiento de actividad (HAT) para ver los datos históricos o controlados. Para obtener más información, consulte [ver históricos y datos de seguimiento](../../core/viewing-historical-and-tracked-data.md).
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador SQL](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
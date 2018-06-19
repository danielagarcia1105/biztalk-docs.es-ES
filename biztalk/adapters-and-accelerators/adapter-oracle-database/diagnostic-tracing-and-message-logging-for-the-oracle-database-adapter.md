---
title: Seguimiento de diagnóstico y registro de mensajes para el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing
- message logging
- tracing, within the adapter
- tracing, between the adapter client and the adapter
ms.assetid: 971d34e4-5609-42c6-85b9-d9b1989fc47d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d3b7dc5c4feb78abb71360de4497aa20c9e9638
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006197"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a>Seguimiento de diagnóstico y registro de mensajes para el adaptador de la base de datos de Oracle
Seguimiento de diagnóstico ayuda a diagnosticar eficazmente los problemas que pueden surgir al usar los adaptadores. Este tema proporciona información acerca de los dos tipos siguientes de la traza compatibles con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   Seguimiento de WCF entre el cliente de adaptador y el adaptador  
  
-   Seguimiento de WCF en el adaptador  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>Seguimiento de WCF entre el cliente de adaptador y el adaptador  
 Los clientes de adaptador pueden habilitar el seguimiento de WCF para problemas de seguimiento entre el cliente de adaptador y el adaptador. Seguimiento de WCF se usa para realizar un seguimiento el XML de entrada que recibe desde el cliente de adaptador mediante el modelo de servicio WCF y es útil para diagnosticar problemas de serialización. No se utiliza el seguimiento de WCF para el modelo de canal WCF o mensajes de salida desde el adaptador para el cliente de adaptador. Puede activar el seguimiento de WCF para aplicaciones de BizTalk y aplicaciones de modelo de servicio WCF mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
    -   Para una aplicación .NET de modelo de servicio WCF, debe agregar el extracto en el archivo app.config del proyecto.  
  
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
  
 Esto guarda los seguimientos WCF en C:\log\WCFTrace.svclog. [Seguimiento de WCF](https://msdn.microsoft.com/library/ms730342.aspx) proporciona más información adecuada.
  
> [!IMPORTANT]
>  Asegúrese de que mitigar posibles amenazas de seguridad de exponer datos empresariales confidenciales mediante la habilitación del seguimiento. Para obtener recomendaciones, consulte [las prácticas recomendadas para proteger el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)
  
## <a name="wcf-tracing-within-the-adapter"></a>Seguimiento de WCF en el adaptador  
 Los adaptadores de registro diferentes categorías de información útil en el archivo de seguimiento como errores, advertencias y mensajes informativos. Esta información es útil comprender el flujo del proceso en el adaptador y diagnosticar problemas con el adaptador. Puede activar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y adaptador traza de aplicaciones de BizTalk y WCF aplicaciones de modelo de servicio mediante la adición de un extracto a los archivos de configuración correspondientes. Además, puede habilitar el seguimiento en tiempo de diseño y en tiempo de ejecución.  
  
-   **Seguimiento en tiempo de diseño**. Para la experiencia en tiempo de diseño, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Todas estas herramientas pueden usarse desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Por lo tanto, para habilitar el seguimiento de la experiencia en tiempo de diseño, debe agregar el extracto al archivo devenv.exe.config que se encuentra en  *\<unidad de instalación\>*: \Program Visual Studio  *\<versión\>* \Common7\IDE.  
  
-   **Seguimiento en tiempo de ejecución**. Para el seguimiento del tiempo de ejecución, debe agregar el extracto según la aplicación que esté utilizando.  
  
    -   Para una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] de las aplicaciones, debe agregar el extracto en el archivo de configuración de BizTalk, normalmente BTSNTSvc.exe.config. Para que BizTalk Server, este archivo está disponible normalmente en \<unidad de instalación\>: \Program BizTalk Server.  
  
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
      <source name=" Microsoft.Adapters.OracleDB" switchValue="Information">  
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
 Puede usar la herramienta de Visor de seguimiento de servicio de Windows Communication Foundation (WCF) para ver los seguimientos. Vea [utilizando Service Trace Viewer para ver seguimientos asociados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx).
  
## <a name="configuring-tracking-for-biztalk-applications"></a>Configuración del seguimiento de las aplicaciones de BizTalk  
 La consola de administración de BizTalk Server le permite configurar diversas opciones de seguimiento de elementos, como los puertos de envío y puertos de recepción. El seguimiento de valores de configuración permiten realizar un seguimiento de los datos del evento de entrada y salida, propiedades del mensaje, cuerpos de mensajes y orquestaciones. [Administrar artefactos](../../core/managing-artifacts.md) incluye más información. 

  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)
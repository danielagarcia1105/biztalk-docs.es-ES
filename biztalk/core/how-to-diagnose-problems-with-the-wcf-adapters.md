---
title: Cómo diagnosticar problemas con los adaptadores de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 997a4ecd-6077-45d6-82d3-3f658ca62fd4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9bcb513704753363e054d689d2409925ffcd483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995389"
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a>Cómo diagnosticar problemas con los adaptadores de WCF
Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con los adaptadores de WCF.  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>Compruebe si existen errores detallados en el registro IIS y HTTPERR del servidor IIS  
  
- Los archivos de registro del servidor IIS de origen o de destino pueden contener información útil para la solución de problemas con los adaptadores de WCF aislados. De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación de la [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directorio en el servidor IIS.  
  
   De manera predeterminada, los archivos de registro de HTTPERR en equipos basados en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] están ubicados en el directorio siguiente:  
  
  > [!NOTE]
  >  El archivo de registro de HTTPERR únicamente está disponible en equipos basados en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  
  
   <em>% WinDir %\\</em>system32\LogFiles\HTTPERR\  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a>Utilizar el registro de mensajes WCF para la supervisión de los errores y el diagnóstico de problemas derivados de los adaptadores de WCF  
  
1. WCF ofrece la posibilidad de registrar los mensajes entrantes y salientes para el consumo fuera de línea. Puede utilizar el registro de mensajes para ver qué aspecto tienen los mensajes entrantes y salientes a través de los adaptadores de WCF. WCF no registra los mensajes de forma predeterminada. Para activar el registro de mensajes, debe modificar los archivos de configuración que utilizan los adaptadores de WCF. Para obtener más información sobre el registro de mensajes WCF, consulte "Registro de mensajes" en [ http://go.microsoft.com/fwlink/?LinkId=89003 ](http://go.microsoft.com/fwlink/?LinkId=89003).  
  
2. Para los adaptadores WCF en curso, puede habilitar el registro de mensajes WCF modificando el archivo de configuración de la aplicación, **BTSNtSvc.exe.config**, para **BTSNtSvc.exe**. El archivo de configuración puede encontrarse en la ruta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si ha instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la ubicación predeterminada, BtsNtSvc.exe estará en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
3. Para los adaptadores WCF aislados, puede habilitar el registro de mensajes WCF modificando el **Web.config** archivo que el Asistente para publicación de servicio WCF de BizTalk crea en la carpeta de aplicación Web.  
  
4. Para modificar **BTSNtSvc.exe.config** o **Web.config**, abra el archivo de configuración con el Bloc de notas y, a continuación, configurar el registro de mensaje WCF, como se indica en el siguiente ejemplo de configuración:  
  
   ```  
   <configuration>  
     <system.serviceModel>  
       <diagnostics>  
         <messageLogging   
              logEntireMessage="true"   
              logMalformedMessages="false"  
              logMessagesAtServiceLevel="true"   
              logMessagesAtTransportLevel="true"  
              maxMessagesToLog="300000"  
              maxSizeOfMessageToLog="200000"   
       />  
       </diagnostics>  
     </system.serviceModel>  
  
     <system.diagnostics>  
       <sources>  
         <source name="System.ServiceModel.MessageLogging">  
           <listeners>  
             <add name="messages"  
             type="System.Diagnostics.XmlWriterTraceListener"  
             initializeData="c:\wcfTrace.e2e" />  
           </listeners>  
         </source>  
       </sources>  
     </system.diagnostics>  
   </configuration>  
   ```  
  
5. Puede utilizar la herramienta Service Trace Viewer de Windows Communication Foundation (WCF) para analizar los mensajes registrados por WCF. Service Trace Viewer está incluida en el kit de desarrollo de software (SDK) de Microsoft Windows de los componentes en tiempo de ejecución de [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] y Windows Vista. Puede descargar el SDK de Windows desde Microsoft Download Center en [ http://go.microsoft.com/fwlink/?LinkID=75636 ](http://go.microsoft.com/fwlink/?LinkID=75636). Para obtener más información sobre el uso de esta herramienta, vea "herramienta Service Trace Viewer (SvcTraceViewer.exe [ http://go.microsoft.com/fwlink/?LinkId=88991 ](http://go.microsoft.com/fwlink/?LinkId=88991).  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a>Devolver información de excepción administrada al cliente si se produce un error de SOAP para una depuración sencilla.  
  
1. Puede seleccionar la **incluir excepción en errores** opción WCF estándar para la ubicación de recepción para devolver información de excepción administrada al cliente en errores SOAP para facilitar la depuración. Use los pasos siguientes para seleccionar el **incluir excepción en errores** opción.  
  
   1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **Ubicaciones de recepción**, haga clic en una ubicación de recepción mediante un adaptador de WCF estándar y, a continuación, haga clic en **propiedades**.  
  
   2. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **configurar**.  
  
   3. En el cuadro de diálogo de transporte, en el **mensajes** ficha, seleccione el **incluir excepción en errores** opción.  
  
2. Si usas el WCF-Custom o el adaptador WCF-CustomIsolated, puede establecer el **IncludeExceptionDetailInFaults** propiedad de la [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004) para devolver información de excepción administrada a la cliente. Para ello, siga estos pasos:  
  
   1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **Ubicaciones de recepción**, haga clic en una ubicación de recepción con el WCF-Custom o el adaptador WCF-CustomIsolated y, a continuación, haga clic en **propiedades**.  
  
   2. En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **configurar**.  
  
   3. En el cuadro de diálogo de transporte, en el **comportamiento** pestaña, haga clic en el **ServiceBehavior** nodo y, a continuación, haga clic en **Agregar extensión**.  
  
   4. En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **serviceDebug**y, a continuación, haga clic en **Aceptar**.  
  
   5. En el cuadro de diálogo de transporte, en el **comportamiento** pestaña, haga clic en el **serviceDebug** nodo y, a continuación, seleccione **True** para el **includeExceptionDetail** propiedad en el **configuración** vista de lista.  
  
   > [!NOTE]
   >  La devolución de información de excepción administrada a los clientes puede suponer un riesgo para la seguridad, ya que los detalles de la excepción exponen información acerca de la implementación del servicio interna que podría utilizarse por clientes no autorizados.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solución de problemas de los adaptadores de WCF](../core/troubleshooting-the-wcf-adapters.md)   
 [BTSNTSvc.exe.config (archivo)](../core/btsntsvc-exe-config-file.md)
---
title: Optimizar el rendimiento del servicio Web WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93947cef-469c-4126-85a5-06456fa37443
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 413642931fcf9580ade280c2e7b3472599859d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-wcf-web-service-performance"></a>Optimizar el rendimiento del servicio Web WCF
Los servicios WCF exponen numerosos parámetros de configuración que afectan al rendimiento. En este tema se proporciona instrucciones generales para establecer el valor óptimo para estos parámetros de configuración mejorar el rendimiento de los servicios WCF.  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a>Implementar el comportamiento de serviceThrottling para los servicios WCF back-end  
 Implementar el comportamiento de serviceThrottling para los servicios WCF back-end. Servicio limitación permite nivelar la carga en los servidores WCF back-end y para exigir la asignación de recursos. comportamiento de serviceThrottling para los servicios WCF back-end se configura mediante la modificación de los valores de la **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** parámetros en el archivo de configuración para el servicio WCF. Establecer **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor mayor que 16 * el número de CPU o más CPU núcleos. Por ejemplo, en un equipo con 8 núcleos de CPU, establezca **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor superior a 128 (16 * 8 = 128) como se indica a continuación:  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a>Aumentar los valores predeterminados de las propiedades NetTcpBinding.ListenBacklog y NetTcpBinding.MaxConnections en el archivo de web.config del servicio WCF back-end  
 El **NetTcpBinding.ListenBacklog** propiedad controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio Web. El **NetTcpBinding.MaxConnections** propiedad controla el número máximo de conexiones que se agrupe para su reutilización subsiguiente en el cliente y el número máximo de conexiones que pueden estar pendientes de envío en el servidor. Cada una de estas propiedades utiliza un valor predeterminado de 10 que puede ser poco óptimo, especialmente para los escenarios que requieren un alto rendimiento de procesamiento de documentos.  
  
 Considere la posibilidad de aumentar el valor predeterminado de estas propiedades para los escenarios de alto rendimiento, el procesamiento de documentos que usan los servicios WCF que implementan la **netTcpBinding** clase de enlace.  
  
 En el ejemplo siguiente, tanto el **listenBacklog** y **maxConnections** parámetros se establecen en un valor de "200".  
  
```  
<netTcpBinding>  
   <binding name="netTcpBinding"  
      closeTimeout="00:10:00"  
      openTimeout="00:10:00"  
      receiveTimeout="00:10:00"  
      sendTimeout="00:10:00"  
      transactionFlow="false"  
      transferMode="Buffered"  
      transactionProtocol="OleTransactions"  
      hostNameComparisonMode="StrongWildcard"  
      listenBacklog="200"  
      maxBufferPoolSize="1048576"  
      maxBufferSize="10485760"  
      maxConnections="200"  
      maxReceivedMessageSize="10485760">  
      <readerQuotas  
         maxDepth="32"  
         maxStringContentLength="8192"  
         maxArrayLength="16384"  
         maxBytesPerRead="4096"  
         maxNameTableCharCount="16384" />  
      <reliableSession  
         ordered="true"  
         inactivityTimeout="00:10:00"  
         enabled="false" />  
      <security mode="None">  
         <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
         <message clientCredentialType="Windows" />  
      </security>  
   </binding>  
</netTcpBinding>  
```  
  
 Para obtener más información acerca de la propiedad NetTcpBinding.ListenBacklog, consulte [NetTcpBinding.ListenBacklog propiedad](http://go.microsoft.com/fwlink/?LinkId=157752) (http://go.microsoft.com/fwlink/?LinkId=157752) en MSDN.  
  
 Para obtener más información acerca de la propiedad NetTcpBinding.MaxConnections, consulte [NetTcpBinding.MaxConnections propiedad](http://go.microsoft.com/fwlink/?LinkID=157751) (http://go.microsoft.com/fwlink/?LinkID=157751) en MSDN.  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a>Eliminar módulos HTTP ASP.NET que no es necesarios para ejecutar los servicios Web de WCF  
 De forma predeterminada, se definen varias httpModules ASP.NET en la canalización de solicitudes en IIS 6.0 y en el clásico o la canalización integrada en IIS 7.5 o 7.0. Estos componentes se interceptan y procesan todas las solicitudes entrantes. Los módulos predeterminados se definen en el archivo web.config que se encuentra en la carpeta %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG para las aplicaciones de ASP.NET de 32 bits y en la carpeta %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG de ASP de 64 bits. Aplicaciones de NET, tal como se muestra en el siguiente fragmento de código.  
  
```  
<httpModules>  
<add name="OutputCache" type="System.Web.Caching.OutputCacheModule"/>  
<add name="Session" type="System.Web.SessionState.SessionStateModule"/>  
<add name="WindowsAuthentication" type="System.Web.Security.WindowsAuthenticationModule"/>  
<add name="FormsAuthentication" type="System.Web.Security.FormsAuthenticationModule"/>  
<add name="PassportAuthentication" type="System.Web.Security.PassportAuthenticationModule"/>  
<add name="RoleManager" type="System.Web.Security.RoleManagerModule"/>  
<add name="UrlAuthorization" type="System.Web.Security.UrlAuthorizationModule"/>  
<add name="FileAuthorization" type="System.Web.Security.FileAuthorizationModule"/>  
<add name="AnonymousIdentification" type="System.Web.Security.AnonymousIdentificationModule"/>  
<add name="Profile" type="System.Web.Profile.ProfileModule"/>  
<add name="ErrorHandlerModule" type="System.Web.Mobile.ErrorHandlerModule, System.Web.Mobile, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
<add name="ServiceModel" type="System.ServiceModel.Activation.HttpModule, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
</httpModules>  
```  
  
 En la mayoría de los escenarios no es necesario cargar todos estos módulos. Por lo tanto, es posible mejorar el rendimiento eliminando los httpModules siguientes cuando se ejecuta el servicio Web de WCF:  
  
-   Session  
  
-   WindowsAuthentication  
  
-   FormsAuthentication  
  
-   PassportAuthentication  
  
-   RoleManager  
  
-   AnonymousIdentification  
  
-   Perfil  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a>Utilice el módulo WCF/herramienta de registro del controlador para configurar controladores y módulos WCF y mejorar la escalabilidad de IIS 7.5 o 7.0 hospeda los servicios de WCF  
 La herramienta de registro de WCF/controlador de módulo está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593). Esta utilidad se puede usar para instalar, lista, o configurar los siguientes módulos WCF:  
  
-   Controlador y el módulo HTTP sincrónico de WCF  
  
-   Controladores y módulos HTTP asincrónicos de WCF  
  
-   Controladores y módulos HTTP de WCF  
  
 Para obtener más información sobre cómo usar los módulos HTTP de WCF asincrónico/controladores para mejorar la escalabilidad de IIS 7.5 o 7.0 hospeda los servicios de WCF, consulte el blog de Wenlong Dong [Orcas SP1 mejora: asincrónica WCF HTTP/controlador de módulo para IIS7 para mejor Escalabilidad del servidor](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de adaptador WCF de BizTalk Server](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)
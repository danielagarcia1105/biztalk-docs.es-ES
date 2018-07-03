---
title: Optimización del rendimiento de servicio Web WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93947cef-469c-4126-85a5-06456fa37443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b0dc200135d65f179d565ba0fe03cc8df897eeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999381"
---
# <a name="optimizing-wcf-web-service-performance"></a>Optimización del rendimiento de servicio Web WCF
Los servicios WCF exponen varios parámetros de configuración que afectan al rendimiento. En este tema se proporciona instrucciones generales para especifique los valores óptimos de estos parámetros de configuración mejorar el rendimiento de los servicios de WCF.  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a>Implementar el comportamiento de serviceThrottling de servicios WCF back-end  
 Implementar el comportamiento de serviceThrottling de servicios WCF back-end. Limitación del servicio permite a equilibrar la carga en los servidores WCF back-end y para aplicar la asignación de recursos. comportamiento de serviceThrottling para servicios WCF back-end se configura mediante la modificación de los valores para el **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** parámetros en el archivo de configuración para el servicio WCF. Establecer **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor mayor que 16 * número de CPU o CPU núcleos. Por ejemplo, en un equipo con 8 núcleos de CPU, establezca **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor mayor que 128 (16 * 8 = 128) la siguiente manera:  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a>Aumentar los valores predeterminados para las propiedades NetTcpBinding.ListenBacklog y NetTcpBinding.MaxConnections en el archivo de web.config del servicio WCF back-end  
 El **NetTcpBinding.ListenBacklog** propiedad controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio Web. El **NetTcpBinding.MaxConnections** propiedad controla el número máximo de conexiones pueden agruparse para su reutilización subsiguiente en el cliente y el número máximo de conexiones que pueden estar pendientes de envío en el servidor. Cada una de estas propiedades usa un valor predeterminado de 10 que puede ser poco óptimo, especialmente para escenarios que requieren un alto rendimiento de procesamiento de documentos.  
  
 Considere la posibilidad de incrementar el valor predeterminado de estas propiedades para escenarios de alto rendimiento, procesamiento de documentos que utilizan los servicios WCF que implementan la **netTcpBinding** clase de enlace.  
  
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
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a>Eliminar ASP.NET httpModules que no son necesarios para ejecutar servicios Web WCF  
 De forma predeterminada, se define varios módulos HTTP ASP.NET en la canalización de solicitudes en IIS 6.0 y en el modelo clásico o la canalización integrada en IIS 7.5 o 7.0. Estos componentes interceptan y procesan todas las solicitudes entrantes. Los módulos predeterminados se definen en el archivo web.config que se encuentra en la carpeta %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG para las aplicaciones de ASP.NET de 32 bits y en la carpeta %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG de ASP de 64 bits. Aplicaciones de NET, tal como se muestra en el siguiente fragmento de código.  
  
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
  
 En la mayoría de los escenarios no es necesario cargar todos estos módulos. Por lo tanto, es posible mejorar el rendimiento eliminando los httpModules siguientes cuando ejecuta el servicio Web de WCF:  
  
-   Session  
  
-   WindowsAuthentication  
  
-   FormsAuthentication  
  
-   PassportAuthentication  
  
-   RoleManager  
  
-   AnonymousIdentification  
  
-   Perfil  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a>Usar el módulo WCF/herramienta de registro del controlador para configurar los controladores y módulos WCF y mejorar la escalabilidad de IIS 7.5 o 7.0 aloja los servicios de WCF  
 La herramienta de registro del controlador/módulo WCF está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=157593 ](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593). Esta utilidad se puede usar para instalar, lista, o configurar los siguientes módulos WCF:  
  
- Controlador y el módulo HTTP sincrónico de WCF  
  
- Controladores y módulos HTTP asincrónicos de WCF  
  
- Controlador y el módulo HTTP de WCF  
  
  Para obtener más información sobre cómo usar los módulos HTTP de WCF asincrónico/controladores para mejorar la escalabilidad de IIS 7.5 o 7.0 hospeda servicios WCF, vea el blog de Wenlong Dong [Orcas SP1 mejora: WCF controlador HTTP asincrónico módulo/para IIS7 para mejor Escalabilidad del servidor](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento del adaptador de WCF de BizTalk Server](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)
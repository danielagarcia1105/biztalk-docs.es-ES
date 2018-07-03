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
# <a name="optimizing-wcf-web-service-performance"></a><span data-ttu-id="33c00-102">Optimización del rendimiento de servicio Web WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-102">Optimizing WCF Web Service Performance</span></span>
<span data-ttu-id="33c00-103">Los servicios WCF exponen varios parámetros de configuración que afectan al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="33c00-103">WCF services expose numerous configuration parameters that affect performance.</span></span> <span data-ttu-id="33c00-104">En este tema se proporciona instrucciones generales para especifique los valores óptimos de estos parámetros de configuración mejorar el rendimiento de los servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="33c00-104">This topic provides general guidance for setting optimal values for these configuration parameters to improve performance of WCF services.</span></span>  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a><span data-ttu-id="33c00-105">Implementar el comportamiento de serviceThrottling de servicios WCF back-end</span><span class="sxs-lookup"><span data-stu-id="33c00-105">Implement serviceThrottling behavior for backend WCF services</span></span>  
 <span data-ttu-id="33c00-106">Implementar el comportamiento de serviceThrottling de servicios WCF back-end.</span><span class="sxs-lookup"><span data-stu-id="33c00-106">Implement serviceThrottling behavior for backend WCF services.</span></span> <span data-ttu-id="33c00-107">Limitación del servicio permite a equilibrar la carga en los servidores WCF back-end y para aplicar la asignación de recursos.</span><span class="sxs-lookup"><span data-stu-id="33c00-107">Service throttling allows you to even out the load on your backend WCF servers and to enforce resource allocation.</span></span> <span data-ttu-id="33c00-108">comportamiento de serviceThrottling para servicios WCF back-end se configura mediante la modificación de los valores para el **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** parámetros en el archivo de configuración para el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="33c00-108">serviceThrottling behavior for backend WCF services is configured by modifying the values for the **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** parameters in the config file for the WCF service.</span></span> <span data-ttu-id="33c00-109">Establecer **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor mayor que 16 \* número de CPU o CPU núcleos.</span><span class="sxs-lookup"><span data-stu-id="33c00-109">Set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 16 \* the number of CPUs or CPU cores.</span></span> <span data-ttu-id="33c00-110">Por ejemplo, en un equipo con 8 núcleos de CPU, establezca **maxConcurrentCalls**, **maxConcurrentSessions**, y **maxConcurrentInstances** en un valor mayor que 128 (16 \* 8 = 128) la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="33c00-110">For example, on a computer with 8 CPU cores, set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 128 (16 \* 8 = 128) as follows:</span></span>  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a><span data-ttu-id="33c00-111">Aumentar los valores predeterminados para las propiedades NetTcpBinding.ListenBacklog y NetTcpBinding.MaxConnections en el archivo de web.config del servicio WCF back-end</span><span class="sxs-lookup"><span data-stu-id="33c00-111">Increase the default values for the NetTcpBinding.ListenBacklog and NetTcpBinding.MaxConnections properties in the backend WCF service web.config file</span></span>  
 <span data-ttu-id="33c00-112">El **NetTcpBinding.ListenBacklog** propiedad controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="33c00-112">The **NetTcpBinding.ListenBacklog** property controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="33c00-113">El **NetTcpBinding.MaxConnections** propiedad controla el número máximo de conexiones pueden agruparse para su reutilización subsiguiente en el cliente y el número máximo de conexiones que pueden estar pendientes de envío en el servidor.</span><span class="sxs-lookup"><span data-stu-id="33c00-113">The **NetTcpBinding.MaxConnections** property controls the maximum number of connections to be pooled for subsequent reuse on the client and the maximum number of connections allowed to be pending dispatch on the server.</span></span> <span data-ttu-id="33c00-114">Cada una de estas propiedades usa un valor predeterminado de 10 que puede ser poco óptimo, especialmente para escenarios que requieren un alto rendimiento de procesamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="33c00-114">Each of these properties uses a default value of 10 which may be suboptimal, especially for document processing scenarios that require high throughput.</span></span>  
  
 <span data-ttu-id="33c00-115">Considere la posibilidad de incrementar el valor predeterminado de estas propiedades para escenarios de alto rendimiento, procesamiento de documentos que utilizan los servicios WCF que implementan la **netTcpBinding** clase de enlace.</span><span class="sxs-lookup"><span data-stu-id="33c00-115">Consider increasing the default value of these properties for high-throughput, document-processing scenarios that use WCF services which implement the **netTcpBinding** binding class.</span></span>  
  
 <span data-ttu-id="33c00-116">En el ejemplo siguiente, tanto el **listenBacklog** y **maxConnections** parámetros se establecen en un valor de "200".</span><span class="sxs-lookup"><span data-stu-id="33c00-116">In the following example, both the **listenBacklog** and **maxConnections** parameters are set to a value of “200”.</span></span>  
  
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
  
 <span data-ttu-id="33c00-117">Para obtener más información acerca de la propiedad NetTcpBinding.ListenBacklog, consulte [NetTcpBinding.ListenBacklog propiedad](http://go.microsoft.com/fwlink/?LinkId=157752) (http://go.microsoft.com/fwlink/?LinkId=157752) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="33c00-117">For more information about the NetTcpBinding.ListenBacklog property, see [NetTcpBinding.ListenBacklog Property](http://go.microsoft.com/fwlink/?LinkId=157752) (http://go.microsoft.com/fwlink/?LinkId=157752) on MSDN.</span></span>  
  
 <span data-ttu-id="33c00-118">Para obtener más información acerca de la propiedad NetTcpBinding.MaxConnections, consulte [NetTcpBinding.MaxConnections propiedad](http://go.microsoft.com/fwlink/?LinkID=157751) (http://go.microsoft.com/fwlink/?LinkID=157751) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="33c00-118">For more information about the NetTcpBinding.MaxConnections property, see [NetTcpBinding.MaxConnections Property](http://go.microsoft.com/fwlink/?LinkID=157751) (http://go.microsoft.com/fwlink/?LinkID=157751) on MSDN.</span></span>  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a><span data-ttu-id="33c00-119">Eliminar ASP.NET httpModules que no son necesarios para ejecutar servicios Web WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-119">Eliminate ASP.NET httpModules that are not required to run WCF Web services</span></span>  
 <span data-ttu-id="33c00-120">De forma predeterminada, se define varios módulos HTTP ASP.NET en la canalización de solicitudes en IIS 6.0 y en el modelo clásico o la canalización integrada en IIS 7.5 o 7.0.</span><span class="sxs-lookup"><span data-stu-id="33c00-120">By default, several ASP.NET httpModules are defined in the Request Pipeline in IIS 6.0 and in the Classic or Integrated Pipeline in IIS 7.5/7.0.</span></span> <span data-ttu-id="33c00-121">Estos componentes interceptan y procesan todas las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="33c00-121">These components intercept and process all incoming requests.</span></span> <span data-ttu-id="33c00-122">Los módulos predeterminados se definen en el archivo web.config que se encuentra en la carpeta %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG para las aplicaciones de ASP.NET de 32 bits y en la carpeta %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG de ASP de 64 bits. Aplicaciones de NET, tal como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="33c00-122">The default modules are defined in the web.config file contained in the %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG folder for 32-bit ASP.NET applications and in the %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG folder for 64-bit ASP.NET applications, as shown by the following snippet.</span></span>  
  
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
  
 <span data-ttu-id="33c00-123">En la mayoría de los escenarios no es necesario cargar todos estos módulos.</span><span class="sxs-lookup"><span data-stu-id="33c00-123">In most scenarios it is not necessary to load all of these modules.</span></span> <span data-ttu-id="33c00-124">Por lo tanto, es posible mejorar el rendimiento eliminando los httpModules siguientes cuando ejecuta el servicio Web de WCF:</span><span class="sxs-lookup"><span data-stu-id="33c00-124">Therefore, it is possible to improve performance by eliminating the following httpModules when running WCF Web services:</span></span>  
  
-   <span data-ttu-id="33c00-125">Session</span><span class="sxs-lookup"><span data-stu-id="33c00-125">Session</span></span>  
  
-   <span data-ttu-id="33c00-126">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="33c00-126">WindowsAuthentication</span></span>  
  
-   <span data-ttu-id="33c00-127">FormsAuthentication</span><span class="sxs-lookup"><span data-stu-id="33c00-127">FormsAuthentication</span></span>  
  
-   <span data-ttu-id="33c00-128">PassportAuthentication</span><span class="sxs-lookup"><span data-stu-id="33c00-128">PassportAuthentication</span></span>  
  
-   <span data-ttu-id="33c00-129">RoleManager</span><span class="sxs-lookup"><span data-stu-id="33c00-129">RoleManager</span></span>  
  
-   <span data-ttu-id="33c00-130">AnonymousIdentification</span><span class="sxs-lookup"><span data-stu-id="33c00-130">AnonymousIdentification</span></span>  
  
-   <span data-ttu-id="33c00-131">Perfil</span><span class="sxs-lookup"><span data-stu-id="33c00-131">Profile</span></span>  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a><span data-ttu-id="33c00-132">Usar el módulo WCF/herramienta de registro del controlador para configurar los controladores y módulos WCF y mejorar la escalabilidad de IIS 7.5 o 7.0 aloja los servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-132">Use the WCF Module/Handler Registration tool to configure WCF modules/handlers and improve scalability of IIS 7.5/7.0 hosted WCF services</span></span>  
 <span data-ttu-id="33c00-133">La herramienta de registro del controlador/módulo WCF está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=157593 ](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593).</span><span class="sxs-lookup"><span data-stu-id="33c00-133">The WCF Module/Handler Registration Tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593).</span></span> <span data-ttu-id="33c00-134">Esta utilidad se puede usar para instalar, lista, o configurar los siguientes módulos WCF:</span><span class="sxs-lookup"><span data-stu-id="33c00-134">This utility can be used to install, list, or configure the following WCF modules:</span></span>  
  
- <span data-ttu-id="33c00-135">Controlador y el módulo HTTP sincrónico de WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-135">WCF Synchronous HTTP module and handler</span></span>  
  
- <span data-ttu-id="33c00-136">Controladores y módulos HTTP asincrónicos de WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-136">WCF Asynchronous HTTP module and handler</span></span>  
  
- <span data-ttu-id="33c00-137">Controlador y el módulo HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="33c00-137">WCF HTTP module and handler</span></span>  
  
  <span data-ttu-id="33c00-138">Para obtener más información sobre cómo usar los módulos HTTP de WCF asincrónico/controladores para mejorar la escalabilidad de IIS 7.5 o 7.0 hospeda servicios WCF, vea el blog de Wenlong Dong [Orcas SP1 mejora: WCF controlador HTTP asincrónico módulo/para IIS7 para mejor Escalabilidad del servidor](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).</span><span class="sxs-lookup"><span data-stu-id="33c00-138">For more information about using the asynchronous WCF HTTP modules/handlers to improve the scalability of IIS 7.5/7.0 hosted WCF services, see Wenlong Dong’s blog [Orcas SP1 Improvement: Asynchronous WCF HTTP Module/Handler for IIS7 for Better Server Scalability](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c00-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="33c00-139">See Also</span></span>  
 [<span data-ttu-id="33c00-140">Optimización del rendimiento del adaptador de WCF de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="33c00-140">Optimizing BizTalk Server WCF Adapter Performance</span></span>](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)
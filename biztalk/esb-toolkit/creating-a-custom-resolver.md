---
title: Crear un solucionador personalizado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1d583389189e09a0b9e0e5157ce5466004c03a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-resolver"></a><span data-ttu-id="f496f-102">Crear a una resolución personalizada</span><span class="sxs-lookup"><span data-stu-id="f496f-102">Creating a Custom Resolver</span></span>
<span data-ttu-id="f496f-103">La implementación de resolución y marco de proveedores de adaptador en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza un componente de canalización con nombre distribuidor y canalizaciones con nombre ItineraryReceive y ItinerarySend.</span><span class="sxs-lookup"><span data-stu-id="f496f-103">The Resolver and Adapter Provider Framework implementation in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses a pipeline component named Dispatcher and pipelines named ItineraryReceive and ItinerarySend.</span></span>  
  
 <span data-ttu-id="f496f-104">El componente de canalización de distribuidor tiene cuatro propiedades: **validar, Enabled, extremo,** y **Nombredemapa**.</span><span class="sxs-lookup"><span data-stu-id="f496f-104">The Dispatcher pipeline component has four properties: **Validate, Enabled, EndPoint,** and **MapName**.</span></span> <span data-ttu-id="f496f-105">El **extremo** propiedad puede contener cadenas de conexión de resolución con valores como el siguiente, donde **UDDI:\\ \\**  representa el tipo de resolución que se usará (la raíz moniker).</span><span class="sxs-lookup"><span data-stu-id="f496f-105">The **EndPoint** property can contain resolver connection strings with values such as the following, where **UDDI:\\\\** represents the resolution type to use (the root moniker).</span></span>  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="f496f-106">Otros monikers admitidos incluyen **XPATH:\\\\estática:\\\\,** y **BRE:\\\\**.</span><span class="sxs-lookup"><span data-stu-id="f496f-106">Other supported monikers include **XPATH:\\\\, STATIC:\\\\,** and **BRE:\\\\**.</span></span> <span data-ttu-id="f496f-107">Cada tipo de moniker utiliza una clase específica que implementa el **IResolveProvider** interfaz.</span><span class="sxs-lookup"><span data-stu-id="f496f-107">Each moniker type uses a specific class that implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="f496f-108">Puede crear a sus propios solucionadores personalizados para otros tipos de moniker y registrar para su uso por el sistema de resolución dinámica.</span><span class="sxs-lookup"><span data-stu-id="f496f-108">You can create your own custom resolvers for other moniker types and register them for use by the dynamic resolution system.</span></span>  
  
 <span data-ttu-id="f496f-109">El moniker equivale a una cadena de conexión de resolución.</span><span class="sxs-lookup"><span data-stu-id="f496f-109">The moniker equates to a resolver connection string.</span></span> <span data-ttu-id="f496f-110">Esquemas individuales definen los parámetros y su moniker raíz.</span><span class="sxs-lookup"><span data-stu-id="f496f-110">Individual schemas define the parameters and their root moniker.</span></span> <span data-ttu-id="f496f-111">Una resolución toma la resolución de cadena de conexión, lo valida y utiliza el resultado para consultar y rellenar un **diccionario** objeto que puede utilizarse para el enrutamiento, transformación, selección de itinerarios o cualquier otro propósito específico para su servicio.</span><span class="sxs-lookup"><span data-stu-id="f496f-111">A resolver takes the resolver connection string, validates it, and uses the result to query and populate a **Dictionary** object that can be used for routing, transformation, itinerary selection, or some other purpose specific to your service.</span></span>  
  
## <a name="resolver-configuration"></a><span data-ttu-id="f496f-112">Configuración de la resolución</span><span class="sxs-lookup"><span data-stu-id="f496f-112">Resolver Configuration</span></span>  
 <span data-ttu-id="f496f-113">Debe registrar a todas las resoluciones en el archivo de configuración Esb.config.</span><span class="sxs-lookup"><span data-stu-id="f496f-113">You must register all resolvers in the Esb.config configuration file.</span></span> <span data-ttu-id="f496f-114">El siguiente XML muestra un ejemplo del contenido del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f496f-114">The following XML shows an example of the configuration file content.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
     <configSections>  
          <section name="esb" type="Microsoft.Practices.ESB.Configuration.ESBConfigurationSection, Microsoft.Practices.ESB.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
          <!-- Other Section Definitions Here -->  
     </configSections>  
  
     <esb>  
          <resolvers cacheManager= "Resolver Providers Cache Manager"  absoluteExpiration="3600">  
               <resolver name="UDDI" type="Microsoft.Practices.ESB.Resolver.UDDI.ResolveProvider, Microsoft.Practices.ESB.Resolver.UDDI, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
                    <resolverConfig>  
                         <add name="cacheTimeoutValue" value="120" />  
                         <add name="cacheName" value="UDDI Cache Manager" />  
                    </resolverConfig>  
               </resolver>  
               <resolver name="XPATH" type="Microsoft.Practices.ESB.Resolver.XPATH.ResolveProvider, Microsoft.Practices.ESB.Resolver.XPATH, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
               <!-- Other Resolver Definitions Here -->  
          </resolvers>  
          <!-- Other ESB Configuration Settings Here -->  
     </esb>  
     <!-- Other Configuration Sections Here -->  
</configuration>  
```  
  
 <span data-ttu-id="f496f-115">El **resolverConfig** sección en cada nodo de resolución le permite configurar las propiedades adicionales que puede requerir la resolución para que funcione en un entorno concreto.</span><span class="sxs-lookup"><span data-stu-id="f496f-115">The **resolverConfig** section under each resolver node allows you to configure additional properties that your resolver may require to operate in a specific environment.</span></span> <span data-ttu-id="f496f-116">Para tener acceso a la configuración, la resolución debe exponer un constructor que toma un parámetro de tipo **Microsoft.Practices.ESB.Configuration.Resolver**.</span><span class="sxs-lookup"><span data-stu-id="f496f-116">To have access to the configuration, your resolver must expose a constructor that takes in a parameter of type **Microsoft.Practices.ESB.Configuration.Resolver**.</span></span> <span data-ttu-id="f496f-117">En la implementación de la resolución, propiedades de configuración, a continuación, se pueden acceder mediante la **ReadResolverConfigByKey** método de la **ResolverConfigHelper** clase; para ello, pase el parámetro se pasó originalmente al constructor y, a continuación, pasa el nombre del valor en cuestión.</span><span class="sxs-lookup"><span data-stu-id="f496f-117">In your resolver implementation, configuration properties can then be accessed using the **ReadResolverConfigByKey** method of the **ResolverConfigHelper** class; to do this, pass in the parameter originally passed to the constructor, and then pass in the name of the value in question.</span></span> <span data-ttu-id="f496f-118">Si no hay ningún par nombre-valor se especifica en el **resolverConfig** nodo, el constructor sin parámetros predeterminado que se utilizará para crear una instancia de la resolución.</span><span class="sxs-lookup"><span data-stu-id="f496f-118">If no name-value pairs are specified in the **resolverConfig** node, the default parameterless constructor will be used to instantiate your resolver.</span></span>  
  
 <span data-ttu-id="f496f-119">Dos Universal Description, Discovery y Integration (UDDI) 3 resoluciones se han definido en la configuración: 3 de UDDI y 3-SOASOFTWARE de UDDI.</span><span class="sxs-lookup"><span data-stu-id="f496f-119">Two Universal Description, Discovery, and Integration (UDDI) 3 resolvers have been defined in the configuration: UDDI 3 and UDDI 3-SOASOFTWARE.</span></span> <span data-ttu-id="f496f-120">Ambos de estos solucionadores utilizan el mismo ensamblado subyacente, pero proporcionan distintas configuraciones para admitir diferentes registros UDDI 3.0: compatible con diferentes formatos de identificador uniforme de recursos (URI) y los requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f496f-120">Both of these resolvers use the same underlying assembly, but they provide different configurations for supporting different UDDI 3.0–compliant registries with different Uniform Resource Identifier (URI) formats and security requirements.</span></span> <span data-ttu-id="f496f-121">Si tiene que configurar un moniker adicional para un registro UDDI compatible con 3.0 Además de los que ya se admite, se pueden utilizar las siguientes propiedades de configuración:</span><span class="sxs-lookup"><span data-stu-id="f496f-121">If you need to configure an additional moniker for a UDDI 3.0–compliant registry besides those already supported, the following configuration properties can be used:</span></span>  
  
-   <span data-ttu-id="f496f-122">**cacheTimeoutValue**</span><span class="sxs-lookup"><span data-stu-id="f496f-122">**cacheTimeoutValue**</span></span>  
  
-   <span data-ttu-id="f496f-123">**cacheName**</span><span class="sxs-lookup"><span data-stu-id="f496f-123">**cacheName**</span></span>  
  
-   <span data-ttu-id="f496f-124">**publisherKey**</span><span class="sxs-lookup"><span data-stu-id="f496f-124">**publisherKey**</span></span>  
  
-   <span data-ttu-id="f496f-125">**useUddiAuth**</span><span class="sxs-lookup"><span data-stu-id="f496f-125">**useUddiAuth**</span></span>  
  
-   <span data-ttu-id="f496f-126">**baseUri**</span><span class="sxs-lookup"><span data-stu-id="f496f-126">**baseUri**</span></span>  
  
-   <span data-ttu-id="f496f-127">**inquireUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="f496f-127">**inquireUriSuffix**</span></span>  
  
-   <span data-ttu-id="f496f-128">**securityUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="f496f-128">**securityUriSuffix**</span></span>  
  
-   <span data-ttu-id="f496f-129">**securityMode**.</span><span class="sxs-lookup"><span data-stu-id="f496f-129">**securityMode**.</span></span> <span data-ttu-id="f496f-130">Para los valores válidos, vea la enumeración [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)).</span><span class="sxs-lookup"><span data-stu-id="f496f-130">For valid values, see the enumeration [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)).</span></span> <span data-ttu-id="f496f-131">El valor predeterminado es **TransportCredentialOnly**.</span><span class="sxs-lookup"><span data-stu-id="f496f-131">The default value is **TransportCredentialOnly**.</span></span>  
  
-   <span data-ttu-id="f496f-132">**credentialType**.</span><span class="sxs-lookup"><span data-stu-id="f496f-132">**credentialType**.</span></span> <span data-ttu-id="f496f-133">Para los valores válidos, vea la enumeración [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)).</span><span class="sxs-lookup"><span data-stu-id="f496f-133">For valid values, see the enumeration [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)).</span></span> <span data-ttu-id="f496f-134">El valor predeterminado es **Windows**.</span><span class="sxs-lookup"><span data-stu-id="f496f-134">The default value is **Windows**.</span></span>  
  
-   <span data-ttu-id="f496f-135">**nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="f496f-135">**username**</span></span>  
  
-   <span data-ttu-id="f496f-136">**contraseña**</span><span class="sxs-lookup"><span data-stu-id="f496f-136">**password**</span></span>  
  
 <span data-ttu-id="f496f-137">Si desea crear a una resolución que se basa en las capacidades de inyección de dependencia del bloque de aplicación de Unity, se requiere configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="f496f-137">If you want to create a resolver that relies on the dependency injection capabilities of the Unity Application Block, additional configuration is required.</span></span> <span data-ttu-id="f496f-138">Para obtener más información, consulte [crear una resolución personalizada con un contenedor de Unity](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).</span><span class="sxs-lookup"><span data-stu-id="f496f-138">For more information, see [Creating a Custom Resolver with a Unity Container](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).</span></span>  
  
## <a name="the-iresolveprovider-interface"></a><span data-ttu-id="f496f-139">La interfaz de IResolveProvider</span><span class="sxs-lookup"><span data-stu-id="f496f-139">The IResolveProvider Interface</span></span>  
 <span data-ttu-id="f496f-140">Todos los solucionadores deben implementar la **IResolveProvider** interfaz.</span><span class="sxs-lookup"><span data-stu-id="f496f-140">All resolvers must implement the **IResolveProvider** interface.</span></span> <span data-ttu-id="f496f-141">El **IResolveProvider** interfaz, ubicado en el proyecto Microsoft.Practices.ESB.Resolver, consta de tres sobrecargas de la **resolver** método que devuelva una instancia de la  **Diccionario** (clase), que contiene información sobre la resolución proporcionada por la instancia de clase de resolución concretos.</span><span class="sxs-lookup"><span data-stu-id="f496f-141">The **IResolveProvider** interface, located in the Microsoft.Practices.ESB.Resolver project, consists of three overloads of the **Resolve** method that return an instance of the **Dictionary** class, which contains resolution facts provided by the instance of concrete resolver class.</span></span> <span data-ttu-id="f496f-142">En el ejemplo de código siguiente se muestra la firma de estas sobrecargas del método.</span><span class="sxs-lookup"><span data-stu-id="f496f-142">The following code example shows the signature of these method overloads.</span></span>  
  
```csharp  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from a Microsoft BizTalk   
// Server pipeline component.  
// </summary>  
// <param name="config">Configuration string entered into   
// pipeline component as argument</param>  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">IBaseMessage passed from pipeline</param>.  
// <param name="pipelineContext">IPipelineContext passed from   
// pipeline</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(string config, string resolver,  
              IBaseMessage message, IPipelineContext pipelineContext);  
  
// <summary>  
// This is the main interface that is called from the ResolverMgr   
// class.  
// This interface supports being called from a Web service interface.  
// </summary>  
// <param name="config">Configuration string entered into Web   
// service as argument</param>.  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">XML document passed from Web   
// service</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string,string> Resolve(string config, string resolver, System.Xml.XmlDocument message);  
  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from an orchestration.  
// </summary>  
// <param name="resolverInfo">Configuration string containing   
// configuration and resolver</param>.  
// <param name="message">XLANGMessage passed from   
// orchestration</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(ResolverInfo resolverInfo, XLANGs.BaseTypes.XLANGMessage message);  
```  
  
 <span data-ttu-id="f496f-143">El **resolución** estructura, que se encuentra en el proyecto de Microsoft.Practices.ESB.Resolver, también define los pares de nombre/valor que se almacena en la **diccionario** instancia.</span><span class="sxs-lookup"><span data-stu-id="f496f-143">The **Resolution** structure, located in Microsoft.Practices.ESB.Resolver project, also defines the name/value pairs stored in the **Dictionary** instance.</span></span> <span data-ttu-id="f496f-144">El **resolución** estructura expone varias propiedades; en la tabla siguiente se enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="f496f-144">The **Resolution** structure exposes several properties; the following table lists the most relevant of these.</span></span> <span data-ttu-id="f496f-145">El **CreateResolverDictionary** método de la **ResolutionHelper** clase puede usarse para generar un diccionario de resolución que contiene las claves más usadas, con valores de cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f496f-145">The **CreateResolverDictionary** method of the **ResolutionHelper** class can be used to generate a resolver dictionary that contains the most used keys, with empty string values.</span></span> <span data-ttu-id="f496f-146">El **diccionario** instancia admite la adición de pares de nombre/valor de resolución personalizada a través de una implementación concreta de la **resolución** clase.</span><span class="sxs-lookup"><span data-stu-id="f496f-146">The **Dictionary** instance supports the addition of custom resolver name/value pairs through a concrete implementation of the **Resolver** class.</span></span>  
  
|<span data-ttu-id="f496f-147">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f496f-147">Property</span></span>|<span data-ttu-id="f496f-148">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f496f-148">Data type</span></span>|<span data-ttu-id="f496f-149">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f496f-149">Data type</span></span>|<span data-ttu-id="f496f-150">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f496f-150">Data type</span></span>|  
|--------------|---------------|---------------|---------------|  
|<span data-ttu-id="f496f-151">**TransformType**</span><span class="sxs-lookup"><span data-stu-id="f496f-151">**TransformType**</span></span>|<span data-ttu-id="f496f-152">String</span><span class="sxs-lookup"><span data-stu-id="f496f-152">String</span></span>|<span data-ttu-id="f496f-153">**ActionField**</span><span class="sxs-lookup"><span data-stu-id="f496f-153">**ActionField**</span></span>|<span data-ttu-id="f496f-154">String</span><span class="sxs-lookup"><span data-stu-id="f496f-154">String</span></span>|  
|<span data-ttu-id="f496f-155">**Success**</span><span class="sxs-lookup"><span data-stu-id="f496f-155">**Success**</span></span>|<span data-ttu-id="f496f-156">Boolean</span><span class="sxs-lookup"><span data-stu-id="f496f-156">Boolean</span></span>|<span data-ttu-id="f496f-157">**EpmRRCorrelationTokenField**</span><span class="sxs-lookup"><span data-stu-id="f496f-157">**EpmRRCorrelationTokenField**</span></span>|<span data-ttu-id="f496f-158">String</span><span class="sxs-lookup"><span data-stu-id="f496f-158">String</span></span>|  
|<span data-ttu-id="f496f-159">**TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="f496f-159">**TransportNamespace**</span></span>|<span data-ttu-id="f496f-160">String</span><span class="sxs-lookup"><span data-stu-id="f496f-160">String</span></span>|<span data-ttu-id="f496f-161">**InboundTransportLocationField**</span><span class="sxs-lookup"><span data-stu-id="f496f-161">**InboundTransportLocationField**</span></span>|<span data-ttu-id="f496f-162">String</span><span class="sxs-lookup"><span data-stu-id="f496f-162">String</span></span>|  
|<span data-ttu-id="f496f-163">**Tipo de transporte**</span><span class="sxs-lookup"><span data-stu-id="f496f-163">**TransportType**</span></span>|<span data-ttu-id="f496f-164">String</span><span class="sxs-lookup"><span data-stu-id="f496f-164">String</span></span>|<span data-ttu-id="f496f-165">**InterchangeIDField**</span><span class="sxs-lookup"><span data-stu-id="f496f-165">**InterchangeIDField**</span></span>|<span data-ttu-id="f496f-166">String</span><span class="sxs-lookup"><span data-stu-id="f496f-166">String</span></span>|  
|<span data-ttu-id="f496f-167">**TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="f496f-167">**TransportLocation**</span></span>|<span data-ttu-id="f496f-168">String</span><span class="sxs-lookup"><span data-stu-id="f496f-168">String</span></span>|<span data-ttu-id="f496f-169">**ReceiveLocationNameField**</span><span class="sxs-lookup"><span data-stu-id="f496f-169">**ReceiveLocationNameField**</span></span>|<span data-ttu-id="f496f-170">String</span><span class="sxs-lookup"><span data-stu-id="f496f-170">String</span></span>|  
|<span data-ttu-id="f496f-171">**Acción**</span><span class="sxs-lookup"><span data-stu-id="f496f-171">**Action**</span></span>|<span data-ttu-id="f496f-172">String</span><span class="sxs-lookup"><span data-stu-id="f496f-172">String</span></span>|<span data-ttu-id="f496f-173">**ReceivePortNameField**</span><span class="sxs-lookup"><span data-stu-id="f496f-173">**ReceivePortNameField**</span></span>|<span data-ttu-id="f496f-174">String</span><span class="sxs-lookup"><span data-stu-id="f496f-174">String</span></span>|  
|<span data-ttu-id="f496f-175">**MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="f496f-175">**MessageExchangePattern**</span></span>|<span data-ttu-id="f496f-176">String</span><span class="sxs-lookup"><span data-stu-id="f496f-176">String</span></span>|<span data-ttu-id="f496f-177">**InboundTransportTypeField**</span><span class="sxs-lookup"><span data-stu-id="f496f-177">**InboundTransportTypeField**</span></span>|<span data-ttu-id="f496f-178">String</span><span class="sxs-lookup"><span data-stu-id="f496f-178">String</span></span>|  
|<span data-ttu-id="f496f-179">**EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="f496f-179">**EndpointConfig**</span></span>|<span data-ttu-id="f496f-180">String</span><span class="sxs-lookup"><span data-stu-id="f496f-180">String</span></span>|<span data-ttu-id="f496f-181">**IsRequestResponseField**</span><span class="sxs-lookup"><span data-stu-id="f496f-181">**IsRequestResponseField**</span></span>|<span data-ttu-id="f496f-182">String</span><span class="sxs-lookup"><span data-stu-id="f496f-182">String</span></span>|  
|<span data-ttu-id="f496f-183">**TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="f496f-183">**TargetNamespace**</span></span>|<span data-ttu-id="f496f-184">String</span><span class="sxs-lookup"><span data-stu-id="f496f-184">String</span></span>|<span data-ttu-id="f496f-185">**DocumentSpecStrongNameField**</span><span class="sxs-lookup"><span data-stu-id="f496f-185">**DocumentSpecStrongNameField**</span></span>|<span data-ttu-id="f496f-186">String</span><span class="sxs-lookup"><span data-stu-id="f496f-186">String</span></span>|  
|<span data-ttu-id="f496f-187">**FixJaxRPC**</span><span class="sxs-lookup"><span data-stu-id="f496f-187">**FixJaxRPC**</span></span>|<span data-ttu-id="f496f-188">Boolean</span><span class="sxs-lookup"><span data-stu-id="f496f-188">Boolean</span></span>|<span data-ttu-id="f496f-189">**DocumentSpecNameField**</span><span class="sxs-lookup"><span data-stu-id="f496f-189">**DocumentSpecNameField**</span></span>|<span data-ttu-id="f496f-190">String</span><span class="sxs-lookup"><span data-stu-id="f496f-190">String</span></span>|  
|<span data-ttu-id="f496f-191">**WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="f496f-191">**WindowUserField**</span></span>|<span data-ttu-id="f496f-192">String</span><span class="sxs-lookup"><span data-stu-id="f496f-192">String</span></span>|<span data-ttu-id="f496f-193">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="f496f-193">**MessageType**</span></span>|<span data-ttu-id="f496f-194">String</span><span class="sxs-lookup"><span data-stu-id="f496f-194">String</span></span>|  
|<span data-ttu-id="f496f-195">**CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="f496f-195">**CacheTimeout**</span></span>|<span data-ttu-id="f496f-196">String</span><span class="sxs-lookup"><span data-stu-id="f496f-196">String</span></span>|<span data-ttu-id="f496f-197">**OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="f496f-197">**OutboundTransportCLSID**</span></span>|<span data-ttu-id="f496f-198">String</span><span class="sxs-lookup"><span data-stu-id="f496f-198">String</span></span>|  
|<span data-ttu-id="f496f-199">**MethodNameField**</span><span class="sxs-lookup"><span data-stu-id="f496f-199">**MethodNameField**</span></span>|<span data-ttu-id="f496f-200">String</span><span class="sxs-lookup"><span data-stu-id="f496f-200">String</span></span>|||  
  
## <a name="creating-a-custom-resolver"></a><span data-ttu-id="f496f-201">Crear a una resolución personalizada</span><span class="sxs-lookup"><span data-stu-id="f496f-201">Creating a Custom Resolver</span></span>  
 <span data-ttu-id="f496f-202">En tiempo de ejecución, una canalización recupera la cadena de conexión de resolución y llama a la resolución de administrador (una instancia de la **ResolverMgr** clase).</span><span class="sxs-lookup"><span data-stu-id="f496f-202">At run time, a pipeline retrieves the resolver connection string and calls the resolver manager (an instance of the **ResolverMgr** class).</span></span> <span data-ttu-id="f496f-203">El Administrador de resolución analiza, rellena y valida la cadena de conexión de resolución.</span><span class="sxs-lookup"><span data-stu-id="f496f-203">The resolver manager parses, populates, and validates the resolver connection string.</span></span> <span data-ttu-id="f496f-204">Para ello, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f496f-204">It does this by doing the following:</span></span>  
  
-   <span data-ttu-id="f496f-205">Analiza la cadena de conexión para determinar qué **resolución** tipo a cargar.</span><span class="sxs-lookup"><span data-stu-id="f496f-205">It parses the connection string to determine which **Resolver** type to load.</span></span>  
  
-   <span data-ttu-id="f496f-206">Coincide con este tipo de un moniker definido en el archivo de configuración (la clave es el moniker raíz, por ejemplo, UDDI).</span><span class="sxs-lookup"><span data-stu-id="f496f-206">It matches this type to a moniker defined in the configuration file (the key is the root moniker, such as UDDI).</span></span>  
  
-   <span data-ttu-id="f496f-207">Lee el nombre del ensamblado de la resolución para este moniker.</span><span class="sxs-lookup"><span data-stu-id="f496f-207">It reads the assembly name of the resolver for this moniker.</span></span>  
  
-   <span data-ttu-id="f496f-208">Carga el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="f496f-208">It loads the specified assembly.</span></span>  
  
 <span data-ttu-id="f496f-209">El mecanismo de resolución dinámica almacena en caché cargadas todas las implementaciones de la **IResolveProvider** interfaz para evitar lecturas repetidas de información de configuración y el ensamblado que se carga cuando varios mensajes entrantes utilizan el mismo resolución.</span><span class="sxs-lookup"><span data-stu-id="f496f-209">The dynamic resolution mechanism caches all loaded implementations of the **IResolveProvider** interface to avoid repeated reading of configuration information and assembly loading when several incoming messages use the same resolver.</span></span>  
  
 <span data-ttu-id="f496f-210">Por último, se ejecuta el Administrador de la resolución del **resolver** método el hormigón **IResolveProvider** implementación y devuelve el rellenado **diccionario** instancia.</span><span class="sxs-lookup"><span data-stu-id="f496f-210">Finally, the resolver manager executes the **Resolve** method of the concrete **IResolveProvider** implementation and returns the populated **Dictionary** instance.</span></span>  
  
 <span data-ttu-id="f496f-211">**Para crear a una resolución personalizada**</span><span class="sxs-lookup"><span data-stu-id="f496f-211">**To create a custom resolver**</span></span>  
  
1.  <span data-ttu-id="f496f-212">Crear un ensamblado con una clase que implementa el **IResolveProvider** de interfaz y contiene un **resolver** método que devuelve los hechos de resolución como una instancia de la **diccionario**clase.</span><span class="sxs-lookup"><span data-stu-id="f496f-212">Create an assembly with a class that implements the **IResolveProvider** interface and contains a **Resolve** method that returns resolver facts as an instance of the **Dictionary** class.</span></span>  
  
2.  <span data-ttu-id="f496f-213">Registre el solucionador, éste se agrega al archivo de configuración Esb.config utilizando un  **\<resolución >** elemento que contiene el moniker raíz como la **nombre** atributo y el nombre completo nombre del ensamblado como el **tipo** atributo.</span><span class="sxs-lookup"><span data-stu-id="f496f-213">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
3.  <span data-ttu-id="f496f-214">(Opcional) Crear un esquema que define el moniker raíz y los parámetros de consulta y, a continuación, guárdelo en ESB. Carpeta Schemas.Resolvers.</span><span class="sxs-lookup"><span data-stu-id="f496f-214">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="f496f-215">El nombre debe seguir convenciones de nomenclatura de ESB existentes; Esto significa que debe usar el nombre del moniker raíz anexado "_Resolution.xsd".</span><span class="sxs-lookup"><span data-stu-id="f496f-215">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
4.  <span data-ttu-id="f496f-216">(Opcional) Generar una clase desde el nuevo esquema y lo guarda en el ensamblado de la resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="f496f-216">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="f496f-217">Esto expone los parámetros de tipo en la resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="f496f-217">This exposes typed parameters in the custom resolver.</span></span>  
  
5.  <span data-ttu-id="f496f-218">Registrar el nuevo ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f496f-218">Register the new assembly in the global assembly cache.</span></span>
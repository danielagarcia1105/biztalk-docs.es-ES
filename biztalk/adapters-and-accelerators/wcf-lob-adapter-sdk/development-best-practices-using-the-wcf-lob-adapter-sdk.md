---
title: Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4693d3ae4a443138c078e0da415fb72205dbd528
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967986"
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="4d2f1-102">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="4d2f1-102">Development best practices using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="4d2f1-103">Puede usar los procedimientos recomendados en este tema para mejorar las aplicaciones y los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-103">You can use the best practices in this topic to improve your applications and adapters.</span></span>  
  
## <a name="call-abort-before-close-on-channel-exception"></a><span data-ttu-id="4d2f1-104">Anulación de la llamada antes de cerrar en la excepción de canal</span><span class="sxs-lookup"><span data-stu-id="4d2f1-104">Call Abort Before Close on Channel Exception</span></span>  
 <span data-ttu-id="4d2f1-105">Cuando se escribe una aplicación que utiliza el modelo de canal WCF, debe llamar a `IRequestChannel.Abort` antes de llamar a `ChannelFactory.Close`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-105">When you write an application that uses the WCF channel model, you should call `IRequestChannel.Abort` before calling `ChannelFactory.Close`.</span></span> <span data-ttu-id="4d2f1-106">Si no, `ChannelFactory.Close` produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-106">If you do not, `ChannelFactory.Close` throws an exception.</span></span>  
  
 <span data-ttu-id="4d2f1-107">En el ejemplo siguiente, las operaciones de canal se intentan dentro de un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-107">In the following example, channel operations are attempted within a try/catch block.</span></span> <span data-ttu-id="4d2f1-108">Si se produce una excepción, se anula el canal.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-108">If an exception occurs, the channel is aborted.</span></span>  
  
```csharp  
ChannelFactory<IRequestChannel> cf = new  ChannelFactory<IRequestChannel>();  
IRequestChannel channel = null;  
try  
{  
  cf.Open();  
  channel = cf.CreateChannel();  
  channel.Open();  
  channel.Request();// This causes the channel to go into a faulted state.  
  channel.Close();  
}  
catch (Exception e)  
{  
  // Abort the channel if we have one  
  if(channel != null)  
    channel.Abort();  
}  
finally  
{  
  if (cf.State == CommunicationState.Opened)  
  {  
    cf.Close(); // It throws an exception that the channel is in a faulted state.  
  }  
}  
```  
  
## <a name="implement-both-asynchronous-and-synchronous-handlers"></a><span data-ttu-id="4d2f1-109">Implementar controladores asincrónicos y sincrónicos</span><span class="sxs-lookup"><span data-stu-id="4d2f1-109">Implement Both Asynchronous and Synchronous Handlers</span></span>  
 <span data-ttu-id="4d2f1-110">Si es posible, implemente controladores asincrónicos y sincrónicos en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-110">If possible, implement both asynchronous and synchronous handlers in your adapter.</span></span> <span data-ttu-id="4d2f1-111">Si el adaptador solo implementa las llamadas sincrónicas, puede encontrarse con problemas de bloqueo al procesar un gran volumen de mensajes o cuando se usa el adaptador en un entorno multiproceso.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-111">If your adapter only implements synchronous calls, you may run into blocking issues when processing a large volume of messages or when the adapter is used in a multithreaded environment.</span></span>  
  
## <a name="use-connection-pooling"></a><span data-ttu-id="4d2f1-112">Usar la agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="4d2f1-112">Use Connection Pooling</span></span>  
 <span data-ttu-id="4d2f1-113">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es compatible con la agrupación de conexiones de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports connection pooling by default.</span></span> <span data-ttu-id="4d2f1-114">Sin embargo, resulta depende del desarrollador de adaptador para determinar qué propiedades que se expondrán como propiedades de enlace de la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-114">However, it is up to the adapter developer to determine which connection pooling properties to expose as binding properties.</span></span> <span data-ttu-id="4d2f1-115">Las opciones disponibles de la agrupación de conexiones se definen en `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-115">The available Connection Pool settings are defined within `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.</span></span>  
  
 <span data-ttu-id="4d2f1-116">No hay ninguna opción dentro de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para exponer fácilmente estas propiedades como propiedades de conexión del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-116">There are no options within the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to easily expose these properties as adapter connection properties.</span></span> <span data-ttu-id="4d2f1-117">El desarrollador de adaptadores debe definir manualmente las propiedades de la implementación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-117">The adapter developer must manually define the properties in the adapter implementation.</span></span>  
  
```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  
  
## <a name="ensure-that-the-adapter-supports-two-way-operations"></a><span data-ttu-id="4d2f1-118">Asegúrese de que el adaptador admite operaciones bidireccionales</span><span class="sxs-lookup"><span data-stu-id="4d2f1-118">Ensure That the Adapter Supports Two-Way Operations</span></span>  
 <span data-ttu-id="4d2f1-119">Si se llama a su adaptador de BizTalk Server, debe admitir operaciones bidireccionales, incluso si el valor devuelto es void.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-119">If your adapter is called from BizTalk Server, it must support two-way operations, even if the return value is void.</span></span> <span data-ttu-id="4d2f1-120">Esto es porque BizTalk Server espera una respuesta procedente de cualquier solicitud de salida y produce una excepción si el adaptador sólo implementa las operaciones unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-120">This is because BizTalk Server expects a response returned from any outgoing request, and throws an exception if your adapter only implements one-way operations.</span></span>  
  
 <span data-ttu-id="4d2f1-121">Este es un ejemplo de un contrato de solicitud-respuesta que devuelve void.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-121">Here is an example of a request-response contract that returns void.</span></span>  
  
```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  
  
## <a name="implement-tracing"></a><span data-ttu-id="4d2f1-122">Implementar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="4d2f1-122">Implement Tracing</span></span>  
 <span data-ttu-id="4d2f1-123">Durante el ciclo de desarrollo, no puede parecer importante agregar seguimiento a su adaptador, ya que puede recorrer el código y depurar los problemas.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-123">During the development cycle, it might not seem important to add tracing to your adapter, since you can step through the code and debug any problems.</span></span> <span data-ttu-id="4d2f1-124">Sin embargo, una vez que el adaptador está instalado en un entorno de producción, no puede usar la depuración en tiempo de ejecución para aislar los problemas.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-124">However, once the adapter is installed in a production environment, you might not be able to use run-time debugging to isolate problems.</span></span> <span data-ttu-id="4d2f1-125">Si ha habilitado el seguimiento a lo largo de su adaptador, se puede utilizar para aislar dónde se producen errores.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-125">If you have enabled tracing throughout your adapter, it can be used to isolate where failures are occurring.</span></span>  
  
 <span data-ttu-id="4d2f1-126">Vea [un adaptador con el SDK de adaptador LOB de WCF de seguimiento](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-126">See [Trace an adapter with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) for further details.</span></span>  
  
## <a name="use-uri-properties-for-frequently-changed-settings"></a><span data-ttu-id="4d2f1-127">Utilizar propiedades de URI para valores cambiados con frecuencia</span><span class="sxs-lookup"><span data-stu-id="4d2f1-127">Use URI Properties for Frequently Changed Settings</span></span>  
 <span data-ttu-id="4d2f1-128">Al decidir si desea exponer una propiedad personalizada como un enlace o una propiedad URI, se recomienda usar una propiedad URI si el valor cambia con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-128">When deciding whether to expose a custom property as a binding or URI property, it is recommended to use a URI property if the value changes often.</span></span> <span data-ttu-id="4d2f1-129">Propiedades de enlace se deben reservar para los valores que rara vez cambian.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-129">Binding properties should be reserved for values that rarely change.</span></span>  
  
 <span data-ttu-id="4d2f1-130">Una propiedad de enlace de ejemplo sería un nombre de servidor de base de datos que se usa por todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-130">An example binding property would be a database server name that is used by all connections.</span></span> <span data-ttu-id="4d2f1-131">Un propiedad URI de ejemplo sería una tabla específica o un procedimiento almacenado que va a usar esa conexión concreta.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-131">An example URI property would be a specific table or stored procedure to be used by that specific connection.</span></span>  
  
## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a><span data-ttu-id="4d2f1-132">No pase valores de contraseña o nombre de usuario en el URI</span><span class="sxs-lookup"><span data-stu-id="4d2f1-132">Do Not Pass User Name or Password Values in the URI</span></span>  
 <span data-ttu-id="4d2f1-133">Si el adaptador requiere las credenciales del llamador, se recomienda utilizar la **ClientCredentials** clase para recuperar valores de credenciales en lugar de pasar las credenciales del cliente como parte del URI.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-133">If your adapter requires the caller’s credentials, it is recommended to use the **ClientCredentials** class to retrieve credential values instead of passing client credentials as part of the URI.</span></span> <span data-ttu-id="4d2f1-134">El **ClientCredentials** clase es una característica estándar de WCF que está diseñado para pasar información de credenciales desde el cliente al servicio de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-134">The **ClientCredentials** class is a standard feature of WCF that is intended for passing credential information from the client to the service in a more secure manner.</span></span> <span data-ttu-id="4d2f1-135">Pasar la información de usuario como parte de la cadena URI puede exponer la información de usuario mientras están en tránsito.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-135">Passing the user information as part of the URI string may expose the user information while in transit.</span></span>  
  
 <span data-ttu-id="4d2f1-136">Los métodos recomendados de pasar las credenciales se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-136">The recommended methods of passing credentials are shown in the following table.</span></span>  
  
|<span data-ttu-id="4d2f1-137">Método</span><span class="sxs-lookup"><span data-stu-id="4d2f1-137">Method</span></span>|<span data-ttu-id="4d2f1-138">Description</span><span class="sxs-lookup"><span data-stu-id="4d2f1-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4d2f1-139">Tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4d2f1-139">Design time</span></span>|<span data-ttu-id="4d2f1-140">Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede especificar los tipos de credencial de cliente que admite el adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-140">When using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you can specify the client credential types that the adapter supports.</span></span>|  
|<span data-ttu-id="4d2f1-141">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4d2f1-141">Run time</span></span>|<span data-ttu-id="4d2f1-142">Cuando se utiliza a un proxy de .NET CLR generado, se pueden establecer mediante programación el cliente las credenciales.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-142">When using a generated .NET CLR proxy, you can programmatically set the client credentials.</span></span><br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> <span data-ttu-id="4d2f1-143">O bien, si necesita interactuar directamente con el canal, puede usar el modelo de canal WCF para especificar las credenciales del cliente al crear un generador de canales.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-143">Alternatively, if you need to interact with the channel directly, you can use the WCF channel model to specify the client credentials when creating a channel factory.</span></span><br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();`|  
|<span data-ttu-id="4d2f1-144">Configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="4d2f1-144">WCF configuration</span></span>|<span data-ttu-id="4d2f1-145">En el archivo de configuración de cliente, agregue un \<endpointBehaviors\> elemento que incluye \<clientCredentials\>.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-145">In the client configuration file, add an \<endpointBehaviors\> element that includes \<clientCredentials\>.</span></span><br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`|  
|<span data-ttu-id="4d2f1-146">Uso de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4d2f1-146">Using BizTalk</span></span>|<span data-ttu-id="4d2f1-147">Cuando se usa el adaptador de WCF para utilizar el adaptador, puede agregar el **clientCredentials** extensión de comportamiento en la **comportamiento** ficha. Una vez que se ha agregado, puede establecer credenciales del cliente deseado en el comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-147">When using the WCF adapter to consume your adapter, you can add the **clientCredentials** behavior extension on the **Behavior** tab. Once this has been added, you can set the desired client credentials in the endpoint behavior.</span></span>|  
  
## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a><span data-ttu-id="4d2f1-148">No se devuelven ambos StrongDataSetType y WeakDataSetType</span><span class="sxs-lookup"><span data-stu-id="4d2f1-148">Do Not Return Both StrongDataSetType and WeakDataSetType</span></span>  
 <span data-ttu-id="4d2f1-149">Si el adaptador devuelve un `DataSet`, use `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` o `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, pero no use ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-149">If your adapter returns a `DataSet`, use either `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` or `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, but do not use both at the same time.</span></span> <span data-ttu-id="4d2f1-150">El nombre del nodo raíz y el espacio de nombres generado por ambos tipos son idénticas y no pueden existir simultáneamente en un archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-150">The root node name and namespace produced by both types are identical, and cannot exist simultaneously in a WSDL.</span></span>  
  
 <span data-ttu-id="4d2f1-151">Mientras `WeakDataSetType` y `StrongDataSetType` los dos representan un `System.Data.DataSet`, `StrongDataSetType` es más fácil de usar en aplicaciones. NET, ya que el proxy generado aparece como `System.Data.Dataset`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-151">While `WeakDataSetType` and `StrongDataSetType` both represent a `System.Data.DataSet`, `StrongDataSetType` is easier to use in .NET applications, since the proxy generated appears as `System.Data.Dataset`.</span></span> <span data-ttu-id="4d2f1-152">El proxy generado por `WeakDataSetType` es `XmlElement[]`, que es más difícil de utilizar en una aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-152">The proxy generated by `WeakDataSetType` is `XmlElement[]`, which is more difficult to use in a .NET application.</span></span>  <span data-ttu-id="4d2f1-153">BizTalk Server no puede usar el esquema devuelto desde `StrongDataSet`, pero puede consumir `WeakDataSetType`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-153">BizTalk Server cannot consume the schema returned from `StrongDataSet`, but is able to consume `WeakDataSetType`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d2f1-154">`StrongDataSetType`y `WeakDataSetType` sólo controlan el modo en que la aplicación cliente interpreta los mensajes XML que se pasa por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-154">`StrongDataSetType` and `WeakDataSetType` only control how the client application interprets the XML messages passed by the adapter.</span></span> <span data-ttu-id="4d2f1-155">El mensaje XML es el mismo con independencia de qué tipo se especifica.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-155">The XML message is the same regardless of which type is specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d2f1-156">Cuando se devuelven `StrongDataSetType`, debe establecer `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` a `false`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-156">When returning `StrongDataSetType`, you must set `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` to `false`.</span></span> <span data-ttu-id="4d2f1-157">Cuando se establece en `true`, el valor predeterminado, `XmlSchemaSet::Compile` se llama en el adaptador para asegurarse de que no hay ningún error en el archivo WSDL, sin embargo el esquema generado por `StrongDataSetType` genera una excepción en `XmlSchemaSet`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-157">When set to `true`, the default, `XmlSchemaSet::Compile` is called within the adapter to ensure there are no errors in the WSDL, however the schema produced by `StrongDataSetType` generates an exception in `XmlSchemaSet`.</span></span>  
>   
>  <span data-ttu-id="4d2f1-158">Establecer `CompileWsdl` a `false` omite la validación del esquema WSDL en el adaptador y la validación se produce durante la generación de proxy.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-158">Setting `CompileWsdl` to `false` bypasses WSDL schema validation within the adapter and validation occurs during proxy generation.</span></span>  <span data-ttu-id="4d2f1-159">Utilidades como svcutil.exe son capaces de generar un proxy para ambos `StrongDataSetType` y `WeakDataSetType`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-159">Utilities such as svcutil.exe are able to generate a proxy for both `StrongDataSetType` and `WeakDataSetType`.</span></span>  
  
 <span data-ttu-id="4d2f1-160">Para trabajar con entornos de BizTalk y. NET, considere la posibilidad de implementar una propiedad de enlace que permite cambiar entre los dos tipos de valor devueltos según lo dictado por el entorno.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-160">To work with both BizTalk and .NET environments, consider implementing a binding property that allows switching between the two return types as dictated by the environment.</span></span>  
  
```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  
  
## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a><span data-ttu-id="4d2f1-161">Crear nombres de esquema XSD significativo en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4d2f1-161">Create Meaningful XSD Schema Names in BizTalk Server</span></span>  
 <span data-ttu-id="4d2f1-162">Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] herramienta de tiempo de diseño, el nombre del esquema XSD generado en el proyecto de BizTalk se crea utilizando el `DefaultXsdFileNamePrefix` propiedad, el `fileNameHint` anotación en el WSDL y, si es necesario, un valor entero único.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-162">When using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] design-time tool, the name of the XSD schema generated in your BizTalk project is created using the `DefaultXsdFileNamePrefix` property, the `fileNameHint` annotation in the WSDL and, if required, a unique integer value.</span></span>  
  
 <span data-ttu-id="4d2f1-163">Por ejemplo, si `DefaultXsdFileNamePrefix` se establece en "MyAdapter" y el `fileNameHint` anotación está establecida en "Stream", el esquema XSD que se crea se denomina MyAdapterStream.xsd.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-163">For example, if `DefaultXsdFileNamePrefix` is set to “MyAdapter” and the `fileNameHint` annotation is set to “Stream”, the XSD schema created is named MyAdapterStream.xsd.</span></span>  
  
```  
<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
<xs:annotation>  
<xs:appinfo>  
<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
</xs:appinfo>  
</xs:annotation>  
<xs:simpleType name='StreamBody'>  
<xs:restriction base='xs:base64Binary' />  
</xs:simpleType>  
</xs:schema>  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="4d2f1-164">El valor predeterminado de `DefaultXsdFileNamePrefix` es el nombre de su enlace.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-164">The default value of `DefaultXsdFileNamePrefix` is the name of your binding.</span></span> <span data-ttu-id="4d2f1-165">Para especificar un valor diferente, invalidar `DefaultXsdFileNamePrefix` en la clase de adaptador que se deriva de `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-165">To specify a different value, override `DefaultXsdFileNamePrefix` in your Adapter class that is derived from `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.</span></span>  
  
 <span data-ttu-id="4d2f1-166">Hay dos métodos posibles para agregar el `fileNameHint` anotación en el esquema: reemplazar la exportación... Métodos de esquema en OperationMetadata\TypeMetadata o invalidar la implementación de IWsdlRetrieval del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-166">There are two possible methods to add the `fileNameHint` annotation to the schema: override the Export…Schema methods on OperationMetadata\TypeMetadata or override the IWsdlRetrieval implementation of the adapter.</span></span> <span data-ttu-id="4d2f1-167">Para cualquiera de los métodos, puede llamar a la implementación base y, a continuación, agregue la anotación a los esquemas en la colección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-167">For either method, you can call the base implementation and then add the annotation to the schemas in the schema collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d2f1-168">Al reemplazar la exportación... Métodos de esquema, puede haber varias definiciones de tipo de operación o en el mismo esquema; el adaptador debe asegurarse de que varias repeticiones de la `fileNameHints` anotación en el mismo esquema no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-168">When overriding the Export…Schema methods, there may be multiple operation/type definitions in the same schema; the adapter should make sure that multiple occurrences of the `fileNameHints` annotation in the same schema do not conflict.</span></span> <span data-ttu-id="4d2f1-169">El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] usa la primera aparición de `fileNameHint` si se produce varias veces dentro de un esquema.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-169">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] uses the first occurrence of `fileNameHint` if it occurs multiple times within a schema.</span></span>  
  
 <span data-ttu-id="4d2f1-170">En el ejemplo siguiente, IWsdlRetrieval se utiliza para agregar el `fileNameHint` anotación a WSDL.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-170">In the following example, IWsdlRetrieval is used to add the `fileNameHint` annotation to the WSDL.</span></span>  
  
```csharp  
sealed class MyAdapterWsdlRetrieval : IWsdlRetrieval  
{  
   IWsdlRetrieval mBaseWsdlRetrieval;  
   public MyAdapterWsdlRetrieval(IWsdlRetrieval baseWsdlRetrieval)  
   {  
      mBaseWsdlRetrieval = baseWsdlRetrieval;  
   }  
  
   ServiceDescription IWsdlRetrieval.GetWsdl(Microsoft.ServiceModel.Channels.MetadataRetrievalNode[] nodes, Uri uri, TimeSpan timeout)  
   {  
      ServiceDescription baseDesc = mBaseWsdlRetrieval.GetWsdl(nodes, uri, timeout);  
      foreach (XmlSchema schema in baseDesc.Types.Schemas)  
      {  
         CreateFileNameHint(schema);  
      }  
      return baseDesc;  
   }  
  
   void CreateFileNameHint(XmlSchema schema)  
   {  
      string targetNamespace = schema.TargetNamespace;  
      if (string.IsNullOrEmpty(targetNamespace))  
         return;  
      string fileNameHint = null;  
      //determine the filename based on namespace  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadaptpter/HelloWorld"))  
      {  
         fileNameHint = "HelloWorld";  
      }  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadapter/Hello"))  
      {  
         fileNameHint = "Hello";  
      }  
      //create the annotation and populate it with fileNameHint  
      XmlSchemaAnnotation annotation = new XmlSchemaAnnotation();  
      XmlSchemaAppInfo appInfo = new XmlSchemaAppInfo();  
      XmlDocument doc = new XmlDocument();  
      XmlNode[] fileNameHintNodes = new XmlNode[1];  
      fileNameHintNodes[0] = doc.CreateElement(null, "fileNameHint", "http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd");  
      fileNameHintNodes[0].AppendChild(doc.CreateTextNode(fileNameHint));  
      appInfo.Markup = fileNameHintNodes;  
      annotation.Items.Add(appInfo);  
      schema.Items.Insert(0, annotation);  
   }  
```  
  
## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a><span data-ttu-id="4d2f1-171">No modifique AdapterEnvironmentSettings durante el procesamiento</span><span class="sxs-lookup"><span data-stu-id="4d2f1-171">Do Not Modify AdapterEnvironmentSettings During Processing</span></span>  
 <span data-ttu-id="4d2f1-172">El adaptador solo debe establecer el **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, y **CommonCacheSize**durante la inicialización del adaptador y no debe intentar modificar los valores de una instancia en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-172">The adapter should only set the **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, and **CommonCacheSize** during adapter initialization and should not attempt to modify the values for a running instance.</span></span>  
  
 <span data-ttu-id="4d2f1-173">Si estos valores se modifican en una instancia de adaptador que se están ejecutando, esto puede producir en las nuevas conexiones, sobrescribiendo los valores de configuración para conexiones está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4d2f1-173">If these settings are modified on a currently running adapter instance, this may result in new connections overwriting configuration settings for currently executing connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2f1-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d2f1-174">See Also</span></span>  
 [<span data-ttu-id="4d2f1-175">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="4d2f1-175">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)
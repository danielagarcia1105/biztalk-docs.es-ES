---
title: "Problemas de diseño del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5568be-a046-40ff-a94a-eda086457564
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c6228db8342f3d1ad2628d4e4caf418efd9b29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-design-issues"></a><span data-ttu-id="d82b7-102">Problemas de diseño del adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-102">Adapter Design Issues</span></span>
<span data-ttu-id="d82b7-103">La configuración del adaptador se almacena en la base de datos de inicio de sesión único (SSO) cuando el usuario realiza cambios de configuración durante el tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="d82b7-103">Adapter configuration is stored in the Single Sign-On (SSO) database when the user makes configuration changes during design time.</span></span> <span data-ttu-id="d82b7-104">En el tiempo de ejecución, el motor de mensajería recupera la configuración del adaptador y la entrega a éste.</span><span class="sxs-lookup"><span data-stu-id="d82b7-104">At run time the Messaging Engine retrieves the adapter's configuration and delivers it to the adapter.</span></span> <span data-ttu-id="d82b7-105">La información de configuración que se entrega a los adaptadores es de cuatro tipos:</span><span class="sxs-lookup"><span data-stu-id="d82b7-105">Four types of configuration information are delivered to adapters:</span></span>  
  
-   <span data-ttu-id="d82b7-106">Configuración del controlador de recepción</span><span class="sxs-lookup"><span data-stu-id="d82b7-106">Receive handler configuration</span></span>  
  
-   <span data-ttu-id="d82b7-107">Configuración de la ubicación de recepción (extremo)</span><span class="sxs-lookup"><span data-stu-id="d82b7-107">Receive location (endpoint) configuration</span></span>  
  
-   <span data-ttu-id="d82b7-108">Configuración del controlador de envío</span><span class="sxs-lookup"><span data-stu-id="d82b7-108">Send handler configuration</span></span>  
  
-   <span data-ttu-id="d82b7-109">Configuración de la ubicación de envío (extremo)</span><span class="sxs-lookup"><span data-stu-id="d82b7-109">Send location (endpoint) configuration</span></span>  
  
## <a name="receive-and-send-handler-configuration"></a><span data-ttu-id="d82b7-110">Configuración del controlador de recepción y de envío</span><span class="sxs-lookup"><span data-stu-id="d82b7-110">Receive and Send Handler Configuration</span></span>  
 <span data-ttu-id="d82b7-111">Configuración del controlador de un adaptador se entrega al adaptador en su implementación de la parte opcional **IPersistPropertyBag**. **Carga** interfaz.</span><span class="sxs-lookup"><span data-stu-id="d82b7-111">An adapter's handler configuration is delivered to the adapter on its implementation of the optional **IPersistPropertyBag**.**Load** interface.</span></span> <span data-ttu-id="d82b7-112">La configuración del controlador se entrega solo una vez, de modo que si la configuración del controlador del adaptador cambia una vez que el servicio de BizTalk ha comenzado, el adaptador no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="d82b7-112">The handler configuration is delivered only once, so if the adapter handler configuration is changed after the BizTalk service has started the adapter is not updated.</span></span> <span data-ttu-id="d82b7-113">El modelo común consiste en que el adaptador trate la configuración del controlador como la configuración predeterminada; la configuración de extremo invalida la configuración del controlador según un esquema por extremos.</span><span class="sxs-lookup"><span data-stu-id="d82b7-113">The common model is for the adapter to treat the handler configuration as the default configuration; endpoint configuration overrides the handler configuration on a per-endpoint basis.</span></span>  
  
 <span data-ttu-id="d82b7-114">El fragmento de código que se muestra a continuación demuestra el análisis de la configuración.</span><span class="sxs-lookup"><span data-stu-id="d82b7-114">The following code fragment demonstrates parsing the configuration.</span></span> <span data-ttu-id="d82b7-115">La configuración del adaptador se encuentra en la propiedad que se pasa a la **carga** llamar a en la propiedad de cadena **AdapterConfig**.</span><span class="sxs-lookup"><span data-stu-id="d82b7-115">The adapter's configuration is in the property passed in to the **Load** call in the string property **AdapterConfig**.</span></span> <span data-ttu-id="d82b7-116">Este valor de propiedad contiene un documento XML que representa la configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="d82b7-116">This property value contains an XML document representing the adapter's configuration.</span></span> <span data-ttu-id="d82b7-117">El adaptador necesita cargar su configuración en un modelo de objetos de documento (DOM) o en un lector XML y usa XPath para recuperar las propiedades individuales.</span><span class="sxs-lookup"><span data-stu-id="d82b7-117">The adapter needs to load this configuration into a document object model (DOM) or an XML reader and use XPath to retrieve the individual properties.</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,  
 IPersistPropertyBag,   
 IBaseComponent  
{  
...  
// Handler configuration properties...  
private int defaultBatchSize = 0;  
private string defaultHeader;  
  
// IPersistPropertyBag.Load() implementation...  
public void Load(IPropertyBag pb, int pErrorLog)  
{  
// The adapter configuration is in the property  
 // “AdapterConfig” in the form of an Xml blob...  
object obj = null;  
pb.Read("AdapterConfig", out obj, 0);  
  
// Create a DOM and load the Xml blob...  
XmlDocument dom = new XmlDocument();  
string adapterConfig = (string)obj;  
dom.LoadXml(adapterConfig);  
  
// XPath the individual properties...  
XmlNode node =   
 document.SelectSingleNode(“/Config/batchSize”);  
defaultBatchSize = int.Parse(node.InnerText);  
  
node = document.SelectSingleNode(“/Config/header”);  
defaultHeader = node.InnerText;  
}  
}  
```  
  
## <a name="receive-location-configuration"></a><span data-ttu-id="d82b7-118">Configuración de la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="d82b7-118">Receive Location Configuration</span></span>  
 <span data-ttu-id="d82b7-119">Ubicación de recepción de información de configuración se entrega a un adaptador en su implementación de **IBTTransportConfig**.</span><span class="sxs-lookup"><span data-stu-id="d82b7-119">Receive location configuration information is delivered to an adapter on its implementation of **IBTTransportConfig**.</span></span> <span data-ttu-id="d82b7-120">Esta interfaz contiene tres métodos **AddReceiveEndpoint**, **UpdateEndpointConfig**, y **RemoveReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="d82b7-120">This interface contains the three methods **AddReceiveEndpoint**, **UpdateEndpointConfig**, and **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="d82b7-121">El motor de mensajería notifica al adaptador sobre cuáles son los extremos que necesita escuchar para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="d82b7-121">The Messaging Engine notifies the adapter of which endpoints it needs to listen on to receive messages.</span></span> <span data-ttu-id="d82b7-122">Cuando la configuración de un extremo individual cambia, se notifica ese cambio al adaptador.</span><span class="sxs-lookup"><span data-stu-id="d82b7-122">When the configuration for an individual endpoint is changed the adapter is notified of the change for that endpoint.</span></span> <span data-ttu-id="d82b7-123">En cambio, cuando la configuración del controlador cambia, no se notifica este cambio al adaptador.</span><span class="sxs-lookup"><span data-stu-id="d82b7-123">This is in contrast to the fact that when handler configuration changes the adapter is not notified.</span></span> <span data-ttu-id="d82b7-124">Del mismo modo, el adaptador no tiene que controlar ventanas de servicio porque BizTalk Server agregue o quite extremos a medida que las ventanas de servicio se activan o inactivan.</span><span class="sxs-lookup"><span data-stu-id="d82b7-124">Similarly, the adapter does not need to handle service windows because BizTalk Server adds or removes endpoints as service windows become active or inactive.</span></span>  
  
### <a name="addreceiveendpoint"></a><span data-ttu-id="d82b7-125">AddReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="d82b7-125">AddReceiveEndpoint</span></span>  
 <span data-ttu-id="d82b7-126">Cuando un adaptador necesita empezar a escuchar en un punto de conexión, el motor llama **IBTTransportConfig.AddReceiveEndpoint** pasando el URI de la ubicación de recepción, un contenedor de propiedades con la configuración del adaptador para dicho extremo, y una segunda bolsa de propiedades que contiene la configuración específica de BizTalk Server para ese extremo.</span><span class="sxs-lookup"><span data-stu-id="d82b7-126">When an adapter needs to begin listening on an endpoint, the engine calls **IBTTransportConfig.AddReceiveEndpoint** passing in the receive location's URI, a property bag containing the adapter's configuration for that endpoint, and a second property bag containing BizTalk Server-specific configuration for that endpoint.</span></span> <span data-ttu-id="d82b7-127">El adaptador tiene que escribir el URI en el contexto del mensaje como la propiedad del sistema BizTalk Server **InboundTransportLocation**.</span><span class="sxs-lookup"><span data-stu-id="d82b7-127">The adapter needs to write the URI to the message context as the BizTalk Server system property **InboundTransportLocation**.</span></span>  
  
 <span data-ttu-id="d82b7-128">La lectura de las propiedades de la ubicación de recepción desde la bolsa de propiedades del adaptador es lo mismo que la lectura de la configuración del controlador, tal y como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d82b7-128">Reading the receive location properties from the adapter's property bag is the same as reading the handler configuration as detailed above.</span></span> <span data-ttu-id="d82b7-129">La configuración de BizTalk Server pasada al adaptador contiene una propiedad única, **TwoWayReceivePort**, lo que indica si el puerto es unidireccional o bidireccional.</span><span class="sxs-lookup"><span data-stu-id="d82b7-129">The BizTalk Server configuration passed into the adapter contains a single property, **TwoWayReceivePort**, which indicates whether the port is one-way or two-way.</span></span> <span data-ttu-id="d82b7-130">El fragmento de código siguiente ilustra cómo se evalúa si el puerto de recepción es unidireccional o bidireccional desde la bolsa de propiedades de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="d82b7-130">The following code fragment illustrates how to evaluate if the receive port is one-way or two-way from the BizTalk Server property bag:</span></span>  
  
```  
public void AddReceiveEndpoint(  
 string  url,   
 IPropertyBag adapterConfig,   
 IPropertyBag bizTalkConfig )  
{  
...  
  
// The property "TwoWayReceivePort" in the BizTalk Config  
// property bag indicates whether the port is one or two  
 // way...  
  
 // Add receive location to config cache (not shown here)  
  
object obj = null;  
bizTalkConfig.Read("TwoWayReceivePort", out obj, 0);  
  
if ( null != obj )  
this.twoWay = (bool)obj;  
}  
```  
  
### <a name="updateendpointconfig"></a><span data-ttu-id="d82b7-131">UpdateEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="d82b7-131">UpdateEndpointConfig</span></span>  
 <span data-ttu-id="d82b7-132">Cuando la configuración de un activo de recepción se cambia la ubicación, el motor utiliza el **UpdateEndpointConfig** API para notificar el adaptador que debe usar una configuración diferente.</span><span class="sxs-lookup"><span data-stu-id="d82b7-132">When the configuration of an active receive location is changed, the engine uses the **UpdateEndpointConfig** API to notify the adapter that it needs to use a different configuration.</span></span> <span data-ttu-id="d82b7-133">Toda la configuración se entrega al adaptador, incluida la configuración específica de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d82b7-133">All of the configuration is delivered to the adapter, including the BizTalk Server-specific configuration.</span></span>  
  
### <a name="removereceiveendpoint"></a><span data-ttu-id="d82b7-134">RemoveReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="d82b7-134">RemoveReceiveEndpoint</span></span>  
 <span data-ttu-id="d82b7-135">Cuando una ubicación de recepción ya no está activa, el adaptador recibe la notificación a través de **RemoveReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="d82b7-135">When a receive location is no longer active, the adapter is notified through **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="d82b7-136">Después de que el adaptador vuelve desde **RemoveReceiveEndpoint** ya no está permitido usar ese URI para enviar mensajes al motor.</span><span class="sxs-lookup"><span data-stu-id="d82b7-136">After the adapter returns from **RemoveReceiveEndpoint** it is no longer allowed to use that URI to submit messages into the engine.</span></span>  
  
## <a name="send-port-configuration"></a><span data-ttu-id="d82b7-137">Configuración del puerto de envío</span><span class="sxs-lookup"><span data-stu-id="d82b7-137">Send Port Configuration</span></span>  
 <span data-ttu-id="d82b7-138">El motor de mensajería escribe la configuración del puerto de envío en el contexto del mensaje en el espacio de nombres del adaptador antes de entregar el mensaje a éste.</span><span class="sxs-lookup"><span data-stu-id="d82b7-138">The Messaging Engine writes the configuration for the send port to the message context in the adapter’s namespace before delivering the message to the adapter.</span></span> <span data-ttu-id="d82b7-139">Ahora, es el adaptador el responsable de leer y validar la configuración que usa posteriormente para controlar la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d82b7-139">It is the adapters’ responsibility to read and validate the configuration, which it subsequently uses to control the transmission of the message.</span></span> <span data-ttu-id="d82b7-140">Para los adaptadores de envío compatibles con los envíos por lotes, los mensajes destinados a diferentes puertos de envío pueden encontrarse en el mismo lote, por lo que el adaptador necesita controlar estos lotes “mixtos”.</span><span class="sxs-lookup"><span data-stu-id="d82b7-140">For send adapters that support batched sends, messages destined for different send ports may be in the same batch, so the adapter needs to handle these "mixed" batches.</span></span>  
  
 <span data-ttu-id="d82b7-141">El siguiente fragmento de código muestra cómo leer el **OutboundTransportLocation** que es el URI del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d82b7-141">The following code fragment illustrates how to read the **OutboundTransportLocation** that is the URI for the send port.</span></span> <span data-ttu-id="d82b7-142">También muestra cómo se lee el Blob de tipo XML que contiene la configuración del adaptador y, después, cómo se leen las propiedades individuales.</span><span class="sxs-lookup"><span data-stu-id="d82b7-142">It also shows how to read the XML blob containing the adapter's configuration and then read the individual properties.</span></span>  
  
```  
...  
 private static readonly PropertyBase UriProperty =   
 new BTS.OutboundTransportLocation();  
  
 private string propertyNamespace =   
  "http://schemas.mySchemas.com/MyAdapter/myadapter-properties";  
private string uri;  
private string headers;  
private int timeOut = 1000;  
  
private void ReadSendPortConfig(IBaseMessage msg)  
{  
// Read the OutboundTransportLocation,   
 // i.e. the send port uri....  
uri = (string)msg.Context.Read(  
 UriProperty.Name.Name, UriProperty.Name.Namespace);  
  
// Read the adapters configuration Xml blob from   
 // the message...  
XmlDocument locationConfigDom = null;  
object obj = msg.Context.Read(  
 "AdapterConfig", this.propertyNamespace);  
  
// If this is a dynamic send there will not be   
 // any configuration...  
if ( null != obj )  
{  
locationConfigDom = new XmlDocument();  
locationConfigDom.LoadXml((string)obj);  
  
this.headers = Extract(  
 locationConfigDom, "/Config/headers", true);  
  
 this.timeOut = ExtractInt32(  
 locationConfigDom, "/Config/timeOut", true);  
}  
}  
  
 // Helper method to XPath string properties...  
private static string Extract(  
 XmlDocument document, string path, bool required)  
{  
XmlNode node = document.SelectSingleNode(path);  
if (!required && null == node)  
return String.Empty;  
if (null == node)  
throw new ApplicationException(string.Format(  
 "No property was found at {0}", path));  
return node.InnerText;  
}  
  
  // Helper method to XPath int32 properties...  
private static int ExtractInt32(  
 XmlDocument document, string path, bool required)  
{  
string s = Extract(document, path, required);  
return int.Parse(s);  
}   
```  
  
 <span data-ttu-id="d82b7-143">**Sugerencia para la implementación:** adaptadores en general deben usar el **OutboundTransportLocation** propiedad de contexto para determinar la dirección para enviar el mensaje del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d82b7-143">**Implementation Tip:** Adapters should in general use the **OutboundTransportLocation** message context property to determine the address to send the message to.</span></span> <span data-ttu-id="d82b7-144">De este modo, el adaptador puede controlar las transmisiones en los envíos estáticos y dinámicos de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="d82b7-144">By doing this the adapter can handle transmissions to both static and dynamic sends consistently.</span></span> <span data-ttu-id="d82b7-145">Además, simplifica la modificación de direcciones en los archivos de enlace de producción.</span><span class="sxs-lookup"><span data-stu-id="d82b7-145">This also simplifies the modification of addresses in production binding files.</span></span>  
  
## <a name="xsd"></a><span data-ttu-id="d82b7-146">XSD</span><span class="sxs-lookup"><span data-stu-id="d82b7-146">XSD</span></span>  
 <span data-ttu-id="d82b7-147">Cuatro archivos XSD incluidos en el ejemplo de adaptador de archivo del SDK principalmente identificador de configuración del adaptador: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd y TransmitHandler.xsd.</span><span class="sxs-lookup"><span data-stu-id="d82b7-147">Four XSD files included in the SDK File Adapter sample primarily handle adapter configuration: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd, and TransmitHandler.xsd.</span></span>  
  
 <span data-ttu-id="d82b7-148">En los temas siguientes se aborda cada uno de estos archivos y se describe cómo se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="d82b7-148">The following topics discuss each of these files and describe how you can modify them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d82b7-149">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d82b7-149">In This Section</span></span>  
  
-   [<span data-ttu-id="d82b7-150">Validar la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-150">Validating the Adapter Configuration</span></span>](../core/validating-the-adapter-configuration.md)  
  
-   [<span data-ttu-id="d82b7-151">Registrar un adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-151">Registering an Adapter</span></span>](../core/registering-an-adapter.md)  
  
-   [<span data-ttu-id="d82b7-152">Extensiones de esquema de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="d82b7-152">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [<span data-ttu-id="d82b7-153">Tipos de elemento XSD compatibles con el adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-153">Supported Adapter XSD Element Types</span></span>](../core/supported-adapter-xsd-element-types.md)  
  
-   [<span data-ttu-id="d82b7-154">Construcciones de elemento-atributo XSD de adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-154">Adapter XSD Element-Attribute Constructs</span></span>](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [<span data-ttu-id="d82b7-155">Construcciones de faceta del tipo de datos XSD de adaptador</span><span class="sxs-lookup"><span data-stu-id="d82b7-155">Adapter XSD Data Type-Facet Constructs</span></span>](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [<span data-ttu-id="d82b7-156">Componentes de configuración avanzada para adaptadores</span><span class="sxs-lookup"><span data-stu-id="d82b7-156">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)
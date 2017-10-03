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
# <a name="adapter-design-issues"></a>Problemas de diseño del adaptador
La configuración del adaptador se almacena en la base de datos de inicio de sesión único (SSO) cuando el usuario realiza cambios de configuración durante el tiempo de diseño. En el tiempo de ejecución, el motor de mensajería recupera la configuración del adaptador y la entrega a éste. La información de configuración que se entrega a los adaptadores es de cuatro tipos:  
  
-   Configuración del controlador de recepción  
  
-   Configuración de la ubicación de recepción (extremo)  
  
-   Configuración del controlador de envío  
  
-   Configuración de la ubicación de envío (extremo)  
  
## <a name="receive-and-send-handler-configuration"></a>Configuración del controlador de recepción y de envío  
 Configuración del controlador de un adaptador se entrega al adaptador en su implementación de la parte opcional **IPersistPropertyBag**. **Carga** interfaz. La configuración del controlador se entrega solo una vez, de modo que si la configuración del controlador del adaptador cambia una vez que el servicio de BizTalk ha comenzado, el adaptador no se actualiza. El modelo común consiste en que el adaptador trate la configuración del controlador como la configuración predeterminada; la configuración de extremo invalida la configuración del controlador según un esquema por extremos.  
  
 El fragmento de código que se muestra a continuación demuestra el análisis de la configuración. La configuración del adaptador se encuentra en la propiedad que se pasa a la **carga** llamar a en la propiedad de cadena **AdapterConfig**. Este valor de propiedad contiene un documento XML que representa la configuración del adaptador. El adaptador necesita cargar su configuración en un modelo de objetos de documento (DOM) o en un lector XML y usa XPath para recuperar las propiedades individuales.  
  
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
  
## <a name="receive-location-configuration"></a>Configuración de la ubicación de recepción  
 Ubicación de recepción de información de configuración se entrega a un adaptador en su implementación de **IBTTransportConfig**. Esta interfaz contiene tres métodos **AddReceiveEndpoint**, **UpdateEndpointConfig**, y **RemoveReceiveEndpoint**. El motor de mensajería notifica al adaptador sobre cuáles son los extremos que necesita escuchar para recibir mensajes. Cuando la configuración de un extremo individual cambia, se notifica ese cambio al adaptador. En cambio, cuando la configuración del controlador cambia, no se notifica este cambio al adaptador. Del mismo modo, el adaptador no tiene que controlar ventanas de servicio porque BizTalk Server agregue o quite extremos a medida que las ventanas de servicio se activan o inactivan.  
  
### <a name="addreceiveendpoint"></a>AddReceiveEndpoint  
 Cuando un adaptador necesita empezar a escuchar en un punto de conexión, el motor llama **IBTTransportConfig.AddReceiveEndpoint** pasando el URI de la ubicación de recepción, un contenedor de propiedades con la configuración del adaptador para dicho extremo, y una segunda bolsa de propiedades que contiene la configuración específica de BizTalk Server para ese extremo. El adaptador tiene que escribir el URI en el contexto del mensaje como la propiedad del sistema BizTalk Server **InboundTransportLocation**.  
  
 La lectura de las propiedades de la ubicación de recepción desde la bolsa de propiedades del adaptador es lo mismo que la lectura de la configuración del controlador, tal y como se ha descrito anteriormente. La configuración de BizTalk Server pasada al adaptador contiene una propiedad única, **TwoWayReceivePort**, lo que indica si el puerto es unidireccional o bidireccional. El fragmento de código siguiente ilustra cómo se evalúa si el puerto de recepción es unidireccional o bidireccional desde la bolsa de propiedades de BizTalk Server:  
  
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
  
### <a name="updateendpointconfig"></a>UpdateEndpointConfig  
 Cuando la configuración de un activo de recepción se cambia la ubicación, el motor utiliza el **UpdateEndpointConfig** API para notificar el adaptador que debe usar una configuración diferente. Toda la configuración se entrega al adaptador, incluida la configuración específica de BizTalk Server.  
  
### <a name="removereceiveendpoint"></a>RemoveReceiveEndpoint  
 Cuando una ubicación de recepción ya no está activa, el adaptador recibe la notificación a través de **RemoveReceiveEndpoint**. Después de que el adaptador vuelve desde **RemoveReceiveEndpoint** ya no está permitido usar ese URI para enviar mensajes al motor.  
  
## <a name="send-port-configuration"></a>Configuración del puerto de envío  
 El motor de mensajería escribe la configuración del puerto de envío en el contexto del mensaje en el espacio de nombres del adaptador antes de entregar el mensaje a éste. Ahora, es el adaptador el responsable de leer y validar la configuración que usa posteriormente para controlar la transmisión del mensaje. Para los adaptadores de envío compatibles con los envíos por lotes, los mensajes destinados a diferentes puertos de envío pueden encontrarse en el mismo lote, por lo que el adaptador necesita controlar estos lotes “mixtos”.  
  
 El siguiente fragmento de código muestra cómo leer el **OutboundTransportLocation** que es el URI del puerto de envío. También muestra cómo se lee el Blob de tipo XML que contiene la configuración del adaptador y, después, cómo se leen las propiedades individuales.  
  
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
  
 **Sugerencia para la implementación:** adaptadores en general deben usar el **OutboundTransportLocation** propiedad de contexto para determinar la dirección para enviar el mensaje del mensaje. De este modo, el adaptador puede controlar las transmisiones en los envíos estáticos y dinámicos de forma coherente. Además, simplifica la modificación de direcciones en los archivos de enlace de producción.  
  
## <a name="xsd"></a>XSD  
 Cuatro archivos XSD incluidos en el ejemplo de adaptador de archivo del SDK principalmente identificador de configuración del adaptador: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd y TransmitHandler.xsd.  
  
 En los temas siguientes se aborda cada uno de estos archivos y se describe cómo se pueden modificar.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Validar la configuración del adaptador](../core/validating-the-adapter-configuration.md)  
  
-   [Registrar un adaptador](../core/registering-an-adapter.md)  
  
-   [Extensiones de esquema de configuración de marco de trabajo de adaptadores](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [Tipos de elemento XSD compatibles con el adaptador](../core/supported-adapter-xsd-element-types.md)  
  
-   [Construcciones de elemento-atributo XSD de adaptador](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [Construcciones de faceta del tipo de datos XSD de adaptador](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [Componentes de configuración avanzada para adaptadores](../core/advanced-configuration-components-for-adapters.md)
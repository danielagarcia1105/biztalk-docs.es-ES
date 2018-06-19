---
title: Encabezados SOAP con servicios WCF publicados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, SOAP headers [WCF services]
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: 5564a57e-e241-4595-a959-4289c8502410
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f36e778930a781ac797e18308240ecb4bef667
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975690"
---
# <a name="soap-headers-with-published-wcf-services"></a><span data-ttu-id="c66e7-102">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="c66e7-102">SOAP Headers with Published WCF Services</span></span>
<span data-ttu-id="c66e7-103">Adaptadores de recepción de WCF pueden copiar todos los valores de encabezado SOAP en los mensajes entrantes en el **InboundHeaders** propiedad, o puede escribir o promover valores específicos en el contexto del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c66e7-103">The WCF receive adapters can copy all the SOAP header values in the inbound messages to the **InboundHeaders** property, or they can write or promote specified values to the BizTalk message context.</span></span> <span data-ttu-id="c66e7-104">Los adaptadores pueden funcionar con los encabezados SOAP personalizados y los encabezados SOAP estándar que utiliza la infraestructura de WCF, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="c66e7-104">The adapters can work with both custom SOAP headers and standard SOAP headers that the WCF infrastructure uses, such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="c66e7-105">El **InboundHeaders** propiedad de contexto está en el espacio de nombres de destino **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**y contiene representaciones de cadena de SOAP valores de encabezado de mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c66e7-105">The **InboundHeaders** context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the SOAP header values in inbound messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c66e7-106">Si va a promover los valores del encabezado SOAP que ha especificado, debe haber un esquema de propiedades implementado en el proyecto de BizTalk que corresponda a los valores que se van a promover.</span><span class="sxs-lookup"><span data-stu-id="c66e7-106">If you are going to promote the SOAP header values you specified, there must be a deployed property schema in your BizTalk project that corresponds to the values you are promoting.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c66e7-107">Las propiedades promocionadas no pueden ser superiores a 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="c66e7-107">The promoted properties cannot be longer than 256 characters.</span></span>  
  
 <span data-ttu-id="c66e7-108">Los siguientes datos XML muestran un ejemplo de la representación de cadena de los encabezados SOAP para la **InboundHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c66e7-108">The following XML data shows an example of the string representation of the SOAP headers for the **InboundHeaders** property.</span></span> <span data-ttu-id="c66e7-109">Esto se recibe desde el cliente y se envía a la ubicación de recepción de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c66e7-109">This comes from the client and is sent to the BizTalk receive location.</span></span>  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 <span data-ttu-id="c66e7-110">Para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk, es necesario colocar una colección de parejas de valores que se componen del nombre de propiedad y de espacio de nombres en el mensaje WCF, de modo que los adaptadores de WCF reconocerán que los valores de encabezado se deben escribir o promover.</span><span class="sxs-lookup"><span data-stu-id="c66e7-110">To write or promote SOAP header values to the BizTalk message context, you need to put a collection of value pairs that consist of property name and namespace into the WCF message so that the WCF adapters will recognize that the header values are to be written or promoted.</span></span> <span data-ttu-id="c66e7-111">Un adaptador de WCF espera las siguientes propiedades del mensaje en los mensajes de WCF para escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="c66e7-111">A WCF adapter expects the following message properties in the WCF messages for writing or promoting SOAP header values to the BizTalk message context:</span></span>  
  
-   <span data-ttu-id="c66e7-112">Para promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, los adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote** y el valor **lista\< KeyValuePair\<XmlQualifiedName, objeto\>\>**.</span><span class="sxs-lookup"><span data-stu-id="c66e7-112">To promote the SOAP header values to the BizTalk message context, WCF adapters are looking for the pair of key **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote** and value **List\<KeyValuePair\<XmlQualifiedName, object\>\>**.</span></span>  
  
     <span data-ttu-id="c66e7-113">Con esta pareja, adaptadores de WCF toman el espacio de nombres, el nombre y el valor de la **XmlQualifiedName** objeto y usarlos para la promoción de los valores de encabezado.</span><span class="sxs-lookup"><span data-stu-id="c66e7-113">Using this pair, WCF adapters take the namespace, name, and value from the **XmlQualifiedName** object and use them for promoting the header values.</span></span>  
  
-   <span data-ttu-id="c66e7-114">Para escribir pero no promover los valores del encabezado SOAP en el contexto de mensaje de BizTalk, los adaptadores de WCF se buscan la pareja de clave **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext** y el valor  **Lista\<KeyValuePair\<XmlQualifiedName, objeto\>\>**.</span><span class="sxs-lookup"><span data-stu-id="c66e7-114">To write but not promote the SOAP header values to the BizTalk message context, WCF adapters are looking for the pair of key **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext** and value **List\<KeyValuePair\<XmlQualifiedName, object\>\>**.</span></span>  
  
     <span data-ttu-id="c66e7-115">Con esta pareja, los adaptadores de WCF escriben los valores en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c66e7-115">Using this pair, WCF adapters write the values to the message context.</span></span>  
  
 <span data-ttu-id="c66e7-116">El siguiente código muestra cómo escribir o promover los valores del encabezado SOAP en el contexto del mensaje de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="c66e7-116">The following code shows how to write or promote the SOAP header values to the BizTalk message context:</span></span>  
  
```  
const string PropertiesToPromoteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote";  
const string PropertiesToWriteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext";  
  
XmlQualifiedName PropName1=new XmlQualifiedName("Destination", "http://tempuri.org/2007/sample-properties");  
XmlQualifiedName PropName2=new XmlQualifiedName("Source", "http://tempuri.org/2007/sample-properties");  
  
//Create a List of KeyValuePairs that indicate properties to be promoted to BizTalk message context.   
//A Property Schema must be deployed and string values have a limit of 256 characters  
List<KeyValuePair<XmlQualifiedName, object>> promoteProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
promoteProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName1, "Property value"));  
wcfMessage.Properties[PropertiesToPromoteKey]=promoteProps;  
  
//Create a List of KeyValuePairs that indicate properties to be written to BizTalk message context  
List<KeyValuePair<XmlQualifiedName, object>> writeProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
writeProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName2, "Property value"));  
wcfMessage.Properties[PropertiesToWriteKey]=writeProps;  
```  
  
 <span data-ttu-id="c66e7-117">El Asistente para publicación de Servicio WCF de BizTalk no incluye definiciones de encabezado SOAP personalizadas en los metadatos generados.</span><span class="sxs-lookup"><span data-stu-id="c66e7-117">The BizTalk WCF Service Publishing Wizard does not include custom SOAP header definitions in the generated metadata.</span></span> <span data-ttu-id="c66e7-118">Para publicar los metadatos de los servicios WCF con encabezados SOAP personalizados, debe crear de forma manual un archivo de Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="c66e7-118">To publish metadata for WCF services using custom SOAP headers, you should manually create a Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="c66e7-119">Puede usar el **externalMetadataLocation** atributo de la [ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121) elemento en el archivo Web.config que genera el Asistente para especificar la ubicación de la Archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="c66e7-119">You can use the **externalMetadataLocation** attribute of the [\<serviceMetadata\>](http://go.microsoft.com/fwlink/?LinkId=89121) element in the Web.config file that the wizard generates to specify the location of the WSDL file.</span></span> <span data-ttu-id="c66e7-120">El archivo WSDL se devuelve al usuario en respuesta a las solicitudes de intercambio de metadatos (MEX) WSDL en lugar de WSDL generado de forma automática.</span><span class="sxs-lookup"><span data-stu-id="c66e7-120">The WSDL file is returned to the user in response to WSDL and metadata exchange (MEX) requests instead of the auto-generated WSDL.</span></span>  
  
 <span data-ttu-id="c66e7-121">Los siguientes datos XML muestran un ejemplo de una parte del archivo WSDL que define los encabezados SOAP personalizados:</span><span class="sxs-lookup"><span data-stu-id="c66e7-121">The following XML data shows an example of a part of the WSDL file defining custom SOAP headers:</span></span>  
  
```  
<wsdl:operation name="Request">  
  <soap12:operation soapAction="http://Microsoft.Samples.BizTalk.NetTcpAdapter/OrderProcess/IOrderProcess/Request" style="document" />   
   <wsdl:input name="Order">  
     <soap12:header message="i0:Order_Headers" part="SalesAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:input>  
   <wsdl:output name="OrderConfirmation">  
     <soap12:header message="i0:OrderConfirmation_Headers" part="PaymentAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:output>  
</wsdl:operation>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="c66e7-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c66e7-122">In This Section</span></span>  
  
-   [<span data-ttu-id="c66e7-123">Obtener acceso a encabezados SOAP en mensajes WCF con orquestaciones</span><span class="sxs-lookup"><span data-stu-id="c66e7-123">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="c66e7-124">Obtener acceso a encabezados SOAP en mensajes WCF con componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="c66e7-124">Accessing SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="c66e7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c66e7-125">See Also</span></span>  
 <span data-ttu-id="c66e7-126">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c66e7-126">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="c66e7-127">Encabezados SOAP con servicios WCF consumidos</span><span class="sxs-lookup"><span data-stu-id="c66e7-127">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)
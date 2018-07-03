---
title: Obtener metadatos mediante WS-Metadata Exchange en SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55ba97f7757ff6f61a98002c496d9b6b26fc7be9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002069"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a><span data-ttu-id="88904-102">Obtener metadatos mediante WS-Metadata Exchange en SAP</span><span class="sxs-lookup"><span data-stu-id="88904-102">Get Metadata Using WS-Metadata Exchange in SAP</span></span>
<span data-ttu-id="88904-103">Como un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado, el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone un extremo de WS-Metadata Exchange (MEX) que puede usar para recuperar metadatos para operaciones específicas de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88904-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
 <span data-ttu-id="88904-104">WCF proporciona una infraestructura enriquecida para exportar, publicar, recuperar e importar metadatos sobre un servicio.</span><span class="sxs-lookup"><span data-stu-id="88904-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="88904-105">Servicios WCF, como el adaptador, utilizan metadatos para describir cómo interactuar con los puntos de conexión de servicio para que las herramientas, como svcutil.exe, puedan generar automáticamente código de cliente para consumir el servicio.</span><span class="sxs-lookup"><span data-stu-id="88904-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="88904-106">WCF representa los metadatos para un servicio como una instancia de la **MetadataSet** tipo, que está estrechamente ligado a formato de serialización de metadatos definido en WS-Metadata Exchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="88904-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="88904-107">Puede crear un **MetadataSet** para las operaciones de destino en el adaptador mediante el uso de un **MetadataExchangeClient**.</span><span class="sxs-lookup"><span data-stu-id="88904-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="88904-108">WCF admite para el intercambio de metadatos es un tema amplio y más allá del ámbito de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="88904-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="88904-109">Para obtener más información sobre la compatibilidad con metadatos en WCF, vea "Metadata" en la documentación de WCF en [ http://go.microsoft.com/fwlink/?LinkId=105634 ](http://go.microsoft.com/fwlink/?LinkId=105634).</span><span class="sxs-lookup"><span data-stu-id="88904-109">For more information about support for metadata in WCF, see "Metadata" in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634).</span></span> <span data-ttu-id="88904-110">Para obtener una descripción muy buena de la arquitectura, las clases y espacios de nombres que WCF expone metadatos, vea "Información general de arquitectura de metadatos" en [ http://go.microsoft.com/fwlink/?LinkId=105635 ](http://go.microsoft.com/fwlink/?LinkId=105635).</span><span class="sxs-lookup"><span data-stu-id="88904-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see "Metadata Architecture Overview" at [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635).</span></span> <span data-ttu-id="88904-111">Debe familiarizarse con el contenido relacionado con la recuperación de metadatos de un servicio WCF en estos temas WCF antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="88904-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="88904-112">Los temas siguientes contienen información sobre cómo usar un **MetadataExchangeClient** para recuperar metadatos desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88904-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="88904-113">Usar un MetadataExchangeClient para recuperar metadatos</span><span class="sxs-lookup"><span data-stu-id="88904-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="88904-114">Para usar un **MetadataExchangeClient** debe especificar un URI de conexión y un enlace (**SAPBinding**).</span><span class="sxs-lookup"><span data-stu-id="88904-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**SAPBinding**).</span></span> <span data-ttu-id="88904-115">El URI de conexión identifica las operaciones para el que desea recuperar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="88904-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="88904-116">Las secciones siguientes contienen información acerca de cómo especificar las propiedades de enlace importante, el URI de conexión y cómo usar un **MetadataExchangeClient** para recuperar los metadatos del adaptador.</span><span class="sxs-lookup"><span data-stu-id="88904-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="88904-117">El URI de conexión</span><span class="sxs-lookup"><span data-stu-id="88904-117">The Connection URI</span></span>  
 <span data-ttu-id="88904-118">Para usar el **MetadataExchangeClient** debe proporcionar un URI que especifica un extremo de MEX y la o las operaciones para el que desea recuperar los metadatos de la conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="88904-118">To use the **MetadataExchangeClient** you must supply a SAP connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="88904-119">Especifique una operación de punto de conexión y de destino MEX en el URI de conexión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="88904-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
- <span data-ttu-id="88904-120">Debe incluir el parámetro "wsdl" en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="88904-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="88904-121">Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="88904-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="88904-122">Si no es el primer parámetro, debe ir precedida por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="88904-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
- <span data-ttu-id="88904-123">Debe seguir el parámetro "wsdl" por uno o varios parámetros "op".</span><span class="sxs-lookup"><span data-stu-id="88904-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="88904-124">Cada parámetro de "op" está precedido por una y comercial (&) y especifica la acción de mensaje (Id. de nodo) de una operación de destino.</span><span class="sxs-lookup"><span data-stu-id="88904-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
  <span data-ttu-id="88904-125">Por ejemplo, el siguiente URI de conexión dirige a la operación de envío para el IDOC SALESORDER_CREATEFROMDAT201 y el IDOC SALESORDER_CREATEFROMDAT202.</span><span class="sxs-lookup"><span data-stu-id="88904-125">For example, the following connection URI targets the Send operation for the SALESORDER_CREATEFROMDAT201 IDOC and the SALESORDER_CREATEFROMDAT202 IDOC.</span></span> <span data-ttu-id="88904-126">Se resaltan los parámetros "wsdl" y "op".</span><span class="sxs-lookup"><span data-stu-id="88904-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  <span data-ttu-id="88904-127">No es necesario incluir los parámetros de agente de escucha en el URI de conexión para las operaciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="88904-127">It is not necessary to include listener parameters in the connection URI for inbound operations.</span></span> <span data-ttu-id="88904-128">El adaptador se conecta como un cliente para recuperar metadatos desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="88904-128">The adapter connects as a client to retrieve metadata from the SAP system.</span></span>  
  
 <span data-ttu-id="88904-129">También puede usar las constantes definidas al `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` para especificar las operaciones cuando se crea un URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="88904-129">You can also use the constants defined at `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you specify operations when you create a connection URI.</span></span> <span data-ttu-id="88904-130">Esto se muestra en el ejemplo de código al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="88904-130">This is demonstrated in the code example at the end of this topic.</span></span>  
  
 <span data-ttu-id="88904-131">Cómo pasar este URI de conexión para el **MetadataExchangeClient** dependerá de cuál de los métodos sobrecargados que utilice para crear el cliente y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="88904-131">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="88904-132">Para obtener más información sobre el URI de conexión de SAP, consulte [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="88904-132">For more information about the SAP connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="88904-133">Propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="88904-133">Binding Properties</span></span>  
 <span data-ttu-id="88904-134">Cuando se crea el **MetadataExchangeClient**, debe especificar un **SAPBinding**.</span><span class="sxs-lookup"><span data-stu-id="88904-134">When you create the **MetadataExchangeClient**, you must specify an **SAPBinding**.</span></span>  
  
 <span data-ttu-id="88904-135">Hay varias propiedades de enlace que afectan a cómo el adaptador genera metadatos.</span><span class="sxs-lookup"><span data-stu-id="88904-135">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="88904-136">Estas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="88904-136">These properties are:</span></span>  
  
- <span data-ttu-id="88904-137">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="88904-137">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
- <span data-ttu-id="88904-138">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="88904-138">**ReceiveIDocFormat**</span></span>  
  
- <span data-ttu-id="88904-139">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="88904-139">**EnableSafeTyping**</span></span>  
  
- <span data-ttu-id="88904-140">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="88904-140">**FlatFileSegmentIndicator**</span></span>  
  
  <span data-ttu-id="88904-141">Debe asegurarse de que se establecen estas propiedades de enlace en los valores necesarios para la aplicación antes de invocar el **GetMetadata** método en el **MetadataExchangeClient**.</span><span class="sxs-lookup"><span data-stu-id="88904-141">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="88904-142">Para obtener más información acerca de las propiedades de enlace del adaptador SAP, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="88904-142">For more information about the SAP adapter binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="88904-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88904-143">Example</span></span>  
 <span data-ttu-id="88904-144">En el ejemplo siguiente se usa un **MetadataExchangeClient** para crear una descripción del servicio (documento WSDL) para las operaciones BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="88904-144">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and SAP adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
// Needed for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace SapMetadataExchangeClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //Create a metadata exchange client that will retrieve metadata according to the WS-MEX standard.  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "YourUserName";  
            client.SoapCredentials.UserName.Password = "YourPassword";  
  
            //Set up an endpoint address and specify the operation for which we want metadata.  
            string connectionUri = "sap://Client=800;lang=EN@A/YourSAPHost/00?wsdl&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_COMMIT"  
                + "&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_ROLLBACK";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //Get the metadata.  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size.   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //Get the WSDL from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //Save the WSDL to a file.  
                wsdl.Write("BapiTx.wsdl");    
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="88904-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="88904-145">See Also</span></span>  
 <span data-ttu-id="88904-146">[Recuperar metadatos mediante programación desde SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span><span class="sxs-lookup"><span data-stu-id="88904-146">[Retrieving Metadata Programmatically from SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span></span>  
 [<span data-ttu-id="88904-147">Recuperación de metadatos de SAP mediante IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="88904-147">Retrieving Metadata in SAP using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)
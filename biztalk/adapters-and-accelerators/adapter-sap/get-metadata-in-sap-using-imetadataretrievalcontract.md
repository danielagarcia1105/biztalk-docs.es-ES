---
title: Obtener metadatos de SAP mediante IMetadataRetrievalContract | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, search metadata
- searching metadata
- how to, browse metadata
- browsing metadata
ms.assetid: 0944fc39-9ee5-4702-8b52-e0bc87f202c6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa36eee26dd9467a71f7e8dd4d28d2e37e26606
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a>Obtener metadatos de SAP mediante IMetadataRetrievalContract
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone un **IMetadataRetrievalContract**punto de conexión que puede usar para examinar y buscar artefactos del sistema SAP y para recuperar los metadatos en forma de un documento de lenguaje de descripción de servicios Web (WSDL) para operaciones.  
  
 El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporciona capacidades de exploración, búsqueda y recuperación de metadatos. Además el **IMetadataRetrievalContract** interfaz, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone la **MetadataRetrievalClient** (clase), que implementa la interfaz. Puede usar un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos; los métodos expuestos para examinar, buscar y recuperar metadatos son iguales en cada caso.  
  
 Las secciones siguientes proporcionan información sobre cómo usar el **IMetadataRetrievalContract** interfaz.  
  
## <a name="the-imetadataretrievalcontract-interface"></a>La interfaz de IMetadataRetrievalContract  
 En la tabla siguiente proporciona información acerca de las clases importantes que se utilizan cuando se trabaja con el **IMetadataRetrievalContract** interfaz.  
  
|Clase o interfaz|Description|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract** (interfaz)<br /><br /> (Microsoft.ServiceModel.Channels)|Define la **examinar**, **búsqueda**, y **GetMetadata** métodos. Invocar estos métodos mediante un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos de adaptador.|  
|**MetadataRetrievalClient** (clase)<br /><br /> (Microsoft.ServiceModel.Channels)|Implementa el **IMetadataRetrievalContract** interfaz. Puede crear una instancia de esta clase y configurarlo para el sistema SAP proporcionando un **SAPBinding** y **EndpointAddress**. A continuación, puede invocar sus métodos para trabajar con metadatos.|  
|**MetadataRetrievalNode** (clase)<br /><br /> (Microsoft.ServiceModel.Channels)|Representa un nodo de metadatos en el adaptador. El **examinar** y **búsqueda** métodos devuelven nodos de este tipo y el **GetMetadata** método toma los nodos de este tipo como parámetro.|  
|**ServiceDescription** (clase)<br /><br /> (System.Web.Services.Description)|Proporciona un medio para crear y dar formato a un archivo de documento WSDL válido. El **GetMetadata** método devuelve un **ServiceDescription** objeto.|  
  
 Para obtener más información sobre la **IMetadataRetrievalContract** interfaz, el **MetadataRetrievalClient** (clase) y el **MetadataRetrievalNode** clase; consulte la  **Microsoft.ServiceModel.Channels** referencia en administrada [http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566).  
  
### <a name="metadata-node-ids"></a>Identificadores de nodo de metadatos  
 El adaptador organiza sus metadatos como un árbol jerárquico de nodos. Dentro de esta estructura de árbol hay dos tipos de nodos de metadatos:  
  
-   **Nodos de operación** representan las operaciones que el adaptador de superficies de artefactos SAP. Nodos de operaciones son las hojas de árbol.  
  
-   **Nodos CATEGORY** representan artefactos SAP y agrupaciones de artefactos SAP que no corresponden directamente a una operación en el adaptador. Nodos de categoría son las ramas del árbol; Estas notas contienen otros nodos de categoría o en nodos de la operación. Por ejemplo, los grupos funcionales de RFC u objetos de negocios SAP se representan como nodos de categoría.  
  
 Cada nodo de metadatos obtenida por el adaptador se identifica mediante un identificador de nodo único. Para obtener más información acerca de los identificadores obtenidas por el adaptador de nodo de metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md). Utilizar estos identificadores de nodo para especificar los artefactos SAP de destino cuando se utiliza el **IMetadataRetrievalContract** interfaz para examinar, buscar y recuperar los metadatos. Puede usar las constantes definidas en `Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants` y `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` para ayudarle a construir identificadores de nodo de metadatos.  
  
### <a name="binding-properties"></a>Propiedades de enlace  
 Si utiliza un **IMetadataRetrievalContract** canal o **IMetadataRetrievalClient** para trabajar con metadatos, debe especificar un **SAPBinding** cuando se crea el instancia.  
  
 Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos. Estas propiedades son:  
  
-   **GenerateFlatfileCompatibleIdocSchema**  
  
-   **ReceiveIDocFormat**  
  
-   **EnableSafeTyping**  
  
-   **FlatFileSegmentIndicator**  
  
 Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de abrir el objeto de recuperación de metadatos. Para obtener más información acerca de las propiedades de enlace del adaptador SAP, consulte [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
### <a name="browsing-metadata-nodes"></a>Exploración de nodos de metadatos  
 Usa el **examinar** método para devolver todos los nodos de metadatos que se encuentran en un nodo primario. En el ejemplo siguiente se examina para los tres primeros grupos funcionales RFC en el sistema SAP. En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  Solo puede buscar nodos category; no puede explorar los nodos de la operación.  
  
### <a name="searching-for-metadata-nodes"></a>Búsquedas de nodos de metadatos  
 Usa el **búsqueda** método para realizar una búsqueda de nodos incluidos en un nodo primario. Puede especificar el asterisco (\*) carácter comodín. Este carácter coincide con cero o más caracteres. En el ejemplo siguiente se muestra una búsqueda de todos los documentos RFC que contengan la cadena "BAPI". En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  Solo se admite la búsqueda en un conjunto limitado de nodos. Para obtener más información acerca de los nodos en el que se admite la búsqueda y el carácter comodín que se admiten en expresiones de búsqueda, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>Recuperación de metadatos (WSDL) para las operaciones  
 Usa el **GetMetadata** método para recuperar una descripción de servicio (documento WSDL) para un grupo de nodos de la operación. En el ejemplo siguiente se recupera una descripción del servicio para la solicitud de cambio de BAPI_TRANSACTION_COMMIT. En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**. Tenga en cuenta que el identificador de nodo para un nodo de operación es equivalente a la acción de mensaje para esa operación.  
  
```  
// Get a WSDL document that specifies a contract that contains the  
// BAPI_TRANSACTION_COMMIT operation.  
MetadataRetrievalNode[] nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
nodes[0].IsOperation = true;  
  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
```  
  
> [!IMPORTANT]
>  Solo debería especificar nodos de operación en el **GetMetadata** método.  
  
### <a name="using-a-metadataretrievalclient"></a>Uso de un MetadataRetrievalClient  
 Crear y usar un **MetadataRetrievalClient** es igual que cualquier otro cliente WCF. Crear el cliente mediante la especificación de un punto de conexión y una instancia de **SAPBinding**. Puede hacerlo mediante declaración en configuración o de forma imperativa en el código. A continuación, invocar los métodos de la **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el adaptador.  
  
 En el ejemplo siguiente se muestra cómo utilizar un **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace SapMetaDataBrowseClient  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console.  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //Write all the nodes returned to the console.  
            foreach (MetadataRetrievalNode node in nodes)  
            {  
                Console.WriteLine("NodeId = " + node.NodeId);  
                Console.WriteLine("\tDirection   = " + node.Direction.ToString());  
                Console.WriteLine("\tIsOperation = " + node.IsOperation.ToString());  
                Console.WriteLine("\tDisplayName = " + node.DisplayName);  
                Console.WriteLine("\tDescription = " + node.Description);  
            }  
            Console.WriteLine();  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            MetadataRetrievalClient browser = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // Create a binding  
                SAPBinding binding = new SAPBinding();  
  
                EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
                browser = new MetadataRetrievalClient(binding, address);  
                browser.ClientCredentials.UserName.UserName = "YourUserName";  
                browser.ClientCredentials.UserName.Password = "YourPassword";  
                browser.Open();  
  
                // Return the nodes directly under the root.  
                // The parameters are the parent node ID, the start index, and the maximum number  
                // of nodes to return.  
                MetadataRetrievalNode[] nodes = browser.Browse(MetadataRetrievalNode.Root.NodeId, 0, int.MaxValue);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Return first 3 RFC group nodes.  
                nodes = browser.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
                nodeWriter.Write(String.Format("Browse results for the first {1} nodes of {0}:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, nodes.Length), nodes);  
  
                // Search for first 3 nodes that begin with "BAPI_TRANSACTION" under the RFC node.  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return.  
                nodes = browser.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI_TRANSACTION*", 3);  
                nodeWriter.Write(String.Format("Search results for \"*BAPI_TRANSACTION*\" under {0} node:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // found in the search and write it to a file.  
                // You could explicitly specify operations as in the following:  
                //    nodes[0] = new MetadataRetrievalNode();  
                //    nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
                //    nodes[0].IsOperation = true;  
                // Note that the operation NodeId is equivalent to the message action.  
                System.Web.Services.Description.ServiceDescription description = browser.GetMetadata(nodes);  
                description.Write("SampleContract.wsdl");  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (browser != null)  
                {  
                    if (browser.State == CommunicationState.Opened)  
                        browser.Close();  
                    else  
                        browser.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 A continuación muestra el resultado de este programa en la consola. Puede ver la estructura de los nodos de recuperación de metadatos devueltos para cada método. El programa también escribe un documento WSDL que describe un contrato de servicio que consta de los nodos devueltos por la búsqueda a un archivo. (Para la mayoría de las instalaciones de SAP, la descripción del servicio contendrá las operaciones de BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK.)  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/BAPISECTION/000001  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = BAPI  
        Description = BAPI  
NodeId = http://Microsoft.LobServices.Sap/2007/03/IDOCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = IDOC  
        Description = IDOC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = RFC  
        Description = RFC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/TRFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = TRFC  
        Description = TRFC  
  
Browse results for the first 3 nodes of http://Microsoft.LobServices.Sap/2007/03  
/RFCSECTION/:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/A  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Asset Accounting  
        Description = Asset Accounting  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/S  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Basis  
        Description = Basis  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/B  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Business Information Warehouse  
        Description = Business Information Warehouse  
  
Search results for "*BAPI_TRANSACTION*" under http://Microsoft.LobServices.Sap/2  
007/03/RFCSECTION/ node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_COMMIT  
        Description = Execute external Commit when using BAPIs  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_ROLLBACK  
        Description = Execute external Rollback when using BAPIs  
  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>Uso de un canal IMetadataRetrievalContract  
 También puede crear un **IMetadataRetrievalContract** de canal y, a continuación, utilizar este canal para examinar, buscar y recuperar metadatos desde el adaptador. (Las firmas de método son los mismos que para el **MetadataRetrievalClient** clase.) En el ejemplo siguiente se muestra cómo hacerlo.  
  
```  
…  
//Create a binding and endpoint address.  
SAPBinding binding = new SAPBinding();  
EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "BAPI_TRANSACTION*", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a>Vea también  
 [Al recuperar los metadatos mediante programación desde SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)
---
title: Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving using IMetadataRetrievalContract
ms.assetid: 7d32694f-4384-4c2f-be72-ac52c7b2e9f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9510c7ae534251218826a31eea1cc39c8d1f139
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977997"
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a>Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un **IMetadataRetrievalContract**punto de conexión que puede usar para examinar y buscar artefactos de base de datos de Oracle y recuperar metadatos para las operaciones en forma de una descripción de servicios de Web Language (WSDL ) documento.  
  
 El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporciona funcionalidades de exploración, búsqueda y recuperación de metadatos. Además el **IMetadataRetrievalContract** interfaz, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone el **MetadataRetrievalClient** (clase), que implementa la interfaz. Puede usar un **IMetadataRetrievalContract** canal o un **MetadataRetrievalClient** para trabajar con metadatos; los métodos expuestos a examinar, buscar y recuperar metadatos son los mismos en cada caso.  
  
 Las secciones siguientes proporcionan información sobre cómo usar el **IMetadataRetrievalContract** interfaz.  
  
## <a name="the-imetadataretrievalcontract-interface"></a>La interfaz IMetadataRetrievalContract  
 En la tabla siguiente proporciona información sobre las clases importantes que se usan al trabajar con el **IMetadataRetrievalContract** interfaz.  
  
|Clase o interfaz|Descripción|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract** interfaz<br /><br /> (Microsoft.ServiceModel.Channels)|Define el **examinar**, **búsqueda**, y **GetMetadata** métodos. Invocar estos métodos mediante un **IMetadataRetrievalContract** canal o un **MetadataRetrievalClient** para trabajar con metadatos de adaptador.|  
|**MetadataRetrievalClient** clase<br /><br /> (Microsoft.ServiceModel.Channels)|Implementa el **IMetadataRetrievalContract** interfaz. Puede crear una instancia de esta clase y configurarlo para la base de datos de Oracle proporcionando un **OracleDBBinding** y un **EndpointAddress**. A continuación, puede invocar sus métodos para trabajar con metadatos.|  
|**MetadataRetrievalNode** clase<br /><br /> (Microsoft.ServiceModel.Channels)|Representa un nodo de metadatos en el adaptador. El **examinar** y **búsqueda** métodos devuelven nodos de este tipo y el **GetMetadata** método toma los nodos de este tipo como parámetro.|  
|**ServiceDescription** clase<br /><br /> (System.Web.Services.Description)|Proporciona un medio para crear y dar formato a un archivo de documento WSDL válido. El **GetMetadata** método devuelve un **ServiceDescription** objeto.|  
  
 
### <a name="metadata-node-ids"></a>Identificadores de nodo de metadatos  
 El adaptador organiza sus metadatos como un árbol jerárquico de nodos. Dentro de esta estructura de árbol hay dos tipos de nodos de metadatos:  
  
- **Los nodos de la operación** representan las operaciones que expone el adaptador en artefactos de la base de datos de Oracle. Los nodos de operación son las hojas del árbol.  
  
- **Nodos CATEGORY** representan artefactos de base de datos de Oracle y las agrupaciones de los artefactos de la base de datos de Oracle que no corresponden directamente a una operación en el adaptador. Nodos de categoría son las ramas del árbol; contienen otros nodos de la categoría o en nodos de la operación. Por ejemplo, paquetes y las tablas de Oracle se representan como nodos de categoría.  
  
  Cada nodo de metadatos obtenida por el adaptador se identifica mediante un identificador de nodo único. Para obtener más información acerca del nodo de metadatos identificadores obtenidos por el adaptador, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md). Utilice estos identificadores de nodo para especificar los artefactos de base de datos de Oracle de destino cuando se usa el **IMetadataRetrievalContract** interfaz para examinar, buscar y recuperar los metadatos.  
  
### <a name="binding-properties"></a>Propiedades de enlace  
 Si usa un **IMetadataRetrievalContract** canal o un **IMetadataRetrievalClient** para trabajar con metadatos, debe especificar un **OracleDBBinding** cuando le Cree la instancia.  
  
 Hay varias propiedades de enlace que afectan a cómo el adaptador genera metadatos. Estas propiedades son:  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  Si desea recuperar los metadatos de la operación POLLINGSTMT debe establecer el **PollingStatement** enlaza la propiedad.  
  
 Debe asegurarse de que se establecen estas propiedades de enlace en los valores necesarios para la aplicación antes de abrir el objeto de recuperación de metadatos. Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
### <a name="browsing-metadata-nodes"></a>Exploración de los nodos de metadatos  
 Usa el **examinar** método para devolver todos los nodos de metadatos que se encuentran en un nodo primario. El ejemplo siguiente se examinan para los tres primeros esquemas en la base de datos de Oracle. En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  Solo puede buscar nodos categoría; no puede explorar los nodos de la operación.  
  
### <a name="searching-for-metadata-nodes"></a>Buscar los nodos de metadatos  
 Usa el **búsqueda** método para realizar una búsqueda de nodos contenidos en un nodo primario. El adaptador admite caracteres comodín en las expresiones de búsqueda; Por ejemplo, puede especificar el porcentaje (%) carácter comodín para buscar coincidencias con cero o más caracteres. El ejemplo siguiente muestra una búsqueda de todas las tablas en el esquema SCOTT que contengan la cadena "EMP". En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  Solo se admite la búsqueda en un conjunto limitado de nodos. Para obtener más información acerca de los nodos en el que se admite la búsqueda y los caracteres comodín admitidos en expresiones de búsqueda, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>Recuperación de metadatos (WSDL) para las operaciones  
 Usa el **GetMetadata** método para recuperar una descripción del servicio (documento WSDL) para un grupo de nodos de la operación. El ejemplo siguiente recupera una descripción del servicio que contiene todas las operaciones que expone el adaptador para la SCOTT. Tabla EMP especificando su identificador de nodo. En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.  
  
```  
// Get a service description that contains all of the operations   
// surfaced for the SCOTT.EMP table. The IsOperation  
// property is set false because this is a category node.  
nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
nodes[0].IsOperation = false;  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
  
```  
  
> [!IMPORTANT]
>  El **IsOperation** propiedad debe ser false para los nodos de categoría y true para los nodos de la operación.  
  
### <a name="using-a-metadataretrievalclient"></a>Uso de un MetadataRetrievalClient  
 Crear y usar un **MetadataRetrievalClient** es igual que cualquier otro cliente WCF. Crear el cliente mediante la especificación de un punto de conexión y una instancia de **OracleDBBinding**. Puede hacerlo mediante declaración en configuración o de forma imperativa en el código. A continuación, invoque los métodos de la **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el adaptador.  
  
 El ejemplo siguiente muestra cómo usar un **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. El ejemplo se muestra:  
  
-   Examinar el nodo raíz del árbol de metadatos para los esquemas de base de datos de Oracle.  
  
-   Búsqueda de las tablas en el esquema SCOTT con nombres que contengan la cadena "EMP".  
  
-   Recuperar los metadatos de todas las operaciones compatibles con el SCOTT. La tabla EMP pasando un nodo de categoría a la **GetMetadata** método.  
  
-   Recuperar metadatos para la operación POLLINGSTMT al pasar el nodo de operación POLLINGSTMT a la **GetMetadata** método...  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace OracleMetadataRetrieval  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //write all the nodes returned to the console.  
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
            MetadataRetrievalClient client = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // create a binding and   
                // set the PollingStatement binding property if you want to  
                // return metadata for the POLLINGSTMT operation  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.PollingStatement = "SELECT * FROM EMP";  
  
                // Set PollingId parameter if you want to alter the namespace of the POLLINGSTMT operation  
                EndpointAddress address = new EndpointAddress("oracledb://ADAPTER?PollingId=1");  
  
                client = new MetadataRetrievalClient(binding, address);  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
                client.Open();  
  
                // Browse for the first 3 (schema) nodes directly under the root  
                // The parameters are the parent Node ID, the start index, and the maximum number  
                // of nodes to return  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Search for first 3 tables that contain "EMP" in the SCOTT schema  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return  
                nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
                nodeWriter.Write(String.Format("Search results for \"%EMP%\" under {0} node:", "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table"), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // surfaced for the SCOTT.EMP table. The IsOperation property is set false  
                // because this is a category node.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
                nodes[0].IsOperation = false;  
                System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
                description.Write("EmpTableContract.wsdl");  
  
                // Get a WSDL document that specifies a contract that contains the   
                // the POLLINGSTMT operation. The IsOperation property is set true  
                // because this is an operation node.  
                // Note that the operation NodeId is equivalent to the message action.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT";  
                nodes[0].IsOperation = true;  
                description = client.GetMetadata(nodes);  
                description.Write("PollingContract.wsdl");  
  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 A continuación muestra el resultado de este programa en la consola. Puede ver la estructura de los nodos de recuperación de los metadatos devueltos por cada método. El programa también escribe dos documentos WSDL en archivos.  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTERTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTERTEST  
        Description = Owned By ADAPTERTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTEST  
        Description = Owned By ADAPTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADMIN123  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADMIN123  
        Description = Owned By ADMIN123  
  
Search results for "%EMP%" under http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/AEMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = AEMP  
        Description = Table.AEMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP  
        Description = Table.EMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP1  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP1  
        Description = Table.EMP1  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>Uso de un canal IMetadataRetrievalContract  
 También puede crear un **IMetadataRetrievalContract** de canal y, a continuación, use este canal para examinar, buscar y recuperar metadatos desde el adaptador. (Las firmas de método son los mismos que para el **MetadataRetrievalClient** clase.) En el ejemplo siguiente se muestra cómo hacerlo.  
  
```  
…  
//Create a binding and endpoint address.  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER/");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos mediante programación de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)
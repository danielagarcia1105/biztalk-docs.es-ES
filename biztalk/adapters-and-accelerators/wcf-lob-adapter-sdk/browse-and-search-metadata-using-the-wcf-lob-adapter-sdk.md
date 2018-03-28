---
title: Examinar y buscar los metadatos mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbb4add7-6cc8-4b93-b559-471b6e31c01a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f4717c8621b798ff960487dfd156c4f0934dfc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="browse-and-search-metadata-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="91f28-102">Examinar y buscar los metadatos mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="91f28-102">Browse and search metadata using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="91f28-103">Esta sección proporciona información acerca de cómo exponer la funcionalidad de exploración y búsqueda con un adaptador mediante la implementación IMetadataBrowseHandler y IMetadataSearchHandler, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="91f28-103">This section provides information about how to expose browse and search functionality with an adapter by implementing IMetadataBrowseHandler and IMetadataSearchHandler, respectively.</span></span>  
  
## <a name="imetadatabrowsehandler"></a><span data-ttu-id="91f28-104">IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="91f28-104">IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="91f28-105">Cuando se agrega un adaptador a un proyecto, IMetadataBrowseHandler permite explorar las categorías y las operaciones que admite el adaptador.</span><span class="sxs-lookup"><span data-stu-id="91f28-105">When adding an adapter to a project, IMetadataBrowseHandler allows browsing of the categories and operations that the adapter supports.</span></span> <span data-ttu-id="91f28-106">Esto permite que el consumidor de adaptador para ver la información de metadatos en tiempo de diseño y para seleccionar solo las operaciones que requiera el proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="91f28-106">This allows the adapter consumer to view metadata information at design time, and to select only the operations that the client process requires.</span></span>  
  
 <span data-ttu-id="91f28-107">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para agregar un adaptador a un proyecto, se rellena la IMetadataBrowseHandler la **tipo de contrato Select**, **seleccione una categoría de**, y  **Operaciones y categorías disponibles** cuadros.</span><span class="sxs-lookup"><span data-stu-id="91f28-107">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataBrowseHandler populates the **Select contract type**, **Select a Category**, and **Available categories and operations** boxes.</span></span>  
  
 <span data-ttu-id="91f28-108">![Browse Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span><span class="sxs-lookup"><span data-stu-id="91f28-108">![Browse Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span></span>  
  
 <span data-ttu-id="91f28-109">En el ejemplo siguiente se muestra cómo implementar IMetadataBrowseHandler.</span><span class="sxs-lookup"><span data-stu-id="91f28-109">The following example demonstrates how to implement IMetadataBrowseHandler.</span></span> <span data-ttu-id="91f28-110">Crea una matriz de MetadataRetrievalNode que contiene información sobre las categorías y las operaciones que admite el adaptador.</span><span class="sxs-lookup"><span data-stu-id="91f28-110">It constructs a MetadataRetrievalNode array containing information on the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataBrowseHandler : EchoAdapterHandlerBase, IMetadataBrowseHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataBrowseHandler class  
        /// </summary>  
        public EchoAdapterMetadataBrowseHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataBrowseHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes from the target system.  
        /// The browse operation will return nodes starting from the childStartIndex in the path provided in absoluteName, and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  
        /// If absoluteName is null or an empty string, return nodes starting from the root + childStartIndex.  
        /// If childStartIndex is zero, then return starting at the node indicated by absoluteName (or the root node if absoluteName is null or empty).  
        /// </summary>  
        public MetadataRetrievalNode[] Browse(string nodeId  
            , int childStartIndex  
            , int maxChildNodes, TimeSpan timeout)  
        {  
            // note we don't support timeout in this sample  
            if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
            {  
                MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
                node.DisplayName = "Main Category";  
                node.IsOperation = false;  
                node.Description = "This category contains inbound and outbound categories.";  
                node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
                return new MetadataRetrievalNode[] { node };  
            }  
            else if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
            {  
                // Inbound operations  
                MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                inOpNode1.DisplayName = "OnReceiveEcho";  
                inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
                inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
                inOpNode1.IsOperation = true;  
                // Outbound operations  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
            }  
  
            return null;  
        }  
  
        #endregion IMetadataBrowseHandler Members  
    }  
```  
  
## <a name="imetadatasearchhandler"></a><span data-ttu-id="91f28-111">IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="91f28-111">IMetadataSearchHandler</span></span>  
 <span data-ttu-id="91f28-112">Implementar IMetadataSearchHandler dentro de un adaptador proporciona la capacidad para buscar las operaciones disponibles en tiempo de diseño mediante la especificación de un término de búsqueda, como una parte de un nombre de operación.</span><span class="sxs-lookup"><span data-stu-id="91f28-112">Implementing IMetadataSearchHandler within an adapter provides the ability to search for available operations at design time by entering a search term, such as a portion of an operation name.</span></span> <span data-ttu-id="91f28-113">Esto es muy útil si el adaptador contiene muchas operaciones, ya que puede escribir valores de búsqueda para limitar las operaciones que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="91f28-113">This is very useful if your adapter contains many operations, since you can enter search values to limit the operations returned.</span></span>  
  
 <span data-ttu-id="91f28-114">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para agregar un adaptador a un proyecto, se resuelve el IMetadataSearchHandler buscar las cadenas especificadas en el **búsqueda en la categoría** cuadro y devuelve los elementos de una lista de búsqueda de coincidencias en la  **Operaciones y categorías disponibles** cuadro.</span><span class="sxs-lookup"><span data-stu-id="91f28-114">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataSearchHandler resolves search strings entered in the **Search in category** box, and returns a list of matching items in the **Available categories and operations** box.</span></span>  
  
 <span data-ttu-id="91f28-115">![Las operaciones de búsqueda](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span><span class="sxs-lookup"><span data-stu-id="91f28-115">![Search Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span></span>  
  
 <span data-ttu-id="91f28-116">También puede realizar búsquedas con svcutil.exe al generar el WSDL o proxy para un adaptador, pasando el valor de búsqueda como una cadena de consulta en el formato de op = valor.</span><span class="sxs-lookup"><span data-stu-id="91f28-116">You can also perform searches with svcutil.exe when generating WSDL or proxy for an adapter, by passing the search value as a query string in the format of op=value.</span></span> <span data-ttu-id="91f28-117">El siguiente es un ejemplo del uso de svcutil.exe para devolver únicamente la información de la operación de eco/EchoStrings.</span><span class="sxs-lookup"><span data-stu-id="91f28-117">The following is an example of using svcutil.exe to return only the Echo/EchoStrings operation information.</span></span>  
  
```  
svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="91f28-118">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no proporciona una funcionalidad de búsqueda de carácter comodín de forma predeterminada como eco \* o % Echo %.</span><span class="sxs-lookup"><span data-stu-id="91f28-118">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not provide a default wildcard search functionality such as Echo\* or %Echo%.</span></span> <span data-ttu-id="91f28-119">Es el autor del adaptador para implementar comodín o funcionalidad de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="91f28-119">It is up to the adapter author to implement wildcard or pattern matching functionality.</span></span>  
  
 <span data-ttu-id="91f28-120">En el ejemplo siguiente se muestra cómo implementar IMetadataSearchHandler.</span><span class="sxs-lookup"><span data-stu-id="91f28-120">The following example demonstrates how to implement IMetadataSearchHandler.</span></span> <span data-ttu-id="91f28-121">Crea una matriz de MetadataRetrievalNode que contiene información acerca de las categorías y las operaciones que admite el adaptador.</span><span class="sxs-lookup"><span data-stu-id="91f28-121">It constructs a MetadataRetrievalNode array containing information about the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataSearchHandler : EchoAdapterHandlerBase, IMetadataSearchHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataSearchHandler class  
        /// </summary>  
        public EchoAdapterMetadataSearchHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataSearchHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes (see Microsoft.ServiceModel.Channels) from the target system.  
        /// The search will begin at the path provided in absoluteName, which points to a location in the tree of metadata nodes.  
        /// The contents of the array are filtered by SearchCriteria and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  If absoluteName is null or an empty string, return nodes starting from the root.  
        /// If SearchCriteria is null or an empty string, return all nodes.  
        /// </summary>  
        public MetadataRetrievalNode[] Search(string nodeId  
            , string searchCriteria  
            , int maxChildNodes, TimeSpan timeout)  
        {  
  
            List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
            if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                nodeInbound.DisplayName = "OnReceiveEcho";  
                nodeInbound.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
                nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
                nodeInbound.IsOperation = true;  
                resultList.Add(nodeInbound);  
            }  
            if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                resultList.Add(outOpNode1);  
            }  
            if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                resultList.Add(outOpNode2);  
            }  
            if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                resultList.Add(outOpNode3);  
            }  
            return resultList.ToArray();  
        }  
  
        #endregion IMetadataSearchHandler Members  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="91f28-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f28-122">See Also</span></span>  
 [<span data-ttu-id="91f28-123">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="91f28-123">Development Activities</span></span>](../../esb-toolkit/development-activities.md)
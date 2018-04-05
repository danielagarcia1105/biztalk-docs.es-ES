---
title: Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract | Documentos de Microsoft
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
ms.openlocfilehash: 132ad3f64d377a3bfcbf7b1b2303e1c0de0c612f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a><span data-ttu-id="ea6ab-102">Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="ea6ab-102">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>
<span data-ttu-id="ea6ab-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un **IMetadataRetrievalContract**punto de conexión que puede usar para examinar y buscar artefactos de base de datos de Oracle y para recuperar los metadatos para las operaciones en el formulario de una descripción de servicios de Web Language (WSDL ) documento.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for Oracle database artifacts and to retrieve metadata for operations in the form of a Web Services Description Language (WSDL) document.</span></span>  
  
 <span data-ttu-id="ea6ab-104">El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporciona capacidades de exploración, búsqueda y recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="ea6ab-105">Además el **IMetadataRetrievalContract** interfaz, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone la **MetadataRetrievalClient** (clase), que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="ea6ab-106">Puede usar un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos; los métodos expuestos para examinar, buscar y recuperar metadatos son iguales en cada caso.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="ea6ab-107">Las secciones siguientes proporcionan información sobre cómo usar el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="ea6ab-108">La interfaz de IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="ea6ab-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="ea6ab-109">En la tabla siguiente proporciona información acerca de las clases importantes que se utilizan cuando se trabaja con el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="ea6ab-110">Clase o interfaz</span><span class="sxs-lookup"><span data-stu-id="ea6ab-110">Class or Interface</span></span>|<span data-ttu-id="ea6ab-111">Description</span><span class="sxs-lookup"><span data-stu-id="ea6ab-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="ea6ab-112">**IMetadataRetrievalContract** (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="ea6ab-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="ea6ab-114">Define la **examinar**, **búsqueda**, y **GetMetadata** métodos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="ea6ab-115">Invocar estos métodos mediante un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="ea6ab-116">**MetadataRetrievalClient** (clase)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="ea6ab-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="ea6ab-118">Implementa el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="ea6ab-119">Puede crear una instancia de esta clase y configurarlo para la base de datos de Oracle, proporcionando un **OracleDBBinding** y **EndpointAddress**.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-119">You can create an instance of this class and configure it for your Oracle database by providing an **OracleDBBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="ea6ab-120">A continuación, puede invocar sus métodos para trabajar con metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="ea6ab-121">**MetadataRetrievalNode** (clase)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="ea6ab-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="ea6ab-123">Representa un nodo de metadatos en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="ea6ab-124">El **examinar** y **búsqueda** métodos devuelven nodos de este tipo y el **GetMetadata** método toma los nodos de este tipo como parámetro.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="ea6ab-125">**ServiceDescription** (clase)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="ea6ab-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="ea6ab-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="ea6ab-127">Proporciona un medio para crear y dar formato a un archivo de documento WSDL válido.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="ea6ab-128">El **GetMetadata** método devuelve un **ServiceDescription** objeto.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 
### <a name="metadata-node-ids"></a><span data-ttu-id="ea6ab-129">Identificadores de nodo de metadatos</span><span class="sxs-lookup"><span data-stu-id="ea6ab-129">Metadata Node IDs</span></span>  
 <span data-ttu-id="ea6ab-130">El adaptador organiza sus metadatos como un árbol jerárquico de nodos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-130">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="ea6ab-131">Dentro de esta estructura de árbol hay dos tipos de nodos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="ea6ab-131">Within this tree structure there are two types of metadata nodes:</span></span>  
  
-   <span data-ttu-id="ea6ab-132">**Nodos de operación** representan las operaciones que el adaptador de superficies de artefactos de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-132">**Operation nodes** represent operations that the adapter surfaces on Oracle database artifacts.</span></span> <span data-ttu-id="ea6ab-133">Nodos de operaciones son las hojas de árbol.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-133">Operation nodes are the leaves of the tree.</span></span>  
  
-   <span data-ttu-id="ea6ab-134">**Nodos CATEGORY** representan artefactos de base de datos de Oracle y agrupaciones de artefactos de base de datos de Oracle que no se corresponden directamente a una operación en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-134">**Category nodes** represent Oracle database artifacts and groupings of Oracle database artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="ea6ab-135">Nodos de categoría son las ramas del árbol; Estas notas contienen otros nodos de categoría o en nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-135">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="ea6ab-136">Por ejemplo, los paquetes y las tablas de Oracle se representan como nodos de categoría.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-136">For example, Oracle tables and packages are represented as category nodes.</span></span>  
  
 <span data-ttu-id="ea6ab-137">Cada nodo de metadatos obtenida por el adaptador se identifica mediante un identificador de nodo único.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-137">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="ea6ab-138">Para obtener más información acerca de los identificadores obtenidas por el adaptador de nodo de metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span><span class="sxs-lookup"><span data-stu-id="ea6ab-138">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span> <span data-ttu-id="ea6ab-139">Utilizar estos identificadores de nodo para especificar los artefactos de base de datos de Oracle de destino cuando se utiliza el **IMetadataRetrievalContract** interfaz para examinar, buscar y recuperar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-139">You use these node IDs to specify target Oracle database artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="ea6ab-140">Propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="ea6ab-140">Binding Properties</span></span>  
 <span data-ttu-id="ea6ab-141">Si utiliza un **IMetadataRetrievalContract** canal o **IMetadataRetrievalClient** para trabajar con metadatos, debe especificar un **OracleDBBinding** cuando se crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-141">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **OracleDBBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="ea6ab-142">Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-142">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="ea6ab-143">Estas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="ea6ab-143">These properties are:</span></span>  
  
-   <span data-ttu-id="ea6ab-144">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="ea6ab-144">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="ea6ab-145">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="ea6ab-145">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="ea6ab-146">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="ea6ab-146">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea6ab-147">Si desea recuperar los metadatos de la operación de POLLINGSTMT debe establecer el **PollingStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-147">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="ea6ab-148">Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de abrir el objeto de recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-148">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="ea6ab-149">Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ea6ab-149">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="ea6ab-150">Exploración de nodos de metadatos</span><span class="sxs-lookup"><span data-stu-id="ea6ab-150">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="ea6ab-151">Usa el **examinar** método para devolver todos los nodos de metadatos que se encuentran en un nodo primario.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-151">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="ea6ab-152">En el ejemplo siguiente se examina para los tres primeros esquemas en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-152">The following example browses for the first three schemas on the Oracle database.</span></span> <span data-ttu-id="ea6ab-153">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-153">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea6ab-154">Solo puede buscar nodos category; no puede explorar los nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-154">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="ea6ab-155">Búsquedas de nodos de metadatos</span><span class="sxs-lookup"><span data-stu-id="ea6ab-155">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="ea6ab-156">Usa el **búsqueda** método para realizar una búsqueda de nodos incluidos en un nodo primario.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-156">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="ea6ab-157">El adaptador admite caracteres comodín en expresiones de búsqueda; Por ejemplo, puede especificar el porcentaje (%) carácter comodín para buscar coincidencias con cero o más caracteres.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-157">The adapter supports wildcard characters in search expressions; for example you can specify the percent (%) wildcard character to match zero or more characters.</span></span> <span data-ttu-id="ea6ab-158">En el ejemplo siguiente se muestra una búsqueda de todas las tablas en el esquema SCOTT que contengan la cadena "EMP".</span><span class="sxs-lookup"><span data-stu-id="ea6ab-158">The following example shows a search for all the tables in the SCOTT schema that contain the string "EMP".</span></span> <span data-ttu-id="ea6ab-159">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-159">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea6ab-160">Solo se admite la búsqueda en un conjunto limitado de nodos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-160">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="ea6ab-161">Para obtener más información acerca de los nodos en el que se admite la búsqueda y los caracteres comodín que se admiten en expresiones de búsqueda, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span><span class="sxs-lookup"><span data-stu-id="ea6ab-161">For more information about the nodes on which search is supported and about the wildcard characters supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="ea6ab-162">Recuperación de metadatos (WSDL) para las operaciones</span><span class="sxs-lookup"><span data-stu-id="ea6ab-162">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="ea6ab-163">Usa el **GetMetadata** método para recuperar una descripción de servicio (documento WSDL) para un grupo de nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-163">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="ea6ab-164">En el ejemplo siguiente se recupera una descripción de servicio que contiene todas las operaciones que el adaptador de superficies para el SCOTT. Tabla EMP especificando su identificador de nodo.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-164">The following example retrieves a service description that contains all of the operations that the adapter surfaces for the SCOTT.EMP table by specifying its node ID.</span></span> <span data-ttu-id="ea6ab-165">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-165">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
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
>  <span data-ttu-id="ea6ab-166">El **IsOperation** propiedad debe ser false para los nodos de categoría y true para los nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-166">The **IsOperation** property should be false for category nodes and true for operation nodes.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="ea6ab-167">Uso de un MetadataRetrievalClient</span><span class="sxs-lookup"><span data-stu-id="ea6ab-167">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="ea6ab-168">Crear y usar un **MetadataRetrievalClient** es igual que cualquier otro cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-168">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="ea6ab-169">Crear el cliente mediante la especificación de un punto de conexión y una instancia de **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-169">You create the client by specifying an endpoint and an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="ea6ab-170">Puede hacerlo mediante declaración en configuración o de forma imperativa en el código.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-170">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="ea6ab-171">A continuación, invocar los métodos de la **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-171">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="ea6ab-172">En el ejemplo siguiente se muestra cómo utilizar un **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea6ab-172">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="ea6ab-173">El ejemplo muestra:</span><span class="sxs-lookup"><span data-stu-id="ea6ab-173">The example demonstrates:</span></span>  
  
-   <span data-ttu-id="ea6ab-174">Examinando el nodo raíz del árbol de metadatos para los esquemas de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-174">Browsing the root node of the metadata tree for Oracle Database schemas.</span></span>  
  
-   <span data-ttu-id="ea6ab-175">Buscar las tablas en el esquema SCOTT con nombres que contengan la cadena "EMP".</span><span class="sxs-lookup"><span data-stu-id="ea6ab-175">Searching for the tables in the SCOTT schema with names that contain the string "EMP".</span></span>  
  
-   <span data-ttu-id="ea6ab-176">Recuperar los metadatos de todas las operaciones compatibles para el SCOTT. Tabla EMP pasando un nodo de categoría a la **GetMetadata** método.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-176">Retrieving metadata for all of the operations supported for the SCOTT.EMP table by passing a category node to the **GetMetadata** method.</span></span>  
  
-   <span data-ttu-id="ea6ab-177">Recuperar metadatos para la operación de POLLINGSTMT al pasar el nodo de operación POLLINGSTMT a la **GetMetadata** método...</span><span class="sxs-lookup"><span data-stu-id="ea6ab-177">Retrieving metadata for the POLLINGSTMT operation by passing the POLLINGSTMT operation node to the **GetMetadata** method..</span></span>  
  
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
  
 <span data-ttu-id="ea6ab-178">A continuación muestra el resultado de este programa en la consola.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-178">The following shows the output of this program on the console.</span></span> <span data-ttu-id="ea6ab-179">Puede ver la estructura de los nodos de recuperación de metadatos devueltos por cada método.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-179">You can see the structure of the metadata retrieval nodes returned by each method.</span></span> <span data-ttu-id="ea6ab-180">El programa también escribe dos documentos WSDL en archivos.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-180">The program also writes two WSDL documents to files.</span></span>  
  
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
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="ea6ab-181">Uso de un canal IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="ea6ab-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="ea6ab-182">También puede crear un **IMetadataRetrievalContract** de canal y, a continuación, utilizar este canal para examinar, buscar y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="ea6ab-183">(Las firmas de método son los mismos que para el **MetadataRetrievalClient** clase.) En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ea6ab-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea6ab-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea6ab-184">See Also</span></span>  
 [<span data-ttu-id="ea6ab-185">Obtener metadatos mediante programación de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ea6ab-185">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)
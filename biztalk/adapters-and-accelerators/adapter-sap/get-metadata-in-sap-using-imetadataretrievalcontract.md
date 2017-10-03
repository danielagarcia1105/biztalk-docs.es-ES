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
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a><span data-ttu-id="6b882-102">Obtener metadatos de SAP mediante IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="6b882-102">Get Metadata in SAP using IMetadataRetrievalContract</span></span>
<span data-ttu-id="6b882-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone un **IMetadataRetrievalContract**punto de conexión que puede usar para examinar y buscar artefactos del sistema SAP y para recuperar los metadatos en forma de un documento de lenguaje de descripción de servicios Web (WSDL) para operaciones.</span><span class="sxs-lookup"><span data-stu-id="6b882-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for SAP system artifacts and to retrieve metadata in the form of a Web Services Description Language (WSDL) document for operations.</span></span>  
  
 <span data-ttu-id="6b882-104">El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporciona capacidades de exploración, búsqueda y recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="6b882-105">Además el **IMetadataRetrievalContract** interfaz, el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone la **MetadataRetrievalClient** (clase), que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="6b882-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="6b882-106">Puede usar un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos; los métodos expuestos para examinar, buscar y recuperar metadatos son iguales en cada caso.</span><span class="sxs-lookup"><span data-stu-id="6b882-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="6b882-107">Las secciones siguientes proporcionan información sobre cómo usar el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="6b882-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="6b882-108">La interfaz de IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="6b882-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="6b882-109">En la tabla siguiente proporciona información acerca de las clases importantes que se utilizan cuando se trabaja con el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="6b882-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="6b882-110">Clase o interfaz</span><span class="sxs-lookup"><span data-stu-id="6b882-110">Class or Interface</span></span>|<span data-ttu-id="6b882-111">Description</span><span class="sxs-lookup"><span data-stu-id="6b882-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="6b882-112">**IMetadataRetrievalContract** (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b882-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="6b882-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="6b882-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="6b882-114">Define la **examinar**, **búsqueda**, y **GetMetadata** métodos.</span><span class="sxs-lookup"><span data-stu-id="6b882-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="6b882-115">Invocar estos métodos mediante un **IMetadataRetrievalContract** canal o **MetadataRetrievalClient** para trabajar con metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b882-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="6b882-116">**MetadataRetrievalClient** (clase)</span><span class="sxs-lookup"><span data-stu-id="6b882-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="6b882-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="6b882-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="6b882-118">Implementa el **IMetadataRetrievalContract** interfaz.</span><span class="sxs-lookup"><span data-stu-id="6b882-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="6b882-119">Puede crear una instancia de esta clase y configurarlo para el sistema SAP proporcionando un **SAPBinding** y **EndpointAddress**.</span><span class="sxs-lookup"><span data-stu-id="6b882-119">You can create an instance of this class and configure it for your SAP system by providing an **SAPBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="6b882-120">A continuación, puede invocar sus métodos para trabajar con metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="6b882-121">**MetadataRetrievalNode** (clase)</span><span class="sxs-lookup"><span data-stu-id="6b882-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="6b882-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="6b882-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="6b882-123">Representa un nodo de metadatos en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b882-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="6b882-124">El **examinar** y **búsqueda** métodos devuelven nodos de este tipo y el **GetMetadata** método toma los nodos de este tipo como parámetro.</span><span class="sxs-lookup"><span data-stu-id="6b882-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="6b882-125">**ServiceDescription** (clase)</span><span class="sxs-lookup"><span data-stu-id="6b882-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="6b882-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="6b882-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="6b882-127">Proporciona un medio para crear y dar formato a un archivo de documento WSDL válido.</span><span class="sxs-lookup"><span data-stu-id="6b882-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="6b882-128">El **GetMetadata** método devuelve un **ServiceDescription** objeto.</span><span class="sxs-lookup"><span data-stu-id="6b882-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 <span data-ttu-id="6b882-129">Para obtener más información sobre la **IMetadataRetrievalContract** interfaz, el **MetadataRetrievalClient** (clase) y el **MetadataRetrievalNode** clase; consulte la  **Microsoft.ServiceModel.Channels** referencia en administrada [http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566).</span><span class="sxs-lookup"><span data-stu-id="6b882-129">For more information about the **IMetadataRetrievalContract** interface, the **MetadataRetrievalClient** class, and the **MetadataRetrievalNode** class; see the **Microsoft.ServiceModel.Channels** managed reference at [http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566).</span></span>  
  
### <a name="metadata-node-ids"></a><span data-ttu-id="6b882-130">Identificadores de nodo de metadatos</span><span class="sxs-lookup"><span data-stu-id="6b882-130">Metadata Node IDs</span></span>  
 <span data-ttu-id="6b882-131">El adaptador organiza sus metadatos como un árbol jerárquico de nodos.</span><span class="sxs-lookup"><span data-stu-id="6b882-131">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="6b882-132">Dentro de esta estructura de árbol hay dos tipos de nodos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="6b882-132">Within this tree structure there are two types of metadata nodes:</span></span>  
  
-   <span data-ttu-id="6b882-133">**Nodos de operación** representan las operaciones que el adaptador de superficies de artefactos SAP.</span><span class="sxs-lookup"><span data-stu-id="6b882-133">**Operation nodes** represent operations that the adapter surfaces on SAP artifacts.</span></span> <span data-ttu-id="6b882-134">Nodos de operaciones son las hojas de árbol.</span><span class="sxs-lookup"><span data-stu-id="6b882-134">Operation nodes are the leaves of the tree.</span></span>  
  
-   <span data-ttu-id="6b882-135">**Nodos CATEGORY** representan artefactos SAP y agrupaciones de artefactos SAP que no corresponden directamente a una operación en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b882-135">**Category nodes** represent SAP artifacts and groupings of SAP artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="6b882-136">Nodos de categoría son las ramas del árbol; Estas notas contienen otros nodos de categoría o en nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="6b882-136">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="6b882-137">Por ejemplo, los grupos funcionales de RFC u objetos de negocios SAP se representan como nodos de categoría.</span><span class="sxs-lookup"><span data-stu-id="6b882-137">For example, RFC functional groups or SAP business objects are represented as category nodes.</span></span>  
  
 <span data-ttu-id="6b882-138">Cada nodo de metadatos obtenida por el adaptador se identifica mediante un identificador de nodo único.</span><span class="sxs-lookup"><span data-stu-id="6b882-138">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="6b882-139">Para obtener más información acerca de los identificadores obtenidas por el adaptador de nodo de metadatos, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span><span class="sxs-lookup"><span data-stu-id="6b882-139">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span> <span data-ttu-id="6b882-140">Utilizar estos identificadores de nodo para especificar los artefactos SAP de destino cuando se utiliza el **IMetadataRetrievalContract** interfaz para examinar, buscar y recuperar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-140">You use these node IDs to specify target SAP artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span> <span data-ttu-id="6b882-141">Puede usar las constantes definidas en `Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants` y `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` para ayudarle a construir identificadores de nodo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-141">You can use the constants defined in `Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants` and `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you construct metadata node IDs.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="6b882-142">Propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="6b882-142">Binding Properties</span></span>  
 <span data-ttu-id="6b882-143">Si utiliza un **IMetadataRetrievalContract** canal o **IMetadataRetrievalClient** para trabajar con metadatos, debe especificar un **SAPBinding** cuando se crea el instancia.</span><span class="sxs-lookup"><span data-stu-id="6b882-143">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **SAPBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="6b882-144">Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-144">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="6b882-145">Estas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="6b882-145">These properties are:</span></span>  
  
-   <span data-ttu-id="6b882-146">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="6b882-146">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
-   <span data-ttu-id="6b882-147">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="6b882-147">**ReceiveIDocFormat**</span></span>  
  
-   <span data-ttu-id="6b882-148">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="6b882-148">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="6b882-149">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="6b882-149">**FlatFileSegmentIndicator**</span></span>  
  
 <span data-ttu-id="6b882-150">Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de abrir el objeto de recuperación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6b882-150">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="6b882-151">Para obtener más información acerca de las propiedades de enlace del adaptador SAP, consulte [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6b882-151">For more information about the SAP adapter binding properties, see [Read about  BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="6b882-152">Exploración de nodos de metadatos</span><span class="sxs-lookup"><span data-stu-id="6b882-152">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="6b882-153">Usa el **examinar** método para devolver todos los nodos de metadatos que se encuentran en un nodo primario.</span><span class="sxs-lookup"><span data-stu-id="6b882-153">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="6b882-154">En el ejemplo siguiente se examina para los tres primeros grupos funcionales RFC en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="6b882-154">The following example browses for the first three RFC functional groups on the SAP system.</span></span> <span data-ttu-id="6b882-155">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="6b882-155">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b882-156">Solo puede buscar nodos category; no puede explorar los nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="6b882-156">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="6b882-157">Búsquedas de nodos de metadatos</span><span class="sxs-lookup"><span data-stu-id="6b882-157">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="6b882-158">Usa el **búsqueda** método para realizar una búsqueda de nodos incluidos en un nodo primario.</span><span class="sxs-lookup"><span data-stu-id="6b882-158">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="6b882-159">Puede especificar el asterisco (\*) carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="6b882-159">You can specify the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="6b882-160">Este carácter coincide con cero o más caracteres.</span><span class="sxs-lookup"><span data-stu-id="6b882-160">This character matches zero or more characters.</span></span> <span data-ttu-id="6b882-161">En el ejemplo siguiente se muestra una búsqueda de todos los documentos RFC que contengan la cadena "BAPI".</span><span class="sxs-lookup"><span data-stu-id="6b882-161">The following example shows a search for all RFCs that contain the string "BAPI".</span></span> <span data-ttu-id="6b882-162">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="6b882-162">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b882-163">Solo se admite la búsqueda en un conjunto limitado de nodos.</span><span class="sxs-lookup"><span data-stu-id="6b882-163">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="6b882-164">Para obtener más información acerca de los nodos en el que se admite la búsqueda y el carácter comodín que se admiten en expresiones de búsqueda, vea [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span><span class="sxs-lookup"><span data-stu-id="6b882-164">For more information about the nodes on which search is supported and about the wildcard character supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="6b882-165">Recuperación de metadatos (WSDL) para las operaciones</span><span class="sxs-lookup"><span data-stu-id="6b882-165">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="6b882-166">Usa el **GetMetadata** método para recuperar una descripción de servicio (documento WSDL) para un grupo de nodos de la operación.</span><span class="sxs-lookup"><span data-stu-id="6b882-166">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="6b882-167">En el ejemplo siguiente se recupera una descripción del servicio para la solicitud de cambio de BAPI_TRANSACTION_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="6b882-167">The following example retrieves a service description for the BAPI_TRANSACTION_COMMIT RFC.</span></span> <span data-ttu-id="6b882-168">En este ejemplo, **cliente** es una instancia de **MetadataRetrievalClient**.</span><span class="sxs-lookup"><span data-stu-id="6b882-168">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span> <span data-ttu-id="6b882-169">Tenga en cuenta que el identificador de nodo para un nodo de operación es equivalente a la acción de mensaje para esa operación.</span><span class="sxs-lookup"><span data-stu-id="6b882-169">Note that the node ID for an operation node is equivalent to the message action for that operation.</span></span>  
  
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
>  <span data-ttu-id="6b882-170">Solo debería especificar nodos de operación en el **GetMetadata** método.</span><span class="sxs-lookup"><span data-stu-id="6b882-170">You should only specify operation nodes in the **GetMetadata** method.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="6b882-171">Uso de un MetadataRetrievalClient</span><span class="sxs-lookup"><span data-stu-id="6b882-171">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="6b882-172">Crear y usar un **MetadataRetrievalClient** es igual que cualquier otro cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="6b882-172">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="6b882-173">Crear el cliente mediante la especificación de un punto de conexión y una instancia de **SAPBinding**.</span><span class="sxs-lookup"><span data-stu-id="6b882-173">You create the client by specifying an endpoint and an instance of **SAPBinding**.</span></span> <span data-ttu-id="6b882-174">Puede hacerlo mediante declaración en configuración o de forma imperativa en el código.</span><span class="sxs-lookup"><span data-stu-id="6b882-174">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="6b882-175">A continuación, invocar los métodos de la **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b882-175">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="6b882-176">En el ejemplo siguiente se muestra cómo utilizar un **MetadataRetrievalClient** para examinar, buscar y recuperar metadatos desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b882-176">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
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
  
 <span data-ttu-id="6b882-177">A continuación muestra el resultado de este programa en la consola.</span><span class="sxs-lookup"><span data-stu-id="6b882-177">The following shows the output of this program on the console.</span></span> <span data-ttu-id="6b882-178">Puede ver la estructura de los nodos de recuperación de metadatos devueltos para cada método.</span><span class="sxs-lookup"><span data-stu-id="6b882-178">You can see the structure of the metadata retrieval nodes returned for each method.</span></span> <span data-ttu-id="6b882-179">El programa también escribe un documento WSDL que describe un contrato de servicio que consta de los nodos devueltos por la búsqueda a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6b882-179">The program also writes a WSDL document that describes a service contract consisting of the nodes returned by the search to a file.</span></span> <span data-ttu-id="6b882-180">(Para la mayoría de las instalaciones de SAP, la descripción del servicio contendrá las operaciones de BAPI_TRANSACTION_COMMIT y BAPI_TRANSACTION_ROLLBACK.)</span><span class="sxs-lookup"><span data-stu-id="6b882-180">(For most SAP installations, the service description will contain the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.)</span></span>  
  
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
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="6b882-181">Uso de un canal IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="6b882-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="6b882-182">También puede crear un **IMetadataRetrievalContract** de canal y, a continuación, utilizar este canal para examinar, buscar y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6b882-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="6b882-183">(Las firmas de método son los mismos que para el **MetadataRetrievalClient** clase.) En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6b882-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b882-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b882-184">See Also</span></span>  
 [<span data-ttu-id="6b882-185">Al recuperar los metadatos mediante programación desde SAP</span><span class="sxs-lookup"><span data-stu-id="6b882-185">Retrieving Metadata Programmatically from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)
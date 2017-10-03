---
title: "Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de eco | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f93b4efeb65092c4ca61ab1fc2ef58a0ac53ae4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a><span data-ttu-id="83c08-102">Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="83c08-102">Step 4: Implement the Metadata Browse Handler for the Echo Adapter</span></span>
<span data-ttu-id="83c08-103">![Paso 4 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="83c08-103">![Step 4 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="83c08-104">**Tiempo en completarse:** 45 minutos</span><span class="sxs-lookup"><span data-stu-id="83c08-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="83c08-105">En este paso, implementará la capacidad de examinar del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="83c08-105">In this step, you implement the browse capability of the Echo adapter.</span></span> <span data-ttu-id="83c08-106">Esta capacidad permite que el adaptador realizar una exploración según la conexión para obtener los metadatos del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="83c08-106">This capability allows your adapter to perform a connection-based browse to obtain metadata from the target system.</span></span> <span data-ttu-id="83c08-107">Independientemente de las capacidades de su adaptador, el adaptador debe admitir la capacidad de examinar.</span><span class="sxs-lookup"><span data-stu-id="83c08-107">Regardless of your adapter's capabilities, your adapter must support the browse capability.</span></span>  
  
 <span data-ttu-id="83c08-108">Según la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la funcionalidad de exploración, debe implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="83c08-108">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support browse capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="83c08-109">Para el adaptador de eco, el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente la clase derivada denominada EchoAdapterMetadataBrowseHandler.</span><span class="sxs-lookup"><span data-stu-id="83c08-109">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdapterMetadataBrowseHandler.</span></span>  
  
 <span data-ttu-id="83c08-110">En los pasos siguientes, va a actualizar esta clase para obtener una mejor comprensión de cómo implementar el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método, cómo establecer varias propiedades de la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto y la aparecen de la operación y los nodos de categoría compatibles con el adaptador en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta.</span><span class="sxs-lookup"><span data-stu-id="83c08-110">In the following steps, you update this class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, how to set various properties of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the operation and category nodes supported by the adapter appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83c08-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="83c08-111">Prerequisites</span></span>  
 <span data-ttu-id="83c08-112">Antes de comenzar este paso, debe haber completado correctamente [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="83c08-112">Before you begin this step, you must have successfully completed [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span> <span data-ttu-id="83c08-113">También debe comprender las siguientes clases:</span><span class="sxs-lookup"><span data-stu-id="83c08-113">You must also understand the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a><span data-ttu-id="83c08-114">La interfaz de IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="83c08-114">The IMetadataBrowseHandler Interface</span></span>  
 <span data-ttu-id="83c08-115">El `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz se define como:</span><span class="sxs-lookup"><span data-stu-id="83c08-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface is defined as:</span></span>  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="83c08-116">El `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método devuelve una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos basados en los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="83c08-116">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the method parameters.</span></span> <span data-ttu-id="83c08-117">Las definiciones de parámetro para el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="83c08-117">The parameter definitions for the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method are described in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c08-118">La implementación del adaptador eco utiliza solo el identificador de nodo y omite los otros tres parámetros, ya que el adaptador de eco admite pocos nodos.</span><span class="sxs-lookup"><span data-stu-id="83c08-118">The Echo adapter implementation uses only the node ID and ignores the other three parameters, since the Echo adapter supports only a few nodes.</span></span>  
  
|<span data-ttu-id="83c08-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="83c08-119">**Parameter**</span></span>|<span data-ttu-id="83c08-120">**Definición**</span><span class="sxs-lookup"><span data-stu-id="83c08-120">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="83c08-121">nodeId</span><span class="sxs-lookup"><span data-stu-id="83c08-121">nodeId</span></span>|<span data-ttu-id="83c08-122">Cada elemento de la jerarquía del explorador de metadatos (el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y</span><span class="sxs-lookup"><span data-stu-id="83c08-122">Each item in the hierarchy of the metadata explorer (the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and</span></span><br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]<span data-ttu-id="83c08-123">) tiene una nodeId.</span><span class="sxs-lookup"><span data-stu-id="83c08-123">) has a nodeId.</span></span> <span data-ttu-id="83c08-124">Cada identificador de nodo debe ser único y puede ser una operación o una categoría.</span><span class="sxs-lookup"><span data-stu-id="83c08-124">Each node ID must be unique and can be a category or an operation.</span></span> <span data-ttu-id="83c08-125">La categoría puede tener subcategorías.</span><span class="sxs-lookup"><span data-stu-id="83c08-125">The category can have subcategories.</span></span> <span data-ttu-id="83c08-126">**Nota:** si es null o una cadena vacía (""), las operaciones se recuperan desde el nodo raíz ("/") de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="83c08-126">**Note:**  If null or an empty string (""), operations are retrieved from the root node ("/") by default.</span></span>|  
|<span data-ttu-id="83c08-127">childStartIndex</span><span class="sxs-lookup"><span data-stu-id="83c08-127">childStartIndex</span></span>|<span data-ttu-id="83c08-128">El índice del primer elemento secundario para devolver.</span><span class="sxs-lookup"><span data-stu-id="83c08-128">The index of the first child to return.</span></span><br /><br /> <span data-ttu-id="83c08-129">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="83c08-129">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="83c08-130">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="83c08-130">maxChildNodes</span></span>|<span data-ttu-id="83c08-131">El número máximo de nodos de resultado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="83c08-131">The maximum number of result nodes to return.</span></span> <span data-ttu-id="83c08-132">Usar Int32.Max para recuperar todos los nodos de resultado.</span><span class="sxs-lookup"><span data-stu-id="83c08-132">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="83c08-133">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="83c08-133">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="83c08-134">timeout</span><span class="sxs-lookup"><span data-stu-id="83c08-134">timeout</span></span>|<span data-ttu-id="83c08-135">El tiempo máximo permitido para que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="83c08-135">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="83c08-136">No se admite el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="83c08-136">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="83c08-137">Al implementar el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método, debe agregar cada nodo de categoría y operación a la matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="83c08-137">When implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, you must add every category and operation node to the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="83c08-138">Para especificar un nodo como categoría, establezca el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` a `false`.</span><span class="sxs-lookup"><span data-stu-id="83c08-138">To specify a node as category, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `false`.</span></span> <span data-ttu-id="83c08-139">Para especificar un nodo como operación, establezca la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` a `true`.</span><span class="sxs-lookup"><span data-stu-id="83c08-139">To specify a node as operation, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `true`.</span></span>  
  
## <a name="echo-adapter-metadata-browse"></a><span data-ttu-id="83c08-140">Exploración de metadatos de adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="83c08-140">Echo Adapter Metadata Browse</span></span>  
 <span data-ttu-id="83c08-141">Dependiendo del sistema de destino categorías y operaciones, hay muchas maneras de crear una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="83c08-141">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="83c08-142">Las operaciones y categorías que elija deberían representar las operaciones que desea exponer.</span><span class="sxs-lookup"><span data-stu-id="83c08-142">The operations and categories you choose should represent the operations you want to expose.</span></span> <span data-ttu-id="83c08-143">Pero para el adaptador de eco, simplemente crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para cada uno de los siguientes nodos con el Id. de nodo en la lista:</span><span class="sxs-lookup"><span data-stu-id="83c08-143">But for the Echo adapter, it simply creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each of the following nodes with node ID listed:</span></span>  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 <span data-ttu-id="83c08-144">El EchoMainCategory es el nodo de categoría bajo el nodo raíz ("/").</span><span class="sxs-lookup"><span data-stu-id="83c08-144">The EchoMainCategory is the category node under the root node ("/").</span></span> <span data-ttu-id="83c08-145">Este nodo también se utiliza como la categoría para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="83c08-145">This node is also used as the category for both inbound and outbound operations.</span></span> <span data-ttu-id="83c08-146">Por lo tanto, al crear el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objeto para esa categoría, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83c08-146">Hence, when creating the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that category, you can do the following:</span></span>  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 <span data-ttu-id="83c08-147">Para una operación de salida como eco/EchoString que pertenece a la EchoMainCategory, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83c08-147">For an outbound operation such as Echo/EchoString that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
      {  
          // Outbound operations  
          MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
          outOpNode1.DisplayName = "EchoStrings";  
          outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
          outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
          outOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="83c08-148">Para una operación de entrada como eco/OnReceiveEcho que pertenece a la EchoMainCategory, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83c08-148">For an inbound operation such as Echo/OnReceiveEcho that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
  if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
        {             
// Inbound operations  
            MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
            inOpNode1.DisplayName = "OnReceiveEcho";  
            inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
            inOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="83c08-149">Cuando el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas explorar los metadatos de adaptador eco, de forma predeterminada, inicia desde el nodo raíz ("/").</span><span class="sxs-lookup"><span data-stu-id="83c08-149">When the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools explore the Echo adapter metadata, by default, it starts from the root node ("/").</span></span>  
  
 <span data-ttu-id="83c08-150">La siguiente ilustración muestra que el nodo EchoMainCategory aparece bajo el nodo raíz ("/"):</span><span class="sxs-lookup"><span data-stu-id="83c08-150">The following figure shows that the EchoMainCategory node appears under the root node ("/"):</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 <span data-ttu-id="83c08-151">Para examinar las tres operaciones de salida, en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, en el **seleccione el tipo de contrato** lista desplegable, seleccione la **Client (Outbound operations)** opción.</span><span class="sxs-lookup"><span data-stu-id="83c08-151">To browse the three outbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Client (Outbound operations)** option.</span></span> <span data-ttu-id="83c08-152">Consulte esas operaciones en el **categorías y operaciones disponibles** cuadro de lista, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="83c08-152">You see those operations in the **Available categories and operations** list box, as shown below:</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 <span data-ttu-id="83c08-153">En la figura anterior, observe que la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A` valor aparece en el **nombre** columna de la **categorías y operaciones disponibles** cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="83c08-153">In the previous figure, notice that the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A` value appears in the **Name** column of the **Available categories and operations** list box.</span></span> <span data-ttu-id="83c08-154">El parámetro pasado a la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` constructor aparece en el **Id. de nodo** columna de la **categorías y operaciones disponibles** cuadro de lista y el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A` valor aparece como la información sobre herramientas que contiene la descripción, cuando hace doble clic en el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`.</span><span class="sxs-lookup"><span data-stu-id="83c08-154">The parameter passed into the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` constructor appears in the **Node ID** column of the **Available categories and operations** list box, and the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A` value appears as the tool tip that contains the description, when you right-click the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`.</span></span>  
  
 <span data-ttu-id="83c08-155">Para ver las operaciones de entrada, en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, en el **seleccione el tipo de contrato** lista desplegable, seleccione la **(operaciones de entrada) de servicio** opción.</span><span class="sxs-lookup"><span data-stu-id="83c08-155">To see the inbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Service (Inbound operations)** option.</span></span> <span data-ttu-id="83c08-156">Verá que la operación de OnReceiveEcho entrante en el **categorías y operaciones disponibles** cuadro de lista, como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="83c08-156">You see the inbound OnReceiveEcho operation in the **Available categories and operations** list box, as shown in the following figure:</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a><span data-ttu-id="83c08-157">Implementar el IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="83c08-157">Implementing the IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="83c08-158">En este paso, va a actualizar la clase EchoAdapterMetadataBrowseHandler para implementar la exploración de metadatos del adaptador de eco, es decir, para implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="83c08-158">In this step, you update the EchoAdapterMetadataBrowseHandler class to implement the Echo adapter's metadata browse, that is, to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="83c08-159">En concreto, se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para cada categoría y la operación, establezca los valores adecuados para ese objeto y, a continuación, devolver la matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos para category y operaciones.</span><span class="sxs-lookup"><span data-stu-id="83c08-159">Specifically, you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each category and operation, set appropriate values for that object, and then return the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects for category and operations.</span></span> <span data-ttu-id="83c08-160">Tenga en cuenta que cuando se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objeto, debe pasar el identificador de nodo, no el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="83c08-160">Keep in mind that when you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, you need to pass in the node ID, not the display name.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a><span data-ttu-id="83c08-161">Para actualizar la clase EchoAdapterMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="83c08-161">To update the EchoAdapterMetadataBrowseHandler class</span></span>  
  
1.  <span data-ttu-id="83c08-162">En el Explorador de soluciones, haga doble clic en el **EchoAdapterMetadataBrowseHandler.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="83c08-162">In Solution Explorer, double-click the **EchoAdapterMetadataBrowseHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="83c08-163">En el editor de Visual Studio, el botón secundario en cualquier lugar en el editor, en el menú contextual, seleccione **esquematización**y, a continuación, haga clic en **Detener esquematización**.</span><span class="sxs-lookup"><span data-stu-id="83c08-163">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="83c08-164">En el editor de Visual Studio, dentro de la **examinar** método, reemplace la lógica existente con lo siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para EchoMainCategory.</span><span class="sxs-lookup"><span data-stu-id="83c08-164">In the Visual Studio editor, inside the **Browse** method, replace the existing logic with the following to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for EchoMainCategory.</span></span>  
  
    ```csharp  
    if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
    {  
        MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
        node.DisplayName = "Main Category";  
        node.IsOperation = false;  
        node.Description = "This category contains inbound and outbound categories.";  
        node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
        return new MetadataRetrievalNode[] { node };  
    }  
    ```  
  
4.  <span data-ttu-id="83c08-165">Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para el eco/OnReceiveEcho.</span><span class="sxs-lookup"><span data-stu-id="83c08-165">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/OnReceiveEcho.</span></span>  
  
    ```csharp  
    if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
    {  
        // Inbound operations  
        MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        inOpNode1.DisplayName = "OnReceiveEcho";  
        inOpNode1.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
        inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
        inOpNode1.IsOperation = true;  
    ```  
  
5.  <span data-ttu-id="83c08-166">Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para el eco/EchoStrings.</span><span class="sxs-lookup"><span data-stu-id="83c08-166">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoStrings.</span></span>  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  <span data-ttu-id="83c08-167">Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para el eco/EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="83c08-167">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoGreetings.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  <span data-ttu-id="83c08-168">Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para el eco / EchoGreetingFromFile.</span><span class="sxs-lookup"><span data-stu-id="83c08-168">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/ EchoGreetingFromFile.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  <span data-ttu-id="83c08-169">Continúe agregando el código siguiente para devolver una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos o null si no coincide.</span><span class="sxs-lookup"><span data-stu-id="83c08-169">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects or null if not matched.</span></span>  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. <span data-ttu-id="83c08-170">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="83c08-170">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
10. <span data-ttu-id="83c08-171">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="83c08-171">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="83c08-172">Debe generar correctamente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="83c08-172">You should successfully build the project.</span></span> <span data-ttu-id="83c08-173">Si no es así, asegúrese de que ha seguido todos los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="83c08-173">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c08-174">Ya ha guardado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="83c08-174">You saved your work.</span></span> <span data-ttu-id="83c08-175">Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 5: implementar el controlador de búsqueda de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="83c08-175">You can safely close Visual Studio at this time or go to the next step, [Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="83c08-176">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="83c08-176">What Did I Just Do?</span></span>  
 <span data-ttu-id="83c08-177">Acaba de implementar los metadatos de exploración de capacidad del adaptador de eco, implementando la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="83c08-177">You just implemented the metadata browsing capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="83c08-178">En concreto, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objeto para la categoría y, a continuación, se devuelve como una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="83c08-178">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for the category, and then returned it as an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="83c08-179">Para cada operación, ha creado un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto y, a continuación, devuelve todos los objetos en una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`.</span><span class="sxs-lookup"><span data-stu-id="83c08-179">For each operation, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and then returned all those objects in an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83c08-180">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="83c08-180">Next Steps</span></span>  
 <span data-ttu-id="83c08-181">Implementar metadatos buscar y resolver capacidades y el intercambio de mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="83c08-181">You implement metadata searching and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="83c08-182">Por último, generará e implementará el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="83c08-182">Finally, you build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c08-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c08-183">See Also</span></span>  
 <span data-ttu-id="83c08-184">[Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83c08-184">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="83c08-185">[Paso 3: Implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83c08-185">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="83c08-186">Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="83c08-186">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)
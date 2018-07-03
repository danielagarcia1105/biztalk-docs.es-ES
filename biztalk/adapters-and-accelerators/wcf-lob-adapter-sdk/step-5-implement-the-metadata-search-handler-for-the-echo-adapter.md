---
title: 'Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29768fa47fd26f32308d517f175d906ec088ff7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004093"
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a><span data-ttu-id="5b6de-102">Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="5b6de-102">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>
<span data-ttu-id="5b6de-103">![Paso 5 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="5b6de-103">![Step 5 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="5b6de-104">**Tiempo en completarse:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="5b6de-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="5b6de-105">En este paso del tutorial, implementará la capacidad de búsqueda del adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-105">In this step of the tutorial, you implement the search capability of the Echo adapter.</span></span> <span data-ttu-id="5b6de-106">A diferencia de exploración, búsqueda es opcional.</span><span class="sxs-lookup"><span data-stu-id="5b6de-106">Unlike browse, search is optional.</span></span> <span data-ttu-id="5b6de-107">Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la capacidad de búsqueda, debe implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b6de-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support search capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="5b6de-108">Para el adaptador de Echo la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente una clase derivada denominada EchoAdapterMetadataSearchHandler.</span><span class="sxs-lookup"><span data-stu-id="5b6de-108">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterMetadataSearchHandler.</span></span>  
  
 <span data-ttu-id="5b6de-109">Actualizar la clase EchoAdapterMetadataSearchHandler para obtener una mejor comprensión de cómo implementar esta interfaz, cómo rellenar `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto y cómo aparecen los resultados de búsqueda en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta.</span><span class="sxs-lookup"><span data-stu-id="5b6de-109">You first update the EchoAdapterMetadataSearchHandler class to get a better understanding of how to implement this interface, how to populate  `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the search results appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b6de-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5b6de-110">Prerequisites</span></span>  
 <span data-ttu-id="5b6de-111">Antes de comenzar este paso, completar [paso 4: implementar el controlador de examinar los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="5b6de-111">Before you begin this step, complete [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="5b6de-112">También debe tener una idea clara sobre las clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b6de-112">You must also have a clear understanding about the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a><span data-ttu-id="5b6de-113">La interfaz IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="5b6de-113">The IMetadataSearchHandler Interface</span></span>  
 <span data-ttu-id="5b6de-114">El `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` se define como:</span><span class="sxs-lookup"><span data-stu-id="5b6de-114">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` is defined as:</span></span>  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="5b6de-115">El `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método devuelve una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos según los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5b6de-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the search criteria.</span></span> <span data-ttu-id="5b6de-116">En la tabla siguiente se describen las definiciones de parámetro para el método de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="5b6de-116">The parameter definitions for the Search method are described in the following table:</span></span>  
  
|<span data-ttu-id="5b6de-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="5b6de-117">**Parameter**</span></span>|<span data-ttu-id="5b6de-118">**Definición**</span><span class="sxs-lookup"><span data-stu-id="5b6de-118">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="5b6de-119">nodeId</span><span class="sxs-lookup"><span data-stu-id="5b6de-119">nodeId</span></span>|<span data-ttu-id="5b6de-120">Para iniciar la búsqueda en el identificador de nodo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-120">The node ID to start searching from.</span></span> <span data-ttu-id="5b6de-121">Si es null o una cadena vacía (""), las operaciones se recuperan desde el nodo raíz ("/").</span><span class="sxs-lookup"><span data-stu-id="5b6de-121">If null or an empty string (""), operations will be retrieved from the root node ("/").</span></span>|  
|<span data-ttu-id="5b6de-122">searchCriteria</span><span class="sxs-lookup"><span data-stu-id="5b6de-122">searchCriteria</span></span>|<span data-ttu-id="5b6de-123">Los criterios de búsqueda, que es específica del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5b6de-123">The search criteria, which is adapter-specific.</span></span> <span data-ttu-id="5b6de-124">Si se especifica ningún criterio de búsqueda, el adaptador debería devolver todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="5b6de-124">If no search criteria are specified, the adapter should return all nodes.</span></span>|  
|<span data-ttu-id="5b6de-125">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="5b6de-125">maxChildNodes</span></span>|<span data-ttu-id="5b6de-126">El número máximo de nodos de resultados para devolver.</span><span class="sxs-lookup"><span data-stu-id="5b6de-126">The maximum number of result nodes to return.</span></span> <span data-ttu-id="5b6de-127">Utilice Int32.Max para recuperar todos los nodos de resultados.</span><span class="sxs-lookup"><span data-stu-id="5b6de-127">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="5b6de-128">No admite el adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="5b6de-129">timeout</span><span class="sxs-lookup"><span data-stu-id="5b6de-129">timeout</span></span>|<span data-ttu-id="5b6de-130">El tiempo máximo permitido para que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="5b6de-130">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="5b6de-131">No admite el adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-131">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="5b6de-132">Resultado de la búsqueda, puede elegir el adaptador devolver los nodos de la categoría o nodos de la operación o ambas.</span><span class="sxs-lookup"><span data-stu-id="5b6de-132">For search result, your adapter can choose to return either category nodes or operation nodes, or both.</span></span> <span data-ttu-id="5b6de-133">Es hasta el tipo de característica de búsqueda de su adaptador admite.</span><span class="sxs-lookup"><span data-stu-id="5b6de-133">It is up to the type of search feature your adapter supports.</span></span>  
  
## <a name="echo-adapter-metadata-search"></a><span data-ttu-id="5b6de-134">Búsqueda de metadatos de adaptador de echo</span><span class="sxs-lookup"><span data-stu-id="5b6de-134">Echo adapter Metadata Search</span></span>  
 <span data-ttu-id="5b6de-135">Dependiendo de las categorías y las operaciones de su sistema de destino, hay muchas formas de crear una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="5b6de-135">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects to return.</span></span> <span data-ttu-id="5b6de-136">El adaptador de Echo implementa la funcionalidad de búsqueda consiste en pasar por cada operación con su Id. de nodo en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b6de-136">The way Echo adapter implements the search functionality is to go through every operation with its node ID in the following list:</span></span>  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- <span data-ttu-id="5b6de-137">Si el identificador de nodo, a continuación, coincide con los criterios de búsqueda, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` con el identificador de nodo de la operación de objeto y, a continuación, asigna las propiedades con valores.</span><span class="sxs-lookup"><span data-stu-id="5b6de-137">If the node ID then matches the search criteria, it creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object using the node ID of the operation, and then assigns the properties with values.</span></span> <span data-ttu-id="5b6de-138">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="5b6de-138">For example,</span></span>  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- <span data-ttu-id="5b6de-139">Y, a continuación, agregue el objeto a una colección de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="5b6de-139">And then add the object to a collection of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, for example,</span></span>  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- <span data-ttu-id="5b6de-140">Por último, devuelve la colección en un formato de matriz.</span><span class="sxs-lookup"><span data-stu-id="5b6de-140">Lastly returns the collection in an array format.</span></span>  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  <span data-ttu-id="5b6de-141">Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas para realizar una búsqueda basada en la conexión para las operaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="5b6de-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools to perform a connection-based search for the available operations.</span></span> <span data-ttu-id="5b6de-142">Por ejemplo, en la siguiente ilustración muestra que cuando los criterios de búsqueda es la cadena **saludo**, la búsqueda devuelve el **EchoGreetings** y **EchoGreetingFromFile** operaciones.</span><span class="sxs-lookup"><span data-stu-id="5b6de-142">For example, the following figure shows that when the searching criteria is the string **Greeting**, the search returns the **EchoGreetings** and **EchoGreetingFromFile** operations.</span></span>  
  
  <span data-ttu-id="5b6de-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span><span class="sxs-lookup"><span data-stu-id="5b6de-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span></span>  
  
  <span data-ttu-id="5b6de-144">Si se encuentra ninguna coincidencia, cualquiera de las herramientas devolverá el mensaje de error que se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b6de-144">If no match is found, either tool will return the error message shown in the following figure.</span></span>  
  
  <span data-ttu-id="5b6de-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span><span class="sxs-lookup"><span data-stu-id="5b6de-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span></span>  
  
## <a name="implementing-the-imetadatasearchhandler"></a><span data-ttu-id="5b6de-146">Implementar el IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="5b6de-146">Implementing the IMetadataSearchHandler</span></span>  
 <span data-ttu-id="5b6de-147">Implementará el `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b6de-147">You will implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="5b6de-148">Si el nombre para mostrar de la operación coincide con los criterios de búsqueda, creará un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para esa operación y, a continuación, agregue dicho objeto a una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="5b6de-148">If the operation's display name matches the search criteria, you will create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that operation, and then add that object to an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a><span data-ttu-id="5b6de-149">Para actualizar la clase EchoAdapterMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="5b6de-149">To update the EchoAdapterMetadataSearchHandler class</span></span>  
  
1.  <span data-ttu-id="5b6de-150">En el Explorador de soluciones, haga doble clic en el **EchoAdapterMetadataSearchHandler.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-150">In Solution Explorer, double-click the **EchoAdapterMetadataSearchHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="5b6de-151">En el editor de Visual Studio, dentro de la **búsqueda** método, reemplace la lógica existente por lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b6de-151">In the Visual Studio editor, inside the **Search** method, replace the existing logic with the following.</span></span> <span data-ttu-id="5b6de-152">Esta lógica se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/OnReceiveEcho coincide con los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="5b6de-152">This logic creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/OnReceiveEcho matches the specified search criteria.</span></span>  
  
    ```csharp  
    List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
    if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        nodeInbound.DisplayName = "OnReceiveEcho";  
        nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
        nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
        nodeInbound.IsOperation = true;  
        resultList.Add(nodeInbound);  
    }  
    ```  
  
3.  <span data-ttu-id="5b6de-153">Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoStrings coincide con los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="5b6de-153">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoStrings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
        outOpNode1.DisplayName = "EchoStrings";  
        outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode1.IsOperation = true;  
        resultList.Add(outOpNode1);  
    }  
    ```  
  
4.  <span data-ttu-id="5b6de-154">Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoGreetings coincide con los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="5b6de-154">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
        {  
            MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
            outOpNode2.DisplayName = "EchoGreetings";  
            outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
            outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
            outOpNode2.IsOperation = true;  
            resultList.Add(outOpNode2);  
        }  
    ```  
  
5.  <span data-ttu-id="5b6de-155">Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoGreetingFromFile coincide con los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="5b6de-155">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetingFromFile matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
        outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
        outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
        outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode3.IsOperation = true;  
        resultList.Add(outOpNode3);  
    }  
    ```  
  
6.  <span data-ttu-id="5b6de-156">Continúe agregando el código siguiente para devolver una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="5b6de-156">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  <span data-ttu-id="5b6de-157">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="5b6de-157">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="5b6de-158">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="5b6de-158">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="5b6de-159">Correctamente, debe compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5b6de-159">You should successfully compiled the project.</span></span> <span data-ttu-id="5b6de-160">Si no, asegúrese de que ha seguido todos los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5b6de-160">If not, ensure that you have followed every step above.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b6de-161">Ya ha guardado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-161">You saved your work.</span></span> <span data-ttu-id="5b6de-162">Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 6: implementar el controlador de resolver los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="5b6de-162">You can safely close Visual Studio at this time or go to the next step, [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5b6de-163">¿Qué simplemente hacer?</span><span class="sxs-lookup"><span data-stu-id="5b6de-163">What Did I Just Do?</span></span>  
 <span data-ttu-id="5b6de-164">Acaba de implementar los metadatos de búsqueda capacidad del adaptador de Echo, implementando la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b6de-164">You just implemented the metadata searching capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="5b6de-165">En concreto, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para cada operación que coincide con los criterios y, a continuación, devuelve una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.</span><span class="sxs-lookup"><span data-stu-id="5b6de-165">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for every operation that matches the criteria and then returned an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b6de-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5b6de-166">Next Steps</span></span>  
 <span data-ttu-id="5b6de-167">Implementará los metadatos de resolución de capacidad y las capacidades de intercambio de mensajes entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="5b6de-167">You will implement the metadata resolving capability, and the outbound and inbound message exchange capabilities.</span></span> <span data-ttu-id="5b6de-168">Por último, se compilará e implementará el adaptador de Echo.</span><span class="sxs-lookup"><span data-stu-id="5b6de-168">Finally, you will build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6de-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b6de-169">See Also</span></span>  
 <span data-ttu-id="5b6de-170">[Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5b6de-170">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="5b6de-171">[Paso 6: Implementar el controlador de resolución de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5b6de-171">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="5b6de-172">Tutorial 1: Desarrollar el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="5b6de-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)
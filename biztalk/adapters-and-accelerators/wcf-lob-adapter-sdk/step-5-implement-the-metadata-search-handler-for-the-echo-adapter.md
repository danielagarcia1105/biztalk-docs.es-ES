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
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a>Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de Echo
![Paso 5 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 **Tiempo en completarse:** 30 minutos  
  
 En este paso del tutorial, implementará la capacidad de búsqueda del adaptador de Echo. A diferencia de exploración, búsqueda es opcional. Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la capacidad de búsqueda, debe implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz. Para el adaptador de Echo la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente una clase derivada denominada EchoAdapterMetadataSearchHandler.  
  
 Actualizar la clase EchoAdapterMetadataSearchHandler para obtener una mejor comprensión de cómo implementar esta interfaz, cómo rellenar `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto y cómo aparecen los resultados de búsqueda en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, completar [paso 4: implementar el controlador de examinar los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md). También debe tener una idea clara sobre las clases siguientes:  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a>La interfaz IMetadataSearchHandler  
 El `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` se define como:  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 El `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método devuelve una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos según los criterios de búsqueda. En la tabla siguiente se describen las definiciones de parámetro para el método de búsqueda:  
  
|**Parámetro**|**Definición**|  
|-------------------|--------------------|  
|nodeId|Para iniciar la búsqueda en el identificador de nodo. Si es null o una cadena vacía (""), las operaciones se recuperan desde el nodo raíz ("/").|  
|searchCriteria|Los criterios de búsqueda, que es específica del adaptador. Si se especifica ningún criterio de búsqueda, el adaptador debería devolver todos los nodos.|  
|maxChildNodes|El número máximo de nodos de resultados para devolver. Utilice Int32.Max para recuperar todos los nodos de resultados.<br /><br /> No admite el adaptador de Echo.|  
|timeout|El tiempo máximo permitido para que se complete la operación.<br /><br /> No admite el adaptador de Echo.|  
  
 Resultado de la búsqueda, puede elegir el adaptador devolver los nodos de la categoría o nodos de la operación o ambas. Es hasta el tipo de característica de búsqueda de su adaptador admite.  
  
## <a name="echo-adapter-metadata-search"></a>Búsqueda de metadatos de adaptador de echo  
 Dependiendo de las categorías y las operaciones de su sistema de destino, hay muchas formas de crear una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos que se va a devolver. El adaptador de Echo implementa la funcionalidad de búsqueda consiste en pasar por cada operación con su Id. de nodo en la lista siguiente:  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- Si el identificador de nodo, a continuación, coincide con los criterios de búsqueda, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` con el identificador de nodo de la operación de objeto y, a continuación, asigna las propiedades con valores. Por ejemplo,  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- Y, a continuación, agregue el objeto a una colección de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, por ejemplo,  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- Por último, devuelve la colección en un formato de matriz.  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas para realizar una búsqueda basada en la conexión para las operaciones disponibles. Por ejemplo, en la siguiente ilustración muestra que cuando los criterios de búsqueda es la cadena **saludo**, la búsqueda devuelve el **EchoGreetings** y **EchoGreetingFromFile** operaciones.  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")  
  
  Si se encuentra ninguna coincidencia, cualquiera de las herramientas devolverá el mensaje de error que se muestra en la ilustración siguiente.  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")  
  
## <a name="implementing-the-imetadatasearchhandler"></a>Implementar el IMetadataSearchHandler  
 Implementará el `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz. Si el nombre para mostrar de la operación coincide con los criterios de búsqueda, creará un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para esa operación y, a continuación, agregue dicho objeto a una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a>Para actualizar la clase EchoAdapterMetadataSearchHandler  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterMetadataSearchHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, dentro de la **búsqueda** método, reemplace la lógica existente por lo siguiente. Esta lógica se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/OnReceiveEcho coincide con los criterios de búsqueda especificados.  
  
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
  
3.  Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoStrings coincide con los criterios de búsqueda especificados.  
  
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
  
4.  Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoGreetings coincide con los criterios de búsqueda especificados.  
  
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
  
5.  Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto a si Echo/EchoGreetingFromFile coincide con los criterios de búsqueda especificados.  
  
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
  
6.  Continúe agregando el código siguiente para devolver una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
8.  En el menú **Compilar** , haga clic en **Compilar solución**. Correctamente, debe compilar el proyecto. Si no, asegúrese de que ha seguido todos los pasos anteriores.  
  
    > [!NOTE]
    >  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 6: implementar el controlador de resolver los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Qué simplemente hacer?  
 Acaba de implementar los metadatos de búsqueda capacidad del adaptador de Echo, implementando la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interfaz. En concreto, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para cada operación que coincide con los criterios y, a continuación, devuelve una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementará los metadatos de resolución de capacidad y las capacidades de intercambio de mensajes entrantes y salientes. Por último, se compilará e implementará el adaptador de Echo.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [Paso 6: Implementar el controlador de resolución de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)
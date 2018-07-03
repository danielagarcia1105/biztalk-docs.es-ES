---
title: 'Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50110fff32b81bdaa429a479cefe8041d919356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003421"
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a>Paso 4: Implementar el controlador de exploración de metadatos para el adaptador de Echo
![Paso 4 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 **Tiempo en completarse:** 45 minutos  
  
 En este paso, implementará la capacidad de examinar del adaptador de Echo. Esta funcionalidad permite que el adaptador realizar una exploración basada en la conexión para obtener metadatos del sistema de destino. Independientemente de las capacidades de su adaptador, el adaptador debe admitir la funcionalidad de exploración.  
  
 Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la funcionalidad de exploración, debe implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz. Para el adaptador de Echo la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente la clase derivada denominada EchoAdapterMetadataBrowseHandler.  
  
 En los pasos siguientes, va a actualizar esta clase para obtener una mejor comprensión de cómo implementar la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método, cómo establecer diversas propiedades de la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto y cómo la operación y los nodos de categoría admitidos por el adaptador aparecen en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 3: implementar la conexión para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md). También debe comprender las siguientes clases:  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a>La interfaz IMetadataBrowseHandler  
 El `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz se define como:  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 El `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método devuelve una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos basados en los parámetros del método. Las definiciones de parámetro para el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método se describen en la tabla siguiente.  
  
> [!NOTE]
>  La implementación del adaptador de Echo usa solo el identificador de nodo y omite los otros tres parámetros, ya que el adaptador de Echo es compatible con solo unos pocos nodos.  
  
|  **Parámetro**  |                                                                                                                                                                                                                               **Definición**                                                                                                                                                                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     nodeId      | Cada elemento de la jerarquía del explorador de metadatos (el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y<br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]) tiene el nodeId. Cada identificador de nodo debe ser único y puede ser una categoría o una operación. La categoría puede tener subcategorías. **Nota:** si es null o una cadena vacía (""), las operaciones se recuperan desde el nodo raíz ("/") de forma predeterminada. |
| childStartIndex |                                                                                                                                                                                           El índice del primer elemento secundario para devolver.<br /><br /> No admite el adaptador de Echo.                                                                                                                                                                                            |
|  maxChildNodes  |                                                                                                                                                                  El número máximo de nodos de resultados para devolver. Utilice Int32.Max para recuperar todos los nodos de resultados.<br /><br /> No admite el adaptador de Echo.                                                                                                                                                                   |
|     timeout     |                                                                                                                                                                                   El tiempo máximo permitido para que se complete la operación.<br /><br /> No admite el adaptador de Echo.                                                                                                                                                                                    |
  
 Al implementar el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método, debe agregar cada nodo de categoría y la operación a la matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos. Para especificar un nodo como la categoría, establezca el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` a `false`. Para especificar un nodo como operación, establezca el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` a `true`.  
  
## <a name="echo-adapter-metadata-browse"></a>Exploración de metadatos de adaptador de echo  
 Dependiendo de las categorías y las operaciones de su sistema de destino, hay muchas formas de crear una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos. Las operaciones y categorías que elija deberían representar las operaciones que desea exponer. Pero para el adaptador de Echo, simplemente se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto para cada uno de los siguientes nodos con el Id. de nodo en la lista:  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 El EchoMainCategory es el nodo de categoría bajo el nodo raíz ("/"). Este nodo también se usa como la categoría para las operaciones de entrada y salidas. Por lo tanto, al crear el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objetos de la categoría, puede hacer lo siguiente:  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 Para una operación de salida como eco/EchoString que pertenece el EchoMainCategory, puede hacer lo siguiente:  
  
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
  
 Para una operación de entrada como eco/OnReceiveEcho que pertenece el EchoMainCategory, puede hacer lo siguiente:  
  
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
  
 Cuando el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas exploración los metadatos de adaptador de Echo, de forma predeterminada, inicia desde el nodo raíz ("/").  
  
 La siguiente ilustración muestra que el nodo EchoMainCategory aparece bajo el nodo raíz ("/"):  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 Para examinar las tres operaciones de salida, en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, en el **seleccione el tipo de contrato** lista desplegable, seleccione el **Client (Outbound operations)** opción. Consulte esas operaciones en el **operaciones y categorías disponibles** cuadro de lista, como se muestra a continuación:  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 En la ilustración anterior, tenga en cuenta que el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A` valor aparece en el **nombre** columna de la **operaciones y categorías disponibles** cuadro de lista. El parámetro pasa a la `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` constructor aparece en el **Id. de nodo** columna de la **operaciones y categorías disponibles** cuadro de lista y el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A` valor aparece como información sobre herramientas que contiene la descripción, cuando hace clic en el `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`.  
  
 Para ver las operaciones de entrada, en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta, en el **seleccione el tipo de contrato** lista desplegable, seleccione el **(operaciones de entrada) de servicio** opción. Vea la operación OnReceiveEcho entrante en el **operaciones y categorías disponibles** cuadro de lista, como se muestra en la ilustración siguiente:  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a>Implementar el IMetadataBrowseHandler  
 En este paso, va a actualizar la clase EchoAdapterMetadataBrowseHandler para implementar la exploración de metadatos del adaptador de Echo, es decir, para implementar el `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz. En concreto, se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objeto para cada categoría y la operación, establezca los valores adecuados para ese objeto y, a continuación, devolver la matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos para las operaciones y categorías. Tenga en cuenta que cuando se crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objeto, deberá pasar el Id. de nodo, no el nombre para mostrar.  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a>Para actualizar la clase EchoAdapterMetadataBrowseHandler  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterMetadataBrowseHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, el botón secundario en cualquier lugar dentro del editor, en el menú contextual, elija **esquematización**y, a continuación, haga clic en **Detener esquematización**.  
  
3.  En el editor de Visual Studio, dentro de la **examinar** método, reemplace la lógica existente con lo siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto EchoMainCategory.  
  
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
  
4.  Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto eco/OnReceiveEcho.  
  
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
  
5.  Continúe agregando la lógica siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto eco/EchoStrings.  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto eco/EchoGreetings.  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  Continúe agregando el código siguiente para crear un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objeto eco / EchoGreetingFromFile.  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  Continúe agregando el código siguiente para devolver una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos o null si no coincide.  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
10. En el menú **Compilar** , haga clic en **Compilar solución**. El proyecto se compilará correctamente. Si no, asegúrese de que ha seguido todos los pasos anteriores.  
  
> [!NOTE]
>  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 5: implementar el controlador de búsqueda de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Qué simplemente hacer?  
 Acaba de implementar los metadatos de exploración de capacidad del adaptador de Echo, implementando la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` método de la `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interfaz. En concreto, crea un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` para la categoría de objeto y, a continuación, se devuelven como una matriz de los `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objetos. Para cada operación, ha creado un `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` de objetos y, a continuación, devuelve todos los objetos en una matriz de `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementar metadatos búsqueda y capacidades de resolución y el intercambio de mensajes salientes. Por último, compilar e implementar el adaptador de Echo.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [Paso 3: Implementar la conexión para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)
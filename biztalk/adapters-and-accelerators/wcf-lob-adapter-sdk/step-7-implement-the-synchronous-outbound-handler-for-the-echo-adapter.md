---
title: "Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2e2679edafd72dc0d64510e7a8566180818f8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a><span data-ttu-id="79900-102">Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="79900-102">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="79900-103">![Paso 7 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span><span class="sxs-lookup"><span data-stu-id="79900-103">![Step 7 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span></span>  
  
 <span data-ttu-id="79900-104">**Tiempo en completarse:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="79900-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="79900-105">En este paso, implementará la capacidad de salida sincrónica del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="79900-105">In this step, you implement the synchronous outbound capability of the Echo adapter.</span></span> <span data-ttu-id="79900-106">Según la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la capacidad de salida sincrónica, debe implementar la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interfaz.</span><span class="sxs-lookup"><span data-stu-id="79900-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support the synchronous outbound capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interface.</span></span> <span data-ttu-id="79900-107">Para el adaptador de eco, el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente una clase derivada denominada EchoAdapterOutboundHandler.</span><span class="sxs-lookup"><span data-stu-id="79900-107">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterOutboundHandler.</span></span>  
  
 <span data-ttu-id="79900-108">En las siguientes secciones, se actualiza la clase EchoAdapterOutboundHandler para obtener una mejor comprensión de cómo implementar el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, cómo analizar el mensaje de solicitud entrante de WCF y cómo generar mensajes de respuesta WCF salientes.</span><span class="sxs-lookup"><span data-stu-id="79900-108">In the following sections, you update the EchoAdapterOutboundHandler class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, how to parse the incoming WCF request message, and how to generate outgoing WCF response messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79900-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="79900-109">Prerequisites</span></span>  
 <span data-ttu-id="79900-110">Antes de comenzar este paso, debe haber completado correctamente [paso 6: implementar el controlador de resolver metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="79900-110">Before you begin this step, you must have successfully completed [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="79900-111">Un conocimiento básico de `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` también es útil.</span><span class="sxs-lookup"><span data-stu-id="79900-111">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is also helpful.</span></span>  
  
## <a name="the-ioutboundhandler-interface"></a><span data-ttu-id="79900-112">La interfaz de IOutboundHandler</span><span class="sxs-lookup"><span data-stu-id="79900-112">The IOutboundHandler Interface</span></span>  
 <span data-ttu-id="79900-113">El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` se define como:</span><span class="sxs-lookup"><span data-stu-id="79900-113">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is defined as:</span></span>  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="79900-114">El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método ejecuta el mensaje de solicitud entrante de WCF invocando el método correspondiente en el sistema de destino y, a continuación, devuelve un mensaje de respuesta saliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="79900-114">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method executes the incoming WCF request message by invoking the corresponding method on the target system and then returns an outgoing WCF response message.</span></span> <span data-ttu-id="79900-115">Las definiciones de los parámetros se enumeran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="79900-115">The definitions of its parameters are listed in the following table:</span></span>  
  
|<span data-ttu-id="79900-116">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="79900-116">**Parameter**</span></span>|<span data-ttu-id="79900-117">**Definición**</span><span class="sxs-lookup"><span data-stu-id="79900-117">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="79900-118">message</span><span class="sxs-lookup"><span data-stu-id="79900-118">message</span></span>|<span data-ttu-id="79900-119">Mensaje de solicitud entrante de WCF.</span><span class="sxs-lookup"><span data-stu-id="79900-119">Incoming WCF request message.</span></span>|  
|<span data-ttu-id="79900-120">timeout</span><span class="sxs-lookup"><span data-stu-id="79900-120">timeout</span></span>|<span data-ttu-id="79900-121">Intervalo de tiempo dentro del cual se debe completar esta operación.</span><span class="sxs-lookup"><span data-stu-id="79900-121">Time interval within which this operation should be completed.</span></span> <span data-ttu-id="79900-122">La operación debería iniciar una `System.TimeoutException` si se supera el tiempo de espera antes de que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="79900-122">The operation should throw a `System.TimeoutException` if the specified timeout is exceeded before the operation is completed.</span></span>|  
  
 <span data-ttu-id="79900-123">Si el adaptador está realizando un envío unidireccional (no hay ningún mensaje de respuesta esperado por el adaptador), este método debe devolver null.</span><span class="sxs-lookup"><span data-stu-id="79900-123">If your adapter is performing a one-way send (there is no response message expected by your adapter), this method should return null.</span></span> <span data-ttu-id="79900-124">Si el adaptador está realizando una operación bidireccional con `Microsoft.ServiceModel.Channels.Common.OperationResult` igual que `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, este método devuelve un mensaje de respuesta WCF con un cuerpo vacío.</span><span class="sxs-lookup"><span data-stu-id="79900-124">If your adapter is performing a two-way operation with `Microsoft.ServiceModel.Channels.Common.OperationResult` equal to `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, this method returns a WCF response message with an empty body.</span></span> <span data-ttu-id="79900-125">En caso contrario, debe devolver el mensaje de respuesta WCF con un cuerpo que contiene los valores de la `Microsoft.ServiceModel.Channels.Common.OperationResult` objeto.</span><span class="sxs-lookup"><span data-stu-id="79900-125">Otherwise, it should return the WCF response message with a body that contains the values in the `Microsoft.ServiceModel.Channels.Common.OperationResult` object.</span></span> <span data-ttu-id="79900-126">Para construir la cadena de acción de respuesta, utilice `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.</span><span class="sxs-lookup"><span data-stu-id="79900-126">To construct the response action string, use `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.</span></span>  
  
## <a name="echo-adapter-synchronous-outbound"></a><span data-ttu-id="79900-127">Echo adaptador sincrónico saliente</span><span class="sxs-lookup"><span data-stu-id="79900-127">Echo Adapter Synchronous Outbound</span></span>  
 <span data-ttu-id="79900-128">Dependiendo de las operaciones de su sistema de destino, hay muchas maneras de implementar la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método.</span><span class="sxs-lookup"><span data-stu-id="79900-128">Depending on your target system's operations, there are many ways to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method.</span></span> <span data-ttu-id="79900-129">Para el adaptador de eco, hay tres operaciones de salida y sus identificadores de nodo asignada y nombres para mostrar son:</span><span class="sxs-lookup"><span data-stu-id="79900-129">For the Echo adapter, there are three outbound operations, and their assigned node IDs and display names are:</span></span>  
  
-   <span data-ttu-id="79900-130">String [] EchoStrings (datos de cadena), Id. de nodo = eco/EchoString, nombre para mostrar = EchoString</span><span class="sxs-lookup"><span data-stu-id="79900-130">string[] EchoStrings(string data), node ID = Echo/EchoString, display name=EchoString</span></span>  
  
-   <span data-ttu-id="79900-131">[] EchoGreetings(Greeting greeting), Id. de nodo de saludo = eco/EchoGreetings, nombre para mostrar = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="79900-131">Greeting[] EchoGreetings(Greeting greeting), node ID=Echo/EchoGreetings, display name=EchoGreetings</span></span>  
  
-   <span data-ttu-id="79900-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID = eco/EchoCustomGreetingFromFile, nombre para mostrar = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="79900-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID=Echo/EchoCustomGreetingFromFile, display name=EchoGreetings</span></span>  
  
 <span data-ttu-id="79900-133">Para analizar el mensaje de solicitud entrante de WCF y generar el mensaje de respuesta saliente de WCF correctamente, debe estar familiarizado con los siguientes elementos dentro del mensaje SOAP utilizado por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="79900-133">To correctly parse the incoming WCF request message and generate the outgoing WCF response message, you must be familiar with the following elements within the SOAP message used by the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span></span>  
  
 <span data-ttu-id="79900-134">Para el mensaje de solicitud entrante de WCF:</span><span class="sxs-lookup"><span data-stu-id="79900-134">For the incoming WCF request message:</span></span>  
  
-   <span data-ttu-id="79900-135">La acción del mensaje de entrada de WCF = Id. de nodo de la operación</span><span class="sxs-lookup"><span data-stu-id="79900-135">The WCF input message action = operation's node ID</span></span>  
  
-   <span data-ttu-id="79900-136">Cuerpo del mensaje entrante = el inicio es el elemento del cuerpo del \<displayname\>\<nombre de parámetro\>{datos}\<nombre/parámetro\>\</displayname\></span><span class="sxs-lookup"><span data-stu-id="79900-136">Incoming message body = The start element of the body is \<displayname\>\<parameter name\>{data}\</parameter name\>\</displayname\></span></span>  
  
 <span data-ttu-id="79900-137">Para el mensaje de respuesta saliente de WCF:</span><span class="sxs-lookup"><span data-stu-id="79900-137">For the outgoing WCF response message:</span></span>  
  
-   <span data-ttu-id="79900-138">Acción de mensaje de salida de WCF = Id. de nodo de la operación + "/ respuesta"</span><span class="sxs-lookup"><span data-stu-id="79900-138">The WCF output message action = operation's node ID + "/response"</span></span>  
  
-   <span data-ttu-id="79900-139">El cuerpo del mensaje de salida = el inicio es el elemento del cuerpo del \<displayname + "Respuesta"\>, seguido de \<displayname + "Resultado"\>y seguido por el \<datatype\>datos\</datatype\>\</displayname+ "resultado\>\</displayname +"Respuesta"\></span><span class="sxs-lookup"><span data-stu-id="79900-139">Outgoing message body = The start element of the body is \<displayname + "Response"\>, followed by \<displayname + "Result"\>, and followed by the \<datatype\>data\</datatype\>\</displayname+"Result\>\</displayname + "Response"\></span></span>  
  
 <span data-ttu-id="79900-140">Por ejemplo, operación **string [] EchoStrings (datos de cadena)**, Id. de nodo = eco/EchoStrings y nombre para mostrar = EchoStrings:</span><span class="sxs-lookup"><span data-stu-id="79900-140">For example, operation **string[] EchoStrings(string data)**, node ID = Echo/EchoStrings, and display name= EchoStrings:</span></span>  
  
 <span data-ttu-id="79900-141">La acción del mensaje de entrada de WCF = "Eco/EchoStrings"; o el cuerpo de la entrada de la aplicación como sigue, puesto que es el nombre del parámetro `data`.</span><span class="sxs-lookup"><span data-stu-id="79900-141">The WCF input message action = "Echo/EchoStrings"; and the input body looks as follows, since the parameter name is `data`.</span></span>  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 <span data-ttu-id="79900-142">Acción de mensaje de salida de WCF = "/ EchoStrings/respuesta de eco"; y el cuerpo de la salida tiene el siguiente aspecto, puesto que el tipo de datos es **cadena**.</span><span class="sxs-lookup"><span data-stu-id="79900-142">The WCF output message action = "Echo/EchoStrings/response"; and the output body looks as follows, since the data type is **string**.</span></span>  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 <span data-ttu-id="79900-143">Al analizar el mensaje de solicitud entrante de WCF, puede usar el `System.Xml.XmlDictionaryReader` para recuperar el contenido dentro del mensaje WCF; cuando se crea el mensaje de respuesta WCF, puede usar el `System.Xml.XmlWriter` para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="79900-143">When parsing the incoming WCF request message, you can use the `System.Xml.XmlDictionaryReader` to retrieve content within the WCF message; when composing the WCF response message, you can use the `System.Xml.XmlWriter` to do so.</span></span>  
  
## <a name="implementing-the-ioutboundhandler"></a><span data-ttu-id="79900-144">Implementar el IOutboundHandler</span><span class="sxs-lookup"><span data-stu-id="79900-144">Implementing the IOutboundHandler</span></span>  
 <span data-ttu-id="79900-145">Implementar el método Execute de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span><span class="sxs-lookup"><span data-stu-id="79900-145">You implement the Execute method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="79900-146">En primer lugar, se obtiene un `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="79900-146">First, gets a `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the input message action.</span></span> <span data-ttu-id="79900-147">A continuación, analiza el mensaje WCF entrante y se ejecuta la funcionalidad de eco asociados en función de cada operación.</span><span class="sxs-lookup"><span data-stu-id="79900-147">Then, parses the incoming WCF message and executes the associated echo functionality based on each operation.</span></span> <span data-ttu-id="79900-148">Por último, crea un mensaje de respuesta saliente de WCF mediante el formato del cuerpo de mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="79900-148">Finally, creates an outgoing WCF response message by using the format of outgoing message body.</span></span>  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a><span data-ttu-id="79900-149">Para implementar el método Execute de la clase EchoAdapterOutboundHandler</span><span class="sxs-lookup"><span data-stu-id="79900-149">To implement the Execute method of the EchoAdapterOutboundHandler class</span></span>  
  
1.  <span data-ttu-id="79900-150">En el Explorador de soluciones, haga doble clic en el **EchoAdapterOutboundHandler.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="79900-150">In Solution Explorer, double-click the **EchoAdapterOutboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="79900-151">En el editor de Visual Studio, agregue las dos siguientes directivas de uso al conjunto existente de directivas using.</span><span class="sxs-lookup"><span data-stu-id="79900-151">In the Visual Studio editor, add the following two using directives to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="79900-152">Dentro de la **Execute** método, reemplace la lógica existente con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79900-152">Inside the **Execute** method, replace the existing logic with the following:</span></span>  
  
    1.  <span data-ttu-id="79900-153">Esta lógica comprueba la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="79900-153">This logic verifies the requested operation.</span></span>  
  
    2.  <span data-ttu-id="79900-154">Obtiene el `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada de SOAP.</span><span class="sxs-lookup"><span data-stu-id="79900-154">It gets the `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the SOAP input message action.</span></span>  
  
    3.  <span data-ttu-id="79900-155">Según el tipo de acción, se analiza el mensaje de solicitud WCF y se invoca la operación apropiada.</span><span class="sxs-lookup"><span data-stu-id="79900-155">Based on the action type, it parses the WCF request message and invokes the appropriate operation.</span></span>  
  
    ```csharp  
    // Trace input message  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Verbose, "http://Microsoft.Adapters.Samples.Sql/TraceCode/InputWcfMessage", "Input WCF Message", this, new MessageTraceRecord(message));  
    // Timeout is not supported in this sample  
    OperationMetadata om = this.MetadataLookup.GetOperationDefinitionFromInputMessageAction(message.Headers.Action, timeout);  
    if (om == null)  
    {  
        throw new AdapterException("Invalid operation metadata for " + message.Headers.Action);  
    }  
    if (timeout.Equals(TimeSpan.Zero))  
    {  
        throw new AdapterException("time out is zero");  
    }  
  
    switch (message.Headers.Action)  
    {  
        case "Echo/EchoStrings":  
            return ExecuteEchoStrings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoGreetings":  
            return ExecuteEchoGreetings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoCustomGreetingFromFile":  
            return ExecuteEchoCustomGreetingFromFile(om, message, timeout);  
    }  
    return null;              
    ```  
  
4.  <span data-ttu-id="79900-156">A continuación, agregue el **ExecuteEchoStrings** método para controlar el string [] operación EchoStrings (datos de cadena).</span><span class="sxs-lookup"><span data-stu-id="79900-156">Now add the **ExecuteEchoStrings** method to handle the string[] EchoStrings(string data) operation.</span></span> <span data-ttu-id="79900-157">Esta función auxiliar lee el mensaje de solicitud WCF, comprueba si el elemento URI echoInUpperCase se establece como true; Si es así, convierte la cadena de entrada en mayúsculas tantas veces como indica la variable de recuento.</span><span class="sxs-lookup"><span data-stu-id="79900-157">This helper function reads the WCF request message, checks to see if the echoInUpperCase URI element is set to true; if so, it converts the input string to upper case as many times as the count variable indicates.</span></span> <span data-ttu-id="79900-158">A continuación, genera el mensaje de respuesta WCF con el formato: \<EchoStringsResponse\>\<EchoStringResult\>\<cadena\>{datos}\</string\> \</EchoStringResult\>\</EchoStringsResponse\>.</span><span class="sxs-lookup"><span data-stu-id="79900-158">Then, it generates the WCF response message in the format of: \<EchoStringsResponse\>\<EchoStringResult\>\<string\>{data}\</string\>\</EchoStringResult\>\</EchoStringsResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoStrings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // ** Read the WCF request  
        // ** <EchoStrings><name>{text}</name></EchoStrings>  
        XmlDictionaryReader inputReader = message.GetReaderAtBodyContents();  
        while (inputReader.Read())  
        {  
            if ((String.IsNullOrEmpty(inputReader.Prefix) && inputReader.Name.Equals("data"))  
                || inputReader.Name.Equals(inputReader.Prefix + ":" + "data")) break;  
        }  
        inputReader.Read();  
        // if the connection property "echoInUpperCase" is set to true, it echoes the data in upper case  
        bool echoInUpperCase = this.Connection.ConnectionFactory.ConnectionUri.EchoInUpperCase;  
        string inputValue = echoInUpperCase ? inputReader.Value.ToUpper() : inputReader.Value;  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        // ** <EchoStringsResponse><EchoStringResult>{Name}</EchoStringResult></EchoStringsResponse >  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        if (om.OperationResult.IsArray)  
        {  
            for (int count = 0; count < arrayCount; count++)  
            {  
                replywriter.WriteElementString("string", "http://schemas.microsoft.com/2003/10/Serialization/Arrays", inputValue);  
            }  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
5.  <span data-ttu-id="79900-159">Continuar agregando el **ExecuteEchoGreetings** método para controlar la operación de EchoGreetings.</span><span class="sxs-lookup"><span data-stu-id="79900-159">Continue by adding the **ExecuteEchoGreetings** method to handle the EchoGreetings operation.</span></span> <span data-ttu-id="79900-160">Esta función auxiliar lee el mensaje de solicitud WCF, se resuelve la operación y el tipo por la `ResolveOperationMetadata` y `ResolveTypeMetadata` métodos de la `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` de interfaz y, a continuación, genera el mensaje de respuesta WCF con el formato de: \< EchoGreetingsResponse\>\<EchoGreetingsResult\>... mensaje... \</EchoGreetingsResult\>\</EchoGreetingsResponse\>.</span><span class="sxs-lookup"><span data-stu-id="79900-160">This helper function reads the WCF request message, resolves operation and type by the `ResolveOperationMetadata` and `ResolveTypeMetadata` methods of the `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interface, and then generates the WCF response message using the format of: \<EchoGreetingsResponse\>\<EchoGreetingsResult\>…message…\</EchoGreetingsResult\>\</EchoGreetingsResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoGreetings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        String inputValue = String.Empty;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
  
            bool foundGreeting = inputReader.ReadToDescendant("greeting");  
            if (foundGreeting)  
            {  
                inputValue = inputReader.ReadInnerXml();  
            }  
        }  
  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        for(int i = 0; i < arrayCount; i++ )  
        {  
            ComplexQualifiedType cqtResult = om.OperationResult.QualifiedType as ComplexQualifiedType;  
            StructuredTypeMetadata tmResult = MetadataLookup.GetTypeDefinition(cqtResult.TypeId, timeout) as StructuredTypeMetadata;  
            replywriter.WriteStartElement(tmResult.TypeName, tmResult.TypeNamespace);  
            replywriter.WriteRaw(inputValue);  
            replywriter.WriteEndElement();  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
6.  <span data-ttu-id="79900-161">A continuación, agregue el **ExecuteEchoCustomGreetingFromFile** método para controlar la operación de EchoCustomGreetingFromFile.</span><span class="sxs-lookup"><span data-stu-id="79900-161">Now add the **ExecuteEchoCustomGreetingFromFile** method to handle the EchoCustomGreetingFromFile operation.</span></span> <span data-ttu-id="79900-162">Esta función auxiliar lee el mensaje de solicitud WCF, lee el mensaje desde el archivo especificado y, a continuación, genera el mensaje de respuesta WCF con el formato de: \<EchoGreetingsFromFileResponse\> \< EchoGreetingsFromFileResult\>... mensaje... \</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>.</span><span class="sxs-lookup"><span data-stu-id="79900-162">This helper function reads the WCF request message, reads the message from the specified file, and then generates the  WCF response message using the format of: \<EchoGreetingsFromFileResponse\>\<EchoGreetingsFromFileResult\>…message…\</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoCustomGreetingFromFile(OperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        Uri path;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
            inputReader.MoveToContent();  
            inputReader.ReadStartElement(om.DisplayName);  
            inputReader.MoveToContent();  
            // The path contains the location of the XML file that contains the instance of Greeting object to read   
            path = new Uri(inputReader.ReadElementContentAsString());  
            inputReader.ReadEndElement();  
        }  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        // Read the XML file and set it to the reply writer here  
        FileStream stream = new FileStream(path.AbsolutePath, FileMode.Open);  
        XmlDictionaryReader xdr = XmlDictionaryReader.CreateTextReader(stream, new XmlDictionaryReaderQuotas());  
        xdr.MoveToContent();  
        string rawGreeting = xdr.ReadInnerXml();  
        replywriter.WriteRaw(rawGreeting);  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
7.  <span data-ttu-id="79900-163">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="79900-163">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="79900-164">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="79900-164">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="79900-165">Debe compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="79900-165">It should compile without errors.</span></span> <span data-ttu-id="79900-166">Si no es así, asegúrese de que ha seguido todos los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="79900-166">If not, ensure that you have followed every step above.</span></span> <span data-ttu-id="79900-167">Ahora, sin ningún riesgo puede cierre Visual Studio o ir a [paso 8: implementar el controlador sincrónico de entrada para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="79900-167">Now, you can safely close Visual Studio or continue on to [Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="79900-168">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="79900-168">What Did I Just Do?</span></span>  
 <span data-ttu-id="79900-169">En este paso, aprendió a implementar la funcionalidad de mensajería saliente sincrónica del adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="79900-169">In this step, you learned how to implement the synchronous outbound messaging functionality of the Echo adapter.</span></span> <span data-ttu-id="79900-170">Para ello, implementa el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span><span class="sxs-lookup"><span data-stu-id="79900-170">To do so, you implemented the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="79900-171">Este método analiza el mensaje de solicitud entrante de WCF, realiza las acciones necesarias y, a continuación, genera el mensaje de respuesta saliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="79900-171">This method parsed the incoming WCF request message, performed the necessary actions, and then generated the outgoing WCF response message.</span></span>  
  
 <span data-ttu-id="79900-172">En concreto, para el mensaje de solicitud entrante de WCF, usa WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` para recuperar la acción de mensaje de entrada, es necesario comprender la estructura básica del cuerpo del mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="79900-172">Specifically, for the incoming WCF request message, you used WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` to retrieve the input message action by further understanding the basic structure of the incoming message body.</span></span> <span data-ttu-id="79900-173">Para el mensaje de respuesta saliente de WCF, usó `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` para recuperar la acción de mensaje de salida, es necesario comprender la estructura básica del cuerpo del mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="79900-173">For the outgoing WCF response message, you used `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` to retrieve the output message action by further understanding the basic structure of the outgoing message body.</span></span> <span data-ttu-id="79900-174">Al analizar y componer los mensajes de WCF, se utilizaron `System.Xml.XmlDictionaryReader` para leer el mensaje de solicitud entrante de WCF y usar `System.Xml.XmlWriter` para escribir un mensaje de respuesta saliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="79900-174">When parsing and composing WCF messages, you used `System.Xml.XmlDictionaryReader` to read the incoming WCF request message and used `System.Xml.XmlWriter` to write an outgoing WCF response message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79900-175">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="79900-175">Next Steps</span></span>  
<span data-ttu-id="79900-176">Compilar e implementar el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="79900-176">Build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79900-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="79900-177">See Also</span></span>  
 <span data-ttu-id="79900-178">[Paso 6: Implementar el controlador de la resolución de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="79900-178">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="79900-179">Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de Echo</span><span class="sxs-lookup"><span data-stu-id="79900-179">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)
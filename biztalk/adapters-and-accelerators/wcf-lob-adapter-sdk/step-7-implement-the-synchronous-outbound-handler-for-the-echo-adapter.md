---
title: 'Paso 7: Implementar el controlador de salida sincrónico para el adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e44c26c1708f54cceeb979cf20e5c43a95528a54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979469"
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a>Paso 7: Implementar el controlador de salida sincrónico para el adaptador de Echo
![Paso 7 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 **Tiempo en completarse:** 30 minutos  
  
 En este paso, implementará la capacidad de salida sincrónica del adaptador de Echo. Según el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la capacidad de salida sincrónica, se debe implementar la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interfaz. Para el adaptador de Echo la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente una clase derivada denominada EchoAdapterOutboundHandler.  
  
 En las secciones siguientes, va a actualizar la clase EchoAdapterOutboundHandler para obtener una mejor comprensión de cómo implementar el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, cómo analizar el mensaje de solicitud entrante de WCF y cómo generar mensajes de respuesta WCF salientes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 6: implementar el controlador de resolver los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md). Un conocimiento básico `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` también es útil.  
  
## <a name="the-ioutboundhandler-interface"></a>La interfaz IOutboundHandler  
 El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` se define como:  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método se ejecuta el mensaje de solicitud WCF entrante al invocar el método correspondiente en el sistema de destino y, a continuación, devuelve un mensaje de respuesta saliente de WCF. Las definiciones de sus parámetros se muestran en la tabla siguiente:  
  
|**Parámetro**|**Definición**|  
|-------------------|--------------------|  
|message|Mensaje de solicitud WCF entrante.|  
|timeout|Intervalo de tiempo en que se debe completar esta operación. La operación debería iniciar un `System.TimeoutException` si se supera el tiempo de espera especificado antes de que finalice la operación.|  
  
 Si el adaptador está realizando un envío unidireccional (no hay ningún mensaje de respuesta esperado por el adaptador), este método debe devolver null. Si el adaptador está realizando una operación bidireccional con `Microsoft.ServiceModel.Channels.Common.OperationResult` igual a `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, este método devuelve un mensaje de respuesta WCF con un cuerpo vacío. En caso contrario, debe devolver el mensaje de respuesta WCF con un cuerpo que contiene los valores de la `Microsoft.ServiceModel.Channels.Common.OperationResult` objeto. Para construir la cadena de acción de respuesta, utilice `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.  
  
## <a name="echo-adapter-synchronous-outbound"></a>Echo adaptador sincrónico saliente  
 Dependiendo de las operaciones de su sistema de destino, hay muchas maneras de implementar el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método. Para el adaptador de Echo, hay tres operaciones de salida y sus identificadores de nodo asignada y nombres para mostrar son:  
  
- String [] EchoStrings (datos de cadena), Id. de nodo = eco/EchoString, nombre para mostrar = EchoString  
  
- [] EchoGreetings(Greeting greeting), Id. de nodo de saludo = eco/EchoGreetings, nombre para mostrar = EchoGreetings  
  
- CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID = eco/EchoCustomGreetingFromFile, nombre para mostrar = EchoGreetings  
  
  Para analizar el mensaje de solicitud WCF entrante y generar el mensaje de respuesta saliente de WCF correctamente, debe estar familiarizado con los siguientes elementos dentro del mensaje SOAP utilizado por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
  Para el mensaje de solicitud entrante de WCF:  
  
- Acción de mensaje de entrada de WCF = Id. de nodo de la operación  
  
- Cuerpo del mensaje entrante = el inicio de elemento del cuerpo es \<displayname\>\<nombre del parámetro\>{datos}\<nombre/parámetro\>\</displayname\>  
  
  Para el mensaje de respuesta saliente de WCF:  
  
- Acción de mensaje de salida WCF = Id. de nodo de la operación + "/ respuesta"  
  
- El cuerpo del mensaje de salida = el inicio es el elemento del cuerpo del \<displayname + "Respuesta"\>, seguido de \<displayname + "Resultado"\>y seguido por el \<datatype\>datos\</datatype\>\</displayname+ "resultado\>\</displayname +"Respuesta"\>  
  
  Por ejemplo, operación **string [] (datos de cadena) EchoStrings**, Id. de nodo = eco/EchoStrings y nombre para mostrar = EchoStrings:  
  
  Acción de mensaje de entrada de WCF = "Eco/EchoStrings"; y el cuerpo de entrada tiene el siguiente aspecto, puesto que es el nombre del parámetro `data`.  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 Acción de mensaje de salida WCF = "/ EchoStrings/respuesta de eco"; y el cuerpo de la salida tiene el siguiente aspecto, puesto que es el tipo de datos **cadena**.  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 Al analizar el mensaje de solicitud entrante de WCF, puede usar el `System.Xml.XmlDictionaryReader` para recuperar el contenido dentro del mensaje WCF; al redactar el mensaje de respuesta WCF, puede usar el `System.Xml.XmlWriter` para hacerlo.  
  
## <a name="implementing-the-ioutboundhandler"></a>Implementar el IOutboundHandler  
 Implementar el método Execute de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`. En primer lugar, se obtiene un `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada. A continuación, analiza el mensaje WCF entrante y la funcionalidad del eco asociada en función de cada operación se ejecuta. Por último, crea un mensaje de respuesta saliente de WCF con el formato del cuerpo de mensaje saliente.  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a>Para implementar el método Execute de la clase EchoAdapterOutboundHandler  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterOutboundHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, agregue las dos siguientes directivas using al conjunto de directivas de uso existente.  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  Dentro de la **Execute** método, reemplace la lógica existente por lo siguiente:  
  
    1.  Esta lógica comprueba la operación solicitada.  
  
    2.  Obtiene el `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada de SOAP.  
  
    3.  Según el tipo de acción, analiza el mensaje de solicitud WCF e invoca la operación adecuada.  
  
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
  
4.  Ahora, agregue el **ExecuteEchoStrings** método para controlar el string [] operación EchoStrings (datos de cadena). Esta función auxiliar lee el mensaje de solicitud WCF, comprueba si el elemento URI echoInUpperCase se establece como true; Si es así, convierte la cadena de entrada a mayúsculas tantas veces como indica la variable de contador. A continuación, genera el mensaje de respuesta WCF con el formato: \<EchoStringsResponse\>\<EchoStringResult\>\<cadena\>{datos}\</string\> \</EchoStringResult\>\</EchoStringsResponse\>.  
  
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
  
5.  Continúe agregando el **ExecuteEchoGreetings** método para controlar la operación EchoGreetings. Esta función auxiliar lee el mensaje de solicitud WCF, se resuelve como la operación y el tipo por el `ResolveOperationMetadata` y `ResolveTypeMetadata` métodos de la `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interfaz y, a continuación, genera el mensaje de respuesta WCF con el formato de: \< EchoGreetingsResponse\>\<EchoGreetingsResult\>... mensaje... \</EchoGreetingsResult\>\</EchoGreetingsResponse\>.  
  
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
  
6.  Ahora, agregue el **ExecuteEchoCustomGreetingFromFile** método para controlar la operación EchoCustomGreetingFromFile. Esta función auxiliar lee el mensaje de solicitud WCF, lee el mensaje desde el archivo especificado y, a continuación, genera el mensaje de respuesta WCF con el formato de: \<EchoGreetingsFromFileResponse\> \< EchoGreetingsFromFileResult\>... mensaje... \</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>.  
  
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
  
7.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
8.  En el menú **Compilar** , haga clic en **Compilar solución**. Debe compilar sin errores. Si no, asegúrese de que ha seguido todos los pasos anteriores. Ahora, puede cerrar Visual Studio o seguir en forma segura [paso 8: implementar el controlador de entrada sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Qué simplemente hacer?  
 En este paso, ha aprendido cómo implementar la funcionalidad de mensajería saliente sincrónica del adaptador de Echo. Para ello, ha implementado la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`. Este método analiza el mensaje de solicitud entrante de WCF, realiza las acciones necesarias y, a continuación, genera el mensaje de respuesta saliente de WCF.  
  
 En concreto, para el mensaje de solicitud entrante de WCF, usa WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` para recuperar la acción de mensaje de entrada, es necesario comprender la estructura básica del cuerpo del mensaje de entrada. Para el mensaje de respuesta saliente de WCF, usó `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` para recuperar la acción de mensaje de salida, es necesario comprender la estructura básica del cuerpo del mensaje de salida. Al analizar y redactar mensajes WCF, usó `System.Xml.XmlDictionaryReader` para leer el mensaje de solicitud WCF entrante y utiliza `System.Xml.XmlWriter` para escribir un mensaje de respuesta saliente de WCF.  
  
## <a name="next-steps"></a>Pasos siguientes  
Compilar e implementar el adaptador de Echo.  
  
## <a name="see-also"></a>Vea también  
 [Paso 6: Implementar el controlador de resolución de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)
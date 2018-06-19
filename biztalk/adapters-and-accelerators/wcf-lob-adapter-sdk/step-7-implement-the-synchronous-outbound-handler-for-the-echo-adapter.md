---
title: 'Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco | Documentos de Microsoft'
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
ms.openlocfilehash: 9a2e2679edafd72dc0d64510e7a8566180818f8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967738"
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a>Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco
![Paso 7 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 **Tiempo en completarse:** 30 minutos  
  
 En este paso, implementará la capacidad de salida sincrónica del adaptador de eco. Según la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], para admitir la capacidad de salida sincrónica, debe implementar la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interfaz. Para el adaptador de eco, el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente una clase derivada denominada EchoAdapterOutboundHandler.  
  
 En las siguientes secciones, se actualiza la clase EchoAdapterOutboundHandler para obtener una mejor comprensión de cómo implementar el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, cómo analizar el mensaje de solicitud entrante de WCF y cómo generar mensajes de respuesta WCF salientes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 6: implementar el controlador de resolver metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md). Un conocimiento básico de `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` también es útil.  
  
## <a name="the-ioutboundhandler-interface"></a>La interfaz de IOutboundHandler  
 El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` se define como:  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 El `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método ejecuta el mensaje de solicitud entrante de WCF invocando el método correspondiente en el sistema de destino y, a continuación, devuelve un mensaje de respuesta saliente de WCF. Las definiciones de los parámetros se enumeran en la tabla siguiente:  
  
|**Parámetro**|**Definición**|  
|-------------------|--------------------|  
|message|Mensaje de solicitud entrante de WCF.|  
|timeout|Intervalo de tiempo dentro del cual se debe completar esta operación. La operación debería iniciar una `System.TimeoutException` si se supera el tiempo de espera antes de que se complete la operación.|  
  
 Si el adaptador está realizando un envío unidireccional (no hay ningún mensaje de respuesta esperado por el adaptador), este método debe devolver null. Si el adaptador está realizando una operación bidireccional con `Microsoft.ServiceModel.Channels.Common.OperationResult` igual que `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, este método devuelve un mensaje de respuesta WCF con un cuerpo vacío. En caso contrario, debe devolver el mensaje de respuesta WCF con un cuerpo que contiene los valores de la `Microsoft.ServiceModel.Channels.Common.OperationResult` objeto. Para construir la cadena de acción de respuesta, utilice `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.  
  
## <a name="echo-adapter-synchronous-outbound"></a>Echo adaptador sincrónico saliente  
 Dependiendo de las operaciones de su sistema de destino, hay muchas maneras de implementar la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método. Para el adaptador de eco, hay tres operaciones de salida y sus identificadores de nodo asignada y nombres para mostrar son:  
  
-   String [] EchoStrings (datos de cadena), Id. de nodo = eco/EchoString, nombre para mostrar = EchoString  
  
-   [] EchoGreetings(Greeting greeting), Id. de nodo de saludo = eco/EchoGreetings, nombre para mostrar = EchoGreetings  
  
-   CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID = eco/EchoCustomGreetingFromFile, nombre para mostrar = EchoGreetings  
  
 Para analizar el mensaje de solicitud entrante de WCF y generar el mensaje de respuesta saliente de WCF correctamente, debe estar familiarizado con los siguientes elementos dentro del mensaje SOAP utilizado por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
 Para el mensaje de solicitud entrante de WCF:  
  
-   La acción del mensaje de entrada de WCF = Id. de nodo de la operación  
  
-   Cuerpo del mensaje entrante = el inicio es el elemento del cuerpo del \<displayname\>\<nombre de parámetro\>{datos}\<nombre/parámetro\>\</displayname\>  
  
 Para el mensaje de respuesta saliente de WCF:  
  
-   Acción de mensaje de salida de WCF = Id. de nodo de la operación + "/ respuesta"  
  
-   El cuerpo del mensaje de salida = el inicio es el elemento del cuerpo del \<displayname + "Respuesta"\>, seguido de \<displayname + "Resultado"\>y seguido por el \<datatype\>datos\</datatype\>\</displayname+ "resultado\>\</displayname +"Respuesta"\>  
  
 Por ejemplo, operación **string [] EchoStrings (datos de cadena)**, Id. de nodo = eco/EchoStrings y nombre para mostrar = EchoStrings:  
  
 La acción del mensaje de entrada de WCF = "Eco/EchoStrings"; o el cuerpo de la entrada de la aplicación como sigue, puesto que es el nombre del parámetro `data`.  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 Acción de mensaje de salida de WCF = "/ EchoStrings/respuesta de eco"; y el cuerpo de la salida tiene el siguiente aspecto, puesto que el tipo de datos es **cadena**.  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 Al analizar el mensaje de solicitud entrante de WCF, puede usar el `System.Xml.XmlDictionaryReader` para recuperar el contenido dentro del mensaje WCF; cuando se crea el mensaje de respuesta WCF, puede usar el `System.Xml.XmlWriter` para hacerlo.  
  
## <a name="implementing-the-ioutboundhandler"></a>Implementar el IOutboundHandler  
 Implementar el método Execute de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`. En primer lugar, se obtiene un `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada. A continuación, analiza el mensaje WCF entrante y se ejecuta la funcionalidad de eco asociados en función de cada operación. Por último, crea un mensaje de respuesta saliente de WCF mediante el formato del cuerpo de mensaje saliente.  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a>Para implementar el método Execute de la clase EchoAdapterOutboundHandler  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterOutboundHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, agregue las dos siguientes directivas de uso al conjunto existente de directivas using.  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  Dentro de la **Execute** método, reemplace la lógica existente con lo siguiente:  
  
    1.  Esta lógica comprueba la operación solicitada.  
  
    2.  Obtiene el `Microsoft.ServiceModel.Channels.Common.OperationMetadata` objeto basándose en la acción de mensaje de entrada de SOAP.  
  
    3.  Según el tipo de acción, se analiza el mensaje de solicitud WCF y se invoca la operación apropiada.  
  
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
  
4.  A continuación, agregue el **ExecuteEchoStrings** método para controlar el string [] operación EchoStrings (datos de cadena). Esta función auxiliar lee el mensaje de solicitud WCF, comprueba si el elemento URI echoInUpperCase se establece como true; Si es así, convierte la cadena de entrada en mayúsculas tantas veces como indica la variable de recuento. A continuación, genera el mensaje de respuesta WCF con el formato: \<EchoStringsResponse\>\<EchoStringResult\>\<cadena\>{datos}\</string\> \</EchoStringResult\>\</EchoStringsResponse\>.  
  
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
  
5.  Continuar agregando el **ExecuteEchoGreetings** método para controlar la operación de EchoGreetings. Esta función auxiliar lee el mensaje de solicitud WCF, se resuelve la operación y el tipo por la `ResolveOperationMetadata` y `ResolveTypeMetadata` métodos de la `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` de interfaz y, a continuación, genera el mensaje de respuesta WCF con el formato de: \< EchoGreetingsResponse\>\<EchoGreetingsResult\>... mensaje... \</EchoGreetingsResult\>\</EchoGreetingsResponse\>.  
  
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
  
6.  A continuación, agregue el **ExecuteEchoCustomGreetingFromFile** método para controlar la operación de EchoCustomGreetingFromFile. Esta función auxiliar lee el mensaje de solicitud WCF, lee el mensaje desde el archivo especificado y, a continuación, genera el mensaje de respuesta WCF con el formato de: \<EchoGreetingsFromFileResponse\> \< EchoGreetingsFromFileResult\>... mensaje... \</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>.  
  
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
  
8.  En el menú **Compilar** , haga clic en **Compilar solución**. Debe compilar sin errores. Si no es así, asegúrese de que ha seguido todos los pasos anteriores. Ahora, sin ningún riesgo puede cierre Visual Studio o ir a [paso 8: implementar el controlador sincrónico de entrada para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso, aprendió a implementar la funcionalidad de mensajería saliente sincrónica del adaptador de eco. Para ello, implementa el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` método de la `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`. Este método analiza el mensaje de solicitud entrante de WCF, realiza las acciones necesarias y, a continuación, genera el mensaje de respuesta saliente de WCF.  
  
 En concreto, para el mensaje de solicitud entrante de WCF, usa WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` para recuperar la acción de mensaje de entrada, es necesario comprender la estructura básica del cuerpo del mensaje entrante. Para el mensaje de respuesta saliente de WCF, usó `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` para recuperar la acción de mensaje de salida, es necesario comprender la estructura básica del cuerpo del mensaje saliente. Al analizar y componer los mensajes de WCF, se utilizaron `System.Xml.XmlDictionaryReader` para leer el mensaje de solicitud entrante de WCF y usar `System.Xml.XmlWriter` para escribir un mensaje de respuesta saliente de WCF.  
  
## <a name="next-steps"></a>Pasos siguientes  
Compilar e implementar el adaptador de eco.  
  
## <a name="see-also"></a>Vea también  
 [Paso 6: Implementar el controlador de la resolución de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)
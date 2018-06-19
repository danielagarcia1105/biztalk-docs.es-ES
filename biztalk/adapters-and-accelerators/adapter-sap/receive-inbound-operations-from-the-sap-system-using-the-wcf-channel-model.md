---
title: Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b76ae42cf0ffc26b818e35d83f59e64158b923a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966202"
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a>Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF
Para actuar como un servidor RFC y recibir operaciones invocadas por el sistema SAP (por ejemplo, enviar un IDOC o invocar una solicitud de cambio), debe crear una escucha de canales que puede realizar escuchas de mensajes de un identificador de programa de SAP en un  **System.ServiceModel.Channels.IReplyChannel** forma de canal.  
  
 Un agente de escucha de canal (**System.ServiceModel.Channels.IChannelListener**) es un objeto de comunicación de WCF que puede utilizarse para recibir mensajes de los extremos WCF específicos. El agente de escucha de canal funciona como un generador desde el que puede crear canales que se pueden recibir mensajes invocados por un cliente (el sistema SAP) por el servicio. Crear un agente de escucha del canal por desde una **Microsoft.Adapters.SAP.SAPBinding** objeto invocando la **BuildChannelListener** método. Proporcione una URI que especifica el identificador de programa de SAP desde el que se recibirán las operaciones de entrada a este método de conexión de SAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con la **IReplyChannel** forma de canal. **IReplyChannel** canales admiten un patrón de intercambio de mensajes de respuesta de solicitud entrante. Es decir, un patrón en el que un programa externo envía un mensaje de solicitud a través del canal y el programa devuelve una respuesta.  
  
 Para obtener información general sobre el uso de operaciones de recepción de un **IReplyChannel** en WCF, vea [nivel de canal del servicio de programación](https://msdn.microsoft.com/library/ms789029.aspx).
  
 En esta sección se trata los temas siguientes que son específicos para recibir las operaciones de un sistema SAP:  
  
-   Cómo filtrar para operaciones específicas mediante el agente de escucha de canal.  
  
-   Cómo generar una excepción en el sistema SAP.  
  
-   Transmisión por secuencias entrante IDOC de archivo sin formato desde el adaptador SAP.  
  
-   Cómo recibir operaciones desde el sistema SAP.  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a>¿Cómo se puede filtrar las operaciones mediante el agente de escucha de canal?  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a>Uso de un InboundActionCollection para operaciones de filtro  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona el **Microsoft.ServiceModel.Channels.InboundActionCollection** clase que le permite filtrar las operaciones que se reciben un agente de escucha de canal y se pasa al código de aplicación. Para filtrar para operaciones específicas, crea una instancia de esta clase mediante el URI del extremo de agente de escucha. A continuación, agregar la acción de mensaje (solicitud) para cada operación de destino a la colección. Por último, puede agregar a la colección de entrada de acción un **System.ServiceModel.Channels.BindingParameterCollection** objeto y, a continuación, pasar esta colección de parámetros de enlace en la llamada para crear la escucha del canal.  
  
 Si el sistema SAP, invoca una operación que no está en la colección de acciones de entrada:  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] devuelve una excepción al llamador en el sistema SAP con el siguiente mensaje: "no se controla la llamada entrante de RFC [RFC_NAME] en el servidor de Rfc". En este mensaje, [RFC_NAME] es el nombre de la solicitud de cambio (por ejemplo, IDOC_INBOUND_ASYNCHRONOUS).  
  
-   El adaptador lanza una **Microsoft.ServiceModel.Channels.Common.AdapterException** con un mensaje que indica que la operación que se recibió. Para obtener un ejemplo de cómo usar esta excepción, vea el ejemplo al final de este tema.  
  
 En el ejemplo de código siguiente se muestra cómo utilizar un **InboundActionCollection** para crear un agente de escucha de canal que filtra una RFC única, Z_RFC_MKD_DIV.  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a>Operaciones de filtrado manualmente  
 Si no especifica una colección de acciones de entrada para el agente de escucha de canal, todas las operaciones invocadas por el sistema SAP se pasarán al código. Puede filtrar manualmente estas operaciones mediante la comprobación de la acción de mensaje de las solicitudes de entrada.  
  
 También puede haber escenarios en los que desea filtrar una operación en función de su contenido. Por ejemplo, si recibe IDOC en:  
  
-   Formato de cadena (el **ReceiveIDocFormat** propiedad de enlace es **cadena**); todos los IDOC se recibe mediante la operación de ReceiveIdoc.  
  
-   Formato de RFC (la **ReceiveIDocFormat** propiedad de enlace es **Rfc**); todos los IDOC se recibe mediante la solicitud de cambio de IDOC_INBOUND_ASYNCHRONOUS o la solicitud de cambio de INBOUND_IDOC_PROCESS.  
  
 En este escenario puede que desee implementar filtrado basándose en los parámetros específicos de IDOC (por ejemplo, el tipo IDOC) en el código.  
  
 Cuando se filtran las operaciones manualmente, puede devolver un error en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para las operaciones que no se encarga de. Esto producirá la excepción al llamador en el sistema SAP. También puede devolver una respuesta vacía si no desea generar una excepción en SAP.  
  
 El código siguiente muestra cómo filtrar manualmente para la operación de Z_RFC_MKD_DIV.  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a>¿Cómo se puede producir una excepción en el sistema SAP?  
 Para indicar un error al llamador en el sistema SAP puede responder a un mensaje de solicitud con un error de SOAP. Cuando se devolverá un error SOAP para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el adaptador devuelve una excepción al llamador en el sistema SAP. Se crea el mensaje de excepción de los elementos de los errores SOAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] crea el mensaje para la excepción de SAP según el orden de prioridad siguiente:  
  
1.  Si el error de SOAP contiene un objeto de detalle, el adaptador serializa el nivel de detalle para una cadena y el mensaje de excepción se establece en esta cadena.  
  
2.  Si el error de SOAP contiene un motivo, el mensaje de excepción se establece en su valor.  
  
3.  En caso contrario, el adaptador serializa el **MessageFault** objeto a una cadena y el mensaje de excepción se establece en esta cadena.  
  
> [!NOTE]
>  El adaptador utiliza solo el mensaje de error para crear el mensaje de excepción que se devuelven en la excepción que se inicia en el sistema SAP; por lo tanto, los valores que establezca para estas entidades es decisión suya.  
  
 WCF proporciona el **System.ServiceModel.Channels.MessageFault** clase para encapsular una representación en memoria de un error de SOAP. Puede usar cualquiera de los métodos estático, sobrecargar **MessageFault.CreateFault** métodos para crear un nuevo error de SOAP desde el que, a continuación, puede crear un mensaje de error mediante la invocación de la correspondiente **Message.CreateMessage** se puede sobrecargar. WCF también proporciona sobrecargas de **CreateMessage** que crean un mensaje de error sin usar un **MessageFault** objeto.  
  
 Usa el **System.ServiceModel.Channels.RequestContext.Reply** método para devolver el mensaje de error para el adaptador. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] omite la acción de mensaje para los mensajes de error, por lo que puede establecer la acción de mensaje a cualquier valor.  
  
 En el ejemplo siguiente se muestra cómo devolver un mensaje de error para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Este ejemplo omiten los pasos para crear la escucha del canal y el canal.  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a>Transmisión por secuencias IDOC de archivo sin formato entrante del adaptador SAP  
 Recibir IDOC (cadena) desde el adaptador en la operación de ReceiveIdoc entrada de archivo sin formato. Los datos IDOC se representan como una cadena en un único nodo en esta operación. Por este motivo, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con transmisión por secuencias en el mensaje de solicitud en el valor de nodo. Para realizar la transmisión por secuencias de valor de nodo, debe consumir el mensaje de solicitud para la operación ReceiveIdoc invocando la **Message.WriteBodyContents** método con un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir por secuencias los datos IDOC. Para obtener información acerca de cómo hacerlo, consulte [IDOC de archivo plano de transmisión por secuencias en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a>¿Cómo obtengo operaciones desde un sistema SAP mediante un IReplyChannel?  
 Para operaciones de recepción de un sistema SAP mediante el modelo de canal WCF, realice los pasos siguientes.  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a>Para operaciones de recepción desde el sistema SAP mediante un IReplyChannel  
  
1.  Cree una instancia de **SAPBinding** y establezca las propiedades de enlace necesarias para las operaciones que desea recibir. Como mínimo debe establecer el **AcceptCredentialsInUri** enlaza la propiedad en true. Para que actúe como un servidor de tRFC, debe establecer el **TidDatabaseConnectionString** propiedad de enlace. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  Crear un **BindingParameterCollection** y agregue un **InboundActionCollection** que contiene las acciones de las operaciones que desea recibir. El adaptador devolverá una excepción al sistema SAP para todas las demás operaciones. Este paso es opcional. Para obtener más información, consulte [recibir las operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  Crear un agente de escucha de canal invocando **BuildChannelListener < IReplyChannel\>**  método en el **SAPBinding** y ábralo. Especifique el URI de conexión de SAP como uno de los parámetros a este método. El URI de conexión debe contener parámetros para un destino RFC en el sistema SAP. Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md). Si ha creado un **BindingParameterCollection** en el paso 3, también especificarlo al crear la escucha del canal.  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  Obtener un **IReplyChannel** canal invocando la **AcceptChannel** método en el agente de escucha y ábralo.  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  Invocar **ReceiveRequest** en el canal que se va a obtener el mensaje de solicitud de la siguiente operación del adaptador.  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  Consumir el mensaje de solicitud enviado por el adaptador. Aparece el mensaje de solicitud desde el **RequestMessage** propiedad de la **RequestContext**. Puedes utilizar el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  Completar la operación al devolver una respuesta o error al sistema SAP:  
  
    1.  Procesar el mensaje y devolver una respuesta al sistema SAP devolviendo el mensaje de respuesta al adaptador. En este ejemplo se devuelve un mensaje vacío.  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  Devuelve una excepción al sistema SAP devolviendo un mensaje de error para el adaptador. Puede utilizar un valor para la acción de mensaje, el código de error y el motivo.  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  Cierre el contexto de solicitud después de haber enviado el mensaje.  
  
    ```  
    rc.Close();  
    ```  
  
9. Cierre el canal cuando se hayan completado de procesar la solicitud.  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  Debe cerrar el canal cuando haya terminado de procesar la operación. Si no se cierra el canal puede afectar al comportamiento del código.  
  
10. Cierre el agente de escucha cuando haya terminado de recibir las operaciones desde el sistema SAP.  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  Debe cerrar explícitamente el agente de escucha cuando haya terminado de usarlo; en caso contrario, el programa no funcione correctamente. Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha. Debe cerrar explícitamente cada canal que se crea mediante el agente de escucha.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recibe una solicitud de cambio, Z_RFC_MKD_DIV desde el sistema SAP. Este RFC divide dos números. La implementación en este ejemplo utiliza un **InboundActionCollection** para filtrar para la operación de Z_RFC_MKD_DIV y hace lo siguiente cuando se recibe un mensaje:  
  
-   Si el divisor es distinto de cero, el resultado de la división se escribe en la consola y lo devuelve al sistema SAP.  
  
-   Si el divisor es cero, escribe el mensaje de excepción resultante en la consola y devuelve un error al sistema SAP.  
  
-   Si cualquier otra operación es enviado por el sistema SAP, escribe un mensaje en la consola. En este caso, el propio adaptador devuelve un error al sistema SAP.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)
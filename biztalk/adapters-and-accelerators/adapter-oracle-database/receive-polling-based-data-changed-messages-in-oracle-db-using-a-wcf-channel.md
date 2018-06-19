---
title: Recibir mensajes de cambio de datos basado en sondeo de base de datos de Oracle mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, receiving polling-based messages
- how to, receive polling-based messages by using the WCF channel model
ms.assetid: 13f501e4-cff7-497c-a9da-fdd6382c779f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e1596c0b0676db916068ff9a33a8be9d6a9fa3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216956"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a>Recibir mensajes de cambio de datos basado en sondeo de base de datos de Oracle mediante el modelo de canal de WCF
Puede configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para sondear una tabla de base de datos de Oracle o la vista de los cambios de datos. Para llevar a cabo una operación de sondeo de este tipo, el adaptador ejecuta periódicamente una consulta SQL en una tabla de Oracle o vista seguido de un bloque de código de PL/SQL opcional. A continuación, se devuelven los resultados de la consulta SQL por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en el código como fuertemente tipados conjunto de resultados en una operación de POLLINGSTMT entrante. Para obtener más información sobre el mecanismo utilizado para configurar y realizar el sondeo de Oracle de base de datos mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [recibir mensajes de cambio de datos basado en sondeo en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md). Se recomienda encarecidamente que lea este tema antes de continuar.  
  
 Configurar la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a sondeo y la tabla de base de datos de Oracle o la vista estableciendo las propiedades de enlace en una instancia de **OracleDBBinding**. En el modelo de canal WCF, a continuación, utilizar este enlace para compilar un agente de escucha de canal desde el que se puede obtener un **IInputChannel** canal para recibir la operación de POLLINGSTMT desde el adaptador.  
  
 Para obtener información general sobre el uso de operaciones de recepción de un **IInputChannel** en WCF, vea [nivel de canal del servicio de programación](https://msdn.microsoft.com/library/ms789029.aspx). 
  
 Las secciones de este tema proporcionan información para ayudarle a realizar el sondeo en las tablas de base de datos de Oracle y vistas que usan WCF modelo del canal.  
  
## <a name="consuming-the-pollingstmt-request-message"></a>Consumir el mensaje de solicitud POLLINGSTMT  
 El adaptador invoca la operación de POLLINGSTMT en su código para sondear la base de datos de Oracle. Es decir, el adaptador envía un mensaje de solicitud POLLINGSTMT que recibe en un **IInputChannel** forma de canal. El mensaje de solicitud POLLINGSTMT contiene el conjunto de resultados de la consulta especificada por el **PollingStatement** propiedad de enlace. Puede utilizar el mensaje POLLINGSTMT en uno de dos maneras:  
  
-   Para consumir el mensaje con el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y lo pasará un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  
  
-   Para consumir el mensaje mediante transmisión por secuencias de nodo que se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.  
  
 Se suele usa para consumir conjuntos de resultados que contienen columnas de datos LOB de Oracle de transmisión por secuencias en el valor de nodo.  
  
 Para obtener más información acerca de la estructura del mensaje de la operación de POLLINGSTMT, consulte [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [transmisión por secuencias de tipos de datos de objetos grandes en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).  
  
 Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir-to-end de transmisión por secuencias de datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema usa al SCOTT. Tabla ACCOUNTACTIVITY y el SCOTT. ACCOUNT_PKG. Función PROCESS_ACTIVITY. Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos. El ejemplo realiza las siguientes operaciones:  
  
-   Como parte de la instrucción de sondeo, selecciona todos los registros de la tabla ACCOUNTACTIVITY y que se muestran en la consola.  
  
-   Como parte de la instrucción de sondeo de envío, en el ejemplo se invoca la función PROCESS_ACTIVITY que mueve todos los registros de tabla ACCOUNTACTIVITY a la tabla ACTIVITYHISTORY.  
  
-   Los sondeos subsiguientes en la tabla ACCOUNTACTIVITY no devolvió ningún registro. Sin embargo, si desea que el ejemplo para devolver más registros como parte de la operación de sondeo, debe insertar algunos registros en la tabla ACCOUNTACTIVITY. Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos.  
  
 Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a>¿Cómo se puede sondear una base de datos de Oracle mediante una IInputChannel?  
 Para sondear una tabla de base de datos de Oracle o la vista para recibir mensajes de cambio de datos mediante el modelo de canal WCF, realice los pasos siguientes.  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a>Para recibir mensajes de cambio de datos mediante un IInputChannel  
  
1.  Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. De este tema, cree una aplicación de consola.  
  
2.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleDB`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.  
  
3.  Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
    -   `Microsoft.Adapters.OracleDB`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
    -   `System.Runtime.Serialization`  
  
    -   `System.IO`  
  
    -   `Microsoft.ServiceModel.Channels.Common`  
  
4.  Cree una instancia de **OracleDBBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo. Como mínimo debe establecer el **InboundOperationType**, **PollingStatement**, y **PollingInterval** propiedades de enlace. En este ejemplo, establece también el **PostPollStatement** propiedad de enlace. Para obtener más información sobre el enlace de propiedades que se usan para configurar el sondeo, consulte [recibir mensajes de cambio de datos basado en sondeo en el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).  
  
    ```  
    OracleDBBinding binding = new OracleDBBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PollingInterval = 30;  
    binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
    ```  
  
5.  Crear una colección de parámetros de enlace y establecer las credenciales.  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "SCOTT";  
    credentials.UserName.Password = "TIGER";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
6.  Crear un agente de escucha de canal y ábralo. Crear el agente de escucha mediante la invocación de **BuildChannelListener < IInputChannel\>**  método en el **OracleDBBinding**. Puede modificar el espacio de nombres de destino para la operación POLLINGSTMT estableciendo la propiedad PollingId en el URI de conexión. Para obtener más información acerca de lo URI de conexión del adaptador, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
7.  Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha y ábralo.  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
8.  Invocar **recepción** en el canal que se va a obtener el siguiente mensaje POLLINGSTMT desde el adaptador.  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
9. Consumir el conjunto de resultados devuelto por la operación de POLLINGSTMT. Puedes utilizar el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. Cierre el canal cuando se hayan completado de procesar la solicitud.  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  Debe cerrar el canal cuando haya terminado de procesar la operación de POLLINGSTMT. Si no se cierra el canal puede afectar al comportamiento del código.  
  
11. Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha. Debe cerrar explícitamente cada canal que se crea mediante el agente de escucha.  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear vistas y tablas de base de datos de Oracle y recibir la POLLLINGSTMT operación mediante WCF canal modelo. El conjunto de resultados devuelto en la operación de POLLINGSTMT se escribe en la consola mediante el uso de un **XmlReader**.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Add this namespace for channel model  
using System.ServiceModel.Channels;  
  
using System.Xml;  
using System.Runtime.Serialization;  
using System.IO;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace OraclePollingCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Uri connectionUri = new Uri("oracleDB://ADAPTER/");  
  
            IChannelListener<IInputChannel> listener = null;  
            IInputChannel channel = null;  
  
            // set timeout to receive POLLINGSTMT message  
            TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
            Console.WriteLine("Sample Started");  
  
            try  
            {  
                // Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the           
                // PollingStatement,and the PostPollStatement.  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingInterval = 30;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Create a binding parameter collection and set the credentials  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                Console.WriteLine("Opening listener");  
                // get a listener  from the binding  
                listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
                listener.Open();  
  
                Console.WriteLine("Opening channel");  
                // get a channel from the listener  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel opened -- waiting for polled data");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    // Write the TID, ACCOUNT, AMOUNT, and TRANSDATE for each record to the Console  
                    Console.WriteLine("\nPolling data received for request number {0}", i+1);  
                    Console.WriteLine("Tx ID\tACCOUNT\tAMOUNT\tTx DATE");  
  
                    while (reader.Read())  
                    {  
                        if (reader.IsStartElement())  
                        {  
                            switch (reader.Name)  
                            {  
                                case "POLLINGSTMTRECORD":  
                                    Console.Write("\n");  
                                    break;  
  
                                case "TID":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "ACCOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
                                case "AMOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "TRANSDATE":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                default:  
                                    break;  
                            }  
                        }  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    //            To save the polling data to a file you can REPLACE the code above with the following  
                    //  
                    //            XmlDocument doc = new XmlDocument();  
                    //            doc.Load(reader);  
                    //            using (XmlWriter writer = XmlWriter.Create("PollingOutput.xml"))  
                    //            {  
                    //                doc.WriteTo(writer);  
                    //            }  
                    message.Close();  
                }  
  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop polling  
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
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)
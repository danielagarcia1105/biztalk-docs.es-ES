---
title: Invocar operaciones en la base de datos de Oracle mediante el modelo de canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking operations, using the WCF channel model
- WCF channel model, invoking operations
- invoking operations
- operations, invoking
ms.assetid: 6dd95c18-8f78-46d0-8845-b74890614c33
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1ff19d925ac8892fdaed62204f4da742d1e86ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007421"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a>Invocar operaciones en la base de datos de Oracle mediante el modelo de canal de WCF
Puede invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el uso de un **IRequestChannel** o **IOutputChannel** forma para enviar mensajes al adaptador. El patrón básico consiste en crear un generador de canales para la forma del canal necesarios mediante el uso de un enlace (**OracleDBBinding**) y un punto de conexión creado a partir de un URI de conexión. A continuación, cree un **mensaje** instancia que representa un mensaje SOAP que se ajusta al esquema de mensajes para la operación de destino. A continuación, puede enviar este **mensaje** a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el uso de un canal creado desde el generador de canales. Si usas un **IRequestChannel**, recibirá una respuesta. Si hay un problema al ejecutar la operación en la base de datos de Oracle, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.  
  
 Para obtener información general de cómo enviar las operaciones mediante una **IRequestChannel** en WCF, vea "Programación de nivel de canal de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=106081 ](http://go.microsoft.com/fwlink/?LinkId=106081).  
  
 Las secciones de este tema proporcionan información para ayudarle a invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el modelo de canal WCF.  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a>Creación y consumo de mensajes para las operaciones de salida  
 Para invocar una operación en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], enviar el mensaje de solicitud para la operación de destino mediante un **IRequestChannel** o un **IOutputChannel**. Si usa un **IRequestChannel** el adaptador devuelve los resultados de la operación en el mensaje de respuesta.  
  
 Para obtener más información acerca de la solicitud y esquemas de mensaje de respuesta y las acciones de mensaje para cada operación, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).  
  
 Cómo crear el mensaje de solicitud y consumir el mensaje de respuesta determina si el valor del nodo de transmisión por secuencias o transmisión por secuencias de nodo se realiza por el adaptador. A su vez, esto determina si se realiza la transmisión por secuencias to-end de los datos LOB para las operaciones admitidas.  
  
### <a name="creating-the-request-message"></a>Crear el mensaje de solicitud  
 Puede crear el mensaje de solicitud de dos maneras:  
  
- Para crear un mensaje que se puede usar para el valor del nodo de transmisión por secuencias debe pasar el cuerpo del mensaje en un **XmlBodyWriter** que implementa el valor del nodo de transmisión por secuencias.  
  
- Para crear un mensaje que se puede usar para el nodo de streaming puede pasar el cuerpo del mensaje en un **XmlReader**.  
  
  Normalmente se utiliza para permitir el vertido to-end de datos LOB de Oracle en el mensaje de solicitud de transmisión por secuencias en el valor de nodo. La única operación que admita esta característica es UpdateLOB.  
  
### <a name="consuming-the-response-message"></a>Consume el mensaje de respuesta  
 Puede consumir el mensaje de respuesta en uno de dos maneras:  
  
- Para consumir el mensaje mediante el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y pasarle un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  
  
- Para consumir el mensaje mediante el flujo de nodo se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.  
  
  Normalmente se utiliza para permitir el vertido to-end de datos LOB de Oracle en el mensaje de respuesta de transmisión por secuencias en el valor de nodo. Hay muchas operaciones que admitan esta característica.  
  
### <a name="lob-data-and-message-streaming-support"></a>Compatibilidad con Streaming de mensaje y los datos LOB  
 Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).  
  
 Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir streaming to-end de los datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a>Compatibilidad con transacciones en las operaciones de salida en el modelo del canal de WCF.  
 El adaptador ejecuta cada operación que se invoca dentro de una transacción dedicada en la base de datos de Oracle. Puede controlar el nivel de aislamiento de estas transacciones estableciendo la **TransactionIsolationLevel** enlaza la propiedad.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 El ejemplo de este tema usa al SCOTT. Tabla ACCOUNTACTIVITY. Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>¿Cómo se puede invocar una operación mediante el uso de un canal?  
 Para invocar una operación mediante una **IRequestChannel**, realice los pasos siguientes.  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>Cómo invocar una operación mediante el uso de una instancia de IRequestChannel  
  
1. Compilar un generador de canales (**ChannelFactory\<IRequestChannel\>**). Para ello, debe especificar un enlace (**OracleDBBinding**) y una dirección de punto de conexión. Puede especificar la dirección de enlace y el punto de conexión de forma imperativa en el código o mediante declaración en configuración. Para obtener más información sobre cómo especificar el enlace y dirección de punto de conexión en la configuración, consulte [crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. Establecer el usuario las credenciales de contraseña de nombre para el generador de canales con el **ClientCredentials** propiedad.  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. Abra el generador de canales.  
  
   ```  
   factory.Open();  
   ```  
  
4. Obtener un canal de fábrica y ábralo.  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. Crear un **mensaje** instancia para la operación de destino. Asegúrese de que se ha especificado la acción de mensaje para la operación de destino. En este ejemplo, se pasa el cuerpo del mensaje mediante la creación de un **XmlReader** a través de un archivo. La operación de destino es una operación Select en la tabla EMP/SCOTT.  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. Invocar el **solicitar** método en el canal para enviar el mensaje a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y recibir la respuesta. Si la base de datos de Oracle encuentra una excepción, el adaptador lanza una **TargetSystemException**. (Otras excepciones son posibles para las excepciones que no sean Oracle). Puede obtener una descripción del error de Oracle desde el **InnerException.Message** propiedad de la **TargetSystemException**.  
  
   ```  
   try  
   {  
       Message messageOut = channel.Request(messageIn);  
   }  
   catch (Exception ex)  
   {  
       // handle exception  
   }  
   ```  
  
7. Procesar la respuesta. En este ejemplo, **GetReaderAtBodyContents** se llama en el mensaje de respuesta para obtener el cuerpo del mensaje.  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. Cuando haya terminado procesar el mensaje de respuesta, cierre el lector y el mensaje.  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. Cuando haya terminado utilizando el canal y el generador de canales, cerrarlos. Cierre el generador se cerrará todos los canales que se crearon con él.  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   Siga los mismos pasos para enviar un mensaje con el **IOutputChannel** forma excepto:  
  
-   Crear un **ChannelFactory\<IOutputChannel\>**  en el paso 1.  
  
-   Se llama a la **enviar** método en el canal en el paso 6. `channel.Send(messageIn);`.  
  
-   No hay ningún mensaje de respuesta devuelto para un **IOutputChannel**.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo invocar una operación de selección mediante el uso de un **IRequestChannel** canal. Se puede consumir el mensaje de respuesta seleccione mediante un **XmlReader** y el número de registros devueltos se escribe en la consola.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
using System.Xml;  
using System.IO;  
using System.Runtime.Serialization;  
  
namespace RequestChanneSample  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The Select operation request message  
            const string selectRequestString =  
                "\<Select xmlns=\"http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY\"\>" +  
                    "<COLUMN_NAMES>*</COLUMN_NAMES>" +  
                    "<FILTER>ACCOUNT = 100002</FILTER>" +  
                "</Select>";  
            try  
            {  
                // Create binding -- specify binding properties before you open the factory.  
                OracleDBBinding odbBinding = new OracleDBBinding();  
  
                // Create address.  
                EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
                // Create channel factory from binding and address.  
                ChannelFactory<IRequestChannel> factory =   
                    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
                // Specify credentials   
                factory.Credentials.UserName.UserName = "SCOTT";  
                factory.Credentials.UserName.Password = "TIGER";  
  
                // Open the factory.  
                factory.Open();  
  
                // Get a channel.  
                IRequestChannel channel = factory.CreateChannel();  
  
                // Open the channel.  
                channel.Open();  
  
                // Create the request message from the string  
                StringReader strReader = new StringReader(selectRequestString);  
                XmlReader readerIn = XmlReader.Create(strReader);  
  
                Message requestMessage = Message.CreateMessage(MessageVersion.Default,  
                    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
                    readerIn);  
  
                Send the message and get a respone  
                Message responseMessage = channel.Request(requestMessage);  
  
                // Get an XmlReader from the message  
                XmlReader readerOut = (XmlReader) responseMessage.GetReaderAtBodyContents();  
  
                // Count the number of records returned and write to the console.  
                readerOut.MoveToContent();  
                int numberOfRecordsReturned = 0;  
                while (readerOut.Read())  
                {  
                    if (readerOut.NodeType == XmlNodeType.Element && readerOut.Name == "ACCOUNTACTIVITYRECORDSELECT")  
                        numberOfRecordsReturned++;  
                }  
  
                Console.WriteLine("{0} records returned.", numberOfRecordsReturned);  
  
                // Close the output reader and message  
                readerOut.Close();  
                responseMessage.Close();  
  
                //Close channel  
                channel.Close();  
  
                //Close the factory  
                factory.Close();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)
---
title: Invocar operaciones en el sistema SAP mediante el modelo de canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, supporting BAPI transactions
- WCF channel model, invoking operations on the SAP system
ms.assetid: 80ed85ff-360d-4b7f-a119-cd2a99c21cf4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 408d2ce053a30a4692b6e17a73087b13c648ab2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997341"
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a>Invocar operaciones en el sistema SAP mediante el modelo de canal de WCF
Invocar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el uso de un **IRequestChannel** o **IOutputChannel** forma para enviar mensajes al adaptador de canal. El patrón básico consiste en crear un generador de canales para la forma del canal necesarios mediante el uso de un enlace (**SAPBinding**) y un punto de conexión creado a partir de un URI de conexión. A continuación, cree un **mensaje** instancia que representa un mensaje SOAP que se ajusta al esquema de mensajes para la operación de destino. A continuación, puede enviar este **mensaje** a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el uso de un canal creado desde el generador de canales. Si usas un **IRequestChannel**, recibirá una respuesta. Si hay un problema al ejecutar la operación en el sistema SAP, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce una **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.  
  
 Para obtener información general de cómo enviar las operaciones mediante una **IRequestChannel** en WCF, vea [programación de nivel de canal de cliente](https://msdn.microsoft.com/library/ms788970.aspx).  
  
 Las secciones de este tema proporcionan información para ayudarle a invocar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el modelo de canal WCF.  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a>Compatibilidad con transacciones de BAPI en el modelo del canal de WCF  
 BAPI todos los que se invoca mediante la misma conexión de SAP forman parte de la misma lógica unidad de trabajo (LUW)--o transacción--en el sistema SAP. Cada canal WCF representa una conexión única al sistema SAP. Para admitir transacciones de BAPI mediante WCF channel modelo:  
  
- Asegúrese de que cada BAPI en un LUW (transacción) se envía a través del canal mismo. Esto incluye la confirmación BAPI_TRANSACTION o las operaciones de BAPI_TRANSACTION_ROLLBACK.  
  
- Asegúrese de que cierre cualquier mensaje de respuesta recibido de un BAPI antes de invocar la BAPI siguiente en el canal. (Debe hacerlo para cada operación; pero es especialmente importante para BAPI).  
  
  Para obtener más información acerca de las transacciones de BAPI, consulte [operaciones en BAPI de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a>Transmisión por secuencias los IDOC de archivo sin formato para el adaptador de SAP  
 Utilice la operación SendIdoc para enviar un IDOC (cadena) para el adaptador de archivo sin formato. Los datos IDOC se representan como una cadena en un solo nodo en esta operación. Por este motivo, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con el valor del nodo en el mensaje de solicitud de transmisión por secuencias. Para realizar el streaming de valor de nodo, debe crear el mensaje de solicitud para la operación SendIdoc mediante un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir los datos de IDOC. Para obtener información acerca de cómo hacerlo, consulte [Streaming de IDOC de archivo plano en SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>¿Cómo se puede invocar una operación mediante el uso de un canal?  
 Para invocar una operación mediante una **IRequestChannel**, realice los pasos siguientes.  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>Cómo invocar una operación mediante el uso de una instancia de IRequestChannel  
  
1. Compilar un generador de canales (**ChannelFactory\<IRequestChannel\>**). Para ello, debe especificar un enlace (**SAPBinding**) y una dirección de punto de conexión. Puede especificar la dirección de enlace y el punto de conexión de forma imperativa en el código o mediante declaración en configuración. Debe establecer cualquier enlace de las propiedades necesarias para las operaciones que enviará antes de abrir el generador. Para obtener más información sobre cómo especificar el enlace y dirección de punto de conexión en la configuración, consulte [crean un canal mediante SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).  
  
   ```  
   // Create a binding  
   SAPBinding binding = new SAPBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. Establecer el usuario las credenciales de contraseña de nombre para el generador de canales con el **ClientCredentials** propiedad.  
  
   ```  
   factory.Credentials.UserName.UserName = "YourUserName";  
   factory.Credentials.UserName.Password = "YourPassword";  
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
  
5. Crear un **mensaje** instancia para la operación de destino. Asegúrese de que se ha especificado la acción de mensaje para la operación de destino. En este ejemplo, se pasa el cuerpo del mensaje mediante la creación de un **XmlReader** a través de una cadena. La operación de destino, invoca la RFC SD_RFC_CUSTOMER_GET en un sistema SAP.  
  
   ```  
   string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
   //create an XML reader from the input XML  
   XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
   //create a WCF message from our XML reader  
   Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
   ```  
  
6. Invocar el **solicitar** método en el canal para enviar el mensaje a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y recibir la respuesta. Si el sistema SAP encuentra una excepción, el adaptador lanza una **TargetSystemException**. (Otras excepciones son posibles para las excepciones que no son SAP). Puede obtener una descripción del error SAP desde el **InnerException.Message** propiedad de la **TargetSystemException**.  
  
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
  
10. 
  
    Siga los mismos pasos para enviar un mensaje con el **IOutputChannel** forma excepto:  
  
-   Crear un **ChannelFactory\<IOutputChannel\>**  en el paso 1.  
  
-   Se llama a la **enviar** método en el canal en el paso 6. `channel.Send(messageIn);`.  
  
-   No hay ningún mensaje de respuesta devuelto para un **IOutputChannel**.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo invocar una RFC mediante el uso de un **IRequestChannel** canal. En este ejemplo se invoca la RFC SD_RFC_CUSTOMER_GET para obtener una lista de los clientes cuyos nombres empiezan por "AB". Se puede consumir el mensaje de respuesta mediante un **XmlReader** y el número de cliente y el nombre de cada cliente devuelto se escribe en la consola.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel.Channels;  
  
namespace SapRfcClientCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //set up an endpoint address.  
            EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
            //create a channel factory, capable of sending a request to SAP and receiving a reply (IRequestChannel)  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress);  
  
            // add credentials  
            factory.Credentials.UserName.UserName = "YourUserName";  
            factory.Credentials.UserName.Password = "YourPassword";  
  
            //open the factory  
            factory.Open();  
  
            //obtain a channel from the factory by specifying the address you want to connect to  
            IRequestChannel channel = factory.CreateChannel();  
  
            //open the channel  
            channel.Open();  
  
            //create an XML message to send to the SAP system  
            //We are invoking the SD_RFC_CUSTOMER_GET RFC.  
            //The XML below specifies that we want to search for customers with names starting with "AB"  
            string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
            //create an XML reader from the input XML  
            XmlReader readerOut = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
            //create a WCF message from the XML reader  
            Message messageOut = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", readerOut);  
  
            //send the message to SAP and obtain a reply  
            Message messageIn = channel.Request(messageOut);  
  
            // Write the KUNNR and NAME1 fields for each returned record to the Console  
            Console.WriteLine("Results of SD_RFC_CUSTOMER_GET");  
            Console.WriteLine("KUNNR\t\tNAME1");  
  
            XmlReader readerIn = messageIn.GetReaderAtBodyContents();  
  
            while (readerIn.Read())  
            {  
                if (readerIn.IsStartElement())  
                {  
                    switch (readerIn.Name)  
                    {  
                        case "RFCCUST":  
                            Console.Write("\n");  
                            break;  
  
                        case "KUNNR":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        case "NAME1":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        default:  
                            break;  
                    }  
                }  
            }  
  
            // return the cursor  
            Console.WriteLine();  
  
            // Close the input reader  
            readerIn.Close();  
  
            // Close the input message. You should do this for every message you   
            // send on the channel  
            messageIn.Close();  
  
            // close the channel when you are done using it.  
            channel.Close();  
  
            //close the factory  
            //note: closing the factory will close all of its channels.  
            factory.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)
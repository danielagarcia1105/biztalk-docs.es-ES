---
title: Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, supporting BAPI transactions
- WCF channel model, invoking operations on the SAP system
ms.assetid: 80ed85ff-360d-4b7f-a119-cd2a99c21cf4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8cd252c9aa5557ea3845e7b6665dc749486f01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="e1817-102">Invocar operaciones en el sistema SAP mediante el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e1817-102">Invoke Operations on the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="e1817-103">Invocar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el uso de un **IRequestChannel** o **IOutputChannel** forma para enviar mensajes al adaptador de canal.</span><span class="sxs-lookup"><span data-stu-id="e1817-103">You invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** channel shape to send messages to the adapter.</span></span> <span data-ttu-id="e1817-104">El patrón básico consiste en crear un generador de canales para la forma de canales necesarias utilizando un enlace (**SAPBinding**) y un punto de conexión creado a partir de un URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="e1817-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**SAPBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="e1817-105">A continuación, cree un **mensaje** instancia que representa un mensaje SOAP que se ajusta al esquema de mensajes para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="e1817-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="e1817-106">A continuación, puede enviar este **mensaje** a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el uso de un canal que se crea desde el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="e1817-106">You can then send this **Message** to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="e1817-107">Si usas un **IRequestChannel**, recibirá una respuesta.</span><span class="sxs-lookup"><span data-stu-id="e1817-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="e1817-108">Si hay un problema al ejecutar la operación en el sistema SAP, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce una **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="e1817-108">If there is a problem executing the operation on the SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="e1817-109">Para obtener información general de cómo enviar operaciones mediante una **IRequestChannel** en WCF, vea [programación de nivel de canal de cliente](https://msdn.microsoft.com/library/ms788970.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1817-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see [Client Channel-Level Programming](https://msdn.microsoft.com/library/ms788970.aspx).</span></span>  
  
 <span data-ttu-id="e1817-110">Las secciones de este tema proporcionan información para ayudarle a invocar las operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="e1817-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a><span data-ttu-id="e1817-111">Admitir transacciones de BAPI en el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e1817-111">Supporting BAPI Transactions in the WCF Channel Model</span></span>  
 <span data-ttu-id="e1817-112">BAPI todos los que se invoca utilizando la misma conexión de SAP forman parte de la misma lógica unidad de trabajo (LUW) o transacción--en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="e1817-112">All BAPIs that are invoked using the same SAP connection are part of the same Logical Unit of Work (LUW) -- or transaction -- on the SAP system.</span></span> <span data-ttu-id="e1817-113">Cada canal WCF representa una conexión única al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="e1817-113">Each WCF channel represents a unique connection to the SAP system.</span></span> <span data-ttu-id="e1817-114">Para admitir las transacciones de BAPI mediante WCF canal modelo:</span><span class="sxs-lookup"><span data-stu-id="e1817-114">To support BAPI transactions using the WCF channel model:</span></span>  
  
-   <span data-ttu-id="e1817-115">Asegúrese de que cada BAPI en un LUW (transacción) se envía a través del mismo canal.</span><span class="sxs-lookup"><span data-stu-id="e1817-115">Ensure that every BAPI in an LUW (transaction) is sent over the same channel.</span></span> <span data-ttu-id="e1817-116">Esto incluye la confirmación de BAPI_TRANSACTION o las operaciones de BAPI_TRANSACTION_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="e1817-116">This includes the BAPI_TRANSACTION COMMIT or the BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
-   <span data-ttu-id="e1817-117">Asegúrese de que se cierra cualquier mensaje de respuesta recibido de un BAPI antes de invocar la BAPI siguiente en el canal.</span><span class="sxs-lookup"><span data-stu-id="e1817-117">Ensure that you close any response message received for a BAPI before you invoke the next BAPI on the channel.</span></span> <span data-ttu-id="e1817-118">(Debe hacerlo para cada operación; pero es especialmente importante para BAPI).</span><span class="sxs-lookup"><span data-stu-id="e1817-118">(You should do this for every operation; but it is especially important for BAPIs.)</span></span>  
  
 <span data-ttu-id="e1817-119">Para obtener más información acerca de las transacciones de BAPI, consulte [operaciones de BAPI en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="e1817-119">For more information about BAPI transactions, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a><span data-ttu-id="e1817-120">Transmisión por secuencias IDOC de archivo sin formato para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="e1817-120">Streaming Flat File IDOCs to the SAP Adapter</span></span>  
 <span data-ttu-id="e1817-121">Utilice la operación de SendIdoc para enviar un IDOC (cadena) para el adaptador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="e1817-121">You use the SendIdoc operation to send a flat file (string) IDOC to the adapter.</span></span> <span data-ttu-id="e1817-122">Los datos IDOC se representan como una cadena en un único nodo en esta operación.</span><span class="sxs-lookup"><span data-stu-id="e1817-122">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="e1817-123">Por este motivo, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con transmisión por secuencias en el mensaje de solicitud en el valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="e1817-123">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="e1817-124">Para realizar la transmisión por secuencias de valor de nodo, debe crear el mensaje de solicitud para la operación de SendIdoc mediante un **System.ServiceModel.Channels.BodyWriter** que es capaz de transmitir por secuencias los datos IDOC.</span><span class="sxs-lookup"><span data-stu-id="e1817-124">To perform node-value streaming, you must create the request message for the SendIdoc operation by using a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="e1817-125">Para obtener información acerca de cómo hacerlo, consulte [IDOC de archivo plano de transmisión por secuencias en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="e1817-125">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="e1817-126">¿Cómo se puede invocar una operación mediante un canal?</span><span class="sxs-lookup"><span data-stu-id="e1817-126">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="e1817-127">Para invocar una operación mediante una **IRequestChannel**, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e1817-127">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="e1817-128">Cómo invocar una operación mediante una instancia de IRequestChannel</span><span class="sxs-lookup"><span data-stu-id="e1817-128">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1.  <span data-ttu-id="e1817-129">Crear un generador de canales (**ChannelFactory\<IRequestChannel >**).</span><span class="sxs-lookup"><span data-stu-id="e1817-129">Build a channel factory (**ChannelFactory\<IRequestChannel>**).</span></span> <span data-ttu-id="e1817-130">Para ello, debe especificar un enlace (**SAPBinding**) y una dirección de extremo.</span><span class="sxs-lookup"><span data-stu-id="e1817-130">To do this, you must specify a binding (**SAPBinding**) and an endpoint address.</span></span> <span data-ttu-id="e1817-131">Puede especificar la dirección de enlace y el punto de conexión de forma imperativa en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="e1817-131">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="e1817-132">Debe establecer cualquier enlace propiedades necesarios para las operaciones que enviará antes de abrir el generador.</span><span class="sxs-lookup"><span data-stu-id="e1817-132">You should set any binding properties required for the operations that you will send before you open the factory.</span></span> <span data-ttu-id="e1817-133">Para obtener más información sobre cómo especificar el enlace y la dirección del extremo en la configuración, consulte [crear un canal con SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).</span><span class="sxs-lookup"><span data-stu-id="e1817-133">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).</span></span>  
  
    ```  
    // Create a binding  
    SAPBinding binding = new SAPBinding();  
    // Create an endpoint address by using the connection URI  
    EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
    // Create the channel factory  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    ```  
  
2.  <span data-ttu-id="e1817-134">Establecer el usuario las credenciales de contraseña de nombre para el generador de canales con el **ClientCredentials** propiedad.</span><span class="sxs-lookup"><span data-stu-id="e1817-134">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
    ```  
    factory.Credentials.UserName.UserName = "YourUserName";  
    factory.Credentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="e1817-135">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="e1817-135">Open the channel factory.</span></span>  
  
    ```  
    factory.Open();  
    ```  
  
4.  <span data-ttu-id="e1817-136">Obtener un canal de fábrica y ábralo.</span><span class="sxs-lookup"><span data-stu-id="e1817-136">Get a channel from the factory and open it.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="e1817-137">Crear un **mensaje** instancia para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="e1817-137">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="e1817-138">Asegúrese de que se ha especificado la acción de mensaje para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="e1817-138">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="e1817-139">En este ejemplo, el cuerpo del mensaje se pasa mediante la creación de un **XmlReader** a través de una cadena.</span><span class="sxs-lookup"><span data-stu-id="e1817-139">In this example, the message body is passed by creating an **XmlReader** over a string.</span></span> <span data-ttu-id="e1817-140">La operación de destino, invoca la RFC SD_RFC_CUSTOMER_GET en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="e1817-140">The target operation invokes the SD_RFC_CUSTOMER_GET RFC on an SAP system.</span></span>  
  
    ```  
    string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> \<KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
    //create an XML reader from the input XML  
    XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
    //create a WCF message from our XML reader  
    Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
    ```  
  
6.  <span data-ttu-id="e1817-141">Invocar la **solicitar** método en el canal que se va a enviar el mensaje a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e1817-141">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="e1817-142">Si el sistema SAP encuentra una excepción, el adaptador lanza una **TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="e1817-142">If the SAP system encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="e1817-143">(Otras excepciones son posibles para las excepciones de SAP no). Puede obtener una descripción del error SAP desde el **InnerException.Message** propiedad de la **TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="e1817-143">(Other exceptions are possible for non SAP exceptions.) You can get a description of the SAP error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
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
  
7.  <span data-ttu-id="e1817-144">Procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e1817-144">Process the response.</span></span> <span data-ttu-id="e1817-145">En este ejemplo, **GetReaderAtBodyContents** se llama en el mensaje de respuesta para obtener el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e1817-145">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    ```  
  
8.  <span data-ttu-id="e1817-146">Cuando haya terminado procesando el mensaje de respuesta, cierre el lector y el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e1817-146">When you are done processing the response message, close the reader and the message.</span></span>  
  
    ```  
    readerOut.Close();  
    messageOut.Close();  
    ```  
  
9. <span data-ttu-id="e1817-147">Cuando haya terminado utilizando el canal y el generador de canales, ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="e1817-147">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="e1817-148">Cierre el generador se cerrará todos los canales que se crearon con él.</span><span class="sxs-lookup"><span data-stu-id="e1817-148">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
    ```  
  
10.  
  
 <span data-ttu-id="e1817-149">Siga los mismos pasos para enviar un mensaje mediante la **IOutputChannel** forma excepto:</span><span class="sxs-lookup"><span data-stu-id="e1817-149">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="e1817-150">Crear un **ChannelFactory\<IOutputChannel >** en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="e1817-150">You create a **ChannelFactory\<IOutputChannel>** in step 1.</span></span>  
  
-   <span data-ttu-id="e1817-151">Se llama a la **enviar** método en el canal en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="e1817-151">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="e1817-152">`channel.Send(messageIn);`.</span><span class="sxs-lookup"><span data-stu-id="e1817-152">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="e1817-153">No hay ningún mensaje de respuesta devuelto para un **IOutputChannel**.</span><span class="sxs-lookup"><span data-stu-id="e1817-153">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e1817-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1817-154">Example</span></span>  
 <span data-ttu-id="e1817-155">En el ejemplo siguiente se muestra cómo invocar una solicitud de cambio mediante el uso de un **IRequestChannel** canal.</span><span class="sxs-lookup"><span data-stu-id="e1817-155">The following example shows how to invoke an RFC by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="e1817-156">En este ejemplo, se invoca la RFC SD_RFC_CUSTOMER_GET para obtener una lista de clientes cuyos nombres empiezan por "AB".</span><span class="sxs-lookup"><span data-stu-id="e1817-156">This example invokes the SD_RFC_CUSTOMER_GET RFC to get a list of customers whose names start with "AB".</span></span> <span data-ttu-id="e1817-157">Se consume el mensaje de respuesta mediante el uso de un **XmlReader** y el número de cliente y el nombre de cada cliente devuelto se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="e1817-157">The response message is consumed by using an **XmlReader** and the customer number and name of each customer returned is written to the console.</span></span>  
  
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
            string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> \<KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1817-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1817-158">See Also</span></span>  
[<span data-ttu-id="e1817-159">Desarrollar aplicaciones mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="e1817-159">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)
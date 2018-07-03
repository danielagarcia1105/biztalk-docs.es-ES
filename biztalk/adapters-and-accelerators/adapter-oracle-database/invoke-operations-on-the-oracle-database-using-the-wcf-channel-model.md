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
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="8ea85-102">Invocar operaciones en la base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="8ea85-102">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>
<span data-ttu-id="8ea85-103">Puede invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el uso de un **IRequestChannel** o **IOutputChannel** forma para enviar mensajes al adaptador.</span><span class="sxs-lookup"><span data-stu-id="8ea85-103">You can invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** shape to send messages to the adapter.</span></span> <span data-ttu-id="8ea85-104">El patrón básico consiste en crear un generador de canales para la forma del canal necesarios mediante el uso de un enlace (**OracleDBBinding**) y un punto de conexión creado a partir de un URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ea85-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**OracleDBBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="8ea85-105">A continuación, cree un **mensaje** instancia que representa un mensaje SOAP que se ajusta al esquema de mensajes para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="8ea85-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="8ea85-106">A continuación, puede enviar este **mensaje** a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el uso de un canal creado desde el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="8ea85-106">You can then send this **Message** to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="8ea85-107">Si usas un **IRequestChannel**, recibirá una respuesta.</span><span class="sxs-lookup"><span data-stu-id="8ea85-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="8ea85-108">Si hay un problema al ejecutar la operación en la base de datos de Oracle, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-108">If there is a problem executing the operation on the Oracle database, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="8ea85-109">Para obtener información general de cómo enviar las operaciones mediante una **IRequestChannel** en WCF, vea "Programación de nivel de canal de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=106081 ](http://go.microsoft.com/fwlink/?LinkId=106081).</span><span class="sxs-lookup"><span data-stu-id="8ea85-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see "Client Channel-Level Programming" at [http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081).</span></span>  
  
 <span data-ttu-id="8ea85-110">Las secciones de este tema proporcionan información para ayudarle a invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="8ea85-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a><span data-ttu-id="8ea85-111">Creación y consumo de mensajes para las operaciones de salida</span><span class="sxs-lookup"><span data-stu-id="8ea85-111">Creating and Consuming Messages for Outbound Operations</span></span>  
 <span data-ttu-id="8ea85-112">Para invocar una operación en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], enviar el mensaje de solicitud para la operación de destino mediante un **IRequestChannel** o un **IOutputChannel**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-112">To invoke an operation on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you send the request message for the target operation using either an **IRequestChannel** or an **IOutputChannel**.</span></span> <span data-ttu-id="8ea85-113">Si usa un **IRequestChannel** el adaptador devuelve los resultados de la operación en el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8ea85-113">If you use an **IRequestChannel** the adapter returns the results of the operation in the response message.</span></span>  
  
 <span data-ttu-id="8ea85-114">Para obtener más información acerca de la solicitud y esquemas de mensaje de respuesta y las acciones de mensaje para cada operación, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-114">For more detailed information about the request and response message schemas and the message actions for each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="8ea85-115">Cómo crear el mensaje de solicitud y consumir el mensaje de respuesta determina si el valor del nodo de transmisión por secuencias o transmisión por secuencias de nodo se realiza por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="8ea85-115">How you create the request message and consume the response message determines whether node streaming or node-value streaming is performed by the adapter.</span></span> <span data-ttu-id="8ea85-116">A su vez, esto determina si se realiza la transmisión por secuencias to-end de los datos LOB para las operaciones admitidas.</span><span class="sxs-lookup"><span data-stu-id="8ea85-116">This in turn determines whether end-to-end streaming of LOB data is performed for supported operations.</span></span>  
  
### <a name="creating-the-request-message"></a><span data-ttu-id="8ea85-117">Crear el mensaje de solicitud</span><span class="sxs-lookup"><span data-stu-id="8ea85-117">Creating the request message</span></span>  
 <span data-ttu-id="8ea85-118">Puede crear el mensaje de solicitud de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="8ea85-118">You can create the request message in one of two ways:</span></span>  
  
- <span data-ttu-id="8ea85-119">Para crear un mensaje que se puede usar para el valor del nodo de transmisión por secuencias debe pasar el cuerpo del mensaje en un **XmlBodyWriter** que implementa el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="8ea85-119">To create a message that can be used for node-value streaming you must pass the message body in an **XmlBodyWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="8ea85-120">Para crear un mensaje que se puede usar para el nodo de streaming puede pasar el cuerpo del mensaje en un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-120">To create a message that can be used for node streaming you can pass the message body in an **XmlReader**.</span></span>  
  
  <span data-ttu-id="8ea85-121">Normalmente se utiliza para permitir el vertido to-end de datos LOB de Oracle en el mensaje de solicitud de transmisión por secuencias en el valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="8ea85-121">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the request message.</span></span> <span data-ttu-id="8ea85-122">La única operación que admita esta característica es UpdateLOB.</span><span class="sxs-lookup"><span data-stu-id="8ea85-122">The only operation that supports this feature is UpdateLOB.</span></span>  
  
### <a name="consuming-the-response-message"></a><span data-ttu-id="8ea85-123">Consume el mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="8ea85-123">Consuming the response message</span></span>  
 <span data-ttu-id="8ea85-124">Puede consumir el mensaje de respuesta en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="8ea85-124">You can consume the response message in one of two ways:</span></span>  
  
- <span data-ttu-id="8ea85-125">Para consumir el mensaje mediante el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y pasarle un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="8ea85-125">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="8ea85-126">Para consumir el mensaje mediante el flujo de nodo se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-126">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
  <span data-ttu-id="8ea85-127">Normalmente se utiliza para permitir el vertido to-end de datos LOB de Oracle en el mensaje de respuesta de transmisión por secuencias en el valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="8ea85-127">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the response message.</span></span> <span data-ttu-id="8ea85-128">Hay muchas operaciones que admitan esta característica.</span><span class="sxs-lookup"><span data-stu-id="8ea85-128">There are many operations that support this feature.</span></span>  
  
### <a name="lob-data-and-message-streaming-support"></a><span data-ttu-id="8ea85-129">Compatibilidad con Streaming de mensaje y los datos LOB</span><span class="sxs-lookup"><span data-stu-id="8ea85-129">LOB Data and Message Streaming Support</span></span>  
 <span data-ttu-id="8ea85-130">Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-130">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="8ea85-131">Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir streaming to-end de los datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-131">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a><span data-ttu-id="8ea85-132">Compatibilidad con transacciones en las operaciones de salida en el modelo del canal de WCF.</span><span class="sxs-lookup"><span data-stu-id="8ea85-132">Transaction Support on Outbound Operations in the WCF Channel Model.</span></span>  
 <span data-ttu-id="8ea85-133">El adaptador ejecuta cada operación que se invoca dentro de una transacción dedicada en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8ea85-133">The adapter executes each operation you invoke inside a dedicated transaction on the Oracle database.</span></span> <span data-ttu-id="8ea85-134">Puede controlar el nivel de aislamiento de estas transacciones estableciendo la **TransactionIsolationLevel** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea85-134">You can control the isolation level of these transactions by setting the **TransactionIsolationLevel** binding property.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="8ea85-135">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="8ea85-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="8ea85-136">El ejemplo de este tema usa al SCOTT. Tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="8ea85-136">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="8ea85-137">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="8ea85-137">A script to generate these artifacts is supplied with the SDK samples.</span></span> <span data-ttu-id="8ea85-138">Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="8ea85-139">¿Cómo se puede invocar una operación mediante el uso de un canal?</span><span class="sxs-lookup"><span data-stu-id="8ea85-139">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="8ea85-140">Para invocar una operación mediante una **IRequestChannel**, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8ea85-140">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="8ea85-141">Cómo invocar una operación mediante el uso de una instancia de IRequestChannel</span><span class="sxs-lookup"><span data-stu-id="8ea85-141">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1. <span data-ttu-id="8ea85-142">Compilar un generador de canales (**ChannelFactory\<IRequestChannel\>**).</span><span class="sxs-lookup"><span data-stu-id="8ea85-142">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="8ea85-143">Para ello, debe especificar un enlace (**OracleDBBinding**) y una dirección de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ea85-143">To do this, you must specify a binding (**OracleDBBinding**) and an endpoint address.</span></span> <span data-ttu-id="8ea85-144">Puede especificar la dirección de enlace y el punto de conexión de forma imperativa en el código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="8ea85-144">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="8ea85-145">Para obtener más información sobre cómo especificar el enlace y dirección de punto de conexión en la configuración, consulte [crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="8ea85-145">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span></span>  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. <span data-ttu-id="8ea85-146">Establecer el usuario las credenciales de contraseña de nombre para el generador de canales con el **ClientCredentials** propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea85-146">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. <span data-ttu-id="8ea85-147">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="8ea85-147">Open the channel factory.</span></span>  
  
   ```  
   factory.Open();  
   ```  
  
4. <span data-ttu-id="8ea85-148">Obtener un canal de fábrica y ábralo.</span><span class="sxs-lookup"><span data-stu-id="8ea85-148">Get a channel from the factory and open it.</span></span>  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. <span data-ttu-id="8ea85-149">Crear un **mensaje** instancia para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="8ea85-149">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="8ea85-150">Asegúrese de que se ha especificado la acción de mensaje para la operación de destino.</span><span class="sxs-lookup"><span data-stu-id="8ea85-150">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="8ea85-151">En este ejemplo, se pasa el cuerpo del mensaje mediante la creación de un **XmlReader** a través de un archivo.</span><span class="sxs-lookup"><span data-stu-id="8ea85-151">In this example, the message body is passed by creating an **XmlReader** over a file.</span></span> <span data-ttu-id="8ea85-152">La operación de destino es una operación Select en la tabla EMP/SCOTT.</span><span class="sxs-lookup"><span data-stu-id="8ea85-152">The target operation is a Select operation on the SCOTT/EMP table.</span></span>  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. <span data-ttu-id="8ea85-153">Invocar el **solicitar** método en el canal para enviar el mensaje a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8ea85-153">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="8ea85-154">Si la base de datos de Oracle encuentra una excepción, el adaptador lanza una **TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-154">If the Oracle database encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="8ea85-155">(Otras excepciones son posibles para las excepciones que no sean Oracle). Puede obtener una descripción del error de Oracle desde el **InnerException.Message** propiedad de la **TargetSystemException**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-155">(Other exceptions are possible for non Oracle exceptions.) You can get a description of the Oracle error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
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
  
7. <span data-ttu-id="8ea85-156">Procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8ea85-156">Process the response.</span></span> <span data-ttu-id="8ea85-157">En este ejemplo, **GetReaderAtBodyContents** se llama en el mensaje de respuesta para obtener el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8ea85-157">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. <span data-ttu-id="8ea85-158">Cuando haya terminado procesar el mensaje de respuesta, cierre el lector y el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8ea85-158">When you are done processing the response message, close the reader and the message.</span></span>  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. <span data-ttu-id="8ea85-159">Cuando haya terminado utilizando el canal y el generador de canales, cerrarlos.</span><span class="sxs-lookup"><span data-stu-id="8ea85-159">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="8ea85-160">Cierre el generador se cerrará todos los canales que se crearon con él.</span><span class="sxs-lookup"><span data-stu-id="8ea85-160">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   <span data-ttu-id="8ea85-161">Siga los mismos pasos para enviar un mensaje con el **IOutputChannel** forma excepto:</span><span class="sxs-lookup"><span data-stu-id="8ea85-161">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="8ea85-162">Crear un **ChannelFactory\<IOutputChannel\>**  en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8ea85-162">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="8ea85-163">Se llama a la **enviar** método en el canal en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="8ea85-163">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="8ea85-164">`channel.Send(messageIn);`.</span><span class="sxs-lookup"><span data-stu-id="8ea85-164">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="8ea85-165">No hay ningún mensaje de respuesta devuelto para un **IOutputChannel**.</span><span class="sxs-lookup"><span data-stu-id="8ea85-165">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8ea85-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ea85-166">Example</span></span>  
 <span data-ttu-id="8ea85-167">El ejemplo siguiente muestra cómo invocar una operación de selección mediante el uso de un **IRequestChannel** canal.</span><span class="sxs-lookup"><span data-stu-id="8ea85-167">The following example shows how to invoke a Select operation by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="8ea85-168">Se puede consumir el mensaje de respuesta seleccione mediante un **XmlReader** y el número de registros devueltos se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="8ea85-168">The Select response message is consumed by using an **XmlReader** and the number of records returned is written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ea85-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ea85-169">See Also</span></span>  
 [<span data-ttu-id="8ea85-170">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="8ea85-170">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)
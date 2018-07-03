---
title: Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal WCF | Microsoft Docs
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
ms.openlocfilehash: 03973baf5c55d4f6b5caa3ef28ce0e11b0cd4fa1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969677"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="7f3e6-102">Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="7f3e6-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="7f3e6-103">Puede configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para sondear una tabla de base de datos de Oracle o la vista para que cambie algún dato.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to poll an Oracle database table or view for any data changes.</span></span> <span data-ttu-id="7f3e6-104">Para llevar a cabo una operación de sondeo de este tipo, el adaptador ejecuta periódicamente una consulta SQL en una tabla de Oracle o la vista seguido de un bloque de código PL/SQL opcional.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-104">To perform such a polling operation, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="7f3e6-105">A continuación, se devuelven los resultados de la consulta SQL por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] al código como un conjunto en una operación POLLINGSTMT entrante fuertemente tipada de resultados.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your code as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="7f3e6-106">Para obtener más información sobre el mecanismo utilizado para configurar y realizar el sondeo de Oracle database mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="7f3e6-107">Se recomienda encarecidamente que lea este tema antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-107">It is strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="7f3e6-108">Configurar la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] sondeo y tabla de base de datos de Oracle o estableciendo las propiedades de enlace en una instancia de la vista **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-108">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll and Oracle database table or view by setting binding properties on an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="7f3e6-109">En el modelo de canal WCF, a continuación, usan este enlace para compilar un agente de escucha del canal desde el que puede obtener un **IInputChannel** canal para recibir la operación POLLINGSTMT desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-109">In the WCF channel model, you then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the POLLINGSTMT operation from the adapter.</span></span>  
  
 <span data-ttu-id="7f3e6-110">Para obtener información general de cómo recibir operaciones mediante una **IInputChannel** en WCF, vea [a nivel de canal de servicio de programación](https://msdn.microsoft.com/library/ms789029.aspx).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-110">For an overview of how to receive operations using an **IInputChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span> 
  
 <span data-ttu-id="7f3e6-111">Las secciones de este tema proporcionan información para ayudarle a realizar el sondeo en las tablas de base de datos de Oracle y vistas que usan WCF modelo del canal.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-111">The sections in this topic provide information to help you perform polling on Oracle database tables and views using the WCF channel model.</span></span>  
  
## <a name="consuming-the-pollingstmt-request-message"></a><span data-ttu-id="7f3e6-112">Consume el mensaje de solicitud POLLINGSTMT</span><span class="sxs-lookup"><span data-stu-id="7f3e6-112">Consuming the POLLINGSTMT request message</span></span>  
 <span data-ttu-id="7f3e6-113">El adaptador invoca la operación de POLLINGSTMT en el código para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-113">The adapter invokes the POLLINGSTMT operation on your code to poll the Oracle database.</span></span> <span data-ttu-id="7f3e6-114">Es decir, el adaptador envía un mensaje de solicitud POLLINGSTMT que recibe a través de un **IInputChannel** forma de canal.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-114">That is, the adapter sends a POLLINGSTMT request message that you receive over an **IInputChannel** channel shape.</span></span> <span data-ttu-id="7f3e6-115">El mensaje de solicitud POLLINGSTMT contiene el conjunto de resultados de la consulta especificada por el **PollingStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-115">The POLLINGSTMT request message contains the result set of the query specified by the **PollingStatement** binding property.</span></span> <span data-ttu-id="7f3e6-116">Puede consumir el mensaje POLLINGSTMT en uno de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="7f3e6-116">You can consume the POLLINGSTMT message in one of two ways:</span></span>  
  
- <span data-ttu-id="7f3e6-117">Para consumir el mensaje mediante el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y pasarle un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-117">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="7f3e6-118">Para consumir el mensaje mediante el flujo de nodo se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-118">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
  <span data-ttu-id="7f3e6-119">Se suele usa para consumir conjuntos de resultados que contienen columnas de datos de LOB de Oracle de transmisión por secuencias en el valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-119">You typically use node-value streaming to consume result sets that contain Oracle LOB data columns.</span></span>  
  
  <span data-ttu-id="7f3e6-120">Para obtener más información acerca de la estructura del mensaje de la operación POLLINGSTMT, consulte [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-120">For more information about the message structure of the POLLINGSTMT operation, see [Message Schemas for the Polling Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).</span></span>  
  
  <span data-ttu-id="7f3e6-121">Para obtener más información acerca de cómo los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite la transmisión por secuencias en datos LOB, consulte [hacer Streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-121">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
  <span data-ttu-id="7f3e6-122">Para obtener más información acerca de cómo implementar el valor del nodo en el código para admitir streaming to-end de los datos LOB de transmisión por secuencias, vea [Streaming Oracle base de datos LOB datos tipos con el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-122">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="7f3e6-123">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-123">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="7f3e6-124">El ejemplo de este tema usa al SCOTT. Tabla ACCOUNTACTIVITY y el SCOTT. ACCOUNT_PKG. Función PROCESS_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-124">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table and the SCOTT.ACCOUNT_PKG.PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="7f3e6-125">Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-125">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="7f3e6-126">El ejemplo realiza las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="7f3e6-126">The example performs the following operations:</span></span>  
  
- <span data-ttu-id="7f3e6-127">Como parte de la instrucción de sondeo, selecciona todos los registros de la tabla ACCOUNTACTIVITY y muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-127">As part of the polling statement, selects all the records from the ACCOUNTACTIVITY table and displays on the console.</span></span>  
  
- <span data-ttu-id="7f3e6-128">Como parte de la instrucción de sondeo de envío, en el ejemplo se invoca la función PROCESS_ACTIVITY que mueve todos los registros de la tabla ACCOUNTACTIVITY a tabla ACTIVITYHISTORY.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-128">As part of the post poll statement, the example invokes the PROCESS_ACTIVITY function that moves all the records from ACCOUNTACTIVITY table to ACTIVITYHISTORY table.</span></span>  
  
- <span data-ttu-id="7f3e6-129">Los sondeos subsiguientes en la tabla ACCOUNTACTIVITY no devuelven ningún registro.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-129">Subsequent polls on the ACCOUNTACTIVITY table do not return any records.</span></span> <span data-ttu-id="7f3e6-130">Sin embargo, si desea que el ejemplo para devolver más registros como parte de la operación de sondeo, debe insertar algunos registros de la tabla ACCOUNTACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-130">However, if you want the example to return more records as part of the polling operation, you must insert some records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f3e6-131">Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-131">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
  <span data-ttu-id="7f3e6-132">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-132">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a><span data-ttu-id="7f3e6-133">¿Cómo se puede sondear una base de datos de Oracle mediante un IInputChannel?</span><span class="sxs-lookup"><span data-stu-id="7f3e6-133">How Do I Poll an Oracle Database Using an IInputChannel?</span></span>  
 <span data-ttu-id="7f3e6-134">Para sondear una tabla de base de datos de Oracle o la vista para recibir mensajes de cambio de datos mediante el modelo de canal WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-134">To poll an Oracle database table or view to receive data-change messages using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a><span data-ttu-id="7f3e6-135">Para recibir mensajes de cambio de datos mediante un IInputChannel</span><span class="sxs-lookup"><span data-stu-id="7f3e6-135">To receive data-changed messages using an IInputChannel</span></span>  
  
1. <span data-ttu-id="7f3e6-136">Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3e6-136">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7f3e6-137">Este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-137">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="7f3e6-138">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleDB`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-138">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleDB`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3. <span data-ttu-id="7f3e6-139">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f3e6-139">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleDB`  
  
   -   `Microsoft.ServiceModel.Channels`  
  
   -   `System.ServiceModel`  
  
   -   `System.ServiceModel.Description`  
  
   -   `System.ServiceModel.Channels`  
  
   -   `System.Xml`  
  
   -   `System.Runtime.Serialization`  
  
   -   `System.IO`  
  
   -   `Microsoft.ServiceModel.Channels.Common`  
  
4. <span data-ttu-id="7f3e6-140">Cree una instancia de **OracleDBBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-140">Create an instance of **OracleDBBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="7f3e6-141">Como mínimo, debe establecer el **InboundOperationType**, **PollingStatement**, y **PollingInterval** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-141">At a minimum you must set the **InboundOperationType**, **PollingStatement**, and **PollingInterval** binding properties.</span></span> <span data-ttu-id="7f3e6-142">En este ejemplo, establezca también la **PostPollStatement** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-142">For this example, you also set the **PostPollStatement** binding property.</span></span> <span data-ttu-id="7f3e6-143">Para obtener más información sobre las propiedades utilizadas para configurar el sondeo de enlace, consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-143">For more information about binding properties used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
   ```  
   OracleDBBinding binding = new OracleDBBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PollingInterval = 30;  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
   ```  
  
5. <span data-ttu-id="7f3e6-144">Crear una colección de parámetros de enlace y establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-144">Create a binding parameter collection and set the credentials.</span></span>  
  
   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "SCOTT";  
   credentials.UserName.Password = "TIGER";  
  
   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  
  
6. <span data-ttu-id="7f3e6-145">Cree una escucha de canales y ábralo.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-145">Create a channel listener and open it.</span></span> <span data-ttu-id="7f3e6-146">Crear el agente de escucha mediante la invocación **BuildChannelListener < IInputChannel\>**  método en el **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-146">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleDBBinding**.</span></span> <span data-ttu-id="7f3e6-147">Puede modificar el espacio de nombres de destino para la operación POLLINGSTMT estableciendo la propiedad PollingId en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-147">You can modify the target namespace for the POLLINGSTMT operation by setting the PollingId property in the connection URI.</span></span> <span data-ttu-id="7f3e6-148">Para obtener más información sobre el URI de conexión del adaptador, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-148">For more information about the adapter connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  
  
7. <span data-ttu-id="7f3e6-149">Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha y ábralo.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-149">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
   ```  
   IInputChannel channel = listener.AcceptChannel();  
   channel.Open();  
   ```  
  
8. <span data-ttu-id="7f3e6-150">Invocar **recepción** en el canal para obtener el siguiente mensaje POLLINGSTMT desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-150">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
   ```  
   Message message = channel.Receive();  
   ```  
  
9. <span data-ttu-id="7f3e6-151">Consumir el conjunto de resultados devuelto por la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-151">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="7f3e6-152">Puede consumir el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-152">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. <span data-ttu-id="7f3e6-153">Cierre el canal cuando haya terminado de procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-153">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f3e6-154">Debe cerrar el canal cuando haya terminado de procesar la operación POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-154">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="7f3e6-155">Error al cerrar el canal puede afectan al comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-155">Failure to close the channel may affect the behavior of your code.</span></span>  
  
11. <span data-ttu-id="7f3e6-156">Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-156">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f3e6-157">Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-157">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="7f3e6-158">Debe cerrar explícitamente cada canal creado mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-158">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="7f3e6-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f3e6-159">Example</span></span>  
 <span data-ttu-id="7f3e6-160">El ejemplo siguiente muestra cómo configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear las vistas y tablas de base de datos de Oracle y recibir la POLLLINGSTMT modelo de canal de operación mediante WCF.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-160">The following example shows how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll Oracle database tables and views and receive the POLLLINGSTMT operation using the WCF channel model.</span></span> <span data-ttu-id="7f3e6-161">El conjunto de resultados devuelto en la operación POLLINGSTMT se escriben en la consola mediante el uso de un **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-161">The result set returned in the POLLINGSTMT operation is written to the console by using an **XmlReader**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f3e6-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f3e6-162">See Also</span></span>  
 [<span data-ttu-id="7f3e6-163">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="7f3e6-163">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)
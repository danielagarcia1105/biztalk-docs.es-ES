---
title: Crear un canal con el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e86398f6-c835-46f8-814f-31e43b18970e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c31146310b8c8b559fcd93d19362679b060cb42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="create-a-channel-using-the-sql-adapter"></a><span data-ttu-id="ac9be-102">Crear un canal con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="ac9be-102">Create a channel using the SQL adapter</span></span>
<span data-ttu-id="ac9be-103">En el modelo de canal WCF, invocar las operaciones en la base de datos de SQL Server y recibir los resultados mediante el intercambio de mensajes SOAP con el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] sobre un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="ac9be-103">In the WCF channel model, you invoke operations on the SQL Server database and receive the results by exchanging SOAP messages with the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="ac9be-104">Invocar operaciones de salida utilizando un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac9be-104">You invoke outbound operations by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="ac9be-105">Recibir mensajes para operaciones de entrada por recibir mensajes a través de un **IInputChannel** para **sondeo**, **TypedPolling**, o **notificación** operaciones.</span><span class="sxs-lookup"><span data-stu-id="ac9be-105">You receive messages for inbound operations by receiving messages over an **IInputChannel** for **Polling**, **TypedPolling**, or **Notification** operations.</span></span>  
  
 <span data-ttu-id="ac9be-106">Los procedimientos descritos en este tema proporcionan información acerca de cómo crear y configurar formas del canal que se utilizan para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="ac9be-106">The procedures in this topic provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="ac9be-107">Crear los canales de salida (cliente)</span><span class="sxs-lookup"><span data-stu-id="ac9be-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="ac9be-108">Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac9be-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SQL Server database.</span></span> <span data-ttu-id="ac9be-109">En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="ac9be-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="ac9be-110">A continuación, utilice el generador para crear el canal.</span><span class="sxs-lookup"><span data-stu-id="ac9be-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="ac9be-111">Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac9be-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="ac9be-112">Para crear y abrir un canal de salida</span><span class="sxs-lookup"><span data-stu-id="ac9be-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="ac9be-113">Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante un punto de conexión y un enlace.</span><span class="sxs-lookup"><span data-stu-id="ac9be-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="ac9be-114">El punto de conexión especifica un URI de conexión de SQL Server y el enlace es una instancia de **sqlBinding**.</span><span class="sxs-lookup"><span data-stu-id="ac9be-114">The endpoint specifies a SQL Server connection URI and the binding is an instance of **sqlBinding**.</span></span>  
  
2.  <span data-ttu-id="ac9be-115">Proporcionar credenciales de SQL Server para el generador de canales mediante la **credenciales** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ac9be-115">Provide SQL Server credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="ac9be-116">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="ac9be-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="ac9be-117">Obtener una instancia del canal invocando la **CreateChannel** método en el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="ac9be-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="ac9be-118">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="ac9be-118">Open the channel.</span></span>  
  
 <span data-ttu-id="ac9be-119">Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.</span><span class="sxs-lookup"><span data-stu-id="ac9be-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="ac9be-120">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="ac9be-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="ac9be-121">En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="ac9be-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="ac9be-122">El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para la **ChannelFactory** y tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="ac9be-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SqlAdapterBinding sdbBinding = new SqlAdapterBinding();  
  
// Create address.  
EndpointAddress sdbAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sdbBinding, sdbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="ac9be-123">Especificar el enlace y la dirección del extremo en la configuración</span><span class="sxs-lookup"><span data-stu-id="ac9be-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="ac9be-124">En el ejemplo de código siguiente se muestra cómo crear un generador de canales de un punto de conexión de cliente especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ac9be-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="ac9be-125">Los valores de configuración</span><span class="sxs-lookup"><span data-stu-id="ac9be-125">The Configuration Settings</span></span>  
 <span data-ttu-id="ac9be-126">El código siguiente muestra los valores de configuración que se usa para el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="ac9be-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="ac9be-127">El contrato para el extremo de cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IOutputChannel" según el tipo de forma del canal que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ac9be-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://mysqlserver//mydatabase?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="creating-inbound-service-channels"></a><span data-ttu-id="ac9be-128">Crear los canales de entrada (servicio)</span><span class="sxs-lookup"><span data-stu-id="ac9be-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="ac9be-129">Configurar la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear las vistas y tablas de base de datos de SQL Server mediante el establecimiento de propiedades de enlace en una instancia de **sqlBinding**.</span><span class="sxs-lookup"><span data-stu-id="ac9be-129">You configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database tables and views by setting binding properties on an instance of **sqlBinding**.</span></span> <span data-ttu-id="ac9be-130">A continuación, utilice este enlace para compilar un agente de escucha de canal desde el que se puede obtener un **IInputChannel** canal para recibir la **sondeo**, **TypedPolling**, o  **Notificación** operación desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac9be-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the **Polling**, **TypedPolling**, or **Notification** operation from the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-iinputchannel-to-receive-inbound-operations"></a><span data-ttu-id="ac9be-131">Para crear y abrir un IInputChannel para recibir operaciones entrantes</span><span class="sxs-lookup"><span data-stu-id="ac9be-131">To create and open an IInputChannel to receive inbound operations</span></span>  
  
1.  <span data-ttu-id="ac9be-132">Cree una instancia de **SQLBinding**.</span><span class="sxs-lookup"><span data-stu-id="ac9be-132">Create an instance of **SQLBinding**.</span></span>  
  
2.  <span data-ttu-id="ac9be-133">Establecer las propiedades de enlace necesarias para la operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="ac9be-133">Set the binding properties required for inbound operation.</span></span> <span data-ttu-id="ac9be-134">Por ejemplo, para un **sondeo** operación, como mínimo, debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, y  **PollingStatement** enlace Propiedades para configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac9be-134">For example, for a **Polling** operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="ac9be-135">Crear un agente de escucha de canal invocando **BuildChannelListener\<IInputChannel\>**  método en el **SQLBinding**.</span><span class="sxs-lookup"><span data-stu-id="ac9be-135">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **SQLBinding**.</span></span> <span data-ttu-id="ac9be-136">Especifique el URI de conexión de SQL Server como uno de los parámetros a este método.</span><span class="sxs-lookup"><span data-stu-id="ac9be-136">You specify the SQL Server connection URI as one of the parameters to this method.</span></span>  
  
4.  <span data-ttu-id="ac9be-137">Abra el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ac9be-137">Open the listener.</span></span>  
  
5.  <span data-ttu-id="ac9be-138">Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ac9be-138">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
6.  <span data-ttu-id="ac9be-139">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="ac9be-139">Open the channel.</span></span>  
  
 <span data-ttu-id="ac9be-140">El código siguiente muestra cómo crear un agente de escucha de canal y obtener un **IInputChannel** para recibir mensajes de cambio de datos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac9be-140">The following code shows how to create a channel listener and get an **IInputChannel** to receive data-changed messages from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac9be-141">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] de recepción unidireccional solo admite.</span><span class="sxs-lookup"><span data-stu-id="ac9be-141">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="ac9be-142">Por lo tanto, debe usar **IInputChannel** para recibir mensajes para operaciones de entrada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac9be-142">So, you must use **IInputChannel** to receive messages for inbound operations from SQL Server.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, and   
// the PollingStatement binding properties.  
SqlAdapterBinding binding = new SqlAdapterBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac9be-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac9be-143">See Also</span></span>  
[<span data-ttu-id="ac9be-144">Desarrollar aplicaciones con el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="ac9be-144">Develop applications using the WCF Channel model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)
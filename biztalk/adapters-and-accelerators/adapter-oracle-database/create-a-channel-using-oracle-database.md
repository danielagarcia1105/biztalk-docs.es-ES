---
title: Crear un canal con la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating a channel
- WCF channel model, creating a channel
- how to, create a channel
- channel programming, creating a channel
ms.assetid: a30156a0-5a5a-4418-be17-2e23c3716fc1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdcfe1ac8feee5b4ffa07d3a276ce86c352fe21
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-oracle-database"></a><span data-ttu-id="90df0-102">Crear un canal con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="90df0-102">Create a channel using Oracle Database</span></span>
<span data-ttu-id="90df0-103">En el modelo de canal WCF, que invocar las operaciones en la base de datos de Oracle y recibir los resultados de una consulta de sondeo mediante el intercambio de mensajes SOAP con el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] sobre un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="90df0-103">In the WCF channel model, you invoke operations on the Oracle database and receive the results of a polling query by exchanging SOAP messages with the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="90df0-104">Invocar operaciones (operaciones de salida) utilizando una **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.</span><span class="sxs-lookup"><span data-stu-id="90df0-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
-   <span data-ttu-id="90df0-105">Recibe mensajes de cambio de datos basado en sondeo mediante la recepción de mensajes POLLINGSTMT sobre un **IInputChannel**.</span><span class="sxs-lookup"><span data-stu-id="90df0-105">You receive polling-based data-changed messages by receiving POLLINGSTMT messages over an **IInputChannel**.</span></span>  
  
 <span data-ttu-id="90df0-106">Los temas de esta sección proporcionan información acerca de cómo crear y configurar formas del canal que se utilizan para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="90df0-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="90df0-107">Crear los canales de salida (cliente)</span><span class="sxs-lookup"><span data-stu-id="90df0-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="90df0-108">Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90df0-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle database.</span></span> <span data-ttu-id="90df0-109">En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="90df0-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="90df0-110">A continuación, utilice el generador para crear el canal.</span><span class="sxs-lookup"><span data-stu-id="90df0-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="90df0-111">Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="90df0-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="90df0-112">Para crear y abrir un canal de salida</span><span class="sxs-lookup"><span data-stu-id="90df0-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="90df0-113">Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante un punto de conexión y un enlace.</span><span class="sxs-lookup"><span data-stu-id="90df0-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="90df0-114">El punto de conexión especifica un URI de conexión de Oracle y el enlace es una instancia de **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90df0-114">The endpoint specifies an Oracle connection URI and the binding is an instance of **OracleDBBinding**.</span></span>  
  
2.  <span data-ttu-id="90df0-115">Proporcionar credenciales de Oracle para el generador de canales mediante la **credenciales** propiedad.</span><span class="sxs-lookup"><span data-stu-id="90df0-115">Provide Oracle credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3.  <span data-ttu-id="90df0-116">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="90df0-116">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="90df0-117">Obtener una instancia del canal invocando la **CreateChannel** método en el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="90df0-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="90df0-118">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="90df0-118">Open the channel.</span></span>  
  
 <span data-ttu-id="90df0-119">Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.</span><span class="sxs-lookup"><span data-stu-id="90df0-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="90df0-120">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="90df0-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="90df0-121">En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="90df0-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="90df0-122">El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para la **ChannelFactory** y tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="90df0-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleDBBinding odbBinding = new OracleDBBinding();  
  
// Create address.  
EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="90df0-123">Especificar el enlace y la dirección del extremo en la configuración</span><span class="sxs-lookup"><span data-stu-id="90df0-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="90df0-124">En el ejemplo de código siguiente se muestra cómo crear un generador de canales de un punto de conexión de cliente especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="90df0-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="90df0-125">Los valores de configuración</span><span class="sxs-lookup"><span data-stu-id="90df0-125">The Configuration Settings</span></span>  
 <span data-ttu-id="90df0-126">El código siguiente muestra los valores de configuración que se usa para el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="90df0-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="90df0-127">El contrato para el extremo de cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IRequestChannel" según el tipo de forma del canal que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="90df0-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IRequestChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" metadataPooling="true"  
                    statementCachePurge="false" statementCacheSize="10" pollingInterval="500"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" polledDataAvailableStatement="SELECT 1 FROM DUAL"  
                    pollWhileDataFound="false" notifyOnListenerStart="true" notificationPort="-1"  
                    inboundOperationType="Polling" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="1" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="false" enablePerformanceCounters="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="90df0-128">Crear los canales de entrada (servicio)</span><span class="sxs-lookup"><span data-stu-id="90df0-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="90df0-129">Configurar la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear las vistas y tablas de base de datos de Oracle estableciendo las propiedades de enlace en una instancia de **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90df0-129">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="90df0-130">A continuación, utilice este enlace para compilar un agente de escucha de canal desde el que se puede obtener un **IInputChannel** canal para recibir mensajes para operaciones de entrada desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="90df0-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive message for inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="90df0-131">Para crear y abrir un IInputChannel para recibir mensajes para operaciones de entrada</span><span class="sxs-lookup"><span data-stu-id="90df0-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1.  <span data-ttu-id="90df0-132">Cree una instancia de **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90df0-132">Create an instance of **OracleDBBinding**.</span></span>  
  
2.  <span data-ttu-id="90df0-133">Establecer las propiedades de enlace necesarias para la operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="90df0-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="90df0-134">Por ejemplo, para la operación POLLINGSTMT, como mínimo debe establecer el **InboundOperationType**, **PollingStatement**, y **PollingInterval** propiedades de enlace configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90df0-134">For example, for the POLLINGSTMT operation, at a minimum you must set the **InboundOperationType**, **PollingStatement**, and **PollingInterval** binding properties to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll the Oracle database.</span></span>  
  
3.  <span data-ttu-id="90df0-135">Crear una colección de parámetros de enlace mediante la **BindingParameterCollection** clase y establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="90df0-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4.  <span data-ttu-id="90df0-136">Crear un agente de escucha de canal invocando **BuildChannelListener\<IInputChannel >** método en el **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="90df0-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel>** method on the **OracleDBBinding**.</span></span> <span data-ttu-id="90df0-137">Especifique el URI de conexión de Oracle como uno de los parámetros a este método.</span><span class="sxs-lookup"><span data-stu-id="90df0-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="90df0-138">Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="90df0-138">For more information about the Oracle connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="90df0-139">Abra el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="90df0-139">Open the listener.</span></span>  
  
6.  <span data-ttu-id="90df0-140">Obtener un **IInputChannel** canal invocando la **AcceptChannel** método en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="90df0-140">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="90df0-141">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="90df0-141">Open the channel.</span></span>  
  
 <span data-ttu-id="90df0-142">El código siguiente muestra cómo crear un agente de escucha de canal y obtener un **IInputChannel** para mensajes entrantes desde el adaptador mediante la operación de POLLINGSTMT.</span><span class="sxs-lookup"><span data-stu-id="90df0-142">The following code shows how to create a channel listener and get an **IInputChannel** to inbound messages from the adapter using the POLLINGSTMT operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90df0-143">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] de recepción unidireccional solo admite.</span><span class="sxs-lookup"><span data-stu-id="90df0-143">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="90df0-144">Por lo tanto, debe usar IInputChannel para recibir mensajes para operaciones de entrada de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="90df0-144">So, you must use IInputChannel to receive messages for inbound operations from Oracle database.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the PollingStatement, and  
// the PostPollStatement.  
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
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleDB://ADAPTER");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="90df0-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="90df0-145">See Also</span></span>  
 [<span data-ttu-id="90df0-146">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="90df0-146">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)
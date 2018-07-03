---
title: Crear un canal con Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d18b7c2f-a43e-4499-ba94-4955dd5fe641
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947dc1a0a2b602d1dbcce032f721998b9fc84a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984645"
---
# <a name="create-a-channel-using-oracle-e-business-suite"></a><span data-ttu-id="f652f-102">Crear un canal con Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="f652f-102">Create a channel using Oracle E-Business Suite</span></span>
<span data-ttu-id="f652f-103">En el modelo de canal WCF, podrá invocar operaciones en Oracle E-Business Suite y recibir los resultados mediante el intercambio de mensajes SOAP con el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] a través de un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="f652f-103">In the WCF channel model, you invoke operations on the Oracle E-Business Suite and receive the results by exchanging SOAP messages with the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] over a WCF channel.</span></span>  
  
- <span data-ttu-id="f652f-104">Invocar operaciones (operaciones de salida) mediante el uso un **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador.</span><span class="sxs-lookup"><span data-stu-id="f652f-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter.</span></span>  
  
- <span data-ttu-id="f652f-105">Recibir mensajes de operaciones de entrada a través de un **IInputChannel**.</span><span class="sxs-lookup"><span data-stu-id="f652f-105">You receive messages for inbound operations over an **IInputChannel**.</span></span>  
  
  <span data-ttu-id="f652f-106">Los temas de esta sección proporcionan información acerca de cómo crear y configurar las formas del canal que se usan para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="f652f-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="f652f-107">Crear canales salientes (cliente)</span><span class="sxs-lookup"><span data-stu-id="f652f-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="f652f-108">Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f652f-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the Oracle E-Business Suite.</span></span> <span data-ttu-id="f652f-109">En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="f652f-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="f652f-110">Utilizamos el generador para crear el canal.</span><span class="sxs-lookup"><span data-stu-id="f652f-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="f652f-111">Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="f652f-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="f652f-112">Para crear y abrir un canal de salida</span><span class="sxs-lookup"><span data-stu-id="f652f-112">To create and open an outbound channel</span></span>  
  
1. <span data-ttu-id="f652f-113">Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante el uso de un punto de conexión y un enlace.</span><span class="sxs-lookup"><span data-stu-id="f652f-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="f652f-114">El punto de conexión especifica un URI de conexión de Oracle E-Business Suite y el enlace es una instancia de **OracleEBSBinding**.</span><span class="sxs-lookup"><span data-stu-id="f652f-114">The endpoint specifies an Oracle E-Business Suite connection URI and the binding is an instance of **OracleEBSBinding**.</span></span>  
  
2. <span data-ttu-id="f652f-115">Proporcionar credenciales de Oracle E-Business Suite para el generador de canales mediante la **credenciales** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f652f-115">Provide Oracle E-Business Suite credentials for the channel factory by using the **Credentials** property.</span></span>  
  
3. <span data-ttu-id="f652f-116">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="f652f-116">Open the channel factory.</span></span>  
  
4. <span data-ttu-id="f652f-117">Obtener una instancia del canal invocando el **CreateChannel** método en el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="f652f-117">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5. <span data-ttu-id="f652f-118">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="f652f-118">Open the channel.</span></span>  
  
   <span data-ttu-id="f652f-119">Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.</span><span class="sxs-lookup"><span data-stu-id="f652f-119">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="f652f-120">Especifica el enlace y dirección de punto de conexión en el código</span><span class="sxs-lookup"><span data-stu-id="f652f-120">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="f652f-121">En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="f652f-121">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="f652f-122">El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para el **ChannelFactory** y tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="f652f-122">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
OracleEBSBinding binding = new OracleEBSBinding();  
  
// Create address  
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(binding, address);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="f652f-123">Especifica el enlace y dirección de punto de conexión en la configuración</span><span class="sxs-lookup"><span data-stu-id="f652f-123">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="f652f-124">El ejemplo de código siguiente muestra cómo crear un generador de canales desde un punto de conexión de cliente especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="f652f-124">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
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
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="f652f-125">Los valores de configuración</span><span class="sxs-lookup"><span data-stu-id="f652f-125">The Configuration Settings</span></span>  
 <span data-ttu-id="f652f-126">El código siguiente muestra las opciones de configuración que se usa en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f652f-126">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="f652f-127">El contrato para el extremo del cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IOutputChannel" según el tipo de forma del canal que desea crear.</span><span class="sxs-lookup"><span data-stu-id="f652f-127">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IOutputChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="0"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true" enablePerformanceCounters="false">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://oracle_ebs_instance/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="f652f-128">Creación de canales de entrada (servicio)</span><span class="sxs-lookup"><span data-stu-id="f652f-128">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="f652f-129">Configurar la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear las tablas de base de datos de Oracle y las vistas mediante el establecimiento de propiedades de enlace en una instancia de **OracleEBSBinding**.</span><span class="sxs-lookup"><span data-stu-id="f652f-129">You configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database tables and views by setting binding properties on an instance of **OracleEBSBinding**.</span></span> <span data-ttu-id="f652f-130">A continuación, se usan este enlace para compilar un agente de escucha del canal desde el que puede obtener un **IInputChannel** canal para recibir operaciones de entrada desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="f652f-130">You then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive inbound operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-iinputchannel-to-receive-messages-for-inbound-operations"></a><span data-ttu-id="f652f-131">Para crear y abrir un IInputChannel para recibir mensajes para operaciones de entrada</span><span class="sxs-lookup"><span data-stu-id="f652f-131">To create and open an IInputChannel to receive messages for inbound operations</span></span>  
  
1. <span data-ttu-id="f652f-132">Cree una instancia de **OracleEBSBinding**.</span><span class="sxs-lookup"><span data-stu-id="f652f-132">Create an instance of **OracleEBSBinding**.</span></span>  
  
2. <span data-ttu-id="f652f-133">Establecer las propiedades de enlace necesarias para la operación de entrada.</span><span class="sxs-lookup"><span data-stu-id="f652f-133">Set the binding properties required for the inbound operation.</span></span> <span data-ttu-id="f652f-134">Por ejemplo, para una operación de sondeo, como mínimo debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**y el **PollingInput** enlace de propiedades para configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="f652f-134">For example, for a polling operation, at a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingAction**, and the **PollingInput** binding properties to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database.</span></span>  
  
3. <span data-ttu-id="f652f-135">Crear una colección de parámetros de enlace mediante la **BindingParameterCollection** clase y establecer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f652f-135">Create a binding parameter collection using the **BindingParameterCollection** class and set the credentials.</span></span>  
  
4. <span data-ttu-id="f652f-136">Crear un agente de escucha del canal invocando **BuildChannelListener\<IInputChannel\>**  método en el **OracleEBSBinding**.</span><span class="sxs-lookup"><span data-stu-id="f652f-136">Create a channel listener by invoking **BuildChannelListener\<IInputChannel\>** method on the **OracleEBSBinding**.</span></span> <span data-ttu-id="f652f-137">Especifique el URI de conexión de Oracle como uno de los parámetros a este método.</span><span class="sxs-lookup"><span data-stu-id="f652f-137">You specify the Oracle connection URI as one of the parameters to this method.</span></span>  
  
5. <span data-ttu-id="f652f-138">Abra el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f652f-138">Open the listener.</span></span>  
  
6. <span data-ttu-id="f652f-139">Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f652f-139">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7. <span data-ttu-id="f652f-140">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="f652f-140">Open the channel.</span></span>  
  
   <span data-ttu-id="f652f-141">El código siguiente muestra cómo crear un agente de escucha del canal y obtener un **IInputChannel** para recibir mensajes para operaciones de entrada desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="f652f-141">The following code shows how to create a channel listener and get an **IInputChannel** to receive messages for inbound operations from the adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f652f-142">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] de recepción unidireccional solo admite.</span><span class="sxs-lookup"><span data-stu-id="f652f-142">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] only supports one-way receive.</span></span> <span data-ttu-id="f652f-143">Por lo tanto, debe usar **IInputChannel** para recibir mensajes para operaciones de entrada de Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f652f-143">So, you must use **IInputChannel** to receive messages for inbound operations from Oracle E-Business Suite.</span></span>  
  
```  
// Create a binding: specify the InboundOperationType, the PolledDataAvailableStatement, the PollingAction, and   
// the PollingInput binding properties.  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.InboundOperationType = InboundOperation.Polling;  
binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
  
// Create a binding parameter collection and set the credentials  
ClientCredentials credentials = new ClientCredentials();  
credentials.UserName.UserName = "myuser";  
credentials.UserName.Password = "mypassword";  
  
BindingParameterCollection bindingParams = new BindingParameterCollection();  
bindingParams.Add(credentials);  
  
// Get a listener from the binding and open it.  
Uri connectionUri = new Uri("oracleebs://oracle_ebs_instance/");  
IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
listener.Open();  
  
// Get a channel from the listener and open it.  
IInputChannel channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f652f-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f652f-144">See Also</span></span>  
 [<span data-ttu-id="f652f-145">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="f652f-145">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
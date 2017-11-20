---
title: Crear un canal con SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- channel programming, creating a channel
- how to, create a channel
- creating a channel
- WCF channel model, creating a channel
ms.assetid: 24af1465-bb60-41d7-98bd-e501a981f82a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f69fbeb86cf63485591f048ef75cdcfd3d5056d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-channel-using-sap"></a><span data-ttu-id="fbc8c-102">Crear un canal con SAP</span><span class="sxs-lookup"><span data-stu-id="fbc8c-102">Create a channel using SAP</span></span>
<span data-ttu-id="fbc8c-103">En el modelo del canal WCF, puede invocar las operaciones en el sistema SAP o recibir mensajes desde el sistema SAP mediante el intercambio de mensajes SOAP con el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] sobre un canal WCF.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-103">In the WCF channel model, you invoke operations on the SAP system or receive messages from the SAP system by exchanging SOAP messages with the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] over a WCF channel.</span></span>  
  
-   <span data-ttu-id="fbc8c-104">Invocar operaciones (operaciones de salida) utilizando una **IRequestChannel** o un **IOutputChannel** para enviar mensajes al adaptador</span><span class="sxs-lookup"><span data-stu-id="fbc8c-104">You invoke operations (outbound operations) by using either an **IRequestChannel** or an **IOutputChannel** to send messages to the adapter</span></span>  
  
-   <span data-ttu-id="fbc8c-105">Recibir mensajes (desencadenados desde el sistema SAP) sobre una **IReplyChannel**.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-105">You receive messages (triggered from the SAP system) over an **IReplyChannel**.</span></span>  
  
 <span data-ttu-id="fbc8c-106">Los temas de esta sección proporcionan información acerca de cómo crear y configurar formas del canal que se utilizan para las operaciones de entrada y salidas.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-106">The topics in this section provide information about how to create and configure channel shapes that are used for inbound and outbound operations.</span></span>  
  
## <a name="creating-outbound-client-channels"></a><span data-ttu-id="fbc8c-107">Crear los canales de salida (cliente)</span><span class="sxs-lookup"><span data-stu-id="fbc8c-107">Creating Outbound (Client) Channels</span></span>  
 <span data-ttu-id="fbc8c-108">Puede usar un **IRequestChannel** o un **IOutputChannel** para invocar operaciones en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-108">You can use either an **IRequestChannel** or an **IOutputChannel** to invoke operations on the SAP system.</span></span> <span data-ttu-id="fbc8c-109">En cualquier caso, cree primero un **System.ServiceModel.ChannelFactory** mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-109">In either case, you first create a **System.ServiceModel.ChannelFactory** using the appropriate interface.</span></span> <span data-ttu-id="fbc8c-110">A continuación, utilice el generador para crear el canal.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-110">You then use the factory to create the channel.</span></span> <span data-ttu-id="fbc8c-111">Después de haber creado el canal se puede usar para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-111">After you have created the channel you can use it to invoke operations on the adapter.</span></span>  
  
#### <a name="to-create-and-open-an-outbound-channel"></a><span data-ttu-id="fbc8c-112">Para crear y abrir un canal de salida</span><span class="sxs-lookup"><span data-stu-id="fbc8c-112">To create and open an outbound channel</span></span>  
  
1.  <span data-ttu-id="fbc8c-113">Crear e inicializar una instancia de **ChannelFactory** para la forma del canal deseado mediante un punto de conexión y un enlace.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-113">Create and initialize an instance of **ChannelFactory** for the desired channel shape by using an endpoint and a binding.</span></span> <span data-ttu-id="fbc8c-114">El punto de conexión especifica un URI de conexión de SAP y el enlace es una instancia de **SAPDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-114">The endpoint specifies an SAP connection URI and the binding is an instance of **SAPDBBinding**.</span></span> <span data-ttu-id="fbc8c-115">(Establezca las propiedades de enlace necesarias antes de abrir el generador de canales.)</span><span class="sxs-lookup"><span data-stu-id="fbc8c-115">(Set any binding properties required before you open the channel factory.)</span></span>  
  
2.  <span data-ttu-id="fbc8c-116">Proporcione las credenciales SAP para el generador de canales mediante el uso de la **ClientCredentials** propiedad.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-116">Provide SAP credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
3.  <span data-ttu-id="fbc8c-117">Abra el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-117">Open the channel factory.</span></span>  
  
4.  <span data-ttu-id="fbc8c-118">Obtener una instancia del canal invocando la **CreateChannel** método en el generador de canales.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-118">Get an instance of the channel by invoking the **CreateChannel** method on the channel factory.</span></span>  
  
5.  <span data-ttu-id="fbc8c-119">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-119">Open the channel.</span></span>  
  
 <span data-ttu-id="fbc8c-120">Puede especificar la dirección de enlace y el punto de conexión en el código o de configuración.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-120">You can specify the binding and endpoint address in your code or from configuration.</span></span>  
  
### <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="fbc8c-121">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="fbc8c-121">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="fbc8c-122">En el ejemplo de código siguiente se muestra cómo crear un **IRequestChannel** especificando la dirección de enlace y el punto de conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-122">The following code example shows how to create an **IRequestChannel** by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="fbc8c-123">El código para crear un **IOutputChannel** es el mismo, salvo que debe especificar un **IOutputChannel** interfaz para la **ChannelFactory** y tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-123">The code to create an **IOutputChannel** is the same except that you must specify an **IOutputChannel** interface for the **ChannelFactory** and channel type.</span></span>  
  
```  
// Create binding -- set binding properties before you open the factory.  
SAPBinding sapBinding = new SAPBinding();  
  
// Create address.  
EndpointAddress sapAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
// Create channel factory from binding and address.  
ChannelFactory<IRequestChannel> factory =   
    new ChannelFactory<IRequestChannel>(sapBinding, sapAddress);  
  
// Specify credentials.   
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory  
factory.Open();  
  
// Get channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
### <a name="specifying-the-binding-and-endpoint-address-in-configuration"></a><span data-ttu-id="fbc8c-124">Especificar el enlace y la dirección del extremo en la configuración</span><span class="sxs-lookup"><span data-stu-id="fbc8c-124">Specifying the Binding and Endpoint Address in Configuration</span></span>  
 <span data-ttu-id="fbc8c-125">En el ejemplo de código siguiente se muestra cómo crear un generador de canales de un punto de conexión de cliente especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-125">The following code example shows how to create a channel factory from a client endpoint specified in configuration.</span></span>  
  
```  
// Create channel factory from configuration.  
ChannelFactory<IRequestChannel> factory =  
new ChannelFactory<IRequestChannel>("MyRequestChannel");  
  
// Specify credentials.  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the factory.  
factory.Open();  
  
// Get a channel and open it.  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
```  
  
#### <a name="the-configuration-settings"></a><span data-ttu-id="fbc8c-126">Los valores de configuración</span><span class="sxs-lookup"><span data-stu-id="fbc8c-126">The Configuration Settings</span></span>  
 <span data-ttu-id="fbc8c-127">El código siguiente muestra los valores de configuración que se usa para el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-127">The following code shows the configuration settings used for the preceding example.</span></span> <span data-ttu-id="fbc8c-128">El contrato para el extremo de cliente debe ser "System.ServiceModel.Channels.IRequestChannel" o "System.ServiceModel.Channels.IRequestChannel" según el tipo de forma del canal que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-128">The contract for the client endpoint must be "System.ServiceModel.Channels.IRequestChannel" or "System.ServiceModel.Channels.IRequestChannel" depending on the kind of channel shape that you want to create.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    receiveIdocFormat="Typed" enableSafeTyping="false" generateFlatFileCompatibleIdocSchema="true"  
                    maxConnectionsPerSystem="50" enableConnectionPooling="true"  
                    idleConnectionTimeout="00:15:00" flatFileSegmentIndicator="SegmentDefinition"  
                    enablePerformanceCounters="false" autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false"  
                    padReceivedIdocWithSpaces="false" sncLibrary="" sncPartnerName="" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/ADAPSAP47/00?RfcSdkTrace=False&AbapDebug=False"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="System.ServiceModel.Channels.IRequestChannel"  
                name="MyRequestChannel" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
### <a name="creating-inbound-service-channels"></a><span data-ttu-id="fbc8c-129">Crear los canales de entrada (servicio)</span><span class="sxs-lookup"><span data-stu-id="fbc8c-129">Creating Inbound (Service) Channels</span></span>  
 <span data-ttu-id="fbc8c-130">Configurar el adaptador para recibir mensajes entrantes de un sistema SAP estableciendo las propiedades de enlace en una instancia de **SAPBinding**.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-130">You configure the adapter to receive inbound messages from an SAP system by setting binding properties on an instance of **SAPBinding**.</span></span> <span data-ttu-id="fbc8c-131">A continuación, utilice este enlace para compilar un agente de escucha de canal desde el que se puede obtener un **IReplyChannel** canal para operaciones de recepción del adaptador.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-131">You then use this binding to build a channel listener from which you can get an **IReplyChannel** channel to receive operations from the adapter.</span></span>  
  
##### <a name="to-create-and-open-an-ireplychannel-to-receive-data-changed-notifications"></a><span data-ttu-id="fbc8c-132">Para crear y abrir un IReplyChannel para las notificaciones de cambio de datos de recepción</span><span class="sxs-lookup"><span data-stu-id="fbc8c-132">To create and open an IReplyChannel to Receive Data-changed Notifications</span></span>  
  
1.  <span data-ttu-id="fbc8c-133">Cree una instancia de **SAPBinding**.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-133">Create an instance of **SAPBinding**.</span></span>  
  
2.  <span data-ttu-id="fbc8c-134">Establezca las propiedades de enlace necesarias para las operaciones que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-134">Set any binding properties required for the operations you want to receive.</span></span> <span data-ttu-id="fbc8c-135">Asegúrese de establecer el **AcceptCredentialsInUri** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-135">Be sure to set the **AcceptCredentialsInUri** binding property.</span></span>  
  
3.  <span data-ttu-id="fbc8c-136">Crear un **BindingParameterCollection** y agregue un **InboundActionCollection** que contiene las acciones de las operaciones que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-136">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="fbc8c-137">El adaptador devolverá una excepción al sistema SAP para todas las demás operaciones.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-137">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="fbc8c-138">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-138">This step is optional.</span></span> <span data-ttu-id="fbc8c-139">Para obtener más información, consulte [recibir las operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="fbc8c-139">For more information, see [Receiving Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
4.  <span data-ttu-id="fbc8c-140">Crear un agente de escucha de canal invocando **BuildChannelListener\<IReplyChannel >** método en el **SAPBinding**.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-140">Create a channel listener by invoking **BuildChannelListener\<IReplyChannel>** method on the **SAPBinding**.</span></span> <span data-ttu-id="fbc8c-141">Especifique el URI de conexión de SAP como uno de los parámetros a este método.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-141">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="fbc8c-142">El URI de conexión debe contener parámetros para un destino RFC en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-142">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="fbc8c-143">Para obtener más información sobre el URI de conexión de SAP, consulte la [cree el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="fbc8c-143">For more information about the SAP connection URI, see The [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="fbc8c-144">Si ha creado un **BindingParameterCollection** en el paso 3, también especificarlo al crear la escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-144">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
5.  <span data-ttu-id="fbc8c-145">Abra el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-145">Open the listener.</span></span>  
  
6.  <span data-ttu-id="fbc8c-146">Obtener un **IReplyChannel** canal invocando la **AcceptChannel** método en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-146">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on listener.</span></span>  
  
7.  <span data-ttu-id="fbc8c-147">Abrir el canal.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-147">Open the channel.</span></span>  
  
 <span data-ttu-id="fbc8c-148">El código siguiente muestra cómo crear un agente de escucha de canal y obtener un **IReplyChannel** para operaciones de recepción del adaptador.</span><span class="sxs-lookup"><span data-stu-id="fbc8c-148">The following code shows how to create a channel listener and get an **IReplyChannel** to receive operations from the adapter.</span></span>  
  
```  
// Create a binding and specify any binding properties required  
// for the opreations you want to receive  
SAPBinding binding = new SAPBinding();  
  
// Set AcceptCredentialsInUri because the URI must contain credentials.  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying  
// the binding parameter collection (to filter for the Z_RFC_MKD_ADD action) and   
// a connection URI that contains listener parameters.  
Uri listeneraddress =  
new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, new BindingParameterCollection());  
listener.Open();  
  
// Get a channel from the listener and open it.  
channel = listener.AcceptChannel();  
channel.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbc8c-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbc8c-149">See Also</span></span>  
[<span data-ttu-id="fbc8c-150">Desarrollar aplicaciones mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="fbc8c-150">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)
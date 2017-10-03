---
title: "Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1265a2b7205e372ba9f3769fcc95ea9ac3aeff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="ca42d-102">Operaciones de entrada de recepción desde el sistema SAP mediante el modelo del canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ca42d-102">Receive Inbound Operations from the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="ca42d-103">Para actuar como un servidor RFC y recibir operaciones invocadas por el sistema SAP (por ejemplo, enviar un IDOC o invocar una solicitud de cambio), debe crear una escucha de canales que puede realizar escuchas de mensajes de un identificador de programa de SAP en un  **System.ServiceModel.Channels.IReplyChannel** forma de canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-103">To act as an RFC server and receive operations invoked by the SAP system (such as sending an IDOC or invoking an RFC), you must create a channel listener that can listen for messages from a SAP Program ID over a **System.ServiceModel.Channels.IReplyChannel** channel shape.</span></span>  
  
 <span data-ttu-id="ca42d-104">Un agente de escucha de canal (**System.ServiceModel.Channels.IChannelListener**) es un objeto de comunicación de WCF que puede utilizarse para recibir mensajes de los extremos WCF específicos.</span><span class="sxs-lookup"><span data-stu-id="ca42d-104">A channel listener (**System.ServiceModel.Channels.IChannelListener**) is a WCF communication object that can be used to receive messages from specific WCF endpoints.</span></span> <span data-ttu-id="ca42d-105">El agente de escucha de canal funciona como un generador desde el que puede crear canales que se pueden recibir mensajes invocados por un cliente (el sistema SAP) por el servicio.</span><span class="sxs-lookup"><span data-stu-id="ca42d-105">The channel listener functions as a factory from which you can create channels over which messages invoked by a client (the SAP system) can be received by your service.</span></span> <span data-ttu-id="ca42d-106">Crear un agente de escucha del canal por desde una **Microsoft.Adapters.SAP.SAPBinding** objeto invocando la **BuildChannelListener** método.</span><span class="sxs-lookup"><span data-stu-id="ca42d-106">You create a channel listener by from a **Microsoft.Adapters.SAP.SAPBinding** object by invoking the **BuildChannelListener** method.</span></span> <span data-ttu-id="ca42d-107">Proporcione una URI que especifica el identificador de programa de SAP desde el que se recibirán las operaciones de entrada a este método de conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-107">You supply an SAP connection URI that specifies the SAP Program ID from which inbound operations will be received to this method.</span></span>  
  
 <span data-ttu-id="ca42d-108">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con la **IReplyChannel** forma de canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the **IReplyChannel** channel shape.</span></span> <span data-ttu-id="ca42d-109">**IReplyChannel** canales admiten un patrón de intercambio de mensajes de respuesta de solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="ca42d-109">**IReplyChannel** channels support an inbound request-response message exchange pattern.</span></span> <span data-ttu-id="ca42d-110">Es decir, un patrón en el que un programa externo envía un mensaje de solicitud a través del canal y el programa devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="ca42d-110">That is, a pattern in which an external program sends a request message over the channel and your program returns a response.</span></span>  
  
 <span data-ttu-id="ca42d-111">Para obtener información general sobre el uso de operaciones de recepción de un **IReplyChannel** en WCF, vea [nivel de canal del servicio de programación](https://msdn.microsoft.com/library/ms789029.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca42d-111">For an overview of how to receive operations using an **IReplyChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span>
  
 <span data-ttu-id="ca42d-112">En esta sección se trata los temas siguientes que son específicos para recibir las operaciones de un sistema SAP:</span><span class="sxs-lookup"><span data-stu-id="ca42d-112">This section covers the following topics that are specific to receiving operations from a SAP system:</span></span>  
  
-   <span data-ttu-id="ca42d-113">Cómo filtrar para operaciones específicas mediante el agente de escucha de canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-113">How to filter for specific operations using the channel listener.</span></span>  
  
-   <span data-ttu-id="ca42d-114">Cómo generar una excepción en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-114">How to raise an exception on the SAP system.</span></span>  
  
-   <span data-ttu-id="ca42d-115">Transmisión por secuencias entrante IDOC de archivo sin formato desde el adaptador SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-115">Streaming inbound flat-file IDOCs from the SAP adapter.</span></span>  
  
-   <span data-ttu-id="ca42d-116">Cómo recibir operaciones desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-116">How to receive operations from the SAP system.</span></span>  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a><span data-ttu-id="ca42d-117">¿Cómo se puede filtrar las operaciones mediante el agente de escucha de canal?</span><span class="sxs-lookup"><span data-stu-id="ca42d-117">How Do I Filter Operations Using the Channel Listener?</span></span>  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a><span data-ttu-id="ca42d-118">Uso de un InboundActionCollection para operaciones de filtro</span><span class="sxs-lookup"><span data-stu-id="ca42d-118">Using an InboundActionCollection to Filter Operations</span></span>  
 <span data-ttu-id="ca42d-119">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona el **Microsoft.ServiceModel.Channels.InboundActionCollection** clase que le permite filtrar las operaciones que se reciben un agente de escucha de canal y se pasa al código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca42d-119">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides the **Microsoft.ServiceModel.Channels.InboundActionCollection** class to enable you to filter operations that are received by a channel listener and passed to your application code.</span></span> <span data-ttu-id="ca42d-120">Para filtrar para operaciones específicas, crea una instancia de esta clase mediante el URI del extremo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ca42d-120">To filter for specific operations, you create an instance of this class by using the listener endpoint URI.</span></span> <span data-ttu-id="ca42d-121">A continuación, agregar la acción de mensaje (solicitud) para cada operación de destino a la colección.</span><span class="sxs-lookup"><span data-stu-id="ca42d-121">Then you add the (request) message action for each target operation to the collection.</span></span> <span data-ttu-id="ca42d-122">Por último, puede agregar a la colección de entrada de acción un **System.ServiceModel.Channels.BindingParameterCollection** objeto y, a continuación, pasar esta colección de parámetros de enlace en la llamada para crear la escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-122">Finally, you add the inbound action collection to a **System.ServiceModel.Channels.BindingParameterCollection** object and then pass this binding parameter collection into the call to create the channel listener.</span></span>  
  
 <span data-ttu-id="ca42d-123">Si el sistema SAP, invoca una operación que no está en la colección de acciones de entrada:</span><span class="sxs-lookup"><span data-stu-id="ca42d-123">If the SAP system invokes an operation that is not in the inbound action collection:</span></span>  
  
-   <span data-ttu-id="ca42d-124">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] devuelve una excepción al llamador en el sistema SAP con el siguiente mensaje: "no se controla la llamada entrante de RFC [RFC_NAME] en el servidor de Rfc".</span><span class="sxs-lookup"><span data-stu-id="ca42d-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] returns an EXCEPTION exception to the caller on the SAP system with the following message: "The incoming RFC call [RFC_NAME] on the Rfc Server is not handled".</span></span> <span data-ttu-id="ca42d-125">En este mensaje, [RFC_NAME] es el nombre de la solicitud de cambio (por ejemplo, IDOC_INBOUND_ASYNCHRONOUS).</span><span class="sxs-lookup"><span data-stu-id="ca42d-125">In this message, [RFC_NAME] is the name of the RFC (for example, IDOC_INBOUND_ASYNCHRONOUS).</span></span>  
  
-   <span data-ttu-id="ca42d-126">El adaptador lanza una **Microsoft.ServiceModel.Channels.Common.AdapterException** con un mensaje que indica que la operación que se recibió.</span><span class="sxs-lookup"><span data-stu-id="ca42d-126">The adapter throws a **Microsoft.ServiceModel.Channels.Common.AdapterException** with a message that indicates the operation that was received.</span></span> <span data-ttu-id="ca42d-127">Para obtener un ejemplo de cómo usar esta excepción, vea el ejemplo al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ca42d-127">For an example of how to use this exception, see the example at the end of this topic.</span></span>  
  
 <span data-ttu-id="ca42d-128">En el ejemplo de código siguiente se muestra cómo utilizar un **InboundActionCollection** para crear un agente de escucha de canal que filtra una RFC única, Z_RFC_MKD_DIV.</span><span class="sxs-lookup"><span data-stu-id="ca42d-128">The following code example shows how to use an **InboundActionCollection** to create a channel listener that filters for a single RFC, Z_RFC_MKD_DIV.</span></span>  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a><span data-ttu-id="ca42d-129">Operaciones de filtrado manualmente</span><span class="sxs-lookup"><span data-stu-id="ca42d-129">Manually Filtering Operations</span></span>  
 <span data-ttu-id="ca42d-130">Si no especifica una colección de acciones de entrada para el agente de escucha de canal, todas las operaciones invocadas por el sistema SAP se pasarán al código.</span><span class="sxs-lookup"><span data-stu-id="ca42d-130">If you do not specify an inbound action collection for the channel listener, then all operations invoked by the SAP system will be passed to your code.</span></span> <span data-ttu-id="ca42d-131">Puede filtrar manualmente estas operaciones mediante la comprobación de la acción de mensaje de las solicitudes de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca42d-131">You can manually filter such operations by checking the message action of inbound requests.</span></span>  
  
 <span data-ttu-id="ca42d-132">También puede haber escenarios en los que desea filtrar una operación en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="ca42d-132">There may also be scenarios in which you want to filter an operation based on its content.</span></span> <span data-ttu-id="ca42d-133">Por ejemplo, si recibe IDOC en:</span><span class="sxs-lookup"><span data-stu-id="ca42d-133">For example if you are receiving IDOCs in:</span></span>  
  
-   <span data-ttu-id="ca42d-134">Formato de cadena (el **ReceiveIDocFormat** propiedad de enlace es **cadena**); todos los IDOC se recibe mediante la operación de ReceiveIdoc.</span><span class="sxs-lookup"><span data-stu-id="ca42d-134">String format (the **ReceiveIDocFormat** binding property is **String**); all IDOCs are received using the ReceiveIdoc operation.</span></span>  
  
-   <span data-ttu-id="ca42d-135">Formato de RFC (la **ReceiveIDocFormat** propiedad de enlace es **Rfc**); todos los IDOC se recibe mediante la solicitud de cambio de IDOC_INBOUND_ASYNCHRONOUS o la solicitud de cambio de INBOUND_IDOC_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="ca42d-135">Rfc format (the **ReceiveIDocFormat** binding property is **Rfc**); all IDOCs are received using either the IDOC_INBOUND_ASYNCHRONOUS RFC or the INBOUND_IDOC_PROCESS RFC.</span></span>  
  
 <span data-ttu-id="ca42d-136">En este escenario puede que desee implementar filtrado basándose en los parámetros específicos de IDOC (por ejemplo, el tipo IDOC) en el código.</span><span class="sxs-lookup"><span data-stu-id="ca42d-136">In this scenario you may want to implement filtering based on specific IDOC parameters (such as the IDOC type) in your code.</span></span>  
  
 <span data-ttu-id="ca42d-137">Cuando se filtran las operaciones manualmente, puede devolver un error en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para las operaciones que no se encarga de.</span><span class="sxs-lookup"><span data-stu-id="ca42d-137">When you filter operations manually, you can return a fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for operations that you don't handle.</span></span> <span data-ttu-id="ca42d-138">Esto producirá la excepción al llamador en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-138">This will raise the EXCEPTION exception to the caller on the SAP System.</span></span> <span data-ttu-id="ca42d-139">También puede devolver una respuesta vacía si no desea generar una excepción en SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-139">You can also return an empty response if you don't want to raise an exception on SAP.</span></span>  
  
 <span data-ttu-id="ca42d-140">El código siguiente muestra cómo filtrar manualmente para la operación de Z_RFC_MKD_DIV.</span><span class="sxs-lookup"><span data-stu-id="ca42d-140">The following code shows how to filter manually for the Z_RFC_MKD_DIV operation.</span></span>  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a><span data-ttu-id="ca42d-141">¿Cómo se puede producir una excepción en el sistema SAP?</span><span class="sxs-lookup"><span data-stu-id="ca42d-141">How Do I Raise an Exception on the SAP System?</span></span>  
 <span data-ttu-id="ca42d-142">Para indicar un error al llamador en el sistema SAP puede responder a un mensaje de solicitud con un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-142">To indicate an error to the caller on the SAP system you can reply to a request message with a SOAP fault.</span></span> <span data-ttu-id="ca42d-143">Cuando se devolverá un error SOAP para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el adaptador devuelve una excepción al llamador en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-143">When you return a SOAP fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the adapter returns an EXCEPTION exception to the caller on the SAP system.</span></span> <span data-ttu-id="ca42d-144">Se crea el mensaje de excepción de los elementos de los errores SOAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-144">The exception message is created from the elements of the SOAP fault.</span></span>  
  
 <span data-ttu-id="ca42d-145">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] crea el mensaje para la excepción de SAP según el orden de prioridad siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca42d-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates the message for the SAP EXCEPTION according to the following order of precedence:</span></span>  
  
1.  <span data-ttu-id="ca42d-146">Si el error de SOAP contiene un objeto de detalle, el adaptador serializa el nivel de detalle para una cadena y el mensaje de excepción se establece en esta cadena.</span><span class="sxs-lookup"><span data-stu-id="ca42d-146">If the SOAP fault contains a detail object, the adapter serializes the detail to a string and the exception message is set to this string.</span></span>  
  
2.  <span data-ttu-id="ca42d-147">Si el error de SOAP contiene un motivo, el mensaje de excepción se establece en su valor.</span><span class="sxs-lookup"><span data-stu-id="ca42d-147">If the SOAP fault contains a reason, the exception message is set to its value.</span></span>  
  
3.  <span data-ttu-id="ca42d-148">En caso contrario, el adaptador serializa el **MessageFault** objeto a una cadena y el mensaje de excepción se establece en esta cadena.</span><span class="sxs-lookup"><span data-stu-id="ca42d-148">Otherwise, the adapter serializes the **MessageFault** object itself to a string and the exception message is set to this string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca42d-149">El adaptador utiliza solo el mensaje de error para crear el mensaje de excepción que se devuelven en la excepción que se inicia en el sistema SAP; por lo tanto, los valores que establezca para estas entidades es decisión suya.</span><span class="sxs-lookup"><span data-stu-id="ca42d-149">The adapter only uses the fault message to create the exception message returned in the exception raised on the SAP system; therefore, the values that you set for these entities is completely up to you.</span></span>  
  
 <span data-ttu-id="ca42d-150">WCF proporciona el **System.ServiceModel.Channels.MessageFault** clase para encapsular una representación en memoria de un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-150">WCF provides the **System.ServiceModel.Channels.MessageFault** class to encapsulate an in-memory representation of a SOAP fault.</span></span> <span data-ttu-id="ca42d-151">Puede usar cualquiera de los métodos estático, sobrecargar **MessageFault.CreateFault** métodos para crear un nuevo error de SOAP desde el que, a continuación, puede crear un mensaje de error mediante la invocación de la correspondiente **Message.CreateMessage** se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="ca42d-151">You can use any of the static, overloaded **MessageFault.CreateFault** methods to create a new SOAP fault from which you can then create a fault message by invoking the appropriate **Message.CreateMessage** overload.</span></span> <span data-ttu-id="ca42d-152">WCF también proporciona sobrecargas de **CreateMessage** que crean un mensaje de error sin usar un **MessageFault** objeto.</span><span class="sxs-lookup"><span data-stu-id="ca42d-152">WCF also provides overloads of **CreateMessage** that create a fault message without using a **MessageFault** object.</span></span>  
  
 <span data-ttu-id="ca42d-153">Usa el **System.ServiceModel.Channels.RequestContext.Reply** método para devolver el mensaje de error para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca42d-153">You use the **System.ServiceModel.Channels.RequestContext.Reply** method to return the fault message to the adapter.</span></span> <span data-ttu-id="ca42d-154">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] omite la acción de mensaje para los mensajes de error, por lo que puede establecer la acción de mensaje a cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="ca42d-154">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ignores the message action for fault messages, so you can set the message action to any value.</span></span>  
  
 <span data-ttu-id="ca42d-155">En el ejemplo siguiente se muestra cómo devolver un mensaje de error para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca42d-155">The following example shows how to return a fault message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="ca42d-156">Este ejemplo omiten los pasos para crear la escucha del canal y el canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-156">This example omits the steps to create the channel listener and channel.</span></span>  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a><span data-ttu-id="ca42d-157">Transmisión por secuencias IDOC de archivo sin formato entrante del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="ca42d-157">Streaming Inbound Flat-File IDOCs from the SAP Adapter</span></span>  
 <span data-ttu-id="ca42d-158">Recibir IDOC (cadena) desde el adaptador en la operación de ReceiveIdoc entrada de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="ca42d-158">You receive flat-file (string) IDOCs from the adapter in the inbound ReceiveIdoc operation.</span></span> <span data-ttu-id="ca42d-159">Los datos IDOC se representan como una cadena en un único nodo en esta operación.</span><span class="sxs-lookup"><span data-stu-id="ca42d-159">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="ca42d-160">Por este motivo, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con transmisión por secuencias en el mensaje de solicitud en el valor de nodo.</span><span class="sxs-lookup"><span data-stu-id="ca42d-160">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="ca42d-161">Para realizar la transmisión por secuencias de valor de nodo, debe consumir el mensaje de solicitud para la operación ReceiveIdoc invocando la **Message.WriteBodyContents** método con un **System.Xml.XmlDictionaryWriter** que es capaz de transmitir por secuencias los datos IDOC.</span><span class="sxs-lookup"><span data-stu-id="ca42d-161">To perform node-value streaming, you must consume the request message for the ReceiveIdoc operation by invoking the **Message.WriteBodyContents** method with a **System.Xml.XmlDictionaryWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="ca42d-162">Para obtener información acerca de cómo hacerlo, consulte [IDOC de archivo plano de transmisión por secuencias en SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="ca42d-162">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a><span data-ttu-id="ca42d-163">¿Cómo obtengo operaciones desde un sistema SAP mediante un IReplyChannel?</span><span class="sxs-lookup"><span data-stu-id="ca42d-163">How Do I Receive Operations from a SAP System Using an IReplyChannel?</span></span>  
 <span data-ttu-id="ca42d-164">Para operaciones de recepción de un sistema SAP mediante el modelo de canal WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ca42d-164">To receive operations from a SAP system by using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a><span data-ttu-id="ca42d-165">Para operaciones de recepción desde el sistema SAP mediante un IReplyChannel</span><span class="sxs-lookup"><span data-stu-id="ca42d-165">To receive operations from the SAP system using an IReplyChannel</span></span>  
  
1.  <span data-ttu-id="ca42d-166">Cree una instancia de **SAPBinding** y establezca las propiedades de enlace necesarias para las operaciones que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="ca42d-166">Create an instance of **SAPBinding** and set the binding properties required to for the operations you want to receive.</span></span> <span data-ttu-id="ca42d-167">Como mínimo debe establecer el **AcceptCredentialsInUri** enlaza la propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="ca42d-167">At a minimum you must set the **AcceptCredentialsInUri** binding property to true.</span></span> <span data-ttu-id="ca42d-168">Para que actúe como un servidor de tRFC, debe establecer el **TidDatabaseConnectionString** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="ca42d-168">To act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property.</span></span> <span data-ttu-id="ca42d-169">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ca42d-169">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  <span data-ttu-id="ca42d-170">Crear un **BindingParameterCollection** y agregue un **InboundActionCollection** que contiene las acciones de las operaciones que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="ca42d-170">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="ca42d-171">El adaptador devolverá una excepción al sistema SAP para todas las demás operaciones.</span><span class="sxs-lookup"><span data-stu-id="ca42d-171">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="ca42d-172">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="ca42d-172">This step is optional.</span></span> <span data-ttu-id="ca42d-173">Para obtener más información, consulte [recibir las operaciones de entrada desde el sistema SAP mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="ca42d-173">For more information, see [Receiving Inbound Operations from the SAP System Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  <span data-ttu-id="ca42d-174">Crear un agente de escucha de canal invocando **BuildChannelListener < IReplyChannel\>**  método en el **SAPBinding** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="ca42d-174">Create a channel listener by invoking **BuildChannelListener<IReplyChannel\>** method on the **SAPBinding** and open it.</span></span> <span data-ttu-id="ca42d-175">Especifique el URI de conexión de SAP como uno de los parámetros a este método.</span><span class="sxs-lookup"><span data-stu-id="ca42d-175">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="ca42d-176">El URI de conexión debe contener parámetros para un destino RFC en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-176">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="ca42d-177">Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="ca42d-177">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="ca42d-178">Si ha creado un **BindingParameterCollection** en el paso 3, también especificarlo al crear la escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="ca42d-178">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  <span data-ttu-id="ca42d-179">Obtener un **IReplyChannel** canal invocando la **AcceptChannel** método en el agente de escucha y ábralo.</span><span class="sxs-lookup"><span data-stu-id="ca42d-179">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="ca42d-180">Invocar **ReceiveRequest** en el canal que se va a obtener el mensaje de solicitud de la siguiente operación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca42d-180">Invoke **ReceiveRequest** on the channel to get the request message for the next operation from the adapter.</span></span>  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  <span data-ttu-id="ca42d-181">Consumir el mensaje de solicitud enviado por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca42d-181">Consume the request message sent by the adapter.</span></span> <span data-ttu-id="ca42d-182">Aparece el mensaje de solicitud desde el **RequestMessage** propiedad de la **RequestContext**.</span><span class="sxs-lookup"><span data-stu-id="ca42d-182">You get the request message from the **RequestMessage** property of the **RequestContext**.</span></span> <span data-ttu-id="ca42d-183">Puedes utilizar el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.</span><span class="sxs-lookup"><span data-stu-id="ca42d-183">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  <span data-ttu-id="ca42d-184">Completar la operación al devolver una respuesta o error al sistema SAP:</span><span class="sxs-lookup"><span data-stu-id="ca42d-184">Complete the operation by returning a response or fault to the SAP system:</span></span>  
  
    1.  <span data-ttu-id="ca42d-185">Procesar el mensaje y devolver una respuesta al sistema SAP devolviendo el mensaje de respuesta al adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca42d-185">Process the message and return a response to the SAP system by returning the response message to the adapter.</span></span> <span data-ttu-id="ca42d-186">En este ejemplo se devuelve un mensaje vacío.</span><span class="sxs-lookup"><span data-stu-id="ca42d-186">This example returns an empty message.</span></span>  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  <span data-ttu-id="ca42d-187">Devuelve una excepción al sistema SAP devolviendo un mensaje de error para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca42d-187">Return an exception to the SAP system by returning a fault message to the adapter.</span></span> <span data-ttu-id="ca42d-188">Puede utilizar un valor para la acción de mensaje, el código de error y el motivo.</span><span class="sxs-lookup"><span data-stu-id="ca42d-188">You can use any value for the message action, fault code, and reason.</span></span>  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  <span data-ttu-id="ca42d-189">Cierre el contexto de solicitud después de haber enviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ca42d-189">Close the request context after you have sent the message.</span></span>  
  
    ```  
    rc.Close();  
    ```  
  
9. <span data-ttu-id="ca42d-190">Cierre el canal cuando se hayan completado de procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ca42d-190">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ca42d-191">Debe cerrar el canal cuando haya terminado de procesar la operación.</span><span class="sxs-lookup"><span data-stu-id="ca42d-191">You must close the channel after you have finished processing the operation.</span></span> <span data-ttu-id="ca42d-192">Si no se cierra el canal puede afectar al comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="ca42d-192">Failure to close the channel may affect the behavior of your code.</span></span>  
  
10. <span data-ttu-id="ca42d-193">Cierre el agente de escucha cuando haya terminado de recibir las operaciones desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-193">Close the listener when you are finished receiving operations from the SAP system.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ca42d-194">Debe cerrar explícitamente el agente de escucha cuando haya terminado de usarlo; en caso contrario, el programa no funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca42d-194">You must explicitly close the listener when you are done using it; otherwise, your program may not behave properly.</span></span> <span data-ttu-id="ca42d-195">Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ca42d-195">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="ca42d-196">Debe cerrar explícitamente cada canal que se crea mediante el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ca42d-196">You must also explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca42d-197">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca42d-197">Example</span></span>  
 <span data-ttu-id="ca42d-198">En el ejemplo siguiente se recibe una solicitud de cambio, Z_RFC_MKD_DIV desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-198">The following example receives an RFC, Z_RFC_MKD_DIV from the SAP system.</span></span> <span data-ttu-id="ca42d-199">Este RFC divide dos números.</span><span class="sxs-lookup"><span data-stu-id="ca42d-199">This RFC divides two numbers.</span></span> <span data-ttu-id="ca42d-200">La implementación en este ejemplo utiliza un **InboundActionCollection** para filtrar para la operación de Z_RFC_MKD_DIV y hace lo siguiente cuando se recibe un mensaje:</span><span class="sxs-lookup"><span data-stu-id="ca42d-200">The implementation in this example uses an **InboundActionCollection** to filter for the Z_RFC_MKD_DIV operation and does the following when a message is received:</span></span>  
  
-   <span data-ttu-id="ca42d-201">Si el divisor es distinto de cero, el resultado de la división se escribe en la consola y lo devuelve al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-201">If the divisor is non-zero, it writes the result of the division to the console and returns it to the SAP system.</span></span>  
  
-   <span data-ttu-id="ca42d-202">Si el divisor es cero, escribe el mensaje de excepción resultante en la consola y devuelve un error al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-202">If the divisor is zero, it writes the resulting exception message to the console and returns a fault to the SAP system.</span></span>  
  
-   <span data-ttu-id="ca42d-203">Si cualquier otra operación es enviado por el sistema SAP, escribe un mensaje en la consola.</span><span class="sxs-lookup"><span data-stu-id="ca42d-203">If any other operation is sent by the SAP system, it writes a message to the console.</span></span> <span data-ttu-id="ca42d-204">En este caso, el propio adaptador devuelve un error al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="ca42d-204">In this case, the adapter itself returns a fault to the SAP system.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "\<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
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
  
## <a name="see-also"></a><span data-ttu-id="ca42d-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca42d-205">See Also</span></span>  
[<span data-ttu-id="ca42d-206">Desarrollar aplicaciones mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="ca42d-206">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)
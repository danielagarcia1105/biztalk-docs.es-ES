---
title: Interfaz de IBaseMessage | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a><span data-ttu-id="d80df-102">IBaseMessage (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d80df-102">IBaseMessage Interface</span></span>
<span data-ttu-id="d80df-103">Cuando un adaptador de recepción acepta un paquete de datos entrante a través de su protocolo, utiliza el **IBaseMessage** interfaz para crear un mensaje que se pasará al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="d80df-103">When a receive adapter accepts an incoming data packet through its protocol, it uses the **IBaseMessage** interface to create a message to pass to the Messaging Engine.</span></span> <span data-ttu-id="d80df-104">Todos los mensajes se representan mediante esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="d80df-104">All messages are represented by using this interface.</span></span>  
  
 <span data-ttu-id="d80df-105">Un mensaje tiene uno o más partes del mensaje representan por la **IBaseMessagePart** interfaz.</span><span class="sxs-lookup"><span data-stu-id="d80df-105">A message has one or more message parts represented by the **IBaseMessagePart** interface.</span></span> <span data-ttu-id="d80df-106">Cada parte del mensaje tiene una referencia a sus datos a través de un **IStream** puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="d80df-106">Each message part has a reference to its data through an **IStream** interface pointer.</span></span> <span data-ttu-id="d80df-107">El contexto de un mensaje está representado por su **IBaseMessageContext** interfaz.</span><span class="sxs-lookup"><span data-stu-id="d80df-107">The context of a message is represented by its **IBaseMessageContext** interface.</span></span> <span data-ttu-id="d80df-108">En la siguiente ilustración se muestra el modelo de objetos de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d80df-108">The following figure illustrates the BizTalk message object model.</span></span>  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 <span data-ttu-id="d80df-109">El contexto de mensaje es un diccionario que organizado en pares de claves con una combinación de nombre de propiedad y espacio de nombres de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d80df-109">The message context is a dictionary that is keyed on a combination of the property name and the property namespace.</span></span> <span data-ttu-id="d80df-110">Este modo evita conflictos entre propiedades con nombres parecidos de orígenes diferentes, por ejemplo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] propiedades del sistema y las propiedades de adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="d80df-110">This prevents collisions between similarly named properties from different sources, for example, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system properties and custom adapter properties.</span></span> <span data-ttu-id="d80df-111">Los valores de estas propiedades son del tipo .NET **objeto**, pero en realidad son variantes.</span><span class="sxs-lookup"><span data-stu-id="d80df-111">The values for these properties are of the .NET type **object**, but in fact these properties are VARIANTs.</span></span>  
  
 <span data-ttu-id="d80df-112">Cada parte tiene un contexto de parte que también es un diccionario, pero sin la noción de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d80df-112">Each part has a part context that is also a dictionary but without the notion of a namespace.</span></span> <span data-ttu-id="d80df-113">El valor de un contexto de parte son metadatos que hacen referencia a los datos de esa parte.</span><span class="sxs-lookup"><span data-stu-id="d80df-113">The value of a part context is metadata referring to the data for that part.</span></span> <span data-ttu-id="d80df-114">Un ejemplo de esto es el **Charset** propiedad que especifica el juego de caracteres utilizado para codificar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d80df-114">An example of this is the **Charset** property that specifies the character set used for encoding the message.</span></span>  
  
 <span data-ttu-id="d80df-115">Las propiedades se pueden escribir y leer en el contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d80df-115">Properties may be written to and read from the message context.</span></span> <span data-ttu-id="d80df-116">También se pueden promocionar a fin de utilizarlas para el enrutamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d80df-116">They may also be promoted to be used for message routing.</span></span> <span data-ttu-id="d80df-117">Promocionar significa escribirlas como parte de metadatos que fluyen con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d80df-117">Being promoted means they are written as a part of metadata that flows with the message.</span></span> <span data-ttu-id="d80df-118">Una propiedad promocionada permite que su valor se use en la creación de expresiones de filtro de las orquestaciones y los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="d80df-118">A promoted property allows its value to be used in the creation of filter expressions on send ports and orchestrations.</span></span> <span data-ttu-id="d80df-119">Los componentes de nivel inferior y el código de usuario de las orquestaciones pueden leer las propiedades promocionadas y también escribir en ellas valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="d80df-119">Downstream components and user code in orchestrations may read promoted properties and also write new values to them.</span></span>  
  
 <span data-ttu-id="d80df-120">Después de haber hecho coincidir una propiedad promocionada con una suscripción existente y de haberla utilizado para enrutar un mensaje, se degrada para evitar coincidencias cíclicas con suscripciones.</span><span class="sxs-lookup"><span data-stu-id="d80df-120">After a promoted property has been matched to an existing subscription and used to route a message, the property is demoted to prevent cyclic subscription matches.</span></span> <span data-ttu-id="d80df-121">Una propiedad degradada permanece en el contexto de mensaje como metadatos, pero pierde el estado promocionado.</span><span class="sxs-lookup"><span data-stu-id="d80df-121">A demoted property remains on the message context as metadata but loses its promoted status.</span></span>  
  
 <span data-ttu-id="d80df-122">**Sugerencia para la implementación:** propiedades de contexto de mensaje se cargan en memoria en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d80df-122">**Implementation Tip:** Message context properties are loaded into memory at run time.</span></span> <span data-ttu-id="d80df-123">Muy grandes conjuntos de datos no deben escribirse en el contexto del mensaje porque esto podría impedir potencialmente la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admitir mensajes grandes.</span><span class="sxs-lookup"><span data-stu-id="d80df-123">Very large pieces of data should not be written to the message context because this could potentially break the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] large message support.</span></span> <span data-ttu-id="d80df-124">Los objetos se pueden serializar en el contexto del mensaje siempre que implementen la **IPersistStream** interfaz.</span><span class="sxs-lookup"><span data-stu-id="d80df-124">Objects may be serialized into the message context providing they implement the **IPersistStream** interface.</span></span> <span data-ttu-id="d80df-125">Además, las propiedades promocionadas están limitadas a 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d80df-125">Also, promoted properties are limited to 255 characters.</span></span>  
  
 <span data-ttu-id="d80df-126">Siempre debe utilizarse el generador de mensajes para crear mensajes nuevos.</span><span class="sxs-lookup"><span data-stu-id="d80df-126">The message factory should always be used to create new messages.</span></span>  <span data-ttu-id="d80df-127">El fragmento de código siguiente ilustra cómo se crea un mensaje de BizTalk nuevo a partir de la secuencia de datos recibida por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="d80df-127">The following code fragment illustrates how to create a new BizTalk message from the data stream received by the adapter.</span></span>  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```
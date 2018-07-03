---
title: Adaptadores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c16fc3dd95145d35bd09aeb049d7d38df979e6a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022938"
---
# <a name="adapters"></a><span data-ttu-id="00e24-102">adaptadores</span><span class="sxs-lookup"><span data-stu-id="00e24-102">Adapters</span></span>
<span data-ttu-id="00e24-103">Para intercambiar mensajes con sistemas, aplicaciones y entidades externas, Microsoft BizTalk Server utiliza el concepto de un adaptador.</span><span class="sxs-lookup"><span data-stu-id="00e24-103">To exchange messages with external systems, applications, and entities Microsoft BizTalk Server uses the concept of an adapter.</span></span> <span data-ttu-id="00e24-104">*Adaptadores* son .com o. Componentes basados en red que transfieren mensajes desde y hacia extremos empresariales (como sistemas de archivos, bases de datos y aplicaciones empresariales personalizadas) mediante diversos protocolos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="00e24-104">*Adapters* are COM or .NET-based components that transfer messages to and from business endpoints (such as file systems, databases, and custom business applications) using various communication protocols.</span></span>  
  
 <span data-ttu-id="00e24-105">BizTalk Server utiliza los adaptadores para intercambiar mensajes con entidades externas en operaciones de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="00e24-105">Adapters are used by BizTalk Server to exchange messages with external entities in send and receive operations</span></span>  
  
-   <span data-ttu-id="00e24-106">Las operaciones de envío (o en el lado de envío) se producen cuando BizTalk Server envía información a una entidad externa mediante los protocolos compatibles con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="00e24-106">Send (or send-side) operations occur when information is being sent by BizTalk Server to an external entity using the protocols supported by the adapter.</span></span>  
  
-   <span data-ttu-id="00e24-107">Las operaciones de recepción (o en el lado de recepción) se producen cuando el adaptador recibe información de una entidad externa y la pasa al motor de mensajería de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="00e24-107">Receive (or receive-side) operations occur when the adapter receives information from an external entity and passes it into the BizTalk Server Messaging Engine.</span></span>  
  
## <a name="the-adapter-framework"></a><span data-ttu-id="00e24-108">marco de trabajo del adaptador</span><span class="sxs-lookup"><span data-stu-id="00e24-108">The Adapter Framework</span></span>  
 <span data-ttu-id="00e24-109">En la siguiente ilustración se muestra cómo funcionan el adaptador y el marco de trabajo de adaptadores de forma conjunta para conectar la aplicación con BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="00e24-109">The following figure shows how an adapter and the Adapter Framework work together to connect your application to BizTalk Server.</span></span>  
  
1. <span data-ttu-id="00e24-110">Los datos se reciben a través de una ubicación de recepción que escucha mensajes de un protocolo concreto en una dirección específica.</span><span class="sxs-lookup"><span data-stu-id="00e24-110">Data is received through a receive location that is listening for messages of a certain protocol at a specified address.</span></span> <span data-ttu-id="00e24-111">La ubicación de recepción está asociada con un adaptador y una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="00e24-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="00e24-112">Puede configurar tanto el adaptador como los componentes de canalización para que realicen cierta lógica en los mensajes que tienen un protocolo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="00e24-112">You can configure both the adapter and the pipeline components to perform certain logic on messages having a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="00e24-113">Tras recibir el mensaje la ubicación de recepción, se envía éste al adaptador, que crea un mensaje nuevo de BizTalk Server, agrega la secuencia de datos al mensaje (normalmente al cuerpo del mensaje), agrega cualquier metadato perteneciente al extremo en el que se han recibido los datos y envía dicho mensaje al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="00e24-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk Server message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="00e24-114">El motor de mensajería envía el mensaje a la canalización de recepción donde los datos se transforman en XML, se autentica el remitente del mensaje, se descifra y se valida el código XML.</span><span class="sxs-lookup"><span data-stu-id="00e24-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="00e24-115">El motor de mensajería publica el mensaje en el Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="00e24-115">The Messaging Engine publishes the message to the MessageBox.</span></span> <span data-ttu-id="00e24-116">El Cuadro de mensajes es una tabla de Microsoft SQL Server que contiene mensajes para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="00e24-116">The MessageBox is a Microsoft SQL Server table containing messages to be processed.</span></span> <span data-ttu-id="00e24-117">Tanto las orquestaciones como los puertos de envío se pueden suscribir al Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="00e24-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="00e24-118">El motor de mensajería envía el mensaje a una orquestación o a un suscriptor de puerto de envío según si las propiedades de contexto del mensaje coinciden con las especificaciones establecidas en el filtro del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="00e24-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="00e24-119">Si una orquestación es el suscriptor, procesa el mensaje y lo envía mediante un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="00e24-119">If an orchestration is the subscriber, it processes the message and sends it out using a send port.</span></span> <span data-ttu-id="00e24-120">Una vez que el puerto de envío lo tiene, o si se trata del único suscriptor, el mensaje pasa a través de la canalización de envío a un adaptador de envío antes de transmitirse a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="00e24-120">After the send port has it, or is the only subscriber, the message passes through the send pipeline into a send adapter before being transmitted over the wire.</span></span>  
  
   <span data-ttu-id="00e24-121">marco de trabajo del adaptador</span><span class="sxs-lookup"><span data-stu-id="00e24-121">The Adapter Framework</span></span>  
  
   <span data-ttu-id="00e24-122">![El marco de trabajo de adaptador](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="00e24-122">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
## <a name="receive-adapters"></a><span data-ttu-id="00e24-123">Adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="00e24-123">Receive Adapters</span></span>  
 <span data-ttu-id="00e24-124">Los adaptadores de recepción son los responsables de la creación de un mensaje nuevo de BizTalk Server al adjuntar la secuencia de origen de datos o red al cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="00e24-124">Receive adapters are responsible for creating a new BizTalk Server message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="00e24-125">También agregan todos los metadatos adecuados al extremo en el que se recibieron los datos y, después, envían el mensaje al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="00e24-125">It also adds any metadata pertinent to the endpoint over which the data was received, then submits that message to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="00e24-126">El adaptador elimina los datos del extremo de recepción o envía el mensaje de confirmación correspondiente al cliente indicando que se han aceptado los datos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="00e24-126">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgement message to the client indicating that the data has been accepted into BizTalk Server.</span></span>  
  
## <a name="send-adapters"></a><span data-ttu-id="00e24-127">Adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="00e24-127">Send Adapters</span></span>  
 <span data-ttu-id="00e24-128">Los adaptadores de envío son los responsable del envío de un mensaje de BizTalk Server al extremo especificado mediante su protocolo de transporte específico.</span><span class="sxs-lookup"><span data-stu-id="00e24-128">Send adapters are responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
 <span data-ttu-id="00e24-129">Para obtener más información acerca de los adaptadores, vea la estructura de un adaptador y escribir adaptadores personalizados, [desarrollar adaptadores personalizados](../core/developing-custom-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="00e24-129">For more information about adapters, the structure of an adapter, and writing custom adapters, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e24-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="00e24-130">See Also</span></span>  
 [<span data-ttu-id="00e24-131">Artefactos</span><span class="sxs-lookup"><span data-stu-id="00e24-131">Artifacts</span></span>](../core/artifacts.md)
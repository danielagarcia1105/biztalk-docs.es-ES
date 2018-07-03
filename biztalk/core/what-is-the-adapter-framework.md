---
title: ¿Qué es el marco de trabajo de adaptadores? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7efa468cd21720ae04dc34197f790863fadaeb91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995949"
---
# <a name="what-is-the-adapter-framework"></a><span data-ttu-id="10172-103">¿Qué es el marco de trabajo de adaptadores?</span><span class="sxs-lookup"><span data-stu-id="10172-103">What Is the Adapter Framework?</span></span>
<span data-ttu-id="10172-104">El adaptador de BizTalk Framework ofrece un mecanismo estable y abierto para todos los adaptadores implementen u obtener acceso a trabajo desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="10172-104">The BizTalk Adapter Framework offers a stable, open mechanism for all adapters to implement or access work from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messaging Engine.</span></span> <span data-ttu-id="10172-105">Las interfaces se describen en el **Microsoft.BizTalk.Adapter.Framework** espacio de nombres permiten a los adaptadores proporcionan un medio para modificar las páginas de propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="10172-105">The interfaces described in the **Microsoft.BizTalk.Adapter.Framework** namespace enable adapters to provide a means to modify configuration property pages.</span></span> <span data-ttu-id="10172-106">Además, se trata de un medio para importar servicios y esquemas en el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="10172-106">It also is a means to import services and schemas into the BizTalk project.</span></span>  
  
 <span data-ttu-id="10172-107">En la siguiente ilustración se muestra cómo funcionan conjuntamente un adaptador y el entorno de adaptador para conectar la aplicación a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10172-107">The following figure shows how an adapter and the Adapter Framework work together to connect your application to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="10172-108">![El marco de trabajo de adaptador](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="10172-108">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
 <span data-ttu-id="10172-109">Los siguientes pasos describen la secuencia de pasos indicados en esta ilustración:</span><span class="sxs-lookup"><span data-stu-id="10172-109">The following steps describe the sequence of steps shown in this figure:</span></span>  
  
1. <span data-ttu-id="10172-110">Los datos se reciben desde una ubicación de recepción que escucha mensajes con un protocolo concreto en una dirección específica.</span><span class="sxs-lookup"><span data-stu-id="10172-110">Data is received from a receive location that is listening for messages with a certain protocol at a specified address.</span></span> <span data-ttu-id="10172-111">La ubicación de recepción está asociada con un adaptador y una canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="10172-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="10172-112">Puede configurar el adaptador y los componentes de canalización para llevar a cabo cierta lógica en los mensajes de un protocolo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10172-112">You can configure both the adapter and the pipeline components to perform certain logic on messages of a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="10172-113">Tras recibir el mensaje la ubicación de recepción, se envía éste al adaptador, que crea un mensaje nuevo de BizTalk, agrega la secuencia de datos al mensaje (normalmente al cuerpo del mensaje), agrega cualquier metadato perteneciente al extremo en el que se han recibido los datos y envía dicho mensaje al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="10172-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="10172-114">El motor de mensajería envía el mensaje a la canalización de recepción donde los datos se transforman en XML, se autentica el remitente del mensaje, se descifra y se valida el código XML.</span><span class="sxs-lookup"><span data-stu-id="10172-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="10172-115">El motor de mensajería publica el mensaje en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="10172-115">The Messaging Engine publishes the message to the MessageBox database.</span></span> <span data-ttu-id="10172-116">El cuadro de mensajes es un Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tabla que contiene mensajes para procesarlos.</span><span class="sxs-lookup"><span data-stu-id="10172-116">The MessageBox is a Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] table containing messages to be processed.</span></span> <span data-ttu-id="10172-117">Tanto las orquestaciones como los puertos de envío se pueden suscribir al Cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="10172-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="10172-118">El motor de mensajería envía el mensaje a una orquestación o a un suscriptor de puerto de envío según si las propiedades de contexto del mensaje coinciden con las especificaciones establecidas en el filtro del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="10172-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="10172-119">Si una orquestación es el suscriptor, procesa el mensaje y lo envía a través de un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="10172-119">If an orchestration is the subscriber, it processes the message and sends it out through a send port.</span></span> <span data-ttu-id="10172-120">Si el suscriptor es un envío, el mensaje se transfiere a través de la canalización de envío en un adaptador de envío antes de transmitirlo.</span><span class="sxs-lookup"><span data-stu-id="10172-120">If the subscriber is a send the message passes through the send pipeline into a send adapter before being transmitted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10172-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="10172-121">In This Section</span></span>  
  
-   [<span data-ttu-id="10172-122">Uso de las herramientas de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="10172-122">Using the Adapter Framework Tools</span></span>](../core/using-the-adapter-framework-tools.md)  
  
-   [<span data-ttu-id="10172-123">Patrones de intercambio de mensajes de adaptador</span><span class="sxs-lookup"><span data-stu-id="10172-123">Adapter Message Exchange Patterns</span></span>](../core/adapter-message-exchange-patterns.md)  
  
-   [<span data-ttu-id="10172-124">Componentes del marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="10172-124">Adapter Framework Components</span></span>](../core/adapter-framework-components.md)  
  
-   [<span data-ttu-id="10172-125">Modelo de hospedaje de adaptadores</span><span class="sxs-lookup"><span data-stu-id="10172-125">Adapter Hosting Model</span></span>](../core/adapter-hosting-model.md)  
  
-   [<span data-ttu-id="10172-126">Componentes del adaptador</span><span class="sxs-lookup"><span data-stu-id="10172-126">Adapter Components</span></span>](../core/adapter-components.md)
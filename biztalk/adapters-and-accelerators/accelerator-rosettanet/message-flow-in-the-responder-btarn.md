---
title: Flujo en el Respondedor de BTARN de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629e53f7126c15f84640c8862644beb78e2a5cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980709"
---
# <a name="message-flow-in-the-responder-btarn"></a><span data-ttu-id="3ca6d-102">Flujo de mensajes en el Respondedor de BTARN</span><span class="sxs-lookup"><span data-stu-id="3ca6d-102">Message Flow in the Responder BTARN</span></span>
<span data-ttu-id="3ca6d-103">Inicia el flujo de mensajes en un equipo de servicio de respuesta recibe un mensaje a través de Internet desde el equipo iniciador.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-103">Message flow on a responder computer starts with receiving a message over the Internet from the initiator computer.</span></span> <span data-ttu-id="3ca6d-104">Implica convertir ese mensaje de RosettaNet Implementation Framework (RNIF)-mensaje conforme a un mensaje en el formato de propietario de la aplicación de back-end y, a continuación, enrutar el mensaje a la aplicación de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-104">It involves converting that message from a RosettaNet Implementation Framework (RNIF)-compliant message to a message in the proprietary format of the back-end application, and then routing the message to the line-of-business application.</span></span>  
  
 <span data-ttu-id="3ca6d-105">Si el proceso de interfaz de socio (PIP) es la única acción, la única respuesta es un mensaje de señal de confirmación.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="3ca6d-106">Si el PIP es doble acción, el servicio de respuesta procesar y enviar un mensaje de respuesta y posteriormente, recibirá una confirmación para esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-106">If the PIP is double-action, the responder will process and send a response message, and subsequently receive an acknowledgment for that response.</span></span>  
  
 <span data-ttu-id="3ca6d-107">Si el PIP es asincrónico, se produce cada transmisión de mensajes a través de Internet en una conexión HTTP diferente.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-107">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="3ca6d-108">Si el PIP es sincrónico, se produce cada transmisión del mensaje en la misma conexión, que contiene el adaptador de HTTP hasta que el proceso está completa.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-108">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="3ca6d-109">En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación en el equipo iniciador en respuesta al mensaje de solicitud inicial.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-109">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="3ca6d-110">El mensaje de respuesta sirve como confirmación.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-110">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-responder-computer"></a><span data-ttu-id="3ca6d-111">Componentes BTARN en el equipo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3ca6d-111">BTARN Components on the Responder Computer</span></span>  
 <span data-ttu-id="3ca6d-112">Como un mensaje fluye a través de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo de servicio de respuesta, los siguientes componentes procesará el mensaje:</span><span class="sxs-lookup"><span data-stu-id="3ca6d-112">As a message flows through Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the responder computer, the following components will process the message:</span></span>  
  
- <span data-ttu-id="3ca6d-113">Página de trabajo RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="3ca6d-113">RNIFReceive.aspx page</span></span>  
  
- <span data-ttu-id="3ca6d-114">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="3ca6d-114">HTTP adapter</span></span>  
  
- <span data-ttu-id="3ca6d-115">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="3ca6d-115">Receive pipeline</span></span>  
  
- <span data-ttu-id="3ca6d-116">Proceso público del Respondedor</span><span class="sxs-lookup"><span data-stu-id="3ca6d-116">Responder public process</span></span>  
  
- <span data-ttu-id="3ca6d-117">Proceso privado del Respondedor</span><span class="sxs-lookup"><span data-stu-id="3ca6d-117">Responder private process</span></span>  
  
- <span data-ttu-id="3ca6d-118">Adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="3ca6d-118">SQL adapter</span></span>  
  
- <span data-ttu-id="3ca6d-119">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="3ca6d-119">Send pipeline</span></span>  
  
  <span data-ttu-id="3ca6d-120">Para obtener más información acerca de estos componentes y cómo procesar el mensaje, vea [procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6d-120">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="message-flow-on-the-responder-computer"></a><span data-ttu-id="3ca6d-121">Flujo de mensajes en el equipo de respuesta</span><span class="sxs-lookup"><span data-stu-id="3ca6d-121">Message Flow on the Responder Computer</span></span>  
 <span data-ttu-id="3ca6d-122">El flujo de mensajes de un mensaje recibido a través del servicio de respuesta [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ca6d-122">The message flow of a received message through the responder [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer is as follows:</span></span>  
  
 <span data-ttu-id="3ca6d-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span><span class="sxs-lookup"><span data-stu-id="3ca6d-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span></span>  
  
1. <span data-ttu-id="3ca6d-124">La página de aspx RNIFReceive recibe el mensaje entrante del iniciador.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-124">The RNIFReceive aspx page receives the incoming message from the initiator.</span></span>  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3ca6d-125"> envía el mensaje al adaptador de HTTP, que lo envía a la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-125"> submits the message to the HTTP adapter, which submits it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="3ca6d-126">La canalización de recepción descodifica, desensambla y realiza la resolución de entidades en el mensaje y, a continuación, convierte el mensaje en el formato propietario de la aplicación de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-126">The receive pipeline decodes, disassembles, and performs party resolution on the message, and then converts the message into the proprietary format of the back-end line-of-business application.</span></span>  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3ca6d-127"> enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-127"> routes the message to the MessageBox database.</span></span>  
  
5. <span data-ttu-id="3ca6d-128">El proceso público procesa los encabezados RNIF del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-128">The public process processes the RNIF headers of the message.</span></span>  
  
6. <span data-ttu-id="3ca6d-129">Proceso privado procesa el contenido del mensaje del servicio.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-129">The private process processes the service content of the message.</span></span> <span data-ttu-id="3ca6d-130">Genera una confirmación que se devuelve para el proceso público, la base de datos de cuadro de mensajes, a la canalización de envío y, a continuación, para el adaptador de HTTP para la devolución a través de Internet al iniciador.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-130">It generates an acknowledgement that is returned to the public process, to the MessageBox database, to the send pipeline, and then to the HTTP adapter for return over the Internet to the initiator.</span></span>  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3ca6d-131"> enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-131"> routes the message to the MessageBox database.</span></span>  
  
8. <span data-ttu-id="3ca6d-132">La canalización de envío ensambla y, a continuación, firma o cifra/codifica el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-132">The send pipeline assembles, and then signs/encrypts/encodes the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3ca6d-133"> enruta el mensaje al adaptador de SQL.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-133"> routes the message to the SQL adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3ca6d-134"> envía el mensaje a [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]y a la aplicación de línea de negocio en el back-end.</span><span class="sxs-lookup"><span data-stu-id="3ca6d-134"> submits the message to [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and to the line-of-business application on the back end.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca6d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca6d-135">See Also</span></span>  
 <span data-ttu-id="3ca6d-136">[Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="3ca6d-136">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 [<span data-ttu-id="3ca6d-137">Flujo de mensajes en el iniciador de BTARN</span><span class="sxs-lookup"><span data-stu-id="3ca6d-137">Message Flow in the Initiator BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)
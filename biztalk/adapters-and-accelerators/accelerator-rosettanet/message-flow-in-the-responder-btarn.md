---
title: Flujo en el servicio de respuesta BTARN de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ad33db4f67336f41ac868a7a14e1266a85dd45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-flow-in-the-responder-btarn"></a><span data-ttu-id="d6514-102">Flujo de mensajes en el servicio de respuesta BTARN</span><span class="sxs-lookup"><span data-stu-id="d6514-102">Message Flow in the Responder BTARN</span></span>
<span data-ttu-id="d6514-103">Flujo de mensajes en un equipo de servicio de respuesta se inicia con la recepción de un mensaje a través de Internet desde el equipo del iniciador.</span><span class="sxs-lookup"><span data-stu-id="d6514-103">Message flow on a responder computer starts with receiving a message over the Internet from the initiator computer.</span></span> <span data-ttu-id="d6514-104">Implica convertir ese mensaje de RosettaNet Implementation Framework (RNIF)-mensaje conforme a un mensaje en el formato de propietario de la aplicación de back-end y, a continuación, enrutar el mensaje a la aplicación de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="d6514-104">It involves converting that message from a RosettaNet Implementation Framework (RNIF)-compliant message to a message in the proprietary format of the back-end application, and then routing the message to the line-of-business application.</span></span>  
  
 <span data-ttu-id="d6514-105">Si el proceso de interfaz de socio (PIP) es la única acción, la respuesta sola es un mensaje de señal de confirmación.</span><span class="sxs-lookup"><span data-stu-id="d6514-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="d6514-106">Si el PIP es doble acción, el servicio de respuesta va a procesar y enviar un mensaje de respuesta y posteriormente, recibirá una confirmación de esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="d6514-106">If the PIP is double-action, the responder will process and send a response message, and subsequently receive an acknowledgment for that response.</span></span>  
  
 <span data-ttu-id="d6514-107">Si el PIP es asincrónico, se produce cada transmisión de un mensaje a través de Internet en una conexión HTTP diferente.</span><span class="sxs-lookup"><span data-stu-id="d6514-107">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="d6514-108">Si el PIP es sincrónico, cada transmisión del mensaje se produce en la misma conexión que el adaptador de HTTP contiene hasta que el proceso está completando.</span><span class="sxs-lookup"><span data-stu-id="d6514-108">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="d6514-109">En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación al equipo iniciador en respuesta al mensaje de solicitud inicial.</span><span class="sxs-lookup"><span data-stu-id="d6514-109">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="d6514-110">El mensaje de respuesta sirve como confirmación.</span><span class="sxs-lookup"><span data-stu-id="d6514-110">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-responder-computer"></a><span data-ttu-id="d6514-111">Componentes BTARN en el equipo de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="d6514-111">BTARN Components on the Responder Computer</span></span>  
 <span data-ttu-id="d6514-112">Como un mensaje fluye a través de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo de servicio de respuesta, los siguientes componentes procesarán el mensaje:</span><span class="sxs-lookup"><span data-stu-id="d6514-112">As a message flows through [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the responder computer, the following components will process the message:</span></span>  
  
-   <span data-ttu-id="d6514-113">Página de trabajo RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="d6514-113">RNIFReceive.aspx page</span></span>  
  
-   <span data-ttu-id="d6514-114">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="d6514-114">HTTP adapter</span></span>  
  
-   <span data-ttu-id="d6514-115">Canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="d6514-115">Receive pipeline</span></span>  
  
-   <span data-ttu-id="d6514-116">Proceso público de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="d6514-116">Responder public process</span></span>  
  
-   <span data-ttu-id="d6514-117">Procesos privados del servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="d6514-117">Responder private process</span></span>  
  
-   <span data-ttu-id="d6514-118">Adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="d6514-118">SQL adapter</span></span>  
  
-   <span data-ttu-id="d6514-119">Canalización de envío</span><span class="sxs-lookup"><span data-stu-id="d6514-119">Send pipeline</span></span>  
  
 <span data-ttu-id="d6514-120">Para obtener más información acerca de estos componentes y cómo procesa un mensaje, vea [procesamiento de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span><span class="sxs-lookup"><span data-stu-id="d6514-120">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="message-flow-on-the-responder-computer"></a><span data-ttu-id="d6514-121">Flujo de mensajes en el equipo de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="d6514-121">Message Flow on the Responder Computer</span></span>  
 <span data-ttu-id="d6514-122">El flujo de mensajes de un mensaje recibido mediante el servicio de respuesta [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="d6514-122">The message flow of a received message through the responder [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer is as follows:</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1.  <span data-ttu-id="d6514-123">La página aspx RNIFReceive recibe el mensaje entrante desde el iniciador.</span><span class="sxs-lookup"><span data-stu-id="d6514-123">The RNIFReceive aspx page receives the incoming message from the initiator.</span></span>  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d6514-124">envía el mensaje al adaptador de HTTP, que lo envía a la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d6514-124"> submits the message to the HTTP adapter, which submits it to the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="d6514-125">La canalización de recepción descodifica, desensambla y realiza la resolución de entidades en el mensaje y, a continuación, convierte el mensaje en el formato de propietario de la aplicación de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="d6514-125">The receive pipeline decodes, disassembles, and performs party resolution on the message, and then converts the message into the proprietary format of the back-end line-of-business application.</span></span>  
  
4.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d6514-126">enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d6514-126"> routes the message to the MessageBox database.</span></span>  
  
5.  <span data-ttu-id="d6514-127">El proceso público procesa los encabezados RNIF del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6514-127">The public process processes the RNIF headers of the message.</span></span>  
  
6.  <span data-ttu-id="d6514-128">El proceso privado procesa el contenido del servicio del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6514-128">The private process processes the service content of the message.</span></span> <span data-ttu-id="d6514-129">Genera una confirmación de que se devuelve para el proceso público, la base de datos de cuadro de mensajes, a la canalización de envío y, a continuación, en el adaptador de HTTP de devolución a través de Internet al iniciador.</span><span class="sxs-lookup"><span data-stu-id="d6514-129">It generates an acknowledgement that is returned to the public process, to the MessageBox database, to the send pipeline, and then to the HTTP adapter for return over the Internet to the initiator.</span></span>  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d6514-130">enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d6514-130"> routes the message to the MessageBox database.</span></span>  
  
8.  <span data-ttu-id="d6514-131">La canalización de envío ensambla y, a continuación, firma y cifra/codifica el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d6514-131">The send pipeline assembles, and then signs/encrypts/encodes the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d6514-132">enruta el mensaje al adaptador de SQL.</span><span class="sxs-lookup"><span data-stu-id="d6514-132"> routes the message to the SQL adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d6514-133">envía el mensaje a [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]y a la aplicación de línea de negocio en el back-end.</span><span class="sxs-lookup"><span data-stu-id="d6514-133"> submits the message to [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and to the line-of-business application on the back end.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6514-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6514-134">See Also</span></span>  
 <span data-ttu-id="d6514-135">[Flujo de mensajes de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="d6514-135">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 [<span data-ttu-id="d6514-136">Flujo de mensajes en el iniciador BTARN</span><span class="sxs-lookup"><span data-stu-id="d6514-136">Message Flow in the Initiator BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)
---
title: Flujo en el iniciador de BTARN de mensajes | Microsoft Docs
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
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160f40d4dfd0d11a7bd5a5c7c127d62b3e42a2cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004029"
---
# <a name="message-flow-in-the-initiator-btarn"></a><span data-ttu-id="e2835-102">Flujo de mensajes en el iniciador de BTARN</span><span class="sxs-lookup"><span data-stu-id="e2835-102">Message Flow in the Initiator BTARN</span></span>
<span data-ttu-id="e2835-103">Flujo de mensajes en un equipo iniciador empieza por recibir un mensaje de la aplicación de línea de negocio back-end, en su formato de propietario.</span><span class="sxs-lookup"><span data-stu-id="e2835-103">Message flow on an initiator computer starts with receiving a message from the back-end line-of-business application, in its proprietary format.</span></span> <span data-ttu-id="e2835-104">Implica convertir a un marco de implementación de RosettaNet (RNIF) de ese mensaje-mensaje compatible y, a continuación, enviar el mensaje a través de Internet para el equipo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e2835-104">It involves converting that message to a RosettaNet Implementation Framework (RNIF)-compliant message, and then sending the message over the Internet to the responder computer.</span></span>  
  
 <span data-ttu-id="e2835-105">Si el proceso de interfaz de socio (PIP) es la única acción, la única respuesta es un mensaje de señal de confirmación.</span><span class="sxs-lookup"><span data-stu-id="e2835-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="e2835-106">Para obtener información sobre el flujo de mensajes de acción única, vea "Flujo de un iniciado por mensaje de" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e2835-106">For information about single-action message flow, see "Flow of an Initiated Message" later in this topic.</span></span> <span data-ttu-id="e2835-107">Si el PIP es doble acción, el iniciador recibe un mensaje de respuesta y responde con una confirmación, además del flujo de mensajes de acción única.</span><span class="sxs-lookup"><span data-stu-id="e2835-107">If the PIP is double-action, the initiator will receive a response message, and reply with an acknowledgement, in addition to the single-action message flow.</span></span>  
  
 <span data-ttu-id="e2835-108">Si el PIP es asincrónico, se produce cada transmisión de mensajes a través de Internet en una conexión HTTP diferente.</span><span class="sxs-lookup"><span data-stu-id="e2835-108">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="e2835-109">Si el PIP es sincrónico, se produce cada transmisión del mensaje en la misma conexión, que contiene el adaptador de HTTP hasta que el proceso está completa.</span><span class="sxs-lookup"><span data-stu-id="e2835-109">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="e2835-110">En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación en el equipo iniciador en respuesta al mensaje de solicitud inicial.</span><span class="sxs-lookup"><span data-stu-id="e2835-110">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="e2835-111">El mensaje de respuesta sirve como confirmación.</span><span class="sxs-lookup"><span data-stu-id="e2835-111">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-initiator-computer"></a><span data-ttu-id="e2835-112">Componentes en el equipo iniciador de BTARN</span><span class="sxs-lookup"><span data-stu-id="e2835-112">BTARN Components on the Initiator Computer</span></span>  
 <span data-ttu-id="e2835-113">Como un mensaje fluye a través de [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en el equipo iniciador, los siguientes componentes procesará el mensaje:</span><span class="sxs-lookup"><span data-stu-id="e2835-113">As a message flows through [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the initiator computer, the following components will process the message:</span></span>  
  
- <span data-ttu-id="e2835-114">Adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="e2835-114">SQL adapter</span></span>  
  
- <span data-ttu-id="e2835-115">Canalización de recepción de XML</span><span class="sxs-lookup"><span data-stu-id="e2835-115">XML receive pipeline</span></span>  
  
- <span data-ttu-id="e2835-116">Proceso privado del iniciador</span><span class="sxs-lookup"><span data-stu-id="e2835-116">Initiator private process</span></span>  
  
- <span data-ttu-id="e2835-117">Proceso público del iniciador</span><span class="sxs-lookup"><span data-stu-id="e2835-117">Initiator public process</span></span>  
  
- <span data-ttu-id="e2835-118">Canalización de envío XML</span><span class="sxs-lookup"><span data-stu-id="e2835-118">XML send pipeline</span></span>  
  
- <span data-ttu-id="e2835-119">adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="e2835-119">HTTP adapter</span></span>  
  
- <span data-ttu-id="e2835-120">Página RNIFSend.aspx</span><span class="sxs-lookup"><span data-stu-id="e2835-120">RNIFSend.aspx page</span></span>  
  
  <span data-ttu-id="e2835-121">Para obtener más información acerca de estos componentes y cómo procesar el mensaje, vea [procesamiento de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span><span class="sxs-lookup"><span data-stu-id="e2835-121">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="flow-of-an-initiated-message"></a><span data-ttu-id="e2835-122">Flujo de un mensaje iniciado</span><span class="sxs-lookup"><span data-stu-id="e2835-122">Flow of an Initiated Message</span></span>  
 <span data-ttu-id="e2835-123">Los pasos siguientes describen el flujo de mensajes de un mensaje iniciado por medio del iniciador [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="e2835-123">The following steps describe the message flow of an initiated message through the initiator [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer.</span></span> <span data-ttu-id="e2835-124">En la ilustración siguiente se muestra este proceso.</span><span class="sxs-lookup"><span data-stu-id="e2835-124">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="e2835-125">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")</span><span class="sxs-lookup"><span data-stu-id="e2835-125">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")</span></span>  
  
1. <span data-ttu-id="e2835-126">La aplicación de línea de negocio envía el mensaje a Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2835-126">The line-of-business application sends the message to Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2835-127"> envía el mensaje desde el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos para el adaptador de SQL.</span><span class="sxs-lookup"><span data-stu-id="e2835-127"> sends the message from the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database to the SQL adapter.</span></span>  
  
3. <span data-ttu-id="e2835-128">El XML de recepción canalización hace sencillo validación de XML del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e2835-128">The XML receive pipeline does simple XML validation of the message.</span></span>  
  
4. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e2835-129"> enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e2835-129"> routes the message to the MessageBox database.</span></span>  
  
5. <span data-ttu-id="e2835-130">Proceso privado procesa el contenido del mensaje del servicio.</span><span class="sxs-lookup"><span data-stu-id="e2835-130">The private process processes the service content of the message.</span></span>  
  
6. <span data-ttu-id="e2835-131">El proceso público procesa los encabezados RNIF del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e2835-131">The public process processes the RNIF headers of the message.</span></span>  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2835-132"> enruta el mensaje a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e2835-132"> routes the message back to the MessageBox database.</span></span>  
  
8. <span data-ttu-id="e2835-133">La canalización de envío realiza el ensamblado y firma o cifrado y codificación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e2835-133">The send pipeline performs assembly and signing/encryption/encoding of the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2835-134"> enruta el mensaje al adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2835-134"> routes the message to the HTTP adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2835-135"> enruta el mensaje a la página RNIFSend.aspx, que envía a través de Internet a su destino.</span><span class="sxs-lookup"><span data-stu-id="e2835-135"> routes the message to the RNIFSend.aspx page, which sends it over the Internet to its destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2835-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2835-136">See Also</span></span>  
 <span data-ttu-id="e2835-137">[Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="e2835-137">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 <span data-ttu-id="e2835-138">[Flujo de mensajes en el Respondedor de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="e2835-138">[Message Flow in the Responder BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span></span>  
 [<span data-ttu-id="e2835-139">Procesamiento de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="e2835-139">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)
---
title: Proceso público del iniciador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fa1cd2fc73e37590e25fb381f509c2ad74cd9e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968445"
---
# <a name="initiator-public-process"></a><span data-ttu-id="0e8b6-102">Proceso público del iniciador</span><span class="sxs-lookup"><span data-stu-id="0e8b6-102">Initiator Public Process</span></span>
<span data-ttu-id="0e8b6-103">Este proceso inicia la mensajería de RosettaNet Implementation Framework (RNIF) en el sistema de iniciador creando y enviando el mensaje de negocio RNIF inicial.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-103">This process initiates RosettaNet Implementation Framework (RNIF) messaging on the initiator system by creating and sending the initial RNIF business message.</span></span>  
  
## <a name="message-flow-in-the-initiator-public-process"></a><span data-ttu-id="0e8b6-104">Flujo de mensajes en el proceso público del iniciador</span><span class="sxs-lookup"><span data-stu-id="0e8b6-104">Message Flow in the Initiator Public Process</span></span>  
 <span data-ttu-id="0e8b6-105">El flujo de mensajes a través del proceso público del iniciador es como sigue:</span><span class="sxs-lookup"><span data-stu-id="0e8b6-105">The message flow through the initiator public process is as follows:</span></span>  
  
1. <span data-ttu-id="0e8b6-106">El proceso público del iniciador recibe el contenido del servicio y los datos adjuntos de los procesos privados a través del puerto de contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-106">The initiator public process receives the service content and attachments from the private process through the service-content port.</span></span>  
  
2. <span data-ttu-id="0e8b6-107">El proceso público envía la respuesta al proceso privado y no hace ningún procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-107">The public process sends the response to the private process, and does no further processing.</span></span>  
  
3. <span data-ttu-id="0e8b6-108">Si el proceso público recibe una notificación que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] hizo correctamente no enviar el mensaje, el proceso público envía ese estado al proceso privado del iniciador y, a continuación, finaliza.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-108">If the public process receives notification that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the initiator private process, and then ends.</span></span>  
  
4. <span data-ttu-id="0e8b6-109">Si el proceso público recibe una notificación que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviado correctamente el mensaje, el proceso entra en un estado de espera (espera de una acción mediante el servicio de respuesta).</span><span class="sxs-lookup"><span data-stu-id="0e8b6-109">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the responder).</span></span>  
  
5. <span data-ttu-id="0e8b6-110">Las siguientes acciones pueden finalizar el estado de espera:</span><span class="sxs-lookup"><span data-stu-id="0e8b6-110">The following actions can end the wait state:</span></span>  
  
   1.  <span data-ttu-id="0e8b6-111">El proceso público recibe una señal de confirmación desde el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-111">The public process receives an acknowledgement signal from the responder.</span></span>  
  
        <span data-ttu-id="0e8b6-112">Si sin repudio para la señal es necesarios (como se establece en la configuración del proceso), el proceso lee el resumen, el resumen de la señal correlaciona con la síntesis del mensaje de acción original y, a continuación, continúa la señal.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-112">If non-repudiation for the signal is required (as set in the process configuration settings), the process reads the digest, correlates the digest in the signal with the digest in the original action message, and then persists the signal.</span></span>  
  
        <span data-ttu-id="0e8b6-113">El proceso público envía los encabezados y el contenido del servicio de la señal al proceso privado.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-113">The public process sends the headers and service content of the signal to the private process.</span></span>  
  
   2.  <span data-ttu-id="0e8b6-114">El proceso público recibe un mensaje de respuesta de doble acción desde el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-114">The public process receives a double-action response message from the responder.</span></span>  
  
        <span data-ttu-id="0e8b6-115">El proceso extrae el contenido del servicio y los encabezados del mensaje de respuesta y los envía al proceso privado.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-115">The process extracts the service content and headers from the response message, and sends them to the private process.</span></span>  
  
        <span data-ttu-id="0e8b6-116">Si la actividad es sincrónica, el proceso crea un mensaje de señal RNIF ajustando la parte del mensaje de contenido del servicio con el preámbulo, encabezado de servicio y el encabezado de entrega (para RNIF 2.01).</span><span class="sxs-lookup"><span data-stu-id="0e8b6-116">If the activity is synchronous, the process constructs an RNIF signal message by wrapping the service-content message part with the preamble, service header, and delivery header (for RNIF 2.01).</span></span> <span data-ttu-id="0e8b6-117">El proceso crea el preámbulo y los encabezados con información de configuración acerca de las entidades de origen y destino y las variables PIP almacenadas en el acuerdo entre socios comerciales entre las partes.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-117">The process creates the preamble and headers using configuration information about the source and destination parties, and the PIP variables stored in the trading partner agreement between the parties.</span></span> <span data-ttu-id="0e8b6-118">El proceso, a continuación, envía el mensaje de señal para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-118">The process then sends the signal message to the responder.</span></span>  
  
        <span data-ttu-id="0e8b6-119">Si la actividad es asincrónica, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-119">If the activity is asynchronous, the process ends.</span></span>  
  
   3.  <span data-ttu-id="0e8b6-120">El proceso público recibe un mensaje de notificación de error (ndel) desde el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-120">The public process receives a Notification of Failure (NoF) message from the responder.</span></span> <span data-ttu-id="0e8b6-121">El proceso público, envía un mensaje de estado correspondiente al proceso privado del iniciador.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-121">The public process sends a corresponding status message to the initiator private process.</span></span> <span data-ttu-id="0e8b6-122">Proceso privado, a continuación, controle el error y finaliza ambos procesos.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-122">The private process then handles the error and ends both processes.</span></span>  
  
   4.  <span data-ttu-id="0e8b6-123">El proceso público no recibe una señal de confirmación desde el servicio de respuesta dentro del tiempo período de confirmación (como se establece en la configuración del proceso).</span><span class="sxs-lookup"><span data-stu-id="0e8b6-123">The public process does not receive an acknowledgement signal from the responder within the Time to Acknowledge period (as set in the process configuration settings).</span></span> <span data-ttu-id="0e8b6-124">Si es así, se produce uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e8b6-124">If so, one of the following occurs:</span></span>  
  
        <span data-ttu-id="0e8b6-125">Si el número de reintentos (como se establece en la configuración del proceso) no llegue a cero, y la actividad es asincrónica, el proceso público envía el mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-125">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is asynchronous, the public process sends the message again.</span></span>  
  
        <span data-ttu-id="0e8b6-126">Si el número de reintentos (como se establece en la configuración del proceso) no llegue a cero, y la actividad es sincrónica, el proceso público inicia un mensaje 0A1.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-126">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is synchronous, the public process initiates a 0A1 message.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="0e8b6-127">CIDX no admite mensajes 0A1.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-127">CIDX does not support 0A1 messages.</span></span>  
  
        <span data-ttu-id="0e8b6-128">Si el número de reintentos llega a cero sin un envío correcta, el proceso público envía un mensaje de error y, si esto no es CIDX, el proceso público envía un mensaje 0A1.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-128">If the number of retries reaches zero without a successful send, the public process posts an error message, and if this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
        <span data-ttu-id="0e8b6-129">Si la actividad es sincrónica, y esto no es CIDX, el proceso público inicia un mensaje 0A1.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-129">If the activity is synchronous, and this is not CIDX, the public process initiates a 0A1 message.</span></span>  
  
   5.  <span data-ttu-id="0e8b6-130">Si se realiza ninguna acción dentro del tiempo período realizar, y esto no es CIDX, el proceso público envía un mensaje de 0A1.</span><span class="sxs-lookup"><span data-stu-id="0e8b6-130">If no action occurs within the Time to Perform period, and this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8b6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e8b6-131">See Also</span></span>  
 <span data-ttu-id="0e8b6-132">[Procesos públicos](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="0e8b6-132">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 [<span data-ttu-id="0e8b6-133">Proceso público del respondedor</span><span class="sxs-lookup"><span data-stu-id="0e8b6-133">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)
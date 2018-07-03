---
title: Procesamiento de confirmaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969469"
---
# <a name="acknowledgments-processing"></a><span data-ttu-id="041c8-102">Procesamiento de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="041c8-102">Acknowledgments Processing</span></span>
<span data-ttu-id="041c8-103">La especificación de HL7 admite intercambio de mensajes en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="041c8-103">The HL7 specification supports exchange of messages in two formats:</span></span>  
  
- <span data-ttu-id="041c8-104">Actualización no solicitado y su confirmación (ACK)</span><span class="sxs-lookup"><span data-stu-id="041c8-104">Unsolicited update and its acknowledgment (ACK)</span></span>  
  
- <span data-ttu-id="041c8-105">Consulta y su respuesta</span><span class="sxs-lookup"><span data-stu-id="041c8-105">Query and its response</span></span>  
  
  <span data-ttu-id="041c8-106">En respuesta a un mensaje desde una aplicación iniciadora, la aplicación responde responde con un mensaje que incluye datos o una indicación de error.</span><span class="sxs-lookup"><span data-stu-id="041c8-106">In response to a message from an initiating application, the responding application responds with a message that includes data or an error indication.</span></span> <span data-ttu-id="041c8-107">La aplicación iniciadora puede recibir un estado de rechazo de la aplicación de servicio de respuesta que indica que la aplicación de servicio de respuesta no ha recibido el mensaje correctamente.</span><span class="sxs-lookup"><span data-stu-id="041c8-107">The initiating application may receive a reject status from the responder application indicating that the responder application did not receive the message correctly.</span></span> <span data-ttu-id="041c8-108">En ambos casos, el proceso de intercambio de mensajes implica dos entidades, las aplicaciones de iniciadores y responde.</span><span class="sxs-lookup"><span data-stu-id="041c8-108">In both cases, the process of message exchange involves two entities, the initiating and responding applications.</span></span> <span data-ttu-id="041c8-109">Cada uno es un remitente y receptor de mensajes.</span><span class="sxs-lookup"><span data-stu-id="041c8-109">Each is both a sender and receiver of messages.</span></span> <span data-ttu-id="041c8-110">La aplicación iniciadora envía primero y, a continuación, recibe, mientras que el sistema responde recibe y, a continuación, se envía.</span><span class="sxs-lookup"><span data-stu-id="041c8-110">The initiating application sends first and then receives, while the responding system receives and then sends.</span></span>  
  
## <a name="unsolicited-updates"></a><span data-ttu-id="041c8-111">Actualizaciones no solicitadas</span><span class="sxs-lookup"><span data-stu-id="041c8-111">Unsolicited updates</span></span>  
 <span data-ttu-id="041c8-112">Cuando una aplicación de línea de negocio (LOB) publica un mensaje, o inicia a una transferencia de información cuando se produce un evento de desencadenador, se produce una actualización no solicitada.</span><span class="sxs-lookup"><span data-stu-id="041c8-112">An unsolicited update occurs when a line-of-business (LOB) application publishes a message, or initiates a transfer of information when a trigger event occurs.</span></span> <span data-ttu-id="041c8-113">Por ejemplo, cuando los resultados de laboratorio para un paciente están disponibles, puede haber una necesidad de enviar los resultados de laboratorio a otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="041c8-113">For example, when the laboratory results for a patient are available, there may be a need to send the laboratory results to several other systems.</span></span> <span data-ttu-id="041c8-114">Estas actualizaciones son actualizaciones no solicitadas a la que responde una confirmación.</span><span class="sxs-lookup"><span data-stu-id="041c8-114">These updates are unsolicited updates to which an ACK responds.</span></span>  
  
## <a name="queries"></a><span data-ttu-id="041c8-115">Consultas</span><span class="sxs-lookup"><span data-stu-id="041c8-115">Queries</span></span>  
 <span data-ttu-id="041c8-116">En el caso de una consulta, una aplicación que requiere información envía una consulta a otra aplicación y la aplicación receptora responde a la consulta.</span><span class="sxs-lookup"><span data-stu-id="041c8-116">In the case of a query, an application that requires information sends a query to another application, and the receiving application responds to the query.</span></span> <span data-ttu-id="041c8-117">Por ejemplo, una aplicación de farmacia puede enviar un mensaje de solicitud que contiene el número de identificación del paciente en el sistema de entrada de pedido (CPOE) y recibir una respuesta que contiene los datos necesarios para permitir el procesamiento del pedido.</span><span class="sxs-lookup"><span data-stu-id="041c8-117">For example, a pharmacy application may send a request message containing the ID number of the patient to the Order Entry (CPOE) system and receive a response containing the necessary data to permit processing of the order.</span></span> <span data-ttu-id="041c8-118">Esta transacción solicitante es una consulta y es diferente de una actualización no solicitada.</span><span class="sxs-lookup"><span data-stu-id="041c8-118">This requesting transaction is a query, and is different from an unsolicited update.</span></span> <span data-ttu-id="041c8-119">La información que fluye entre las dos aplicaciones se encuentra en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="041c8-119">The information that flows between the two applications is contained in the response.</span></span> <span data-ttu-id="041c8-120">La propia respuesta no requiere una confirmación con un cuarto mensaje.</span><span class="sxs-lookup"><span data-stu-id="041c8-120">The response itself does not require an acknowledgment with a fourth message.</span></span> <span data-ttu-id="041c8-121">Sin embargo, puede modificar esto en algunos entornos responde con una confirmación.</span><span class="sxs-lookup"><span data-stu-id="041c8-121">However, you can modify this in some environments to respond with an ACK.</span></span> <span data-ttu-id="041c8-122">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responde con una confirmación si está configurado así.</span><span class="sxs-lookup"><span data-stu-id="041c8-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responds with an ACK if so configured.</span></span> <span data-ttu-id="041c8-123">Para obtener un ejemplo de un intercambio de la consulta/respuesta, consulte [Tutorial de interrogación](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="041c8-123">For an example of a query/response exchange, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="041c8-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="041c8-124">In This Section</span></span>  
  
-   [<span data-ttu-id="041c8-125">Validación de mensajes</span><span class="sxs-lookup"><span data-stu-id="041c8-125">Validating Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [<span data-ttu-id="041c8-126">Modos de mensaje de confirmación</span><span class="sxs-lookup"><span data-stu-id="041c8-126">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [<span data-ttu-id="041c8-127">Modelo de procesos de ACK</span><span class="sxs-lookup"><span data-stu-id="041c8-127">ACK Process Model</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)
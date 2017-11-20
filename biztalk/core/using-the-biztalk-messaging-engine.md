---
title: "Motor de uso de la mensajería de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-messaging-engine"></a><span data-ttu-id="c0c48-102">Usar el motor de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c0c48-102">Using the BizTalk Messaging Engine</span></span>
<span data-ttu-id="c0c48-103">El siguiente diagrama ilustra la arquitectura del motor de mensajería y</span><span class="sxs-lookup"><span data-stu-id="c0c48-103">The following diagram illustrates the architecture of the Messaging Engine.</span></span> <span data-ttu-id="c0c48-104">muestra un escenario en el que un mensaje se recibe en un adaptador y se envía a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c0c48-104">It shows a scenario in which a message is received by an adapter and submitted into BizTalk Server.</span></span>  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
<span data-ttu-id="c0c48-105">Arquitectura del motor de mensajería</span><span class="sxs-lookup"><span data-stu-id="c0c48-105">Architecture of the Messaging Engine</span></span>  
  
 <span data-ttu-id="c0c48-106">Cada adaptador tiene su propia instancia de un **TransportProxy** objeto que utiliza para interactuar con el motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="c0c48-106">Each adapter has its own instance of a **TransportProxy** object that it uses to interact with the Messaging Engine.</span></span> <span data-ttu-id="c0c48-107">Los adaptadores funcionan con el motor de mensajería y producen lotes que se procesan de forma atómica.</span><span class="sxs-lookup"><span data-stu-id="c0c48-107">Adapters perform work against the Messaging Engine in batches, which are processed atomically.</span></span> <span data-ttu-id="c0c48-108">Un lote es una colección de operaciones, como SubmitMessage, SuspendMessage o DeleteMessage.</span><span class="sxs-lookup"><span data-stu-id="c0c48-108">A batch is a collection of operations such as SubmitMessage, SuspendMessage, or DeleteMessage.</span></span>  
  
 <span data-ttu-id="c0c48-109">A continuación se muestra la secuencia de eventos de un escenario en el que un adaptador envía un mensaje al motor de mensajería:</span><span class="sxs-lookup"><span data-stu-id="c0c48-109">The following is the sequence of events for the scenario where an adapter submits a message to the Messaging Engine:</span></span>  
  
1.  <span data-ttu-id="c0c48-110">El adaptador crea un nuevo mensaje y conecta la secuencia de datos al mensaje.</span><span class="sxs-lookup"><span data-stu-id="c0c48-110">The adapter creates a new message and connects the data stream to the message.</span></span>  
  
2.  <span data-ttu-id="c0c48-111">El adaptador obtiene un nuevo lote del motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="c0c48-111">The adapter gets a new batch from the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="c0c48-112">El adaptador agrega el mensaje al lote que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="c0c48-112">The adapter adds the message to the batch to be submitted.</span></span>  
  
4.  <span data-ttu-id="c0c48-113">El lote se confirma y se pone en la cola del grupo de subprocesos del motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="c0c48-113">The batch is committed and queued up on the Messaging Engine thread pool.</span></span>  
  
5.  <span data-ttu-id="c0c48-114">El grupo de subprocesos del motor de mensajería empieza a procesar el nuevo lote.</span><span class="sxs-lookup"><span data-stu-id="c0c48-114">The Messaging Engine thread pool starts processing the new batch.</span></span>  
  
6.  <span data-ttu-id="c0c48-115">El mensaje se procesa en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="c0c48-115">The message is processed in the receive pipeline.</span></span>  
  
7.  <span data-ttu-id="c0c48-116">La canalización de recepción produce cero o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="c0c48-116">The receive pipeline produces zero or more messages.</span></span> <span data-ttu-id="c0c48-117">Las canalizaciones pueden consumir mensajes si no devuelven ningún error.</span><span class="sxs-lookup"><span data-stu-id="c0c48-117">Pipelines can consume messages providing they do not return any errors.</span></span> <span data-ttu-id="c0c48-118">Las canalizaciones de recepción pueden producir más de un mensaje; esto ocurre normalmente cuando el componente de desensamblador desensambla un único intercambio en muchos mensajes.</span><span class="sxs-lookup"><span data-stu-id="c0c48-118">Receive pipelines can produce more than one message; typically this happens when the dissassembler component disassembles a single interchange into many messages.</span></span> <span data-ttu-id="c0c48-119">Por lo general, la canalización de recepción normaliza el mensaje enviado a XML.</span><span class="sxs-lookup"><span data-stu-id="c0c48-119">Typically the receive pipeline normalizes the submitted message into XML.</span></span>  
  
8.  <span data-ttu-id="c0c48-120">Los mensajes producidos por la canalización se procesarán en el asignador si está configurada la asignación.</span><span class="sxs-lookup"><span data-stu-id="c0c48-120">The message(s) produced by the pipeline will be processed in the mapper if mapping is configured.</span></span>  
  
9. <span data-ttu-id="c0c48-121">Los mensajes se publican en el agente de mensaje o en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c0c48-121">The message(s) are published to the Message Agent or to the MessageBox database.</span></span>  
  
10. <span data-ttu-id="c0c48-122">El motor de mensajería vuelve a llamar al adaptador para notificarle el resultado del lote de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0c48-122">The Messaging Engine calls back the adapter to notify it of the outcome of the batch of work.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0c48-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0c48-123">In This Section</span></span>  
  
-   [<span data-ttu-id="c0c48-124">Procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="c0c48-124">Recoverable Interchange Processing</span></span>](../core/recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="c0c48-125">Entrega ordenada de mensajes</span><span class="sxs-lookup"><span data-stu-id="c0c48-125">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
  
-   [<span data-ttu-id="c0c48-126">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="c0c48-126">Error Handling</span></span>](../core/error-handling.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0c48-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c48-127">See Also</span></span>  
 <span data-ttu-id="c0c48-128">[Cómo BizTalk Server procesa los mensajes de gran tamaño](../core/how-biztalk-server-processes-large-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c0c48-128">[How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) </span></span>  
 <span data-ttu-id="c0c48-129">[Características de rendimiento del motor](../core/engine-performance-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="c0c48-129">[Engine Performance Characteristics](../core/engine-performance-characteristics.md) </span></span>  
 <span data-ttu-id="c0c48-130">[Medir el rendimiento máximo sostenible del motor](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="c0c48-130">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="c0c48-131">[Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c0c48-131">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="c0c48-132">Con la herramienta de Microsoft BizTalk LoadGen 2007</span><span class="sxs-lookup"><span data-stu-id="c0c48-132">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)
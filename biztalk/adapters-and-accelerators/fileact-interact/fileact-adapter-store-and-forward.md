---
title: Almacenamiento de adaptador FileAct y reenvío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1201a5ab5cb45ceba2622aa1c269404acec910df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223572"
---
# <a name="fileact-adapter-store-and-forward"></a><span data-ttu-id="340d7-102">Almacenamiento de adaptador FileAct y reenvío</span><span class="sxs-lookup"><span data-stu-id="340d7-102">FileAct Adapter Store and Forward</span></span>
<span data-ttu-id="340d7-103">En el almacén y el modo de avance (SnF), los archivos se entregan a poner en cola en el momento de envío y se recuperan de la cola por parte del destino.</span><span class="sxs-lookup"><span data-stu-id="340d7-103">In Store and Forward (SnF) mode, files are delivered to queue at send time, and are retrieved from the queue by the destination.</span></span> <span data-ttu-id="340d7-104">Las respuestas intermedias se devuelven por SWIFTNet al remitente hasta que el archivo de forma segura se entregue en el destino.</span><span class="sxs-lookup"><span data-stu-id="340d7-104">Intermediate responses are returned by SWIFTNet to the sender until the file is safely delivered to the destination.</span></span>  
  
## <a name="sending-using-snf"></a><span data-ttu-id="340d7-105">Envía mediante SnF</span><span class="sxs-lookup"><span data-stu-id="340d7-105">Sending Using SnF</span></span>  
 <span data-ttu-id="340d7-106">Si crea un puerto de envío unidireccional, el adaptador funciona en modo de SnF y envía mensajes a la cola.</span><span class="sxs-lookup"><span data-stu-id="340d7-106">If you create a one-way send port, the adapter works in SnF mode and sends messages to the queue.</span></span>  
  
## <a name="receiving-using-snf"></a><span data-ttu-id="340d7-107">Recibir mediante SnF</span><span class="sxs-lookup"><span data-stu-id="340d7-107">Receiving Using SnF</span></span>  
 <span data-ttu-id="340d7-108">SnF FileAct funciona en modo de inserción.</span><span class="sxs-lookup"><span data-stu-id="340d7-108">SnF FileAct operates in Push mode.</span></span> <span data-ttu-id="340d7-109">Se trata de una opción de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="340d7-109">This is a run-time option.</span></span>  
  
 <span data-ttu-id="340d7-110">Antes de poder recuperar los mensajes de una cola, SWIFTNet SnF debería recibir una solicitud de adquisición de la cola.</span><span class="sxs-lookup"><span data-stu-id="340d7-110">Before being able to retrieve messages from a queue, SWIFTNet SnF should receive a request to acquire the queue.</span></span> <span data-ttu-id="340d7-111">Esto se logra mediante el adaptador de recepción que se invoca el componente COM + fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="340d7-111">This is accomplished by the receive adapter invoking the out-of-proc COM+ component.</span></span> <span data-ttu-id="340d7-112">Después de una adquisición correcta, se crea una sesión.</span><span class="sxs-lookup"><span data-stu-id="340d7-112">After a successful acquire, a session is created.</span></span> <span data-ttu-id="340d7-113">La cola, a continuación, se abrirá en el modo especificado en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="340d7-113">The queue will then be opened in the mode specified in the Request.</span></span> <span data-ttu-id="340d7-114">Todos los mensajes se devolverá el nodo físico que emitió la solicitud.</span><span class="sxs-lookup"><span data-stu-id="340d7-114">All messages will be returned to the physical node which issued the request.</span></span>  
  
 <span data-ttu-id="340d7-115">Los mensajes se entregan en el orden especificado (Observe que las transmisiones de interacción y FileAct pueden intercaladas y organizadas por prioridad). Sin embargo, la secuencia de mensajes, es dependiente en el momento en que están almacenados.</span><span class="sxs-lookup"><span data-stu-id="340d7-115">Messages are delivered in the order specified (note that InterAct and FileAct transmissions can be interspersed, and arranged by priority.) The sequencing of messages, however, is dependent on the time that they were stored.</span></span> <span data-ttu-id="340d7-116">En el caso de FileAct, esto es el tiempo que se complete el almacenamiento en archivo, no cuando inicia.</span><span class="sxs-lookup"><span data-stu-id="340d7-116">In the case of FileAct, this is the time that the file storage is completed, not when it started.</span></span>  
  
### <a name="push-a-file-from-the-queue"></a><span data-ttu-id="340d7-117">Insertar un archivo de la cola</span><span class="sxs-lookup"><span data-stu-id="340d7-117">Push a File From the Queue</span></span>  
 <span data-ttu-id="340d7-118">El adaptador de FileAct (servidor) recibe un HandleFileRequest de SWIFTNet, que contiene la información de la cola, la sesión y la secuencia.</span><span class="sxs-lookup"><span data-stu-id="340d7-118">The FileAct adapter (server) receives a HandleFileRequest from SWIFTNet, containing the queue, session and sequence information.</span></span> <span data-ttu-id="340d7-119">El servidor responde con un HandleFileResponse.</span><span class="sxs-lookup"><span data-stu-id="340d7-119">The server responds with a HandleFileResponse.</span></span>  
  
 <span data-ttu-id="340d7-120">El servidor, a continuación, emite FetchFileRequest y los archivos se entregan al servidor.</span><span class="sxs-lookup"><span data-stu-id="340d7-120">The server then issues FetchFileRequest and the file is delivered to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340d7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="340d7-121">See Also</span></span>  
 <span data-ttu-id="340d7-122">[Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-122">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="340d7-123">[Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-123">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="340d7-124">[Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-124">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="340d7-125">[Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-125">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="340d7-126">[Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-126">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="340d7-127">[Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-127">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="340d7-128">[Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="340d7-128">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="340d7-129">Estado del adaptador de FileAct supervisión</span><span class="sxs-lookup"><span data-stu-id="340d7-129">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
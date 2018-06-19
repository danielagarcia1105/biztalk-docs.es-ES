---
title: Interfaces para una petición-respuesta del adaptador de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb8ce9b625bfea144f9a4a615a604efdbe2a3cb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257604"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a><span data-ttu-id="83773-102">Interfaces de un adaptador de envío de petición-respuesta</span><span class="sxs-lookup"><span data-stu-id="83773-102">Interfaces for a Solicit-Response Send Adapter</span></span>
<span data-ttu-id="83773-103">Los adaptadores de envío utilizan el mismo mecanismo de lotes que los adaptadores de recepción para enviar mensajes de respuesta al servidor.</span><span class="sxs-lookup"><span data-stu-id="83773-103">Send adapters use the same batch mechanism as receive adapters to submit response messages back into the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83773-104">Se recomienda que el adaptador Petición-Respuesta procese mensajes de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="83773-104">It is recommended that a solicit-response adapter is process messages asynchronously.</span></span> <span data-ttu-id="83773-105">Si el adaptador procesa mensajes de manera sincrónica, se corre el riesgo de que se dupliquen los mensajes.</span><span class="sxs-lookup"><span data-stu-id="83773-105">If the adapter processes message in a synchronous manner, there is a risk of message duplication.</span></span>  
  
 <span data-ttu-id="83773-106">Los adaptadores de envío necesitan implementar las interfaces siguientes para funcionar en modo de Petición-Respuesta.</span><span class="sxs-lookup"><span data-stu-id="83773-106">Send adapters need to implement the following interfaces to work in solicit-response mode:</span></span>  
  
-   <span data-ttu-id="83773-107">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="83773-107">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="83773-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="83773-108">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="83773-109">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="83773-109">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="83773-110">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="83773-110">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="83773-111">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="83773-111">**IBTTransmitter**</span></span>  
  
-   <span data-ttu-id="83773-112">**IBTTransmitterBatch** y **IBTBatchTransmitter** (si es necesario el procesamiento por lotes de envío)</span><span class="sxs-lookup"><span data-stu-id="83773-112">**IBTTransmitterBatch** and **IBTBatchTransmitter** (if send batching is required)</span></span>  
  
-   <span data-ttu-id="83773-113">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="83773-113">**IBTBatchCallBack**</span></span>  
  
 <span data-ttu-id="83773-114">Los pasos que conlleva la interacción de objetos se muestran a continuación:</span><span class="sxs-lookup"><span data-stu-id="83773-114">The steps involved in the object interaction are as follows:</span></span>  
  
1.  <span data-ttu-id="83773-115">Cuando el adaptador envía un mensaje de petición, recibe un mensaje de respuesta del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="83773-115">After the adapter sends a solicit message, it receives back a response message from that destination server.</span></span> <span data-ttu-id="83773-116">A continuación, obtiene un lote del proxy de transporte.</span><span class="sxs-lookup"><span data-stu-id="83773-116">It then obtains a batch from the transport proxy.</span></span>  
  
2.  <span data-ttu-id="83773-117">El adaptador agrega el mensaje de respuesta al lote mediante una llamada a **ibttransportproxy:: Submitresponsemessage**.</span><span class="sxs-lookup"><span data-stu-id="83773-117">The adapter adds the response message to the batch by calling **IBTTransportProxy::SubmitResponseMessage**.</span></span>  
  
3.  <span data-ttu-id="83773-118">El adaptador envía el lote mediante una llamada a **ibttransportproxy:: Done** pasando un puntero a su **IBTBatchComplete** interfaz para la devolución de llamada del motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="83773-118">The adapter submits the batch by calling **IBTTransportProxy::Done** passing in a pointer to its **IBTBatchComplete** interface for the callback from the Messaging Engine.</span></span>  
  
4.  <span data-ttu-id="83773-119">El motor de mensajería llama el adaptador **ibtbatchcallback::** método de devolución de llamada mediante el proxy de transporte que se le notifica que el resultado de la operación de envío.</span><span class="sxs-lookup"><span data-stu-id="83773-119">The Messaging Engine calls the adapter's **IBTBatchCallBack::BatchComplete** callback method using the transport proxy notifying it of the result of submission operation.</span></span>  
  
 <span data-ttu-id="83773-120">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de envío Petición-Respuesta.</span><span class="sxs-lookup"><span data-stu-id="83773-120">The following figure shows the object interactions involved in creating a solicit-response send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
<span data-ttu-id="83773-121">Diagrama de interacción para un adaptador de envío Petición-Respuesta</span><span class="sxs-lookup"><span data-stu-id="83773-121">Interaction diagram for a solicit-response send adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83773-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="83773-122">See Also</span></span>  
 <span data-ttu-id="83773-123">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="83773-123">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="83773-124">[Desarrollar un adaptador de envío](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-124">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="83773-125">[Crear instancias e inicializar un adaptador de envío](../core/instantiating-and-initializing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-125">[Instantiating and Initializing a Send Adapter](../core/instantiating-and-initializing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="83773-126">[Interfaces de un envío sincrónico adaptador](../core/interfaces-for-a-synchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-126">[Interfaces for a Synchronous Send Adapter](../core/interfaces-for-a-synchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="83773-127">[Adaptador de envío de interfaces para una asincrónica](../core/interfaces-for-an-asynchronous-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-127">[Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md) </span></span>  
 <span data-ttu-id="83773-128">[Interfaces para un adaptador de envío sincrónico compatible con lotes](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-128">[Interfaces for a Synchronous Batch-Supported Send Adapter](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md) </span></span>  
 <span data-ttu-id="83773-129">[Interfaces de un adaptador de envío asíncrono compatible con lotes](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="83773-129">[Interfaces for an Asynchronous Batch-Supported Send Adapter](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md) </span></span>  
 [<span data-ttu-id="83773-130">Interfaces para un adaptador de envío asincrónica transaccional compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="83773-130">Interfaces for a Transactional Asynchronous Batch-Supported Send Adapter</span></span>](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)
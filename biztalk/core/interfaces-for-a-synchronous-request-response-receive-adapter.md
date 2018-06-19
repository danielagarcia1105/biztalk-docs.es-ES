---
title: Interfaces para una solicitud-respuesta sincrónico del adaptador de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9abd84bab5da623c2dff61c6e07a5898110588af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257812"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a><span data-ttu-id="295b0-102">Interfaces de un adaptador de recepción sincrónico de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="295b0-102">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>
<span data-ttu-id="295b0-103">Todos los adaptadores de recepción necesitan implementar las interfaces siguientes para funcionar en modo de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="295b0-103">All receive adapters need to implement the following interfaces to work in request-response mode:</span></span>  
  
-   <span data-ttu-id="295b0-104">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="295b0-104">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="295b0-105">**IBTTransportControl** (solo adaptadores normales)</span><span class="sxs-lookup"><span data-stu-id="295b0-105">**IBTTransportControl** (regular adapters only)</span></span>  
  
-   <span data-ttu-id="295b0-106">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="295b0-106">**IBTTransportConfig**</span></span>  
  
-   <span data-ttu-id="295b0-107">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="295b0-107">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="295b0-108">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="295b0-108">**IPersistPropertyBag**</span></span>  
  
-   <span data-ttu-id="295b0-109">**IBTBatchCallBack**</span><span class="sxs-lookup"><span data-stu-id="295b0-109">**IBTBatchCallBack**</span></span>  
  
-   <span data-ttu-id="295b0-110">**IBTTransmitter**</span><span class="sxs-lookup"><span data-stu-id="295b0-110">**IBTTransmitter**</span></span>  
  
 <span data-ttu-id="295b0-111">Los adaptadores de recepción que admiten protocolos de solicitud-respuesta (por ejemplo, el adaptador de recepción HTTP) llevan a cabo las acciones siguientes al enviar mensajes de solicitud:</span><span class="sxs-lookup"><span data-stu-id="295b0-111">Receive adapters that support request-response protocols (for example, the HTTP receive adapter) perform the following actions when submitting request messages:</span></span>  
  
1.  <span data-ttu-id="295b0-112">El adaptador de recepción recibe los mensajes de solicitud entrantes.</span><span class="sxs-lookup"><span data-stu-id="295b0-112">The receive adapter receives incoming request messages.</span></span> <span data-ttu-id="295b0-113">Obtiene un lote del proxy de transporte mediante una llamada a la **GetBatch** método de la **IBTTransportProxy** interfaz.</span><span class="sxs-lookup"><span data-stu-id="295b0-113">It obtains a batch from the transport proxy by calling the **GetBatch** method of the **IBTTransportProxy** interface.</span></span> <span data-ttu-id="295b0-114">En esta llamada el adaptador pasa un puntero de devolución de llamada para su implementación de la **IBTBatchCallBack.BatchComplete** método.</span><span class="sxs-lookup"><span data-stu-id="295b0-114">In this call the adapter passes in a callback pointer to its implementation of the **IBTBatchCallBack.BatchComplete** method.</span></span>  
  
2.  <span data-ttu-id="295b0-115">El adaptador agrega mensajes de solicitud en el lote mediante una llamada a la **SubmitRequestMessage** método de la **IBTTransportBatch** interfaz, una vez para cada mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="295b0-115">The adapter adds request messages into the batch by calling the **SubmitRequestMessage** method of the **IBTTransportBatch** interface, once for each request message.</span></span>  
  
3.  <span data-ttu-id="295b0-116">Cuando se han agregado todos los mensajes, el adaptador llama a la **realiza**método de la **IBTTransportBatch** interfaz, que envía el lote al motor de mensajería a través del proxy de transporte.</span><span class="sxs-lookup"><span data-stu-id="295b0-116">When all the messages have been added, the adapter calls the **Done**method of the **IBTTransportBatch** interface, which submits the batch to the Messaging Engine through the transport proxy.</span></span>  
  
4.  <span data-ttu-id="295b0-117">Una vez que se ha procesado el lote, el motor de mensajería invoca el adaptador **IBTBatchCallBack.BatchComplete** método de devolución de llamada a través del proxy de transporte.</span><span class="sxs-lookup"><span data-stu-id="295b0-117">After the batch has been processed, the Messaging Engine invokes the adapter's **IBTBatchCallBack.BatchComplete** callback method through the transport proxy.</span></span> <span data-ttu-id="295b0-118">El estado del envío se pasa al adaptador en forma de matriz de valores HRESULT correspondientes a cada mensaje del lote.</span><span class="sxs-lookup"><span data-stu-id="295b0-118">The status of the submission is passed to the adapter as an array of HRESULT values corresponding to each message in the batch.</span></span> <span data-ttu-id="295b0-119">Si se produce un error en el lote, ya sea en la canalización o en la orquestación, se devuelve al adaptador el mensaje de error SOAP como respuesta.</span><span class="sxs-lookup"><span data-stu-id="295b0-119">If the batch fails, either in the pipeline or in the orchestration, the SOAP fault message is returned to the adapter as a response.</span></span>  
  
5.  <span data-ttu-id="295b0-120">Los mensajes de solicitud entrantes pueden tener suscriptores de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="295b0-120">The incoming request messages may have orchestration subscribers.</span></span> <span data-ttu-id="295b0-121">Después de finalizar la orquestación y se ha procesado el mensaje de solicitud, el motor de mensajería envía el mensaje de respuesta a través del proxy de transporte para el adaptador mediante una llamada del adaptador **TransmitMessage** método desde el  **IBTTransmitter** interfaz.</span><span class="sxs-lookup"><span data-stu-id="295b0-121">After the orchestration completes and the request message has been processed, the Messaging Engine sends the response message through the transport proxy to the adapter by calling the adapter's **TransmitMessage** method from the **IBTTransmitter** interface.</span></span>  
  
6.  <span data-ttu-id="295b0-122">El adaptador envía un mensaje de respuesta y elimina el mensaje original de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="295b0-122">The adapter sends a response message and deletes the original message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="295b0-123">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción sincrónico de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="295b0-123">The following figure shows the object interactions involved in creating a synchronous request-response receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
<span data-ttu-id="295b0-124">Flujo de trabajo de un adaptador de recepción que envía un mensaje sincrónico</span><span class="sxs-lookup"><span data-stu-id="295b0-124">Workflow for a receive adapter submitting a synchronous message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295b0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="295b0-125">See Also</span></span>  
 <span data-ttu-id="295b0-126">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-126">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="295b0-127">[Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-127">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="295b0-128">[Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-128">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="295b0-129">[Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-129">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="295b0-130">[Adaptador de recepción de interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-130">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="295b0-131">[Adaptador de recepción de interfaces para un compatible con lotes](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="295b0-131">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="295b0-132">Adaptador de recepción de interfaces para transaccional compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="295b0-132">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)
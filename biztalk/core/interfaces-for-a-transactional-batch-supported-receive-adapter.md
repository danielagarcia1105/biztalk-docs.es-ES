---
title: Interfaces para transaccional compatible con lotes del adaptador de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b51a67f63f3088ce64c9db35c368289ce156d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257580"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a><span data-ttu-id="62971-102">Interfaces de un adaptador de recepción transaccional compatible con lotes</span><span class="sxs-lookup"><span data-stu-id="62971-102">Interfaces for a Transactional Batch-Supported Receive Adapter</span></span>
<span data-ttu-id="62971-103">Un adaptador de recepción crea y controla transacciones cuando se necesita un envío de mensajes transaccional.</span><span class="sxs-lookup"><span data-stu-id="62971-103">A receive adapter creates and controls transactions when the transactional submission of messages is required.</span></span>  
  
 <span data-ttu-id="62971-104">Recepción transaccional adaptador crea y pasa un puntero a una transacción del Coordinador de transacciones distribuidas de Microsoft (MSDTC) en el **realiza** método de la **IBTTransportBatch** interfaz.</span><span class="sxs-lookup"><span data-stu-id="62971-104">A transactional receive adapter creates and passes a pointer to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction on the **Done** method of the **IBTTransportBatch** interface.</span></span> <span data-ttu-id="62971-105">Esto garantiza que todas las operaciones del lote se realicen en el ámbito de dicho objeto de transacción específico.</span><span class="sxs-lookup"><span data-stu-id="62971-105">This ensures that all batch operations are performed in the scope of that specific transaction object.</span></span> <span data-ttu-id="62971-106">Cuando se completa el envío del lote, el método de devolución de llamada del adaptador confirma o revierte la transacción.</span><span class="sxs-lookup"><span data-stu-id="62971-106">When the batch submission completes, the adapter callback method commits or rolls back the transaction.</span></span> <span data-ttu-id="62971-107">La acción que se realiza depende del estado devuelto desde el proxy de transporte y, probablemente, de otro trabajo relacionado con la transacción que realiza el adaptador y que no es visible para el proxy de transporte.</span><span class="sxs-lookup"><span data-stu-id="62971-107">Which action it takes depends upon the status returned from the transport proxy, and possibly upon other transaction-related work that the adapter does that is not visible to the transport proxy.</span></span> <span data-ttu-id="62971-108">El adaptador determina si la transacción es errónea o correcta.</span><span class="sxs-lookup"><span data-stu-id="62971-108">The adapter determines whether the transaction failed or succeeded.</span></span> <span data-ttu-id="62971-109">El adaptador informa del resultado de la transacción (confirma o revierte) al proxy de transporte mediante el uso de la **DTCCommitConfirm** método de la**IBTDTCCommitConfirm** interfaz.</span><span class="sxs-lookup"><span data-stu-id="62971-109">The adapter reports the result of the transaction (commit or rollback) back to the transport proxy by using the **DTCCommitConfirm** method of the**IBTDTCCommitConfirm** interface.</span></span> <span data-ttu-id="62971-110">Pasa un valor en `true` para una transacción correcta o `false` para un error.</span><span class="sxs-lookup"><span data-stu-id="62971-110">It passes in `true` for a successful transaction or `false` for a failure.</span></span>  
  
 <span data-ttu-id="62971-111">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción transaccional compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="62971-111">The following figure shows the object interactions involved in creating a transactional batch-supported receive adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
<span data-ttu-id="62971-112">Flujo de trabajo de un adaptador de recepción que envía un lote de mensajes mediante transacciones DTC</span><span class="sxs-lookup"><span data-stu-id="62971-112">Workflow for a receive adapter submitting a batch of messages using DTC transactions</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62971-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="62971-113">See Also</span></span>  
 <span data-ttu-id="62971-114">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="62971-114">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="62971-115">[Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="62971-115">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="62971-116">[Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="62971-116">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="62971-117">[Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="62971-117">[Interfaces for an In-Process Receive Adapter](../core/interfaces-for-an-in-process-receive-adapter.md) </span></span>  
 <span data-ttu-id="62971-118">[Adaptador de recepción de interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="62971-118">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="62971-119">[Adaptador de recepción de interfaces para un compatible con lotes](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="62971-119">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="62971-120">Adaptador de recepción de interfaces para una solicitud-respuesta sincrónico</span><span class="sxs-lookup"><span data-stu-id="62971-120">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)
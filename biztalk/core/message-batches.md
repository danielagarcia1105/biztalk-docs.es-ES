---
title: Lotes de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13936fc06807d0bdc4f8e13dbd7742919dc894b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990701"
---
# <a name="message-batches"></a><span data-ttu-id="de68d-102">Lotes de mensajes</span><span class="sxs-lookup"><span data-stu-id="de68d-102">Message Batches</span></span>
<span data-ttu-id="de68d-103">Cuando el adaptador tiene un grupo de mensajes que hay que procesar al mismo tiempo, debe dividir estos mensajes en lotes para optimizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="de68d-103">When your adapter has a group of messages that need to be processed at one time, you should batch these messages to optimize performance.</span></span> <span data-ttu-id="de68d-104">Mediante programación, los lotes de mensajes consisten en colecciones de mensajes con una operación asociada.</span><span class="sxs-lookup"><span data-stu-id="de68d-104">Programmatically, message batches are collections of messages with an associated operation.</span></span> <span data-ttu-id="de68d-105">Agrupar los mensajes en un lote en lugar de enviar los mensajes de forma individual, optimizar el uso de recursos y tareas de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="de68d-105">By grouping messages in a batch rather than submitting each message individually, you optimize the use of resources and processing tasks.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="de68d-106"> usa el procesamiento por lotes para:</span><span class="sxs-lookup"><span data-stu-id="de68d-106"> uses batching to:</span></span>  

- <span data-ttu-id="de68d-107">Amortizar el costo de las transacciones entre varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="de68d-107">Amortize the cost of the transaction across many messages.</span></span>  

- <span data-ttu-id="de68d-108">Aumentar la velocidad mediante la reducción del número interno de ciclos de ida y vuelta de base de datos.</span><span class="sxs-lookup"><span data-stu-id="de68d-108">Increase speed by reducing the internal number of database round trips.</span></span>  

- <span data-ttu-id="de68d-109">Hacen un uso más eficaz de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de subprocesos procesando los mensajes de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="de68d-109">Make more efficient use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] thread pool by processing the messages asynchronously.</span></span>  

  <span data-ttu-id="de68d-110">Un lote es una unidad de trabajo atómica.</span><span class="sxs-lookup"><span data-stu-id="de68d-110">A batch is a unit of work that is atomic.</span></span> <span data-ttu-id="de68d-111">Es decir, todas las operaciones que contiene se realizan correctamente o se producen errores en todas.</span><span class="sxs-lookup"><span data-stu-id="de68d-111">That is, either all operations in it succeed or all operations in it fail.</span></span> <span data-ttu-id="de68d-112">Si una operación en un lote se realiza correctamente pero se producen errores en otra operación, todas las operaciones que componen el lote quedan invalidadas y los mensajes deben volver a enviarse.</span><span class="sxs-lookup"><span data-stu-id="de68d-112">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and the messages must be resubmitted.</span></span> <span data-ttu-id="de68d-113">Ello significa que un adaptador debe realizar tres operaciones en respuesta a un lote con errores:</span><span class="sxs-lookup"><span data-stu-id="de68d-113">This means that an adapter must do three things in response to a failed batch:</span></span>  

- <span data-ttu-id="de68d-114">Determinar qué mensajes tienen errores.</span><span class="sxs-lookup"><span data-stu-id="de68d-114">Determine which messages failed.</span></span>  

- <span data-ttu-id="de68d-115">Decidir qué hacer con los mensajes con errores.</span><span class="sxs-lookup"><span data-stu-id="de68d-115">Decide what to do with the failed messages.</span></span>  

- <span data-ttu-id="de68d-116">Volver a enviar los mensajes sin errores.</span><span class="sxs-lookup"><span data-stu-id="de68d-116">Resubmit the messages that did not fail.</span></span>

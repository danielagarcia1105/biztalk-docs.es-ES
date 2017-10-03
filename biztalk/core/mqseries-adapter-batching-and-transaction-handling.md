---
title: MQSeries control de transacciones y procesamiento por lotes de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffcdec02c464b9398acbece35657e0c3d1dc4432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a><span data-ttu-id="ecf78-102">Control de transacciones y procesamiento por lotes del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ecf78-102">MQSeries Adapter Batching and Transaction Handling</span></span>
<span data-ttu-id="ecf78-103">El adaptador de MQSeries detiene una transacción sólo si no recibe todos los datos.</span><span class="sxs-lookup"><span data-stu-id="ecf78-103">The MQSeries adapter stops a transaction only if it does not receive all the data.</span></span> <span data-ttu-id="ecf78-104">Los límites de una transacción para el adaptador son el extremo del adaptador (cola de MQSeries en el servidor MQSeries) y la base de datos de cuadro de  mensajes.</span><span class="sxs-lookup"><span data-stu-id="ecf78-104">The boundaries of a transaction for the adapter are the adapter endpoint (MQSeries queue on the MQSeries Server) and the MessageBox database.</span></span>  
  
 <span data-ttu-id="ecf78-105">Si la aplicación de BizTalk invalida un mensaje, el adaptador mueve el mensaje a la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="ecf78-105">If the BizTalk application invalidates a message, the adapter moves the message to the suspended queue.</span></span> <span data-ttu-id="ecf78-106">No obstante, puesto que aun entonces es una transacción válida desde el punto de vista del adaptador (el adaptador recibió todos los datos), el adaptador confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="ecf78-106">However, because it is still a valid transaction from the point of view of the adapter (the adapter received all the data), the adapter commits the transaction.</span></span>  
  
 <span data-ttu-id="ecf78-107">Se puede controlar el tratamiento de transacciones y procesamiento por lotes estableciendo propiedades al configurar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ecf78-107">You can control batching and transaction handling by setting properties when configuring the adapter.</span></span> <span data-ttu-id="ecf78-108">Para obtener más información, consulte [configurar el adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="ecf78-108">For more information, see [Configuring the MQSeries Adapter](../core/configuring-the-mqseries-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf78-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf78-109">See Also</span></span>  
 [<span data-ttu-id="ecf78-110">Propiedades del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="ecf78-110">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)
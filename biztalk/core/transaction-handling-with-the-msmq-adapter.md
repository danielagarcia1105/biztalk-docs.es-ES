---
title: Control de transacciones con el adaptador de MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, transaction handling
- transactions, MSMQ adapters
ms.assetid: 2e5dd0da-3852-48bf-9372-b019ecab23be
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55494175029fd8edda1a457298af1d829be3087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980925"
---
# <a name="transaction-handling-with-the-msmq-adapter"></a><span data-ttu-id="5e6af-102">Control de transacciones con el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="5e6af-102">Transaction Handling with the MSMQ Adapter</span></span>
<span data-ttu-id="5e6af-103">En esta sección se analiza la forma en la que funcionan las transacciones en el envío y la recepción.</span><span class="sxs-lookup"><span data-stu-id="5e6af-103">This section discusses how transactions work in receiving and sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e6af-104">Para el adaptador MSMQ, una transacción se extiende desde la base de datos de cuadro de mensajes de BizTalk a la cola de Message Queue Server local, aun si se utiliza una cola remota.</span><span class="sxs-lookup"><span data-stu-id="5e6af-104">For the MSMQ adapter, a transaction extends from the BizTalk MessageBox database to the local Message Queuing queue even if you are using a remote queue.</span></span>  
  
 <span data-ttu-id="5e6af-105">Es posible utilizar transacciones tanto en el envío como en la recepción con el adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="5e6af-105">You can use transactions on both send and receive with the MSMQ adapter.</span></span> <span data-ttu-id="5e6af-106">En envíos de transacción, el adaptador acumula mensajes hasta que tiene un lote completo.</span><span class="sxs-lookup"><span data-stu-id="5e6af-106">On transacted sends, the adapter accumulates messages until it has a complete batch.</span></span> <span data-ttu-id="5e6af-107">Seguidamente, el adaptador envía el lote al servicio Message Queue Server local como una sola transacción.</span><span class="sxs-lookup"><span data-stu-id="5e6af-107">The adapter then submits the batch to the local Message Queuing service as a single transaction.</span></span> <span data-ttu-id="5e6af-108">Si el envío no se realiza correctamente, el adaptador intenta reenviar el lote.</span><span class="sxs-lookup"><span data-stu-id="5e6af-108">If the submission fails, the adapter tries to resubmit the batch.</span></span> <span data-ttu-id="5e6af-109">Si el reenvío no se efectúa correctamente, el adaptador se mueve al transporte secundario.</span><span class="sxs-lookup"><span data-stu-id="5e6af-109">If the resubmission fails, the adapter moves to the secondary transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e6af-110">El adaptador admite las lecturas transaccionales de colas remotas únicamente con Message Queue Server 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5e6af-110">The adapter supports transactional reads of remote queues with Message Queuing 4.0 or later only.</span></span> <span data-ttu-id="5e6af-111">En este escenario el servidor BizTalk Server y el servidor remoto de Message Queue Server deben estar ejecutando Message Queue Server 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5e6af-111">In this scenario both the BizTalk Server and the remote Message Queuing server must be running Message Queuing 4.0 or later.</span></span>  
  
 <span data-ttu-id="5e6af-112">En las recepciones de transacción, el adaptador suspende los mensajes con errores para que, de este modo, no pierda ninguno de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e6af-112">On transacted receives, the adapter suspends failed messages so that it does not lose any one of the messages.</span></span> <span data-ttu-id="5e6af-113">Durante una recepción de transacción, el adaptador agrega mensajes a un lote hasta que éste se completa.</span><span class="sxs-lookup"><span data-stu-id="5e6af-113">During a transacted receive the adapter adds messages to a batch until the batch is complete.</span></span> <span data-ttu-id="5e6af-114">A continuación, envía el lote:</span><span class="sxs-lookup"><span data-stu-id="5e6af-114">It then submits the batch:</span></span>  
  
- <span data-ttu-id="5e6af-115">Si no hay ningún problema y el servidor recibe los mensajes, el adaptador confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="5e6af-115">If there are no problems and the server receives the messages, the adapter commits the transaction.</span></span>  
  
- <span data-ttu-id="5e6af-116">Si hay algún problema, el adaptador crea un nuevo lote como parte de la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="5e6af-116">If there are problems, the adapter creates a new batch as part of the current transaction.</span></span> <span data-ttu-id="5e6af-117">Seguidamente, mueve todos los mensajes que presenten problemas al nuevo lote.</span><span class="sxs-lookup"><span data-stu-id="5e6af-117">It then moves any problem messages into the new batch.</span></span> <span data-ttu-id="5e6af-118">A continuación, reenvía el primer lote y envía el nuevo lote como mensajes suspendidos.</span><span class="sxs-lookup"><span data-stu-id="5e6af-118">It then resubmits the first batch and submits the new batch as suspended messages.</span></span> <span data-ttu-id="5e6af-119">El adaptador confirma la transacción si no hay ningún problema durante este reenvío.</span><span class="sxs-lookup"><span data-stu-id="5e6af-119">The adapter commits the transaction if there are no problems during this resubmission.</span></span>  
  
  <span data-ttu-id="5e6af-120">Si se ejecuta un controlador de envío de adaptador de MSMQ en una instancia agrupada de host de BizTalk, se debería agrupar el servicio MSMQ en el mismo grupo de clúster para garantizar la coherencia transaccional.</span><span class="sxs-lookup"><span data-stu-id="5e6af-120">If you are running an MSMQ adapter send handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to ensure transactional consistency.</span></span>  
  
  <span data-ttu-id="5e6af-121">Si se deshabilita el "Acceso a DTC desde la red" en la utilidad DCOMCNFG, se producirá un error en operación de recepción remota de transacciones MSMQ y creará un mensaje de error críptico.</span><span class="sxs-lookup"><span data-stu-id="5e6af-121">If "Network DTC Access" is disabled in the DCOMCNFG utility, a MSMQ transactional remote receive operation will fail with a cryptic error message.</span></span>  <span data-ttu-id="5e6af-122">Para efectuar una recepción remota de transacciones con el adaptador de MSMQ, debe estar habilitado "Acceso a DTC desde la red".</span><span class="sxs-lookup"><span data-stu-id="5e6af-122">To do a transactional remote receive with the MSMQ adapter, "Network DTC Access" must be enabled.</span></span> <span data-ttu-id="5e6af-123">Puede encontrar más información en [ http://go.microsoft.com/fwlink/?LinkId=124623 ](http://go.microsoft.com/fwlink/?LinkId=124623).</span><span class="sxs-lookup"><span data-stu-id="5e6af-123">More information can be found at [http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623).</span></span>  
  
  <span data-ttu-id="5e6af-124">Si se ejecuta un controlador de recepción del adaptador de MSMQ en una instancia agrupada de host de BizTalk, se debería agrupar el servicio MSMQ en el mismo grupo de clúster para admitir lecturas de transacción locales, puesto que MSMQ no admite lecturas transaccionales remotas.</span><span class="sxs-lookup"><span data-stu-id="5e6af-124">If you are running an MSMQ adapter receive handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to support local transacted reads because MSMQ does not support remote transactional reads.</span></span> <span data-ttu-id="5e6af-125">Para obtener más información sobre la ejecución de controladores del adaptador de MSMQ en una instancia agrupada de Host de BizTalk, consulte [consideraciones para ejecutar controladores de adaptador en un Host agrupado](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span><span class="sxs-lookup"><span data-stu-id="5e6af-125">For more information about running MSMQ adapter handlers in a clustered instance of a BizTalk Host, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6af-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e6af-126">See Also</span></span>  
 [<span data-ttu-id="5e6af-127">Mensajería confiable con el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="5e6af-127">Reliable Messaging with the MSMQ Adapter</span></span>](../core/reliable-messaging-with-the-msmq-adapter.md)
---
title: Estructura del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278500"
---
# <a name="structure-of-the-mqseries-adapter"></a><span data-ttu-id="37b80-102">Estructura del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="37b80-102">Structure of the MQSeries Adapter</span></span>
<span data-ttu-id="37b80-103">El adaptador de MQSeries tiene dos partes: el adaptador que se ejecuta bajo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y una aplicación COM +, MQSAgent, que se ejecuta en MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="37b80-103">The MQSeries adapter has two parts: the adapter running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and a COM+ application, MQSAgent, running under MQSeries Server for Windows.</span></span> <span data-ttu-id="37b80-104">Esta relación se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b80-104">The following figure shows this relationship.</span></span>  
  
 <span data-ttu-id="37b80-105">![Componentes de adaptador de MQSeries](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span><span class="sxs-lookup"><span data-stu-id="37b80-105">![MQSeries Adapter components](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span></span>  
  
 <span data-ttu-id="37b80-106">El adaptador se comunica con la aplicación MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="37b80-106">The adapter communicates with the MQSAgent application.</span></span> <span data-ttu-id="37b80-107">La aplicación MQSAgent, a su vez, se comunica con MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="37b80-107">The MQSAgent application, in turn, communicates with MQSeries Server for Windows.</span></span> <span data-ttu-id="37b80-108">Puede instalar el agente en el mismo equipo del adaptador si instala en él MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="37b80-108">You can install the agent on the same computer as the adapter if you install MQSeries Server for Windows on the computer.</span></span>  
  
 <span data-ttu-id="37b80-109">La parte de envío del adaptador envía el mensaje a MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="37b80-109">The send part of the adapter sends the message to the MQSAgent.</span></span> <span data-ttu-id="37b80-110">MQSAgent, a continuación, usar **MQPut**, envía el mensaje para el Administrador de cola de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="37b80-110">MQSAgent then, using **MQPut**, sends the message to the MQSeries Queue Manager.</span></span>  
  
 <span data-ttu-id="37b80-111">La parte de recepción del adaptador realiza sondeos en el MQSAgent para comprobar si hay mensajes.</span><span class="sxs-lookup"><span data-stu-id="37b80-111">The receive part of the adapter polls the MQSAgent to see if there are messages.</span></span> <span data-ttu-id="37b80-112">Cuando hay un mensaje, MQSAgent realiza una **MQGet** para recuperar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="37b80-112">When there is a message, the MQSAgent performs an **MQGet** to retrieve the message.</span></span> <span data-ttu-id="37b80-113">MQSAgent incluye un intervalo de espera codificado de tres segundos para recuperar el mensaje del administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="37b80-113">MQSAgent includes a hard-coded three-second wait for retrieving the message from the Queue Manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37b80-114">Puede establecer el intervalo de sondeo del adaptador.</span><span class="sxs-lookup"><span data-stu-id="37b80-114">You can set the polling interval of the adapter.</span></span> <span data-ttu-id="37b80-115">Si el intervalo de sondeo es inferior a tres segundos, el intervalo de espera se establece con el intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="37b80-115">When you set the polling interval to less than three seconds, the wait interval is set to the polling interval.</span></span>  
  
 <span data-ttu-id="37b80-116">Tanto las acciones de mensaje de envío como de recepción pueden producirse en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="37b80-116">Both the send and receive message actions may occur in transactions.</span></span> <span data-ttu-id="37b80-117">Esto permite deshacer los mensajes y, posiblemente, recuperar las operaciones de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="37b80-117">This enables the adapter to roll back the message and, possibly, to retry the send or receive operations.</span></span> <span data-ttu-id="37b80-118">Para obtener más información acerca de las transacciones, vea [procesamiento por lotes del adaptador de MQSeries y tratamiento de las transacciones](../core/mqseries-adapter-batching-and-transaction-handling.md).</span><span class="sxs-lookup"><span data-stu-id="37b80-118">For more information about transactions, see [MQSeries Adapter Batching and Transaction Handling](../core/mqseries-adapter-batching-and-transaction-handling.md).</span></span>  
  
 <span data-ttu-id="37b80-119">Puesto que el adaptador funciona en más de un equipo, puede que se produzca un problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37b80-119">Because the adapter works across more than one computer, there is a possible security problem.</span></span> <span data-ttu-id="37b80-120">Un programa hostil podría suplantar al agente y capturar datos.</span><span class="sxs-lookup"><span data-stu-id="37b80-120">A hostile program could impersonate the agent and capture data.</span></span> <span data-ttu-id="37b80-121">Para obtener más información sobre una protección mejorada para el adaptador y el agente, consulte [seguridad del adaptador de MQSeries](../core/mqseries-adapter-security.md).</span><span class="sxs-lookup"><span data-stu-id="37b80-121">For more information about enhanced protection for the adapter and agent, see [MQSeries Adapter Security](../core/mqseries-adapter-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b80-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="37b80-122">See Also</span></span>  
 <span data-ttu-id="37b80-123">[Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="37b80-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="37b80-124">¿Qué es el adaptador de MQSeries?</span><span class="sxs-lookup"><span data-stu-id="37b80-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)
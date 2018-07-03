---
title: Mensaje de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc1157dc270fceae7b092a252f75e2c0de658eb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004973"
---
# <a name="message-batching"></a><span data-ttu-id="9792e-102">Mensaje de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="9792e-102">Message Batching</span></span>
<span data-ttu-id="9792e-103">Estándares de protocolo, problemas de programación o las limitaciones de tamaño de mensaje pueden motivar la necesidad de mensajes por lotes.</span><span class="sxs-lookup"><span data-stu-id="9792e-103">Protocol standards, scheduling issues, or message size limitations may motivate the need to batch messages.</span></span> <span data-ttu-id="9792e-104">Un lote de siete de nivel de mantenimiento (HL7) se compone de mensajes está incluidos en un encabezado de lote de HL7 y finalizador de batch.</span><span class="sxs-lookup"><span data-stu-id="9792e-104">A Health Level Seven (HL7) batch consists of messages enclosed by an HL7 batch header and batch trailer.</span></span> <span data-ttu-id="9792e-105">Separadores de mensaje separan los mensajes individuales dentro del lote.</span><span class="sxs-lookup"><span data-stu-id="9792e-105">Message separators separate the individual messages within the batch.</span></span>  
  
 <span data-ttu-id="9792e-106">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] mensaje admite los siguientes tres escenarios de procesamiento por lotes:</span><span class="sxs-lookup"><span data-stu-id="9792e-106">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] supports the following three message batching scenarios:</span></span>  
  
-   <span data-ttu-id="9792e-107">**Lote de entrada fragmentado**.</span><span class="sxs-lookup"><span data-stu-id="9792e-107">**Fragmented inbound batch**.</span></span> <span data-ttu-id="9792e-108">En este escenario, BTAHL7 recibe un lote de mensajes de HL7 y, a continuación, enruta los mensajes individuales para el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9792e-108">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
-   <span data-ttu-id="9792e-109">**Procesar por lotes en o salida**. En este escenario, BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9792e-109">**Batch in/batch out**. In this scenario, BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
-   <span data-ttu-id="9792e-110">**Creación de lote o el procesamiento por lotes saliente**.</span><span class="sxs-lookup"><span data-stu-id="9792e-110">**Create batch or outbound batching**.</span></span> <span data-ttu-id="9792e-111">En este escenario, BTAHL7 recibe los mensajes individuales y crea los lotes antes de enrutarlos al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="9792e-111">In this scenario, BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9792e-112">BTAHL7 no habilita el procesamiento por lotes de mensajes por lotes saliente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9792e-112">BTAHL7 does not enable message batching for outbound batching by default.</span></span> <span data-ttu-id="9792e-113">Debe usar el Explorador de BizTalk en primer lugar dar de alta la orquestación del lote BTAHL7 y, a continuación, iniciar la orquestación del lote.</span><span class="sxs-lookup"><span data-stu-id="9792e-113">You must use BizTalk Explorer to first enlist the BTAHL7 batch orchestration, and then start the batch orchestration.</span></span> <span data-ttu-id="9792e-114">Para obtener más información acerca de cómo habilitar el procesamiento por lotes de mensajes, vea [configuración de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span><span class="sxs-lookup"><span data-stu-id="9792e-114">For more information about enabling message batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9792e-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9792e-115">In This Section</span></span>  
  
-   [<span data-ttu-id="9792e-116">Lote de entrada fragmentado</span><span class="sxs-lookup"><span data-stu-id="9792e-116">Fragmented Inbound Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [<span data-ttu-id="9792e-117">Configuración del procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="9792e-117">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [<span data-ttu-id="9792e-118">Programación del procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="9792e-118">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [<span data-ttu-id="9792e-119">Configuración de confirmaciones de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="9792e-119">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)
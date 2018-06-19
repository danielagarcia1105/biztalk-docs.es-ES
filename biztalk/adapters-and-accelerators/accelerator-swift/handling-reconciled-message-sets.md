---
title: Control de conjuntos de mensajes reconciliarse | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209044"
---
# <a name="handling-reconciled-message-sets"></a><span data-ttu-id="3f55e-102">Control conciliado conjuntos de mensajes</span><span class="sxs-lookup"><span data-stu-id="3f55e-102">Handling Reconciled Message Sets</span></span>
<span data-ttu-id="3f55e-103">Cuando AAS devolución una respuesta a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] registra la respuesta en el cuadro de mensajes y coincide con la respuesta o respuestas al mensaje original.</span><span class="sxs-lookup"><span data-stu-id="3f55e-103">When SAA returns a response to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] records the response in the MessageBox, and matches the response or responses to the original message.</span></span> <span data-ttu-id="3f55e-104">Puede implementar un comportamiento de aplicación personalizada con esta información.</span><span class="sxs-lookup"><span data-stu-id="3f55e-104">You can implement custom application behavior using this information.</span></span> <span data-ttu-id="3f55e-105">Para ello, desarrollar controladores personalizados que implementan reacciones específica del cliente a los conjuntos de conciliado/respuesta del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3f55e-105">To do so, develop custom handlers that implement customer-specific reactions to reconciled message/response sets.</span></span> <span data-ttu-id="3f55e-106">Puede crear controladores personalizados que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f55e-106">You can create custom handlers that do the following:</span></span>  
  
-   <span data-ttu-id="3f55e-107">Procesar los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, lo que indica que SWIFT no ha recibido correctamente el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f55e-107">Process messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="3f55e-108">Esto puede permitir un taller de reparación solucionar el mensaje y enviarlo de nuevo a la red SWIFT, que después de la reparación espero será capaz de recibir el mensaje correctamente y AAS.</span><span class="sxs-lookup"><span data-stu-id="3f55e-108">This can enable a repairer to fix the message and re-send it to SAA and the SWIFT network, which after the repair will hopefully be able to receive the message successfully.</span></span> <span data-ttu-id="3f55e-109">Para obtener más información sobre esta solución, consulte [FRR NAK controlador ejemplo](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span><span class="sxs-lookup"><span data-stu-id="3f55e-109">For more information about this solution, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
-   <span data-ttu-id="3f55e-110">Quitar conjuntos de respuesta de mensaje publicados por la orquestación en una carpeta de archivos con nombres de archivo único que indica las relaciones de los mensajes en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="3f55e-110">Drop message-response sets published by the orchestration into a file folder with unique file names indicating the relationships of the messages in the set.</span></span> <span data-ttu-id="3f55e-111">A continuación, puede realizar la lógica de negocios en estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f55e-111">You can then perform business logic on these messages.</span></span>  
  
-   <span data-ttu-id="3f55e-112">Mensajes de proceso ha superado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3f55e-112">Process timed-out messages.</span></span>  
  
-   <span data-ttu-id="3f55e-113">Los resultados de la transmisión de mensajes de registro y, a continuación, descartar los mensajes reales.</span><span class="sxs-lookup"><span data-stu-id="3f55e-113">Log the results of message transmission and then discard the actual messages.</span></span>
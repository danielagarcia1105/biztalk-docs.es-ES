---
title: "Resolver la pérdida de datos de las orquestaciones en curso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eca757b80e31ee5db829d2d2079bf657d01079b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a><span data-ttu-id="f063d-102">Resolver la pérdida de datos de orquestaciones en curso</span><span class="sxs-lookup"><span data-stu-id="f063d-102">Resolving Data Loss of In-Progress Orchestrations</span></span>
<span data-ttu-id="f063d-103">Las bases de datos de cuadro de mensajes contienen el estado de las orquestaciones actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="f063d-103">MessageBox databases contain the state of orchestrations that are currently in progress.</span></span> <span data-ttu-id="f063d-104">Aunque no exista ninguna forma de saber con exactitud qué datos se han perdido de las bases de datos de cuadro de mensajes, se pueden seguir algunos pasos para recopilar información acerca de ellos:</span><span class="sxs-lookup"><span data-stu-id="f063d-104">Although there is no way to tell exactly what data has been lost from the MessageBox databases, there are some steps you can take to gather information about the lost data:</span></span>  
  
-   <span data-ttu-id="f063d-105">Determine los mensajes que se han enviado y recibido en las orquestaciones actuales, así como los sistemas externos que se han utilizado después del punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="f063d-105">Determine what messages have been sent and received in the current orchestrations, and what external systems have been used after the point of recovery.</span></span> <span data-ttu-id="f063d-106">Por ejemplo, si su sistema mantiene un registro externo de mensajes y sucesos, puede examinar ese registro.</span><span class="sxs-lookup"><span data-stu-id="f063d-106">For example, if your system maintains an external log of messages and events, you can examine that log.</span></span> <span data-ttu-id="f063d-107">Es posible que también tenga que revisar manualmente los sistemas externos para ver qué actividades han tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="f063d-107">You may also need to manually review the external systems to see what activities have occurred.</span></span>  
  
-   <span data-ttu-id="f063d-108">Después de determinar la causa de la pérdida de los datos, puede empezar a corregir el sistema restaurado decidiendo qué procesos pueden continuar, cuáles deben finalizarse y reiniciarse (para lo que tendrá que reenviar los mensajes de activación perdidos), y cuáles se han completado correctamente y pueden finalizarse.</span><span class="sxs-lookup"><span data-stu-id="f063d-108">After you determine the cause of the data loss, you can begin to correct the restored system, deciding which processes can continue, which processes must be terminated and restarted (by resubmitting the lost activation messages), and which processes have completed successfully and can be terminated.</span></span> <span data-ttu-id="f063d-109">Este proceso depende en gran medida de la arquitectura de su sistema y debe considerarse parte del plan de recuperación del sistema.</span><span class="sxs-lookup"><span data-stu-id="f063d-109">This process depends largely on the architecture of your system and must be considered as part of your system recovery planning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f063d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f063d-110">See Also</span></span>  
 [<span data-ttu-id="f063d-111">Resolver la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="f063d-111">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)
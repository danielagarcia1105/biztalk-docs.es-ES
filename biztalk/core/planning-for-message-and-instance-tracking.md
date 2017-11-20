---
title: "Planeación de mensaje y seguimiento de instancias | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-message-and-instance-tracking"></a><span data-ttu-id="0f333-102">Planeación del seguimiento de instancias y mensajes</span><span class="sxs-lookup"><span data-stu-id="0f333-102">Planning for Message and Instance Tracking</span></span>
<span data-ttu-id="0f333-103">Debería decidir durante las fases de planeamiento la información para la que necesita realizar el seguimiento de modo que, tras implementar el proyecto, pueda establecer las opciones de seguimiento y limitar la cantidad de datos a fin de obtener sólo la información que necesite.</span><span class="sxs-lookup"><span data-stu-id="0f333-103">You should decide during the planning stages which information you need to track, so that after you deploy the project you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
 <span data-ttu-id="0f333-104">Se recomienda no realizar el seguimiento de todos los mensajes puesto que, cada vez que se toca un mensaje, el seguimiento de instancias de servidor y mensajes de BizTalk Server crea otra copia.</span><span class="sxs-lookup"><span data-stu-id="0f333-104">We recommend that you do not track all messages, because each time a message is touched, BizTalk Server message and server instance tracking makes another copy.</span></span> <span data-ttu-id="0f333-105">Por ejemplo, puede limitar el ámbito realizando sólo el seguimiento de un puerto específico.</span><span class="sxs-lookup"><span data-stu-id="0f333-105">For example, you can narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="0f333-106">Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos sin demasiada carga.</span><span class="sxs-lookup"><span data-stu-id="0f333-106">This helps to maximize the performance of your system and keep the databases uncluttered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f333-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f333-107">See Also</span></span>  
 [<span data-ttu-id="0f333-108">Arquitectura de seguimiento y administración</span><span class="sxs-lookup"><span data-stu-id="0f333-108">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)
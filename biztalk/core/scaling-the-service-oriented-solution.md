---
title: "Escalar la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-the-service-oriented-solution"></a><span data-ttu-id="c0213-102">Escalar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="c0213-102">Scaling the Service Oriented Solution</span></span>
<span data-ttu-id="c0213-103">Para escalar la solución de modo que admita un mayor rendimiento a la vez que mantiene un baja latencia de mensajes, debe usar la versión en línea de la solución.</span><span class="sxs-lookup"><span data-stu-id="c0213-103">To scale the solution to support higher throughput while maintaining low message latency requires you to use the inline version of the solution.</span></span> <span data-ttu-id="c0213-104">La solución en línea no tiene en cuenta la base de datos Cuadro de mensajes al interactuar con los sistemas servidor.</span><span class="sxs-lookup"><span data-stu-id="c0213-104">The inline solution bypasses the MessageBox database when interacting with the back-end systems.</span></span>  
  
 <span data-ttu-id="c0213-105">También puede agregar servidores de procesamiento BizTalk Server para ejecutar orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="c0213-105">You can also add BizTalk Server processing servers to run orchestrations.</span></span> <span data-ttu-id="c0213-106">De esta forma se reduce la utilización de cada servidor de modo que las solicitudes nuevas se puedan procesar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="c0213-106">This decreases the utilization of each server so that new requests can be processed quickly.</span></span> <span data-ttu-id="c0213-107">También puede escalar verticalmente el servidor Cuadro de mensajes para que tenga capacidad adicional para controlar el rendimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c0213-107">You can also scale up the MessageBox server so that it has enough additional capacity to handle the message throughput.</span></span>  
  
 <span data-ttu-id="c0213-108">No obstante, la solución de arquitectura orientada a servicios no obtiene ventajas de tener varias bases de datos cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c0213-108">However, the service oriented architecture solution does not benefit from having multiple MessageBox databases.</span></span> <span data-ttu-id="c0213-109">Varios cuadros de mensajes requieren transacciones de coordinador de transacciones distribuidas (DTC).</span><span class="sxs-lookup"><span data-stu-id="c0213-109">Multiple MessageBoxes require distributed transaction coordinator (DTC) transactions.</span></span> <span data-ttu-id="c0213-110">Las transacciones aumentan la latencia de mensajes general.</span><span class="sxs-lookup"><span data-stu-id="c0213-110">The transactions increase overall message latency.</span></span>  
  
 <span data-ttu-id="c0213-111">Puede reducir el tiempo de respuesta mediante la eliminación del componente de canalización que agrega información de encabezado MQSeries.</span><span class="sxs-lookup"><span data-stu-id="c0213-111">You can decrease response time by eliminating the pipeline component that adds MQSeries header information.</span></span> <span data-ttu-id="c0213-112">Para obtener más información, consulte [pone de manifiesto de implementación de la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="c0213-112">For more information, see [Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0213-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0213-113">See Also</span></span>  
 [<span data-ttu-id="c0213-114">Desarrollar un servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="c0213-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)
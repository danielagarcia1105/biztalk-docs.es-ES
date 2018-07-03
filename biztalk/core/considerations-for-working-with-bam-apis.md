---
title: Consideraciones para trabajar con las API de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416f8acca6412b8809d7843de7d8084d3df9efc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005205"
---
# <a name="considerations-for-working-with-bam-apis"></a><span data-ttu-id="22d6e-102">Consideraciones para trabajar con API de BAM</span><span class="sxs-lookup"><span data-stu-id="22d6e-102">Considerations for Working with BAM APIs</span></span>
<span data-ttu-id="22d6e-103">Cuando se utiliza un objeto "Microsoft.BizTalk.Bam.EventObservation.EventStream", por ejemplo DirectEventStream, BufferedEventStream, MessagingEventStream u OrchestrationEventStream, BAM captura hitos como los que se registran automáticamente en formato de hora universal coordinada (UTC) (también hace referencia a la hora del meridiano de Greenwich).</span><span class="sxs-lookup"><span data-stu-id="22d6e-103">When using an  "Microsoft.BizTalk.Bam.EventObservation.EventStream" object, such as DirectEventStream, BufferedEventStream, MessagingEventStream, or OrchestrationEventStream, BAM captures milestones such that they are automatically recorded in Coordinated Universal Time (UTC) format (this is also referred to as Greenwich Mean Time).</span></span> <span data-ttu-id="22d6e-104">Cuando envía la fecha y hora a BAM mediante las API, se reciben en el formato enviado sin conversión a formato UTC.</span><span class="sxs-lookup"><span data-stu-id="22d6e-104">When you send date/times to BAM using the APIs they are received in the format sent with no conversion to UTC format.</span></span> <span data-ttu-id="22d6e-105">Tenga en cuenta las siguientes consideraciones cuando desarrolle sus soluciones de BAM:</span><span class="sxs-lookup"><span data-stu-id="22d6e-105">You should take the following considerations into account when you are developing your BAM solutions:</span></span>  
  
- <span data-ttu-id="22d6e-106">Los datos de los que se ha realizado un seguimiento desde el servidor BizTalk Server se reciben en formato UTC.</span><span class="sxs-lookup"><span data-stu-id="22d6e-106">Data traced from BizTalk Server is received in UTC format.</span></span> <span data-ttu-id="22d6e-107">Puede ser incoherente con otros datos provenientes de la secuencia de eventos.</span><span class="sxs-lookup"><span data-stu-id="22d6e-107">This could be inconsistent with other data that comes from the event stream.</span></span>  
  
- <span data-ttu-id="22d6e-108">Si utiliza la secuencia de eventos de API para proporcionar datos de seguimiento de fecha y hora en el formato de hora local, los datos del portal de BAM serán incorrectos, ya que se espera que todas las horas de los datos BAM estén en formato UTC.</span><span class="sxs-lookup"><span data-stu-id="22d6e-108">If you use the event stream APIs to provide date and time tracking data in local time format, the data in the BAM portal will be incorrect as the expectation is that all times in BAM data are in UTC format.</span></span>  
  
  <span data-ttu-id="22d6e-109">Si tiene aplicaciones existentes que utilicen hora local, que ahora se está actualizando y que planee utilizar el portal de BAM; debe modificar sus datos para que encajen con el formato UTC.</span><span class="sxs-lookup"><span data-stu-id="22d6e-109">If you have existing applications that use local time, and you are now upgrading and planning to use the BAM portal, you must modify your data to make it conform to UTC format.</span></span> <span data-ttu-id="22d6e-110">También es preciso modificar su aplicación personalizada para convertir el formato a UTC.</span><span class="sxs-lookup"><span data-stu-id="22d6e-110">You also need to modify your custom application to convert to UTC format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d6e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22d6e-111">See Also</span></span>  
 [<span data-ttu-id="22d6e-112">Implementar soluciones de BAM</span><span class="sxs-lookup"><span data-stu-id="22d6e-112">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)
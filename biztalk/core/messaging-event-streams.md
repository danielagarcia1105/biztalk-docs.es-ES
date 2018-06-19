---
title: Secuencias de eventos de mensajería | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dc56aff-c093-4c79-9cc7-f72079ee927f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d955dbc2b50d1d9c40b54736762fcbaa2bfe536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262788"
---
# <a name="messaging-event-streams"></a><span data-ttu-id="8d030-102">Secuencias de eventos de mensajería</span><span class="sxs-lookup"><span data-stu-id="8d030-102">Messaging Event Streams</span></span>
<span data-ttu-id="8d030-103">Las secuencias de eventos de mensajería (MES) se usan cuando la aplicación se ejecuta en un equipo en el que BizTalk Server está instalado y cuando realiza el seguimiento de elementos que forman parte de las transacciones de canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8d030-103">You use Messaging Event Streams (MES) when your application runs on a computer on which BizTalk Server is installed and you are you are tracking items that are part of BizTalk pipeline transactions.</span></span> <span data-ttu-id="8d030-104">El uso de MES garantiza que la persistencia de eventos de BAM permanece sincronizada con las transacciones de canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8d030-104">Using MES ensures that your BAM event persistence remains in sync with the BizTalk pipeline transactions.</span></span>  
  
 <span data-ttu-id="8d030-105">Secuencias de eventos de mensajería son instancias de los objetos EventStream devueltas por la [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) método.</span><span class="sxs-lookup"><span data-stu-id="8d030-105">Messaging Event Streams are instances of EventStream objects returned by the [Microsoft.BizTalk.Component.Interop.IPipelineContext.GetEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.ipipelinecontext.geteventstream.aspx) method.</span></span>  
  
 <span data-ttu-id="8d030-106">Las secuencias de eventos de mensajería son asíncronas y almacenan datos de seguimiento primero en la base de datos de cuadro de mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8d030-106">Messaging Event Streams are asynchronous and store tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="8d030-107">De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="8d030-107">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="8d030-108">IPipelineContext se encuentra en la [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8d030-108">IPipelineContext is found in the [Microsoft.BizTalk.Component.Interop](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx) namespace.</span></span> <span data-ttu-id="8d030-109">Para usar la API debe agregar Microsoft.BizTalk.Pipeline (en microsoft.biztalk.pipeline.dll) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d030-109">To use the API you must add the Microsoft.BizTalk.Pipeline (in microsoft.biztalk.pipeline.dll) to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d030-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d030-110">See Also</span></span>  
 <span data-ttu-id="8d030-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span><span class="sxs-lookup"><span data-stu-id="8d030-111">[OrchestrationEventStream](../core/orchestrationeventstream.md) </span></span>  
 <span data-ttu-id="8d030-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span><span class="sxs-lookup"><span data-stu-id="8d030-112">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) </span></span>  
 [<span data-ttu-id="8d030-113">Microsoft.BizTalk.Component.Interop</span><span class="sxs-lookup"><span data-stu-id="8d030-113">Microsoft.BizTalk.Component.Interop</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.aspx)
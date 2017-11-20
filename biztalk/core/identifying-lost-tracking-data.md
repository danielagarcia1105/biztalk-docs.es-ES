---
title: Identificar los datos de seguimiento perdidos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d7a61d974a51e3a811a8cce84a1e22c24a5e84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-lost-tracking-data"></a><span data-ttu-id="bce50-102">Identificar datos de seguimiento perdidos</span><span class="sxs-lookup"><span data-stu-id="bce50-102">Identifying Lost Tracking Data</span></span>
<span data-ttu-id="bce50-103">Puede usar la consola de administración de BizTalk Server para que le ayude a identificar los datos de seguimiento que se han perdido como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="bce50-103">You can use the BizTalk Server Administration console to help identify which tracking data has been lost as a result of a hardware failure.</span></span> <span data-ttu-id="bce50-104">Puede usar la consola de administración de BizTalk Server para datos archivados o activos.</span><span class="sxs-lookup"><span data-stu-id="bce50-104">You can use the BizTalk Server Administration console for live or archived data.</span></span>  
  
 <span data-ttu-id="bce50-105">La consola de administración de BizTalk Server puede usarse para determinar los servicios que se encontraban activos cuando se recuperó el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="bce50-105">You can use the BizTalk Server Administration console to determine which services were active at the time the MessageBox was recovered.</span></span> <span data-ttu-id="bce50-106">Ya que existe un lapso de tiempo entre el momento de recuperación de la base de datos y el tiempo del error de hardware, es posible que no pueda determinar el estado de algunas de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="bce50-106">Because there is a gap between the time that the database was recovered and the time of the hardware failure, you may not be able to determine the state of some of the transactions.</span></span>  
  
 <span data-ttu-id="bce50-107">Los datos de seguimiento pueden usarse para identificar las instancias de servicio completadas e iniciadas después del punto de recuperación:</span><span class="sxs-lookup"><span data-stu-id="bce50-107">You can use tracking data to identify which service instances completed and started after the point of recovery, as follows:</span></span>  
  
-   <span data-ttu-id="bce50-108">Busque las instancias completadas o iniciadas desde la última vez que se realizó una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bce50-108">Look for which instances completed or started since the last time you backed up the database.</span></span>  
  
-   <span data-ttu-id="bce50-109">Si los datos de la base de datos de seguimiento de BizTalk (BizTalkDTADb) indican que el mensaje se ha iniciado pero no completado, y éste no se encuentra en la base de datos, entonces el mensaje se envió después de que se realizara la última copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bce50-109">If data in the BizTalk Tracking (BizTalkDTADb) database indicates that the message started but did not complete, and the message is not in the database, then that message was sent after the last backup.</span></span>  
  
 <span data-ttu-id="bce50-110">El seguimiento puede emitir un informe de cualquier servicio completado, así como indicar que un servicio se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="bce50-110">Tracking can report on any service that completed, and it can indicate that a service started.</span></span> <span data-ttu-id="bce50-111">Los datos de seguimiento se colocan, en una primera fase, en el cuadro de mensajes y, a continuación, se mueven a la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="bce50-111">Tracking data is first staged to the MessageBox and then moved to the BizTalk Tracking database.</span></span> <span data-ttu-id="bce50-112">Es posible que se produzca la pérdida de estos datos en el trabajo acumulado del servicio de bus de sucesos BAM.</span><span class="sxs-lookup"><span data-stu-id="bce50-112">The data that was staged may have been lost to the backlog of the BAM Event Bus service.</span></span>  
  
 <span data-ttu-id="bce50-113">Mientras que, por razones operativas, es preciso que se efectúe la restauración de todas las bases de datos a la misma marca, se puede utilizar la base de datos de seguimiento de BizTalk (que no se perdió) en el modo de archivo para ver lo ocurrido después de la marca.</span><span class="sxs-lookup"><span data-stu-id="bce50-113">While all databases need to be restored to the same mark for operational reasons, you can use a BizTalk Tracking database (that was not lost) in Archive mode to see what happened after the mark.</span></span>  
  
 <span data-ttu-id="bce50-114">Si el seguimiento muestra una instancia de servicio como completada, podrá finalizar esta última.</span><span class="sxs-lookup"><span data-stu-id="bce50-114">If tracking shows a service instance as having completed, you can terminate that instance.</span></span> <span data-ttu-id="bce50-115">Es posible que muestre instancias iniciadas después del punto de recuperación.</span><span class="sxs-lookup"><span data-stu-id="bce50-115">It may show instances that started after the point of recovery.</span></span> <span data-ttu-id="bce50-116">En este caso, tendrá que efectuar una compensación de las acciones que se llevaron a cabo en estas instancias y, seguidamente, volver a enviar sus mensajes de activación inicial.</span><span class="sxs-lookup"><span data-stu-id="bce50-116">If so, you will need to compensate for any actions these instances took and then resubmit their initial activation messages.</span></span>  
  
 <span data-ttu-id="bce50-117">Puede usar el depurador de orquestaciones para ver las últimas formas que se ejecutaron y, a continuación, usar Flujo de mensajes para ver los mensajes que se deberían haber enviado o recibido.</span><span class="sxs-lookup"><span data-stu-id="bce50-117">You can use the Orchestration Debugger to see the last shapes that executed, and then use Message Flow to see what message should have been sent or received.</span></span>  
  
 <span data-ttu-id="bce50-118">Si se produjo la pérdida de la base de datos de seguimiento, el descubrimiento de todo lo ocurrido después del punto de recuperación tendrá que efectuarse mediante mecanismos de elaboración de informes de sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="bce50-118">If the BizTalk Tracking database was lost, all discovery of what happened past the point of recovery will need to be done by using the external systems reporting mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce50-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce50-119">See Also</span></span>  
 [<span data-ttu-id="bce50-120">Resolver la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="bce50-120">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)
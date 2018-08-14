---
title: ¿Qué es el seguimiento de eventos? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HAT tracking], events
- DTA_Services audit table [HAT]
- HAT, events
- events, tracking
- tracking, events
- Tracking database, DTA_Services audit table
- events, HAT
ms.assetid: dd211752-d1af-4287-967a-908b8d067ebb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42799a084c579cfba7d696c700d887b1ae992db2
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640088"
---
# <a name="what-is-event-tracking"></a><span data-ttu-id="828a3-103">¿Qué es el seguimiento de eventos?</span><span class="sxs-lookup"><span data-stu-id="828a3-103">What is Event Tracking?</span></span>
<span data-ttu-id="828a3-104">Los datos de eventos de mensajes de los que se hace seguimiento se basan en eventos (por ejemplo, cuando empieza o finaliza un servicio, o cuando se envía o recibe un mensaje).</span><span class="sxs-lookup"><span data-stu-id="828a3-104">Tracked message event data is based upon events (for example, when a service begins or ends, or when a message is sent or received).</span></span> <span data-ttu-id="828a3-105">El proceso de seguimiento de eventos de mensajes devuelve una lista de los eventos que se han producido, lo que permite ver todo lo que ha ocurrido según los filtros establecidos.</span><span class="sxs-lookup"><span data-stu-id="828a3-105">The message event tracking process returns a list of the events that have occurred, enabling you to see everything that happened based on the tracking filters you have set.</span></span>  
  
 <span data-ttu-id="828a3-106">Puede realizar el seguimiento del inicio y fin de orquestaciones y puertos, cuando los mensajes se envían y reciben, así como de la ejecución de cada forma de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="828a3-106">You can track the start and end of orchestrations and ports, when messages are sent and received, as well as the execution of each shape in an orchestration.</span></span>  
  
 <span data-ttu-id="828a3-107">La base de datos de seguimiento de BizTalk (BizTalkDTAdb) contiene una tabla de auditorías DTA_Services.</span><span class="sxs-lookup"><span data-stu-id="828a3-107">The BizTalk Tracking (BizTalkDTADb) database contains a DTA_Services audit table.</span></span> <span data-ttu-id="828a3-108">Esta tabla contiene el historial de todos los servicios implementados: canalizaciones, transportes y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="828a3-108">This table contains history of all deployed services—pipelines, transports, and orchestrations.</span></span> <span data-ttu-id="828a3-109">No realiza el seguimiento de la anulación de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="828a3-109">It does not keep track of undeployments.</span></span>  
  
 <span data-ttu-id="828a3-110">Puede realizar el seguimiento del contenido de un mensaje y de las propiedades promocionadas de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="828a3-110">You can track the contents of a message as well as the promoted properties of a message.</span></span> <span data-ttu-id="828a3-111">Seguimiento de eventos de mensaje definen estas acciones como **cuerpo del mensaje** seguimiento y **propiedad Message** de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="828a3-111">Tracking message events defines these actions as **Message Body** tracking and **Message Property** tracking.</span></span> <span data-ttu-id="828a3-112">Aunque aparezcan sobres en los resultados del seguimiento de eventos de mensajes, no se puede hacer un seguimiento de las propiedades de mensajes a partir de ellos.</span><span class="sxs-lookup"><span data-stu-id="828a3-112">Although envelopes appear in the message event tracking output, you cannot track message properties from them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828a3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="828a3-113">See Also</span></span>  
 [<span data-ttu-id="828a3-114">Configurar el seguimiento mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="828a3-114">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)

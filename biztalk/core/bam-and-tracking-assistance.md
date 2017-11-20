---
title: Asistencia para el seguimiento y BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, BAM integration
- BAM, HAT integration
ms.assetid: b224cd7d-78db-432a-821a-728eabbf6403
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b915d21111383ca32f2732f1a1bb86bd2c6c8f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-and-tracking-assistance"></a><span data-ttu-id="a793a-102">Asistencia para el seguimiento y BAM</span><span class="sxs-lookup"><span data-stu-id="a793a-102">BAM and Tracking Assistance</span></span>
<span data-ttu-id="a793a-103">También puede solicitar asistencia a través del portal BAM, haga clic en el **asistencia** botón en la página de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="a793a-103">You can request assistance through the BAM portal by clicking the **Assistance** button on the Activity Status page.</span></span>  
  
 <span data-ttu-id="a793a-104">La solicitud de asistencia se coloca en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a793a-104">The assistance request is placed in the Application Event log.</span></span> <span data-ttu-id="a793a-105">El origen de las solicitudes es el servicio Web de BAM, y el Id. de evento es 1000.</span><span class="sxs-lookup"><span data-stu-id="a793a-105">The source for the requests is the BAM Web service and the Event ID is 1000.</span></span>  
  
 <span data-ttu-id="a793a-106">El cuerpo de mensaje se encuentra en el campo Descripción, y contiene el asunto de la solicitud, el texto de la descripción de problema, el Id. de instancia de servicio de BizTalk, el Id. de mensaje, el servidor de bases de datos de administración de BizTalk y el nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a793a-106">The message body is in the Description field and contains the subject of the request, the text of the problem description, the BizTalk service instance ID, the message ID, the BizTalk Management database server, and the BizTalk Management Database name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a793a-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a793a-107">See Also</span></span>  
 <span data-ttu-id="a793a-108">[Supervisión de BizTalk Server](../core/monitoring-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="a793a-108">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) </span></span>  
 [<span data-ttu-id="a793a-109">Solicitar asistencia</span><span class="sxs-lookup"><span data-stu-id="a793a-109">Request Assistance</span></span>](../core/request-assistance.md)
---
title: "Información general sobre el punto de administración de BizTalk de SOA | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-soa-biztalk-management-point"></a><span data-ttu-id="242df-102">Información general sobre el punto de administración de BizTalk de SOA</span><span class="sxs-lookup"><span data-stu-id="242df-102">Overview of the SOA BizTalk Management Point</span></span>
<span data-ttu-id="242df-103">El punto de administración de BizTalk forma nativa se integra con los productos de administrador de servicios de SOA y área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="242df-103">The BizTalk Management Point natively integrates with SOA Service Manager and Workbench products.</span></span> <span data-ttu-id="242df-104">Al contrario que el punto de administración de servicios Web típica, esta implementación está asociada con los servicios proporcionados por el entorno de Microsoft BizTalk Server, expresado en términos de BizTalk Server ubicaciones de recepción y puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="242df-104">Unlike the typical Web Services Management Point, this implementation is associated with services provided by the Microsoft BizTalk Server environment, expressed in terms of BizTalk Server receive locations and send ports.</span></span> <span data-ttu-id="242df-105">Debido a la arbitrario naturaleza de ubicaciones de recepción y envío puertos (configurados con una variedad de adaptadores de BizTalk Server), estos servicios no están necesariamente asociados con los servicios Web, pero se puede tratar como servicios Web en términos de SOA Service Manager y el área de trabajo SOA.</span><span class="sxs-lookup"><span data-stu-id="242df-105">Because of the arbitrary nature of receive locations and send ports (configured against a variety of BizTalk Server adapters), these services are not necessarily associated with Web services, but they can be treated as Web services in terms of the SOA Service Manager and SOA Workbench.</span></span>  
  
 <span data-ttu-id="242df-106">La figura 1 muestra la aplicación Web de administrador de servicios de SOA de mostrar la página de área de trabajo para una aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="242df-106">Figure 1 shows the SOA Service Manager Web application displaying the Workbench page for an example application.</span></span> <span data-ttu-id="242df-107">La vista de árbol de la izquierda permite a los usuarios navegar por las aplicaciones y servicios instalados en el servidor BizTalk Server y el panel de la derecha permite a los usuarios ver los detalles de la aplicación, las operaciones, puertos de acceso, categorías, reglas e información de supervisión.</span><span class="sxs-lookup"><span data-stu-id="242df-107">The left-side tree view allows users to navigate through the applications and services installed within BizTalk Server, and the right-side pane allows users to view application details, operations, access ports, categories, rules, and monitoring information.</span></span>  
  
 <span data-ttu-id="242df-108">![Ch9 &#45; SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")</span><span class="sxs-lookup"><span data-stu-id="242df-108">![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")</span></span>  
  
 <span data-ttu-id="242df-109">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="242df-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="242df-110">**El Administrador de servicios de SOA que muestra las características de supervisión disponibles en la página de área de trabajo**</span><span class="sxs-lookup"><span data-stu-id="242df-110">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="242df-111">Puede supervisar todas las operaciones dentro de una aplicación (todos los puertos de envío y ubicaciones de recepción), o las operaciones concretas; se muestra en el área de trabajo una lista de los mensajes que pasan a través de los puertos de envío y ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="242df-111">You can monitor all the operations within an application (all send ports and receive locations), or specific operations; the Workbench shows a list of the messages passing through the selected send ports and receive locations.</span></span> <span data-ttu-id="242df-112">Al hacer doble clic en un mensaje en la lista, el área de trabajo muestra los detalles del mensaje y sus propiedades de contexto (si está habilitada la grabación).</span><span class="sxs-lookup"><span data-stu-id="242df-112">When you double-click a message in the list, the Workbench displays details of the message, and its context properties (if recording is enabled).</span></span> <span data-ttu-id="242df-113">Como alternativa, puede seleccionar un servicio específico y un monitor de mensajes en tiempo real que se pasan a través de ese servicio.</span><span class="sxs-lookup"><span data-stu-id="242df-113">Alternatively, you can select a specific service and monitor in real-time messages passing through that service.</span></span>
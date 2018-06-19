---
title: Seguimiento de estado y actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c5d7415-38da-47b5-8dbc-0a2ea74548d9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b1720535b58a50fe0c5bd3478bc9b9ec90d0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246604"
---
# <a name="health-and-activity-tracking"></a><span data-ttu-id="455c7-102">Seguimiento de estado y actividad</span><span class="sxs-lookup"><span data-stu-id="455c7-102">Health and Activity Tracking</span></span>
<span data-ttu-id="455c7-103">El **mantenimiento y seguimiento de actividad (HAT)** se quitó la herramienta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span><span class="sxs-lookup"><span data-stu-id="455c7-103">The **Health and Activity Tracking (HAT)** tool was removed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span>  <span data-ttu-id="455c7-104">La función de la herramienta HAT era realizar el seguimiento y mostrar información relacionada con live y datos históricos de mensajes almacenan en la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="455c7-104">The role of the HAT tool was to track and display information relating to live and historical message data stored in the BizTalk Tracking database.</span></span>  <span data-ttu-id="455c7-105">La herramienta permitía depurar el flujo de una orquestación y la capacidad para ver el flujo de un mensaje a través de una visualización secuencial.</span><span class="sxs-lookup"><span data-stu-id="455c7-105">The tool allowed debugging of the flow of an orchestration and the ability to view the flow of a message through a sequential display.</span></span>  <span data-ttu-id="455c7-106">Un generador de consultas permitía realizar consultas estándar y personalizadas de los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="455c7-106">A Query Builder allowed standard and custom queries of the tracking data.</span></span>  
  
 <span data-ttu-id="455c7-107">Aunque la herramienta Seguimiento de estado y actividad (HAT) ya no se invoca directamente desde el menú de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], su funcionalidad de seguimiento sigue existiendo de forma indirecta dentro del entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="455c7-107">While the Health Activity Tracking tool is no longer invoked directly from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] menu, its tracking functionality still indirectly exists from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  <span data-ttu-id="455c7-108">La información sobre estado y actividad está disponible mediante la integración mejorada y las consultas de seguimiento adicionales, dentro de la página Concentrador de grupo de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="455c7-108">Health and activity information is available through improved integration and additional tracking queries within the Group Hub page in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="455c7-109">Gran parte de la documentación relacionada datos de estado y la actividad de seguimiento se pueden encontrar en [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).</span><span class="sxs-lookup"><span data-stu-id="455c7-109">A majority of documentation surrounding tracking health and activity data can be found at [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  <span data-ttu-id="455c7-110">Parte de la información de esta sección incluye [prácticas recomendadas para el mensaje y seguimiento de datos de instancia](../core/best-practices-for-message-and-instance-data-tracking.md), [descripción realiza un seguimiento de los datos](../core/understanding-tracked-data.md), [ver históricos y realiza el seguimiento de datos](../core/viewing-historical-and-tracked-data.md), [Ver el flujo de mensajes](../core/viewing-message-flow.md), y [depurar orquestaciones](../core/debugging-an-orchestration.md).</span><span class="sxs-lookup"><span data-stu-id="455c7-110">Some of the information in this section includes [Best Practices for Message and Instance Data Tracking](../core/best-practices-for-message-and-instance-data-tracking.md), [Understanding Tracked Data](../core/understanding-tracked-data.md), [Viewing Historical and Tracked Data](../core/viewing-historical-and-tracked-data.md), [Viewing Message Flow](../core/viewing-message-flow.md), and [Debugging an Orchestration](../core/debugging-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="455c7-111">Para obtener información adicional sobre las mejoras y las consultas adicionales de esta página, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="455c7-111">For additional information on the improvements and the additional queries to this page, refer to the following topics:</span></span>  
  
-   [<span data-ttu-id="455c7-112">Mediante la página concentrador de grupo</span><span class="sxs-lookup"><span data-stu-id="455c7-112">Using the Group Hub Page</span></span>](../core/using-the-group-hub-page.md)  
  
-   [<span data-ttu-id="455c7-113">Uso de la pestaña de consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="455c7-113">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)  
  
-   [<span data-ttu-id="455c7-114">Búsqueda de eventos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="455c7-114">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="455c7-115">Búsqueda de instancias de servicio controladas</span><span class="sxs-lookup"><span data-stu-id="455c7-115">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)
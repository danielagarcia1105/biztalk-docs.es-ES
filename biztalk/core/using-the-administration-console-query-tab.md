---
title: "Mediante la pestaña de consulta de la consola de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Query tab
- Query tab [Administration Console]
ms.assetid: 7655f0b6-9217-46c4-88e0-ca2e661ce7a6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20046580913ee8ea3ccb4a742ab693bcaa08d38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-administration-console-query-tab"></a><span data-ttu-id="e2b6f-102">Usar la ficha Consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="e2b6f-102">Using the Administration Console Query Tab</span></span>
<span data-ttu-id="e2b6f-103">Utilice la ficha Consulta de la página Concentrador de grupo de la consola de administración de BizTalk Server para buscar instancias de servicio, suscripciones o mensajes específicos en ejecución o en suspensión.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-103">You can use the Query tab on the Group Hub page in the BizTalk Server Administration Console to search for and locate specific running and suspended service instances, messages, or subscriptions.</span></span> <span data-ttu-id="e2b6f-104">Las consultas realizadas con la consola de administración buscan elementos activos, que se almacenan en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-104">Queries performed using the Administration Console locate live items, which are stored in the MessageBox database.</span></span> <span data-ttu-id="e2b6f-105">Cada vez que se ejecuta una nueva consulta, aparece una ficha Consulta nueva.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-105">A new query tab appears each time you run a new query.</span></span>  
  
 <span data-ttu-id="e2b6f-106">Para buscar instancias de servicio o mensajes archivados supervisados, use el seguimiento de eventos de mensaje e instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-106">To locate tracked or archived messages or service instances, you use message event and service instance tracking.</span></span> <span data-ttu-id="e2b6f-107">Para obtener más información, consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).</span><span class="sxs-lookup"><span data-stu-id="e2b6f-107">For more information, see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2b6f-108">Cuando se ejecuta una consulta de instancias de servicio, el conjunto de resultados que se devuelve mostrará el valor de  **\<nombre no está disponible >** para el **ServiceName** campo de un servicio de instancia si el puerto de envío correspondiente ubicación de recepción, o se ha eliminado la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-108">When you execute a query for service instances, the result set that is returned will display a value of **\<Name is not available>** for the **ServiceName** field of a service instance if the corresponding send port, receive location, or orchestration has been deleted.</span></span>  <span data-ttu-id="e2b6f-109">El **ServiceName** campo de una instancia de servicio se rellena mediante una búsqueda en la base de datos de administración de BizTalk para el nombre descriptivo del puerto de envío, ubicación de recepción, u orquestación.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-109">The **ServiceName** field of a service instance is populated by a lookup into the BizTalk management database for the friendly name of the send port, receive location, or orchestration.</span></span>  <span data-ttu-id="e2b6f-110">Si el puerto de envío, ubicación de recepción, o se elimina la orquestación, a continuación, se produce un error en la búsqueda para el nombre descriptivo y  **\<nombre no está disponible >** se muestra.</span><span class="sxs-lookup"><span data-stu-id="e2b6f-110">If the send port, receive location, or orchestration is deleted then the lookup for the friendly name fails and **\<Name is not available>** is displayed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2b6f-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e2b6f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="e2b6f-112">Cómo abrir una consulta guardada</span><span class="sxs-lookup"><span data-stu-id="e2b6f-112">How to Open a Saved Query</span></span>](../core/how-to-open-a-saved-query.md)  
  
-   [<span data-ttu-id="e2b6f-113">Cómo buscar todas las instancias de servicio</span><span class="sxs-lookup"><span data-stu-id="e2b6f-113">How to Search for All Service Instances</span></span>](../core/how-to-search-for-all-service-instances.md)  
  
-   [<span data-ttu-id="e2b6f-114">Búsqueda de instancias de servicio en ejecución</span><span class="sxs-lookup"><span data-stu-id="e2b6f-114">How to Search for Running Service Instances</span></span>](../core/how-to-search-for-running-service-instances.md)  
  
-   [<span data-ttu-id="e2b6f-115">Cómo buscar instancias de servicio suspendidas</span><span class="sxs-lookup"><span data-stu-id="e2b6f-115">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)  
  
-   [<span data-ttu-id="e2b6f-116">Cómo buscar mensajes</span><span class="sxs-lookup"><span data-stu-id="e2b6f-116">How to Search for Messages</span></span>](../core/how-to-search-for-messages.md)  
  
-   [<span data-ttu-id="e2b6f-117">Cómo buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="e2b6f-117">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)  
  
-   [<span data-ttu-id="e2b6f-118">Cómo guardar una consulta</span><span class="sxs-lookup"><span data-stu-id="e2b6f-118">How to Save a Query</span></span>](../core/how-to-save-a-query.md)  
  
-   [<span data-ttu-id="e2b6f-119">Búsqueda de eventos de seguimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e2b6f-119">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="e2b6f-120">Búsqueda de instancias de servicio controladas</span><span class="sxs-lookup"><span data-stu-id="e2b6f-120">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)
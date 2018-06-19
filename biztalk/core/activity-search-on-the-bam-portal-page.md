---
title: Búsqueda de actividad en el Portal de BAM página | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- Activity Search page [BAM portal]
- BAM portal, activity searches
ms.assetid: 24a5111c-026f-4f77-8a17-65955aafd24c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 670d73cb33d9e3cc3aa1a9162cf929382a4dd58a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225124"
---
# <a name="activity-search-on-the-bam-portal-page"></a><span data-ttu-id="0579f-102">Búsqueda de actividad en la página del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="0579f-102">Activity Search on the BAM Portal Page</span></span>
<span data-ttu-id="0579f-103">Los usuarios empresariales finales, programadores y analistas de negocios pueden utilizar la página del portal de BAM cuando necesiten realizar búsquedas en datos de BAM para encontrar casos específicos de este proceso en particular.</span><span class="sxs-lookup"><span data-stu-id="0579f-103">Business end users, developers, and business analysts can use the BAM portal page when they need to perform searches against BAM data to find specific cases of a particular process.</span></span> <span data-ttu-id="0579f-104">Estos procesos se definen como actividades de BAM.</span><span class="sxs-lookup"><span data-stu-id="0579f-104">These processes are defined as BAM activities.</span></span> <span data-ttu-id="0579f-105">Una actividad de BAM representa una unidad de trabajo en un negocio, como un pedido o una aplicación de préstamo.</span><span class="sxs-lookup"><span data-stu-id="0579f-105">A BAM activity represents a unit of work in a business, such as a purchase order or loan application.</span></span>  
  
## <a name="how-an-activity-search-works"></a><span data-ttu-id="0579f-106">Cómo funciona una búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="0579f-106">How an activity search works</span></span>  
 <span data-ttu-id="0579f-107">La búsqueda de actividad permite realizar búsquedas de datos de BAM para encontrar actividades que coincidan con el criterio que determinó, en función de los elementos y valores de seguimiento que están disponibles en la vista de BAM, y para mostrar las actividades para que las pueda editar así como crear alertas en función de las actividades.</span><span class="sxs-lookup"><span data-stu-id="0579f-107">An activity search allows you to perform searches against BAM data to find activities that match criteria you specify based on tracked values and items available in a BAM view, and to display the activities so that you can edit them or create alerts based on them.</span></span>  
  
 <span data-ttu-id="0579f-108">Puede guardar y volver a utilizar las consultas que crea para sus búsquedas.</span><span class="sxs-lookup"><span data-stu-id="0579f-108">Queries that you create for your searches can be saved and reused.</span></span> <span data-ttu-id="0579f-109">También puede usarlas como base para una alerta, por ejemplo, "Notificarme cada vez que llegue un pedido del cliente determinado".</span><span class="sxs-lookup"><span data-stu-id="0579f-109">You can also use them as the basis for an alert, for example, "Notify me any time a purchase order arrives from the specified customer."</span></span> <span data-ttu-id="0579f-110">Los botones situados en la parte superior de la página de contenidos se usan para guardar, abrir y ejecutar consultas, así como para establecer alertas.</span><span class="sxs-lookup"><span data-stu-id="0579f-110">You use the buttons at the top of the content page to save, open, and run queries, as well as to set alerts.</span></span>  
  
 <span data-ttu-id="0579f-111">Las búsquedas de actividad le permiten ubicar las actividades que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="0579f-111">Activity searches allow you to locate the activities that you want to monitor.</span></span> <span data-ttu-id="0579f-112">Tras crear una búsqueda de actividad, puede utilizarla para crear una alerta que le notifique los eventos que le interesen.</span><span class="sxs-lookup"><span data-stu-id="0579f-112">Once you create an activity search, you can use that search to create an alert that will notify you of events that are of interest.</span></span>  
  
## <a name="the-activity-search-page"></a><span data-ttu-id="0579f-113">La página Búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="0579f-113">The Activity Search page</span></span>  
 <span data-ttu-id="0579f-114">La página Búsqueda de actividad económica está dividida en tres secciones principales dentro del marco Contenido:</span><span class="sxs-lookup"><span data-stu-id="0579f-114">The Activity Search page is divided into three main sections inside the Content frame:</span></span>  
  
-   <span data-ttu-id="0579f-115">**Consulta**: esta sección permite a los usuarios buscar actividades mediante la creación de cláusulas de búsqueda en función de los elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="0579f-115">**Query**: This section allows users to search for activities by building search clauses based on specific tracked data items.</span></span> <span data-ttu-id="0579f-116">El usuario puede agregar y quitar cláusulas cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0579f-116">The user can add and remove clauses as required.</span></span>  
  
-   <span data-ttu-id="0579f-117">**Selector de columnas**: esta sección permite a los usuarios especificar qué elementos de datos, de los disponibles en la vista, para devolver si los registros que coincidan con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0579f-117">**Column Chooser**: This section allows users to specify which items of data, from those available in that view, to return if any records match the search criteria.</span></span>  
  
-   <span data-ttu-id="0579f-118">**Resultados**: resultados de la consulta se muestran en esta sección.</span><span class="sxs-lookup"><span data-stu-id="0579f-118">**Results**: Results of the query display in this section.</span></span>  
  
 <span data-ttu-id="0579f-119">Para obtener más información acerca de las búsquedas de actividad y la página de búsqueda de actividad, vea [búsquedas de actividad en el Portal de BAM](../core/activity-searches-in-the-bam-portal.md).</span><span class="sxs-lookup"><span data-stu-id="0579f-119">For more information about activity searches and the Activity Search page, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0579f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0579f-120">See Also</span></span>  
 <span data-ttu-id="0579f-121">[Portal de BAM](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="0579f-121">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="0579f-122">[Implementar actividades BAM con secuencias de eventos](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="0579f-122">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 [<span data-ttu-id="0579f-123">Alert Manager en el Portal de BAM de página</span><span class="sxs-lookup"><span data-stu-id="0579f-123">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)
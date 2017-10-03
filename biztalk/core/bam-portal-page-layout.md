---
title: "Diseño de la página de Portal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal
- Portal page [BAM portal]
ms.assetid: 0d8833b7-dd2f-475c-a890-e925ee47d219
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5569021698eb856d7584a2510a27d69f092f37a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-portal-page-layout"></a><span data-ttu-id="9debb-102">Diseño de la página del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="9debb-102">BAM Portal Page Layout</span></span>
<span data-ttu-id="9debb-103">La página del portal de BAM se presenta en los tres marcos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9debb-103">The BAM portal page is laid out in the following three frames:</span></span>  
  
-   <span data-ttu-id="9debb-104">Pancarta</span><span class="sxs-lookup"><span data-stu-id="9debb-104">Banner</span></span>  
  
-   <span data-ttu-id="9debb-105">Mis vistas</span><span class="sxs-lookup"><span data-stu-id="9debb-105">My Views</span></span>  
  
-   <span data-ttu-id="9debb-106">Contenido</span><span class="sxs-lookup"><span data-stu-id="9debb-106">Content</span></span>  
  
## <a name="banner"></a><span data-ttu-id="9debb-107">Pancarta</span><span class="sxs-lookup"><span data-stu-id="9debb-107">Banner</span></span>  
 <span data-ttu-id="9debb-108">El **pancarta** marco se encuentra en la parte superior de la página del portal.</span><span class="sxs-lookup"><span data-stu-id="9debb-108">The **Banner** frame is located across the top of the portal page.</span></span> <span data-ttu-id="9debb-109">El marco Titular contiene información de marca, como el nombre y el logotipo de la compañía, vínculos a la Ayuda de esa página de la interfaz de usuario (UI) y a títulos de página.</span><span class="sxs-lookup"><span data-stu-id="9debb-109">The Banner frame contains branding information such as the company name and logo, links to Help for that page of the user interface (UI), and page titles.</span></span> <span data-ttu-id="9debb-110">Puede personalizar la marca para que se ajuste a las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="9debb-110">You can customize the branding to conform to your organization's needs.</span></span> <span data-ttu-id="9debb-111">Para obtener más información acerca de cómo personalizar la información de marca en el titular, consulte [personalizar la configuración del Portal de BAM](../core/customizing-the-bam-portal-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="9debb-111">For more information about customizing the branding information in the banner, see [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md).</span></span>  
  
## <a name="my-views"></a><span data-ttu-id="9debb-112">Mis vistas</span><span class="sxs-lookup"><span data-stu-id="9debb-112">My Views</span></span>  
 <span data-ttu-id="9debb-113">El **Mis vistas** marco está en el lado izquierdo de la página del portal.</span><span class="sxs-lookup"><span data-stu-id="9debb-113">The **My Views** frame is on the left side of the portal page.</span></span> <span data-ttu-id="9debb-114">y muestra a los usuarios todas las vistas de las que se le han concedido permisos.</span><span class="sxs-lookup"><span data-stu-id="9debb-114">My Views shows users all views for which they have been granted permissions.</span></span> <span data-ttu-id="9debb-115">Los usuarios puede expandir cualquier vista para ver las características disponibles para ella.</span><span class="sxs-lookup"><span data-stu-id="9debb-115">Users can expand any view to see the features available to them for that view.</span></span> <span data-ttu-id="9debb-116">Si no se muestra ninguna vista, es posible que no se haya creado ninguna vista (tarea que realiza normalmente un analista de negocios) o que no se hayan concedido los permisos al usuario (tarea que realiza normalmente un administrador).</span><span class="sxs-lookup"><span data-stu-id="9debb-116">If there are no views shown, then either views have not been created, a task typically performed by a business analyst, or permissions have not been granted to the user, a task typically performed by an administrator.</span></span>  
  
 <span data-ttu-id="9debb-117">En cada vista puede realizar tres tareas:</span><span class="sxs-lookup"><span data-stu-id="9debb-117">Each view has three tasks that you can perform within the view:</span></span>  
  
-   <span data-ttu-id="9debb-118">**Búsqueda de actividad**: le permite crear consultas y alertas basadas en una actividad.</span><span class="sxs-lookup"><span data-stu-id="9debb-118">**Activity Search**: Allows you to create queries and alerts based on an activity.</span></span>  
  
-   <span data-ttu-id="9debb-119">**Las agregaciones**: le permite ver los datos agregados y crear alertas basadas en los totales en el gráfico de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="9debb-119">**Aggregations**: Allows you to view aggregate data and to create alerts based on totals in the PivotTable chart.</span></span>  
  
-   <span data-ttu-id="9debb-120">**Administrador de alertas**: le permite crear, editar, ver y suscribirse a alertas.</span><span class="sxs-lookup"><span data-stu-id="9debb-120">**Alert Manager**: Allows you to create, edit, view, and subscribe to alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9debb-121">C uando selecciona el Administrador de alertas del marco Mis vistas, solo podrá editar una alerta existente.</span><span class="sxs-lookup"><span data-stu-id="9debb-121">When selecting the Alert Manager from the My Views frame you can only edit an existing alert.</span></span> <span data-ttu-id="9debb-122">Para crear alertas nuevas, debe ir a la página Administrador de alertas desde la página Búsqueda de actividad o Agregaciones.</span><span class="sxs-lookup"><span data-stu-id="9debb-122">To create new alerts you must go to the Alerts Manager page from within the Activity Search or Aggregations page.</span></span>  
  
## <a name="content"></a><span data-ttu-id="9debb-123">Contenido</span><span class="sxs-lookup"><span data-stu-id="9debb-123">Content</span></span>  
 <span data-ttu-id="9debb-124">El **contenido** marco está en el lado derecho de la página del portal.</span><span class="sxs-lookup"><span data-stu-id="9debb-124">The **Content** frame is on the right side of the portal page.</span></span> <span data-ttu-id="9debb-125">La página de contenido contiene la información que presenta cada una de las tareas Mis vistas (Búsqueda de actividad, Agregaciones y Administración de alertas).</span><span class="sxs-lookup"><span data-stu-id="9debb-125">The content page contains the information presented by each of the My View tasks (Activity Search, Aggregations, and Alert Management).</span></span> <span data-ttu-id="9debb-126">Cuando selecciona una tarea, el marco Contenido cambia para reflejar las funciones asociadas a ella.</span><span class="sxs-lookup"><span data-stu-id="9debb-126">As you select a task, the content frame changes to reflect the functions associated with that task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9debb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9debb-127">See Also</span></span>  
 <span data-ttu-id="9debb-128">[Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="9debb-128">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 <span data-ttu-id="9debb-129">[Las agregaciones en el Portal de BAM página](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="9debb-129">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 <span data-ttu-id="9debb-130">[Alert Manager en el Portal de BAM de página](../core/alert-manager-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="9debb-130">[Alert Manager on the BAM Portal Page](../core/alert-manager-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="9debb-131">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="9debb-131">BAM Portal</span></span>](../core/bam-portal.md)
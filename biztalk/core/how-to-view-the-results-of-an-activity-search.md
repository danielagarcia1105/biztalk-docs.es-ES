---
title: Cómo ver los resultados de una búsqueda de actividad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], activity searches
- queries [BAM], viewing results
- Query Builder [BAM portal], activity searches
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
- Query Builder [BAM portal], viewing results
ms.assetid: d45cd777-d798-4f3b-ad9a-5121168d7b99
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5e96da9ed256557306cc4d69ad529161fa3342
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257732"
---
# <a name="how-to-view-the-results-of-an-activity-search"></a><span data-ttu-id="c1b30-102">Cómo ver los resultados de una búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="c1b30-102">How to View the Results of an Activity Search</span></span>
<span data-ttu-id="c1b30-103">Los usuarios pueden ver los resultados de una consulta haciendo clic en el **Ejecutar consulta** botón en la sección superior del marco de contenido del portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c1b30-103">Users can view the results of a query by clicking the **Execute Query** button in the upper section of the content frame of the BAM portal.</span></span> <span data-ttu-id="c1b30-104">Los resultados de la consulta se muestran en la **resultados** sección en la parte inferior del marco.</span><span class="sxs-lookup"><span data-stu-id="c1b30-104">The results of the query are displayed in the **Results** section at the bottom of the frame.</span></span>  
  
 <span data-ttu-id="c1b30-105">Los resultados de una búsqueda de actividad se muestran con un registro por fila.</span><span class="sxs-lookup"><span data-stu-id="c1b30-105">The results of an activity search are displayed with one record per row.</span></span> <span data-ttu-id="c1b30-106">Cada registro consta de los datos y los hitos seleccionado en el selector de columnas y se muestran en el orden en el que se hayan organizado en el **elementos para mostrar** cuadro.</span><span class="sxs-lookup"><span data-stu-id="c1b30-106">Each record consists of the data and milestones selected in the column chooser and are displayed in the order in which they were arranged in the **Items to show** box.</span></span>  
  
 <span data-ttu-id="c1b30-107">Para obtener detalles adicionales acerca de un registro devuelto, puede hacer clic en el interior de la fila.</span><span class="sxs-lookup"><span data-stu-id="c1b30-107">To get additional details about a returned record you can click anywhere in the row.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c1b30-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c1b30-108">Prerequisites</span></span>  
 <span data-ttu-id="c1b30-109">Para llevar a cabo los procedimientos incluidos en este tema, deberá disponer de una actividad implementada.</span><span class="sxs-lookup"><span data-stu-id="c1b30-109">You must have a deployed activity to perform the procedures in this topic.</span></span> <span data-ttu-id="c1b30-110">Para obtener información acerca de cómo hacerlo, consulte [cómo aplicar y quitar un perfil de seguimiento](../core/how-to-apply-and-remove-a-tracking-profile.md).</span><span class="sxs-lookup"><span data-stu-id="c1b30-110">For information about how to do this, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
## <a name="return-results"></a><span data-ttu-id="c1b30-111">Devolver los resultados</span><span class="sxs-lookup"><span data-stu-id="c1b30-111">Return results</span></span>  
  
#### <a name="to-execute-a-query-to-return-results"></a><span data-ttu-id="c1b30-112">Para ejecutar una consulta para que devuelva resultados</span><span class="sxs-lookup"><span data-stu-id="c1b30-112">To execute a query to return results</span></span>  
  
1.  <span data-ttu-id="c1b30-113">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.</span><span class="sxs-lookup"><span data-stu-id="c1b30-113">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2.  <span data-ttu-id="c1b30-114">En el **Mis vistas** panel, haga clic en una vista para la que está creando la búsqueda de actividad.</span><span class="sxs-lookup"><span data-stu-id="c1b30-114">In the **My Views** pane, click a view for which you are creating the activity search.</span></span>  
  
3.  <span data-ttu-id="c1b30-115">Haga clic en una actividad asociada a la vista para cargar dicha actividad en el marco de contenido.</span><span class="sxs-lookup"><span data-stu-id="c1b30-115">Click an activity associated with the view to load that activity in the content frame.</span></span>  
  
4.  <span data-ttu-id="c1b30-116">Cree una búsqueda de actividad o abra una ya existente.</span><span class="sxs-lookup"><span data-stu-id="c1b30-116">Create an activity search or open an existing activity search.</span></span> <span data-ttu-id="c1b30-117">Para obtener información acerca de la creación o apertura de búsquedas de actividad, vea [cómo crear una consulta de búsqueda de actividad](../core/how-to-create-a-query-in-activity-search.md).</span><span class="sxs-lookup"><span data-stu-id="c1b30-117">For information about creating or opening activity searches, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
5.  <span data-ttu-id="c1b30-118">Haga clic en el **Ejecutar consulta** situado en la parte superior del marco de contenido del portal.</span><span class="sxs-lookup"><span data-stu-id="c1b30-118">Click the **Execute Query** button located at the top of the content frame of the portal.</span></span>  
  
6.  <span data-ttu-id="c1b30-119">Desplácese hacia abajo para ver el resultado de la consulta en el **resultados** área del marco de contenido.</span><span class="sxs-lookup"><span data-stu-id="c1b30-119">Scroll down to view the output of the query in the **Results** area of the content frame.</span></span>  
  
## <a name="view-results-information"></a><span data-ttu-id="c1b30-120">Ver información de resultados</span><span class="sxs-lookup"><span data-stu-id="c1b30-120">View results information</span></span>  
 <span data-ttu-id="c1b30-121">Puede ver el estado detallado de los elementos devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="c1b30-121">You can view detailed status for items returned by the query.</span></span> <span data-ttu-id="c1b30-122">Los detalles adicionales que se muestran son:</span><span class="sxs-lookup"><span data-stu-id="c1b30-122">Additional details that are displayed are:</span></span>  
  
-   <span data-ttu-id="c1b30-123">Estado de actividad, que contiene los hitos y datos asociados.</span><span class="sxs-lookup"><span data-stu-id="c1b30-123">Activity status, consisting of associated milestones and data</span></span>  
  
-   <span data-ttu-id="c1b30-124">Documentos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1b30-124">Related documents</span></span>  
  
-   <span data-ttu-id="c1b30-125">Actividades relacionadas</span><span class="sxs-lookup"><span data-stu-id="c1b30-125">Related activities</span></span>  
  
 <span data-ttu-id="c1b30-126">Además, puede solicitar asistencia del administrador haciendo clic en el **asistencia** botón siguiente la **actividades relacionadas** área en el marco de contenido.</span><span class="sxs-lookup"><span data-stu-id="c1b30-126">In addition, you can request assistance from your administrator by clicking the **Assistance** button below the **Related Activities** area in the content frame.</span></span>  
  
#### <a name="to-view-detailed-status-information-on-results"></a><span data-ttu-id="c1b30-127">Para ver información de estado detallada sobre los resultados</span><span class="sxs-lookup"><span data-stu-id="c1b30-127">To view detailed status information on results</span></span>  
  
1.  <span data-ttu-id="c1b30-128">Siga el procedimiento anterior para ejecutar una consulta de modo que devuelva los resultados.</span><span class="sxs-lookup"><span data-stu-id="c1b30-128">Follow the previous procedure to execute a query to return results.</span></span>  
  
2.  <span data-ttu-id="c1b30-129">Haga clic en una fila para cargar la información de estado detallada del elemento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="c1b30-129">Click a row to load the detailed status information for the result item.</span></span>  
  
3.  <span data-ttu-id="c1b30-130">Si el área que contiene la información detallada de interés está contraída, haga clic en el signo MÁS (+) situado junto al área en cuestión para abrirla.</span><span class="sxs-lookup"><span data-stu-id="c1b30-130">If the area containing the detailed information you are interested in is collapsed, click the plus sign (+) next to the area label to open it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1b30-131">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1b30-131">In This Section</span></span>  
  
-   [<span data-ttu-id="c1b30-132">Estado de actividad</span><span class="sxs-lookup"><span data-stu-id="c1b30-132">Activity Status</span></span>](../core/activity-status.md)  
  
-   [<span data-ttu-id="c1b30-133">Documentos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1b30-133">Related Documents</span></span>](../core/related-documents.md)  
  
-   [<span data-ttu-id="c1b30-134">Actividades relacionadas</span><span class="sxs-lookup"><span data-stu-id="c1b30-134">Related Activities</span></span>](../core/related-activities.md)  
  
-   [<span data-ttu-id="c1b30-135">Solicitar asistencia</span><span class="sxs-lookup"><span data-stu-id="c1b30-135">Request Assistance</span></span>](../core/request-assistance.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1b30-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1b30-136">See Also</span></span>  
 [<span data-ttu-id="c1b30-137">Búsquedas de actividad en el Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="c1b30-137">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)
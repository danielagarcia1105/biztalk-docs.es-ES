---
title: Cómo establecer una alerta | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, creating
- Query Builder [BAM portal], creating alerts
- queries [BAM], aggregations
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal], aggregation alerts
- queries [BAM], alerts
- aggregations, alerts
ms.assetid: 8745d2c6-5bc0-4d7a-8c17-361535f5c6e6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774fbab86c1da1389b813f621c89f38cf0aa7656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255708"
---
# <a name="how-to-set-an-alert"></a><span data-ttu-id="2df64-102">Cómo establecer una alerta</span><span class="sxs-lookup"><span data-stu-id="2df64-102">How to Set an Alert</span></span>
<span data-ttu-id="2df64-103">Para establecer una alerta, puede adjuntarla a una búsqueda de actividad, o llegar hasta ella por medio de una agregación.</span><span class="sxs-lookup"><span data-stu-id="2df64-103">You can set an alert by attaching it to an activity search or drilling down through an aggregation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df64-104">Antes de establecer una alerta en una consulta, deberá ejecutar la consulta y evaluar si las duraciones de ciclo de alerta son apropiadas para el proceso que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="2df64-104">Before setting an alert on a query, you should run the query and evaluate whether the alert cycle durations are appropriate for the process you are monitoring.</span></span> <span data-ttu-id="2df64-105">Si la duración de ciclo es demasiado breve, es posible que se produzca una condición de alerta de manera transitoria y que, como consecuencia, el sistema de alerta no pueda detectarla.</span><span class="sxs-lookup"><span data-stu-id="2df64-105">If the cycle duration is too short, it is possible for an alert condition to occur in a transient manner and thus be missed by the alerting system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df64-106">Si hace clic en el botón Atrás durante estos procedimientos, puede recibir el siguiente mensaje: "Advertencia: la página ha caducado."</span><span class="sxs-lookup"><span data-stu-id="2df64-106">If you click the back button during these procedures, you may receive the following message: "Warning: page has expired."</span></span> <span data-ttu-id="2df64-107">Para volver al contenido anterior, presione F5.</span><span class="sxs-lookup"><span data-stu-id="2df64-107">To return to the previous content, press F5.</span></span> <span data-ttu-id="2df64-108">(Es posible que tenga que presionar F5 varias veces.)</span><span class="sxs-lookup"><span data-stu-id="2df64-108">(You may have to press F5 several times.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df64-109">Al crear la primera alerta de una vista, no se mostrarán datos para dicha alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-109">When you create the first alert on a view, there will be no data displayed for the alert.</span></span> <span data-ttu-id="2df64-110">La definición de una alerta no recopila los datos de alerta correspondientes al marco de tiempo anterior a la creación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-110">Defining an alert does not collect alert data from the time frame before the alert was created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2df64-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2df64-111">Prerequisites</span></span>  
 <span data-ttu-id="2df64-112">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="2df64-112">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="2df64-113">Debe tener una vista implementada.</span><span class="sxs-lookup"><span data-stu-id="2df64-113">You must have a deployed view.</span></span>  
  
-   <span data-ttu-id="2df64-114">Asimismo, debe existir una búsqueda de actividad para una alerta de instancia.</span><span class="sxs-lookup"><span data-stu-id="2df64-114">You must have an activity search for an instance alert.</span></span>  
  
-   <span data-ttu-id="2df64-115">Debe existir una agregación rellenada para una alerta de agregación.</span><span class="sxs-lookup"><span data-stu-id="2df64-115">You must have a populated aggregation for an aggregation alert.</span></span>  
  
### <a name="to-set-an-alert-on-an-activity-search"></a><span data-ttu-id="2df64-116">Para establecer una alerta en una búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="2df64-116">To set an alert on an activity search</span></span>  
  
1.  <span data-ttu-id="2df64-117">En el **Mis vistas** de marco, haga clic en una vista para expandir la lista de tareas para la vista.</span><span class="sxs-lookup"><span data-stu-id="2df64-117">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="2df64-118">Haga clic en el **búsqueda de actividad** tarea en la vista que ha expandido.</span><span class="sxs-lookup"><span data-stu-id="2df64-118">Click the **Activity Search** task under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="2df64-119">Cree o abra una búsqueda de actividad.</span><span class="sxs-lookup"><span data-stu-id="2df64-119">Create or open an activity search.</span></span> <span data-ttu-id="2df64-120">Para obtener información acerca de cómo hacerlo, consulte [cómo crear una consulta de búsqueda de actividad](../core/how-to-create-a-query-in-activity-search.md).</span><span class="sxs-lookup"><span data-stu-id="2df64-120">For information about how to do this, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
4.  <span data-ttu-id="2df64-121">En el marco de contenido del portal de BAM, haga clic en el **establecer alerta** botón.</span><span class="sxs-lookup"><span data-stu-id="2df64-121">In the content frame of the BAM portal, click the **Set Alert** button.</span></span> <span data-ttu-id="2df64-122">El marco de contenido se cargará con la plantilla de creación de alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-122">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="2df64-123">En el **nombre** texto, escriba un nombre descriptivo para la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-123">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df64-124">Los nombres están limitados a 100 caracteres y no puede contener los siguientes caracteres: ~! @# $% ^&amp;\* ();  Si usa alguno de estos caracteres en un nombre, aparece un contorno de líneas rojas discontinuo alrededor del campo de texto que indica que debe corregirlo para completar la acción.</span><span class="sxs-lookup"><span data-stu-id="2df64-124">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="2df64-125">Si no desea habilitar la alerta en este momento, desactive la **alerta habilitada** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="2df64-125">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="2df64-126">En el **mensaje** texto, escriba el mensaje que se envía cuando se desencadene la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-126">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="2df64-127">Desde el **prioridad** lista desplegable, elija el nivel de prioridad para esta alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-127">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="2df64-128">El valor de prioridad indica la gravedad del problema para el que se ha establecido la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-128">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="2df64-129">En el **propietarios** cuadro de texto, escriba el alias de los propietarios de esta alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-129">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="2df64-130">Use signos de punto y coma para separar los nombres de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="2df64-130">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="2df64-131">En el **alerta seguridad** área, active la casilla de verificación para permitir que otros usuarios vean esta alerta y suscribirse a él.</span><span class="sxs-lookup"><span data-stu-id="2df64-131">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df64-132">Puede cambiar la seguridad de alertas de privada a pública (y viceversa) en cualquier momento. La presencia de suscriptores en la alerta no afectará a esta acción.</span><span class="sxs-lookup"><span data-stu-id="2df64-132">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="2df64-133">Sin embargo, al cambiar la seguridad de alertas de pública a privada, deberá tener en cuenta si existen suscriptores a la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-133">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="2df64-134">Si existen suscriptores a la alerta, éstos no podrán editar su suscripción cuando la alerta pase a ser privada.</span><span class="sxs-lookup"><span data-stu-id="2df64-134">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
11. <span data-ttu-id="2df64-135">En la esquina superior derecha de la **detalles de la alerta** área, haga clic en el **guardar alerta** botón.</span><span class="sxs-lookup"><span data-stu-id="2df64-135">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
### <a name="to-set-an-alert-on-an-aggregation"></a><span data-ttu-id="2df64-136">Para establecer una alerta en una agregación</span><span class="sxs-lookup"><span data-stu-id="2df64-136">To set an alert on an aggregation</span></span>  
  
1.  <span data-ttu-id="2df64-137">En el **Mis vistas** de marco, haga clic en una vista para expandir la lista de tareas para la vista.</span><span class="sxs-lookup"><span data-stu-id="2df64-137">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="2df64-138">Haga clic en el **agregaciones** de tareas en **Mis vistas** debajo de la vista expande.</span><span class="sxs-lookup"><span data-stu-id="2df64-138">Click the **Aggregations** task in **My Views** under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="2df64-139">En el marco de contenido del portal de BAM, haga clic con el botón secundario en una celda de la columna de totales del informe de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="2df64-139">In the content frame of the BAM portal, right-click a cell in the totals column of the PivotTable report.</span></span> <span data-ttu-id="2df64-140">Se abrirá un menú contextual con funciones disponibles para llevarse a cabo en el total de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="2df64-140">This opens a context menu with functions that are available to perform on the aggregation total.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df64-141">Puede establecer una alerta en un componente específico del total de agregaciones expandiendo el elemento de línea en cuestión.</span><span class="sxs-lookup"><span data-stu-id="2df64-141">You can set an alert on a specific component of the aggregation total by expanding that line item.</span></span> <span data-ttu-id="2df64-142">Puede expandir los niveles sucesivos de esta forma, hasta alcanzar el nivel en el que desea establecer la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-142">You can expand succeeding levels in this manner until you reach the level at which you want to set your alert.</span></span>  
  
4.  <span data-ttu-id="2df64-143">En la parte superior del menú contextual, haga clic en **crear alertas**.</span><span class="sxs-lookup"><span data-stu-id="2df64-143">At the top of the context menu, click **Create Alert**.</span></span> <span data-ttu-id="2df64-144">El marco de contenido se cargará con la plantilla de creación de alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-144">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="2df64-145">En el **nombre** texto, escriba un nombre descriptivo para la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-145">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df64-146">Los nombres están limitados a 100 caracteres y no puede contener los siguientes caracteres: ~! @# $% ^&amp;\* ();  Si usa alguno de estos caracteres en un nombre, aparece un contorno de líneas rojas discontinuo alrededor del campo de texto que indica que debe corregirlo para completar la acción.</span><span class="sxs-lookup"><span data-stu-id="2df64-146">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="2df64-147">Si no desea habilitar la alerta en este momento, desactive la **alerta habilitada** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="2df64-147">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="2df64-148">En el **mensaje** texto, escriba el mensaje que se envía cuando se desencadene la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-148">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="2df64-149">Desde el **prioridad** lista desplegable, elija el nivel de prioridad para esta alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-149">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="2df64-150">El valor de prioridad indica la gravedad del problema para el que se ha establecido la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-150">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="2df64-151">En el **propietarios** cuadro de texto, escriba el alias de los propietarios de esta alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-151">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="2df64-152">Use signos de punto y coma para separar los nombres de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="2df64-152">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="2df64-153">En el **umbral** área, seleccione una condición de comparación de la **recuento** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2df64-153">In the **Threshold** area, select a comparison condition from the **Count** drop-down list.</span></span>  
  
11. <span data-ttu-id="2df64-154">En el **duración** texto cuadro, escriba el número de unidades de tiempo en las que se mide el umbral.</span><span class="sxs-lookup"><span data-stu-id="2df64-154">In the **Duration** text box, enter the number of time units across which the threshold is measured.</span></span>  
  
12. <span data-ttu-id="2df64-155">Desde el **duración** lista desplegable, seleccione la unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2df64-155">From the **Duration** drop-down list, select the unit of time.</span></span>  
  
13. <span data-ttu-id="2df64-156">En el **alerta seguridad** área, active la casilla de verificación para permitir que otros usuarios vean esta alerta y suscribirse a él.</span><span class="sxs-lookup"><span data-stu-id="2df64-156">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2df64-157">Puede cambiar la seguridad de alertas de privada a pública (y viceversa) en cualquier momento. La presencia de suscriptores en la alerta no afectará a esta acción.</span><span class="sxs-lookup"><span data-stu-id="2df64-157">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="2df64-158">Sin embargo, al cambiar la seguridad de alertas de pública a privada, deberá tener en cuenta si existen suscriptores a la alerta.</span><span class="sxs-lookup"><span data-stu-id="2df64-158">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="2df64-159">Si existen suscriptores a la alerta, éstos no podrán editar su suscripción cuando la alerta pase a ser privada.</span><span class="sxs-lookup"><span data-stu-id="2df64-159">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
14. <span data-ttu-id="2df64-160">En la esquina superior derecha de la **detalles de la alerta** área, haga clic en el **guardar alerta** botón.</span><span class="sxs-lookup"><span data-stu-id="2df64-160">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df64-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df64-161">See Also</span></span>  
 [<span data-ttu-id="2df64-162">Cómo crear una consulta de búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="2df64-162">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)
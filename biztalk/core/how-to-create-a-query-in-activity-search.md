---
title: Cómo crear una consulta en búsqueda de actividad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query Builder [BAM portal], creating queries
- queries [BAM], saving
- queries [BAM], creating
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], opening queries
- Query Builder [BAM portal], saving queries
- queries [BAM], opening
ms.assetid: 7940e47d-10e4-4eb1-b4e6-a8b98461e3a8
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd89ec71319a70c0330ebef80c7c8165cacf6c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989753"
---
# <a name="how-to-create-a-query-in-activity-search"></a><span data-ttu-id="3e493-102">Cómo crear una consulta en Búsqueda de actividad</span><span class="sxs-lookup"><span data-stu-id="3e493-102">How to Create a Query in Activity Search</span></span>
<span data-ttu-id="3e493-103">Los usuarios empresariales finales que necesiten recibir notificaciones de eventos y estados relativos a su actividad empresarial deben utilizar consultas para crear búsquedas de actividad en las que basar las alertas.</span><span class="sxs-lookup"><span data-stu-id="3e493-103">Business end users and other users who need to receive notification of events and status pertaining to their business use queries to create activity searches on which to base alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e493-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3e493-104">Prerequisites</span></span>  
 <span data-ttu-id="3e493-105">Debe tener una vista implementada.</span><span class="sxs-lookup"><span data-stu-id="3e493-105">You must have a deployed view.</span></span>  
  
### <a name="to-open-a-query"></a><span data-ttu-id="3e493-106">Para abrir una consulta</span><span class="sxs-lookup"><span data-stu-id="3e493-106">To open a query</span></span>  
  
1. <span data-ttu-id="3e493-107">Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.</span><span class="sxs-lookup"><span data-stu-id="3e493-107">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="3e493-108">En el **Mis vistas** marco del portal, haga clic en una vista existente para expandir los menús disponibles en esa vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-108">In the **My Views** frame of the portal, click an existing view to expand the menus available to that view.</span></span>  
  
3. <span data-ttu-id="3e493-109">Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-109">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="3e493-110">Haga clic en una actividad de la lista.</span><span class="sxs-lookup"><span data-stu-id="3e493-110">Click an activity from the list.</span></span> <span data-ttu-id="3e493-111">Esto cargará la página Búsqueda de actividad de la actividad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3e493-111">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="3e493-112">En el marco de contenido en la parte superior de la página, haga clic en el **examinar** botón para abrir el **Elegir archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e493-112">In the content frame, at the top of the page, click the **Browse** button to open the **Choose file** dialog box.</span></span>  
  
6. <span data-ttu-id="3e493-113">Vaya a la carpeta donde ha guardado consultas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e493-113">Browse to the folder where you have previously saved queries.</span></span>  
  
7. <span data-ttu-id="3e493-114">Haga clic en una operación de Guardar consulta.</span><span class="sxs-lookup"><span data-stu-id="3e493-114">Click a save query.</span></span>  
  
8. <span data-ttu-id="3e493-115">Haga clic en el **abierto** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-115">Click the **Open** button.</span></span> <span data-ttu-id="3e493-116">Esto cargará la ruta de acceso a la consulta en el cuadro de texto a la izquierda de la **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-116">This will load the path to the query in the text box to the left of the **Browse** button.</span></span> <span data-ttu-id="3e493-117">También puede escribir la ruta de la consulta directamente en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3e493-117">You can also type the path to the query directly into the text box.</span></span>  
  
9. <span data-ttu-id="3e493-118">Haga clic en el **Abrir consulta** situado a la derecha de la **examinar** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-118">Click the **Open Query** button to the right of the **Browse** button.</span></span>  
  
### <a name="to-construct-a-query"></a><span data-ttu-id="3e493-119">Procedimiento para generar una consulta</span><span class="sxs-lookup"><span data-stu-id="3e493-119">To construct a query</span></span>  
  
1. <span data-ttu-id="3e493-120">Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.</span><span class="sxs-lookup"><span data-stu-id="3e493-120">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="3e493-121">En el **Mis vistas** marco del portal actualmente no hay una lista de las vistas configuradas.</span><span class="sxs-lookup"><span data-stu-id="3e493-121">In the **My Views** frame of the portal there is a list of currently configured views.</span></span> <span data-ttu-id="3e493-122">Debajo de cada vista se muestran tres tareas que se pueden realizar en dicha vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-122">Under each view there are three tasks that can be performed on the view.</span></span> <span data-ttu-id="3e493-123">Si la vista está contraída, haga clic en ella para expandir la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="3e493-123">If the view is currently collapsed, click the existing view to expand the list of tasks.</span></span>  
  
3. <span data-ttu-id="3e493-124">Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-124">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="3e493-125">Haga clic en una actividad de la lista.</span><span class="sxs-lookup"><span data-stu-id="3e493-125">Click an activity from the list.</span></span> <span data-ttu-id="3e493-126">Esto cargará la página Búsqueda de actividad de la actividad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3e493-126">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="3e493-127">En el marco de contenido en el **consulta** , seleccione un campo desde el **datos empresariales** lista desplegable que se usará para una comparación en la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e493-127">In the content frame, in the **Query** box, choose a field from the **Business Data** drop-down list to use for a comparison in the query.</span></span>  
  
6. <span data-ttu-id="3e493-128">Desde el **operador** lista desplegable, seleccione el operador de comparación a usar.</span><span class="sxs-lookup"><span data-stu-id="3e493-128">From the **Operator** drop-down list, select the comparison operator to use.</span></span>  
  
7. <span data-ttu-id="3e493-129">En el **valor** , escriba el valor para comparar.</span><span class="sxs-lookup"><span data-stu-id="3e493-129">In the **Value** box, enter the value to compare against.</span></span> <span data-ttu-id="3e493-130">Solo podrá escribir un valor adecuado para el campo con el que está comparando.</span><span class="sxs-lookup"><span data-stu-id="3e493-130">You will only be able to enter a value appropriate to the field to which you are comparing.</span></span> <span data-ttu-id="3e493-131">(Si el elemento de datos económicos es un campo de fecha, los datos de comparación son una fecha o una fecha y hora con el formato correspondiente a su configuración regional).</span><span class="sxs-lookup"><span data-stu-id="3e493-131">(If the business data item is a date field, then the comparison data is a date or date time formatted as appropriate for your culture settings.)</span></span>  
  
8. <span data-ttu-id="3e493-132">Si tiene más cláusulas que agregar a la consulta, haga clic en el **agregar** situado a la derecha del cuadro de consulta.</span><span class="sxs-lookup"><span data-stu-id="3e493-132">If you have more clauses to add to the query, click the **Add** button to the right of the query box.</span></span> <span data-ttu-id="3e493-133">Esto agregará una línea nueva para la siguiente cláusula.</span><span class="sxs-lookup"><span data-stu-id="3e493-133">This will add a new line for the next clause.</span></span> <span data-ttu-id="3e493-134">Puede especificar si las cláusulas deben unirse utilizando AND u OR.</span><span class="sxs-lookup"><span data-stu-id="3e493-134">You can select whether the clauses are join by using an AND or an OR.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3e493-135">No puede agrupar cláusulas para formar consultas más complejas.</span><span class="sxs-lookup"><span data-stu-id="3e493-135">You cannot group clauses to form more complex queries.</span></span> <span data-ttu-id="3e493-136">Una consulta es un conjunto sencillo de cláusulas combinadas mediante un operador AND u OR.</span><span class="sxs-lookup"><span data-stu-id="3e493-136">A query is a simple set of clauses joined by an AND or an OR operator.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3e493-137">Si hace clic en el botón Atrás durante estos procedimientos y recibe una "Advertencia: la página ha caducado" puede presionar F5 para regresar el contenido original.</span><span class="sxs-lookup"><span data-stu-id="3e493-137">If you click the back button during these procedures and receive a "warning: page has expired," you can press F5 to get your original contents back.</span></span> <span data-ttu-id="3e493-138">Es posible que tenga que presionar F5 varias veces.</span><span class="sxs-lookup"><span data-stu-id="3e493-138">You may have to press F5 several times.</span></span>  
  
9. <span data-ttu-id="3e493-139">En el selector de columnas, seleccione los datos o hitos de la **datos e hitos disponibles** cuadro de lista para la consulta se devuelven como datos.</span><span class="sxs-lookup"><span data-stu-id="3e493-139">In the Column Chooser select the data or milestones from the **Available Data and Milestones** list box for the query to return as data.</span></span> <span data-ttu-id="3e493-140">Puede seleccionar varios elementos presionando la tecla MAYÚS mientras hace clic en el primer y último elemento del grupo que desea que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="3e493-140">You can select multiple items by holding down the SHIFT key and clicking the first and last items in the group you want to return.</span></span> <span data-ttu-id="3e493-141">También puede seleccionar varios elementos individuales de la lista presionando la tecla CTRL mientras selecciona los elementos que desea obtener.</span><span class="sxs-lookup"><span data-stu-id="3e493-141">You can also select multiple items from the list by holding down the CTRL key and selecting the items to return.</span></span>  
  
10. <span data-ttu-id="3e493-142">Use la **>>** botón para mover los elementos seleccionados a la **elementos para mostrar** cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="3e493-142">Use the **>>** button to move the selected items to the **Items to show** list box.</span></span> <span data-ttu-id="3e493-143">Se pueden quitar elementos de esta lista seleccionándolos y usando el **<<** botón para volver al cuadro de lista datos e hitos.</span><span class="sxs-lookup"><span data-stu-id="3e493-143">You can remove items from this list by selecting them and using the **<<** button to move them back to the data and milestones list box.</span></span>  
  
11. <span data-ttu-id="3e493-144">Una vez seleccionados todos los elementos que debe devolver la consulta, puede reorganizar los resultados para determinar el orden de aparición de las columnas.</span><span class="sxs-lookup"><span data-stu-id="3e493-144">Once you have selected all the items that the query will return, you can rearrange the results to determine in what order the columns are shown.</span></span> <span data-ttu-id="3e493-145">Para mover una columna a la primera posición en el conjunto de datos devuelto, selecciónela haciendo clic en ella y haciendo clic en el **Subir** botón hasta que esté en la parte superior de la lista de elementos.</span><span class="sxs-lookup"><span data-stu-id="3e493-145">To move a column to the first position in the returned data set, select it by clicking it and clicking the **Move Up** button until it is at the top of the list of items.</span></span> <span data-ttu-id="3e493-146">De forma similar, para mover un elemento a una posición posterior en el conjunto de datos devuelto, seleccione el elemento haciendo clic en él y, a continuación, haciendo clic en el **Bajar** botón hasta que se encuentra en la posición en la que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="3e493-146">Similarly, to move an item to a later position in the returned data set, select the item by clicking it and then clicking the **Move Down** button until it is in the position in which you want it to display.</span></span>  
  
### <a name="to-save-a-query"></a><span data-ttu-id="3e493-147">Para guardar una consulta</span><span class="sxs-lookup"><span data-stu-id="3e493-147">To save a query</span></span>  
  
1.  <span data-ttu-id="3e493-148">En el marco de contenido en la parte superior de la página, haga clic en el **Guardar consulta** botón para abrir el **Guardar archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e493-148">In the content frame, at the top of the page, click the **Save Query** button to open the **Save File** dialog box.</span></span>  
  
2.  <span data-ttu-id="3e493-149">En el **de descarga del archivo** cuadro de diálogo, haga clic en el **guardar** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-149">On the **File Download** dialog box, click the **Save** button.</span></span>  
  
3.  <span data-ttu-id="3e493-150">Desplácese hasta la ubicación en que desea guardar la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e493-150">Browse to the location where you want to save the query.</span></span>  
  
4.  <span data-ttu-id="3e493-151">Puede aceptar el nombre predeterminado proporcionado para la consulta o puede escribir un nombre nuevo en el **nombre de archivo** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3e493-151">You can accept the default name provided for the query or you can enter a new name in the **File Name** text box.</span></span>  
  
5.  <span data-ttu-id="3e493-152">Haga clic en el **guardar** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-152">Click the **Save** button.</span></span>  
  
### <a name="to-execute-a-query"></a><span data-ttu-id="3e493-153">Para ejecutar una consulta</span><span class="sxs-lookup"><span data-stu-id="3e493-153">To execute a query</span></span>  
  
1. <span data-ttu-id="3e493-154">Haga clic en **iniciar**, apunte a **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **sitio Web de Portal de BAM**.</span><span class="sxs-lookup"><span data-stu-id="3e493-154">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="3e493-155">En el **Mis vistas** marco del portal, haga clic en una vista existente para expandir los menús disponibles en esa vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-155">In the **My Views** frame of the portal, click an existing view to expand the menus available to that view.</span></span>  
  
3. <span data-ttu-id="3e493-156">Haga clic en **búsqueda de actividad** para expandir la lista de actividades disponibles para la vista.</span><span class="sxs-lookup"><span data-stu-id="3e493-156">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="3e493-157">Haga clic en una actividad de la lista.</span><span class="sxs-lookup"><span data-stu-id="3e493-157">Click an activity from the list.</span></span> <span data-ttu-id="3e493-158">Esto cargará la página Búsqueda de actividad de la actividad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3e493-158">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="3e493-159">Abra una consulta existente o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="3e493-159">Either open an existing query or build a new query.</span></span>  
  
6. <span data-ttu-id="3e493-160">En el marco de contenido del portal, haga clic en el **Ejecutar consulta** botón.</span><span class="sxs-lookup"><span data-stu-id="3e493-160">In the content frame of the portal, click the **Execute Query** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e493-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e493-161">See Also</span></span>  
 [<span data-ttu-id="3e493-162">Búsquedas de actividad del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="3e493-162">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)
---
title: Cómo definir una actividad empresarial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3252d7a96b06da3590b4c823e150366e6ba24168
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983365"
---
# <a name="how-to-define-a-business-activity"></a><span data-ttu-id="3e2a7-102">Definición de actividades económicas</span><span class="sxs-lookup"><span data-stu-id="3e2a7-102">How to Define a Business Activity</span></span>
<span data-ttu-id="3e2a7-103">Para indicar los datos que necesita recopilar para informes, debe definir una actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-103">To indicate the data you need to collect for reports, you must define a BAM activity.</span></span> <span data-ttu-id="3e2a7-104">Dicha actividad contiene una lista de los elementos de datos e hitos importantes sobre los que BAM debe realizar un seguimiento. Use el complemento BAM para Excel a fin de crear una actividad como la que se muestra en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-104">This contains a list of the important milestones and data items you want BAM to track. Use the BAM Excel add-in to create an activity as shown in the following procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e2a7-105">Una vez implementada una actividad, las acciones que puede realizar sobre ella están restringidas.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-105">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="3e2a7-106">Específicamente, no puede eliminar elementos de una actividad a menos que esté dispuesto a que su administrador anule la implementación de toda la actividad de BAM y sus conjuntos de vista y los vuelva a implementar.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-106">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="3e2a7-107">Esto puede provocar una interrupción de la visibilidad y pérdidas de datos a menos que el administrador haga una copia de seguridad de los datos y los restaure.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-107">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
### <a name="to-create-a-business-activity"></a><span data-ttu-id="3e2a7-108">Procedimiento para crear una actividad económica</span><span class="sxs-lookup"><span data-stu-id="3e2a7-108">To create a business activity</span></span>  
  
1.  <span data-ttu-id="3e2a7-109">Abra Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-109">Open Microsoft Excel.</span></span>  
  
2.  <span data-ttu-id="3e2a7-110">En la barra de herramientas del menú, haga clic en el **BAM** elemento de menú y haga clic en **actividad de BAM**.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-110">On the menu tool bar, click the **BAM** menu item, and click **BAM Activity**.</span></span>  
  
     <span data-ttu-id="3e2a7-111">El **Asistente para actividad de supervisión de la actividad económica** aparece.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-111">The **Business Activity Monitoring Activity Wizard** appears.</span></span>  
  
3.  <span data-ttu-id="3e2a7-112">Haga clic en **nueva actividad**.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-112">Click **New Activity**.</span></span>  
  
     <span data-ttu-id="3e2a7-113">El **nueva actividad** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-113">The **New Activity** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="3e2a7-114">Escriba un nombre descriptivo para la actividad en el **nombre de la actividad** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-114">Type a descriptive name for the activity in the **Activity Name** text box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e2a7-115">Una actividad debe contener al menos un elemento de actividad.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-115">An activity must contain at least one activity item.</span></span>  
  
#### <a name="to-create-a-new-item"></a><span data-ttu-id="3e2a7-116">Procedimiento para crear un nuevo elemento</span><span class="sxs-lookup"><span data-stu-id="3e2a7-116">To create a new item</span></span>  
  
1. <span data-ttu-id="3e2a7-117">Haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-117">Click **New Item**.</span></span>  
  
2. <span data-ttu-id="3e2a7-118">En el **nuevo elemento de actividad** cuadro de diálogo el **nuevo elemento de actividad** , escriba un nombre descriptivo para el elemento de actividad.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-118">In the **New Activity Item** dialog box, in the **New Activity Item** box, type a descriptive name for the activity item.</span></span>  
  
3. <span data-ttu-id="3e2a7-119">Desde el **tipo de elemento** menú desplegable, seleccione un tipo para este elemento.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-119">From the **Item type** drop-down menu, select a type for this item.</span></span> <span data-ttu-id="3e2a7-120">Los valores posibles incluyen:</span><span class="sxs-lookup"><span data-stu-id="3e2a7-120">Possible values include:</span></span>  
  
   |<span data-ttu-id="3e2a7-121">Tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="3e2a7-121">Item type</span></span>|<span data-ttu-id="3e2a7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e2a7-122">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="3e2a7-123">Hito económico</span><span class="sxs-lookup"><span data-stu-id="3e2a7-123">Business Milestone</span></span>|<span data-ttu-id="3e2a7-124">Un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-124">A date/time value.</span></span> <span data-ttu-id="3e2a7-125">Por ejemplo, la fecha de aprobación de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-125">For example, an approval date for a purchase order.</span></span>|  
   |<span data-ttu-id="3e2a7-126">Datos económicos: texto</span><span class="sxs-lookup"><span data-stu-id="3e2a7-126">Business Data – Text</span></span>|<span data-ttu-id="3e2a7-127">Cadena que contiene cualquier carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-127">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="3e2a7-128">Por ejemplo, enviar: código de ciudad, estado o provincia y código Postal.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-128">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
   |<span data-ttu-id="3e2a7-129">Datos económicos: Integer</span><span class="sxs-lookup"><span data-stu-id="3e2a7-129">Business Data – Integer</span></span>|<span data-ttu-id="3e2a7-130">Valor numérico entero.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-130">A whole number value.</span></span> <span data-ttu-id="3e2a7-131">Por ejemplo el número total de compras.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-131">For example, the total number of purchases.</span></span>|  
   |<span data-ttu-id="3e2a7-132">Datos económicos: decimal</span><span class="sxs-lookup"><span data-stu-id="3e2a7-132">Business Data – Decimal</span></span>|<span data-ttu-id="3e2a7-133">Valor decimal.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-133">A decimal value.</span></span> <span data-ttu-id="3e2a7-134">Por ejemplo el importe total del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-134">For example the total dollar amount of the PO.</span></span>|  
  
    <span data-ttu-id="3e2a7-135">Si selecciona el elemento de tipo "Datos de económicos: Text", debe especificar el número máximo de caracteres de la cadena en el **longitud máxima** cuadro.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-135">If you select the item type "Business Data – Text", you must enter the maximum number of characters for the string in the **Maximum length** box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3e2a7-136">Para obtener más información sobre la creación de estos elementos, consulte "Partner Management and Business Activity Monitoring" ("Supervisión de la administración de socios comerciales y la actividad económica") en el tutorial de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-136">For more information about creating these items, see "Partner Management and Business Activity Monitoring" in the Microsoft BizTalk Server tutorial.</span></span>  
  
4. <span data-ttu-id="3e2a7-137">Repita los pasos 1 a 3 para agregar tantos elementos como necesite a esta actividad.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-137">Repeat steps 1 through 3 to add as many items as needed to this activity.</span></span>  
  
5. <span data-ttu-id="3e2a7-138">Una vez completado el Asistente para actividad de Supervisión de la actividad económica, se inicia automáticamente el Asistente para vistas de Supervisión de la actividad económica.</span><span class="sxs-lookup"><span data-stu-id="3e2a7-138">After you complete the Business Activity Monitoring Activity Wizard, the Business Activity Monitoring View Wizard starts automatically.</span></span>  
  
   <span data-ttu-id="3e2a7-139">Para obtener más información sobre cómo usar este asistente, consulte [definir una vista de BAM](../core/defining-a-bam-view.md).</span><span class="sxs-lookup"><span data-stu-id="3e2a7-139">For more information about using this wizard, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e2a7-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e2a7-140">See Also</span></span>  
 <span data-ttu-id="3e2a7-141">[Definir una vista BAM](../core/defining-a-bam-view.md) </span><span class="sxs-lookup"><span data-stu-id="3e2a7-141">[Defining a BAM View](../core/defining-a-bam-view.md) </span></span>  
 [<span data-ttu-id="3e2a7-142">Definición de actividades económicas y vistas en Excel</span><span class="sxs-lookup"><span data-stu-id="3e2a7-142">Defining Business Activities and Views in Excel</span></span>](../core/defining-business-activities-and-views-in-excel.md)
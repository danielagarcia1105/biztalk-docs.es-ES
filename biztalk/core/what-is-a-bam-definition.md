---
title: ¿Qué es una definición de BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cbc600f66be7167aabb4cf0273cb1c0bda78973
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289684"
---
# <a name="what-is-a-bam-definition"></a><span data-ttu-id="c0213-103">¿Qué es una definición de BAM?</span><span class="sxs-lookup"><span data-stu-id="c0213-103">What Is a BAM Definition?</span></span>
<span data-ttu-id="c0213-104">Una definición de BAM es una representación XML de un modelo de observación de BAM, que es una definición de alto nivel de un proceso empresarial que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="c0213-104">A BAM definition is an XML representation of a BAM observation model, which is a high-level definition a business process that you want to monitor.</span></span> <span data-ttu-id="c0213-105">Las partes principales del modelo de observación, y por lo tanto, la definición de BAM, son los hitos y eventos de datos que se van a recopilar (la actividad de BAM), una descripción de cualquier agregación de datos y la presentación de la información a los usuarios (la vista de BAM).</span><span class="sxs-lookup"><span data-stu-id="c0213-105">The main parts of the observation model, and therefore the BAM definition, are the milestone and data events to collect (the BAM activity); a description of any data aggregations; and how to present the information to users (the BAM view).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0213-106">Asimismo, puede crear un archivo XML que siga el esquema de BAM aunque no se recomienda para crear la definición de BAM ya que no proporciona una definición que se haya validado.</span><span class="sxs-lookup"><span data-stu-id="c0213-106">You can also manually create an XML file that follows the BAM schema, but this is not a recommended way to create the BAM definition as it does not provide a definition that has been validated.</span></span>  
  
 <span data-ttu-id="c0213-107">Las definiciones de BAM contienen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c0213-107">BAM definitions can contain the following items:</span></span>  
  
-   <span data-ttu-id="c0213-108">Actividades empresariales – Una definición de BAM válida debe contener una actividad empresarial (a la que también se denomina actividad de BAM).</span><span class="sxs-lookup"><span data-stu-id="c0213-108">Business activities - A valid BAM definition must contain a business activity (also referred to as a BAM activity).</span></span> <span data-ttu-id="c0213-109">Todos los demás elementos de la definición son opcionales.</span><span class="sxs-lookup"><span data-stu-id="c0213-109">All other items in the definition are optional.</span></span> <span data-ttu-id="c0213-110">Para obtener información acerca de cómo agregar una actividad económica a una definición, vea [cómo definir una actividad económica](../core/how-to-define-a-business-activity.md).</span><span class="sxs-lookup"><span data-stu-id="c0213-110">For information about adding a business activity to a definition, see [How to Define a Business Activity](../core/how-to-define-a-business-activity.md).</span></span>  
  
-   <span data-ttu-id="c0213-111">Vistas – Las vistas definen el conjunto de usuarios que pueden obtener acceso a los datos que definió la actividad económica.</span><span class="sxs-lookup"><span data-stu-id="c0213-111">Views – Views define the set of users that can access the data defined by the business activity.</span></span> <span data-ttu-id="c0213-112">Las vistas se componen de datos filtrados, agregaciones de los datos filtrados y formas de presentar los datos filtrados, como un informe de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="c0213-112">Views consist of filtered data, aggregations of the filtered data, and ways of presenting the filtered data, such as a PivotChart report.</span></span> <span data-ttu-id="c0213-113">BAM admite la definición de una o más vistas por actividad.</span><span class="sxs-lookup"><span data-stu-id="c0213-113">BAM supports the definition of one or more views per activity.</span></span>  
  
     <span data-ttu-id="c0213-114">En una vista puede definir los siguientes procesos empresariales:</span><span class="sxs-lookup"><span data-stu-id="c0213-114">In a view you can define the following business processes:</span></span>  
  
    -   <span data-ttu-id="c0213-115">Datos económicos con alias – Los alias le permiten aplicar nombres descriptivos a los elementos de datos.</span><span class="sxs-lookup"><span data-stu-id="c0213-115">Aliased business data - Aliasing allows you to apply friendly names to data items.</span></span> <span data-ttu-id="c0213-116">Por ejemplo, un programador puede definir un elemento de datos que se llame “LName”.</span><span class="sxs-lookup"><span data-stu-id="c0213-116">For example, a developer may define a data item called “LName.”</span></span> <span data-ttu-id="c0213-117">Puede crear un alias de manera que “LName” se muestre como “Apellido” cuando se vean los datos activos de BAM.</span><span class="sxs-lookup"><span data-stu-id="c0213-117">You can create an alias so that the “LName” is displayed as “Last Name” when viewing the BAM live data.</span></span>  <span data-ttu-id="c0213-118">Para obtener más información acerca de los alias, vea [cómo cambiar el nombre de elementos de vista](../core/how-to-rename-view-items.md).</span><span class="sxs-lookup"><span data-stu-id="c0213-118">For more information about aliasing, see [How to Rename View Items](../core/how-to-rename-view-items.md).</span></span>  
  
    -   <span data-ttu-id="c0213-119">Duración – El período de tiempo durante el que se supervisa una actividad.</span><span class="sxs-lookup"><span data-stu-id="c0213-119">Duration - The time period over which the activity is monitored.</span></span>  
  
    -   <span data-ttu-id="c0213-120">Grupos de hitos – Conjuntos de hitos económicos.</span><span class="sxs-lookup"><span data-stu-id="c0213-120">Milestone groups - Sets of business milestones.</span></span> <span data-ttu-id="c0213-121">Puede utilizar un grupo como hito económico, tanto de inicio de una duración como de fin.</span><span class="sxs-lookup"><span data-stu-id="c0213-121">You can use a group as either the starting or ending business milestone of a duration.</span></span>  
  
    -   <span data-ttu-id="c0213-122">Agregaciones - resultan agregaciones en tiempo real (ATR) o agregaciones programadas (contempladas también como procesamiento analítico en línea (OLAP)) y constan de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c0213-122">Aggregations -  These can be either real-time aggregations (RTAs) or scheduled aggregations (also referred to as online analytical processing (OLAP)), and consist of the following items:</span></span>  
  
-   <span data-ttu-id="c0213-123">Medidas – Un conjunto de valores numéricos en un cubo de Analysis Services (OLAP) basado en una columna de la taba de hechos del cubo.</span><span class="sxs-lookup"><span data-stu-id="c0213-123">Measures - A set of numeric values in an Analysis Services (OLAP) cube based on a column in the fact table of the cube.</span></span>  
  
-   <span data-ttu-id="c0213-124">Dimensión de progreso – Representa la creación de agregaciones en relación con el progreso de actividades que todavía están en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c0213-124">Progress dimension - Represents the creation of aggregations with respect to the progress of activities that are still in process.</span></span>  
  
-   <span data-ttu-id="c0213-125">Dimensión de datos – Se utiliza para clasificar una agregación.</span><span class="sxs-lookup"><span data-stu-id="c0213-125">Data dimension - Used to categorize an aggregation.</span></span> <span data-ttu-id="c0213-126">Las dimensiones de datos están basadas en el valor de los elementos de datos con formato de cadena de la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="c0213-126">Data dimensions are based on the value of string formatted data items in the BAM activity.</span></span>  
  
-   <span data-ttu-id="c0213-127">Dimensión de tiempo – Se utiliza para crear agregaciones en segmentos de tiempo definidos.</span><span class="sxs-lookup"><span data-stu-id="c0213-127">Time dimension - Used to create aggregations across defined time segments.</span></span>  
  
-   <span data-ttu-id="c0213-128">Dimensión de intervalo numérico – Se utiliza para clasificar las agregaciones basadas en nombres descriptivos de intervalos numéricos determinados.</span><span class="sxs-lookup"><span data-stu-id="c0213-128">Numeric range dimension - Used to categorize aggregations based on friendly names of given numeric ranges.</span></span>  
  
 <span data-ttu-id="c0213-129">Las definiciones de BAM pueden contener definiciones de alertas que se han definido en las vistas.</span><span class="sxs-lookup"><span data-stu-id="c0213-129">BAM definitions can contain alert definitions that are defined in the views.</span></span> <span data-ttu-id="c0213-130">Las definiciones de BAM también pueden contener diseños de tablas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="c0213-130">BAM definitions can also contain PivotTable layouts.</span></span> <span data-ttu-id="c0213-131">Una vez implementada la definición de BAM, el informe de tabla dinámica contiene los datos económicos activos que se pueden ver mediante el libro de datos activos de Excel o mediante el portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="c0213-131">Once the BAM definition is deployed, the PivotTable reports containing the live business data that can be viewed using the Excel livedata workbook or through the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0213-132">Definiciones de BAM creadas con el complemento de BAM para Excel no pueden contener alertas.</span><span class="sxs-lookup"><span data-stu-id="c0213-132">BAM definitions created using the BAM Add-in for Excel cannot contain alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0213-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0213-133">See Also</span></span>  
 <span data-ttu-id="c0213-134">[Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c0213-134">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 <span data-ttu-id="c0213-135">[Portal de BAM](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="c0213-135">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="c0213-136">Infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="c0213-136">BAM Dynamic Infrastructure</span></span>](../core/bam-dynamic-infrastructure.md)
---
title: "Búsqueda de todas las instancias de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-all-service-instances"></a><span data-ttu-id="37f97-102">Cómo buscar todas las instancias de servicio</span><span class="sxs-lookup"><span data-stu-id="37f97-102">How to Search for All Service Instances</span></span>
<span data-ttu-id="37f97-103">Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar todas las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="37f97-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for all service instances.</span></span> <span data-ttu-id="37f97-104">No se podrá dar de baja un tipo de servicio específico cuando se trate de instancias en ejecución o suspendidas.</span><span class="sxs-lookup"><span data-stu-id="37f97-104">You cannot unenlist a specific service type if there are any running or suspended instances.</span></span> <span data-ttu-id="37f97-105">Por ejemplo, antes de poder dar de baja un tipo de servicio específico, puede buscar todas las instancias de servicio para asegurarse de que no haya ninguna en ejecución o suspendida.</span><span class="sxs-lookup"><span data-stu-id="37f97-105">For example, before you can unenlist a specific service type, you can search for all service instances to ensure that there are no running or suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37f97-106">Al agrupar y filtrar por URI, los resultados sólo mostrarán los puertos de envío y de recepción.</span><span class="sxs-lookup"><span data-stu-id="37f97-106">When Grouping and Filtering by URI, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="37f97-107">No se podrá agrupar ni filtrar por URI en el caso de las orquestaciones, ya que éstas no se incluyen en los resultados.</span><span class="sxs-lookup"><span data-stu-id="37f97-107">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37f97-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="37f97-108">Prerequisites</span></span>  
 <span data-ttu-id="37f97-109">Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="37f97-109">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-all-service-instances"></a><span data-ttu-id="37f97-110">Para buscar todas las instancias de servicio</span><span class="sxs-lookup"><span data-stu-id="37f97-110">To search for all service instances</span></span>  
  
1.  <span data-ttu-id="37f97-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="37f97-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="37f97-112">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="37f97-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="37f97-113">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="37f97-113">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="37f97-114">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **todas las instancias de servicio en curso** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="37f97-114">In the **Query Expression** group, in the **Value** column, select **All In-Progress Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="37f97-115">En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="37f97-115">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="37f97-116">Use</span><span class="sxs-lookup"><span data-stu-id="37f97-116">Use this</span></span>|<span data-ttu-id="37f97-117">Para</span><span class="sxs-lookup"><span data-stu-id="37f97-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="37f97-118">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="37f97-118">**Application Name**</span></span>|<span data-ttu-id="37f97-119">Indica la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="37f97-119">The BizTalk Server application.</span></span>|  
    |<span data-ttu-id="37f97-120">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="37f97-120">**Creation Time**</span></span>|<span data-ttu-id="37f97-121">Busca todas las instancias de servicio creadas antes o después de la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="37f97-121">Find all service instances created before or after the specified date.</span></span>|  
    |<span data-ttu-id="37f97-122">**Agrupar los resultados por**</span><span class="sxs-lookup"><span data-stu-id="37f97-122">**Group Results By**</span></span>|<span data-ttu-id="37f97-123">Puede agrupar los resultados por aplicación, nombre de host, clase de servicio, estado de instancia de servicio o nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="37f97-123">You can group results by application, host name, service class, service instance status, or service name.</span></span>|  
    |<span data-ttu-id="37f97-124">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="37f97-124">**Host Name**</span></span>|<span data-ttu-id="37f97-125">Indica el nombre del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="37f97-125">The name of the BizTalk Host.</span></span>|  
    |<span data-ttu-id="37f97-126">**Estado de la instancia**</span><span class="sxs-lookup"><span data-stu-id="37f97-126">**Instance Status**</span></span>|<span data-ttu-id="37f97-127">Puede buscar todas las instancias en ejecución, instancias suspendidas, instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse, instancias programadas, instancias suspendidas no reanudables o instancias suspendidas reanudables.</span><span class="sxs-lookup"><span data-stu-id="37f97-127">You can search for all running instances, all suspended instances, active instances, dehydrated instances, ready to run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="37f97-128">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="37f97-128">**Maximum Matches**</span></span>|<span data-ttu-id="37f97-129">Número de coincidencias que se van a mostrar (requerido).</span><span class="sxs-lookup"><span data-stu-id="37f97-129">The number of matches to display (required).</span></span> <span data-ttu-id="37f97-130">Por lo general, se establece como 50 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="37f97-130">This is usually set to 50, the default.</span></span><br /><br /> <span data-ttu-id="37f97-131">Al incluir Agrupar resultados por, se muestra el número de grupos, no el número total de registros.</span><span class="sxs-lookup"><span data-stu-id="37f97-131">When you include Group Results By, this displays the number of groups, not the total number of records.</span></span>|  
    |<span data-ttu-id="37f97-132">**Clase de servicio**</span><span class="sxs-lookup"><span data-stu-id="37f97-132">**Service Class**</span></span>|<span data-ttu-id="37f97-133">Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="37f97-133">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="37f97-134">**Id. de instancia de servicio**</span><span class="sxs-lookup"><span data-stu-id="37f97-134">**Service Instance ID**</span></span>|<span data-ttu-id="37f97-135">Permite agrupar o filtrar las instancias de servicio por Id. de instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="37f97-135">You can group or filter service instances by service instance ID.</span></span>|  
    |<span data-ttu-id="37f97-136">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="37f97-136">**Service Name**</span></span>|<span data-ttu-id="37f97-137">Permite agrupar o filtrar las instancias de servicio por nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="37f97-137">You can group or filter service instances by service name.</span></span>|  
    |<span data-ttu-id="37f97-138">**Id. de tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="37f97-138">**Service Type ID**</span></span>|<span data-ttu-id="37f97-139">Permite agrupar o filtrar instancias de servicio por Id. de tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="37f97-139">You can group or filter service instances by service type ID.</span></span>|  
  
6.  <span data-ttu-id="37f97-140">Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="37f97-140">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="37f97-141">Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="37f97-141">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f97-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f97-142">See Also</span></span>  
 [<span data-ttu-id="37f97-143">Uso de la pestaña de consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="37f97-143">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
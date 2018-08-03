---
title: Cómo buscar instancias de servicio de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c61b94b440810fc948ae7e9e51c1897204d28c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023938"
---
# <a name="how-to-search-for-running-service-instances"></a><span data-ttu-id="dbba0-102">Cómo buscar instancias de servicio en ejecución</span><span class="sxs-lookup"><span data-stu-id="dbba0-102">How to Search for Running Service Instances</span></span>
<span data-ttu-id="dbba0-103">Puede usar el **consulta** ficha en la consola de administración de BizTalk Server para buscar una determinada deshidratada, activa, en el punto de interrupción, programada y volver a intentar la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="dbba0-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific dehydrated, active, in breakpoint, scheduled, and retrying service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="dbba0-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dbba0-104">Prerequisites</span></span>  
 <span data-ttu-id="dbba0-105">Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="dbba0-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-running-service-instances"></a><span data-ttu-id="dbba0-106">Para buscar instancias de servicio en ejecución</span><span class="sxs-lookup"><span data-stu-id="dbba0-106">To search for running service instances</span></span>  

1. <span data-ttu-id="dbba0-107">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="dbba0-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="dbba0-108">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dbba0-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="dbba0-109">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="dbba0-109">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="dbba0-110">En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio en ejecución** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dbba0-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="dbba0-111">En el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (\*\*\\*\*\*), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="dbba0-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="dbba0-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbba0-112">Item</span></span>          |                                                             <span data-ttu-id="dbba0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbba0-113">Description</span></span>                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="dbba0-114">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="dbba0-114">**Application Name**</span></span>  |                                                   <span data-ttu-id="dbba0-115">Indica la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="dbba0-115">The BizTalk Server application.</span></span>                                                   |
   |   <span data-ttu-id="dbba0-116">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="dbba0-116">**Creation Time**</span></span>    |                             <span data-ttu-id="dbba0-117">Busca instancias de servicio en ejecución creadas antes o después de la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="dbba0-117">Find running service instances created before or after the specified date.</span></span>                              |
   |  <span data-ttu-id="dbba0-118">**Agrupar resultados por**</span><span class="sxs-lookup"><span data-stu-id="dbba0-118">**Group Results By**</span></span>  |  <span data-ttu-id="dbba0-119">Puede agrupar los resultados por aplicación, nombre de host, tipo de operación pendiente, clase de servicio, estado de instancia de servicio o nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="dbba0-119">You can group results by application, host name, pending operation type, service class, service instance status, or service name.</span></span>  |
   |     <span data-ttu-id="dbba0-120">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dbba0-120">**Host Name**</span></span>      |                                                    <span data-ttu-id="dbba0-121">Indica el nombre del host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dbba0-121">The name of the BizTalk Host.</span></span>                                                    |
   |  <span data-ttu-id="dbba0-122">**Estado de la instancia**</span><span class="sxs-lookup"><span data-stu-id="dbba0-122">**Instance Status**</span></span>   |             <span data-ttu-id="dbba0-123">Puede buscar por instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse e instancias programadas.</span><span class="sxs-lookup"><span data-stu-id="dbba0-123">You can search for active instances, dehydrated instances, ready to run instances, and scheduled instances.</span></span>             |
   |  <span data-ttu-id="dbba0-124">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="dbba0-124">**Maximum Matches**</span></span>   |                                                  <span data-ttu-id="dbba0-125">Número de coincidencias que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="dbba0-125">The number of matches to display.</span></span>                                                  |
   | <span data-ttu-id="dbba0-126">**Operaciones pendientes**</span><span class="sxs-lookup"><span data-stu-id="dbba0-126">**Pending Operations**</span></span> |                      <span data-ttu-id="dbba0-127">Puede buscar instancias de servicio en ejecución de finalización o suspensión pendiente.</span><span class="sxs-lookup"><span data-stu-id="dbba0-127">You can search for running service instances that are pending suspension or termination.</span></span>                       |
   |   <span data-ttu-id="dbba0-128">**Clase de servicio**</span><span class="sxs-lookup"><span data-stu-id="dbba0-128">**Service Class**</span></span>    | <span data-ttu-id="dbba0-129">Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="dbba0-129">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span> |
   |    <span data-ttu-id="dbba0-130">**Nombre de servicio**</span><span class="sxs-lookup"><span data-stu-id="dbba0-130">**Service Name**</span></span>    |                                 <span data-ttu-id="dbba0-131">Permite agrupar o filtrar las instancias de servicio en ejecución por nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="dbba0-131">You can group or filter running service instances by service name.</span></span>                                  |
   |  <span data-ttu-id="dbba0-132">**Id. de tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="dbba0-132">**Service Type ID**</span></span>   |                                        <span data-ttu-id="dbba0-133">Puede agrupar o filtrar mensajes por Id. de tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="dbba0-133">You can group or filter messages by service type ID.</span></span>                                         |


6. <span data-ttu-id="dbba0-134">Completar la **valor** columna según corresponda para la selección que haya realizado en el **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="dbba0-134">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="dbba0-135">Seguir agregando líneas adicionales a la consulta según corresponda, completando la **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dbba0-135">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dbba0-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbba0-136">See Also</span></span>  
 [<span data-ttu-id="dbba0-137">Uso de la pestaña Consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="dbba0-137">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
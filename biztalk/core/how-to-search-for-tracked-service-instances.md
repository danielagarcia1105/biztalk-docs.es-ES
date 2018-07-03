---
title: Búsqueda de instancias de servicio controladas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3770e871e7be022ff7f4597b8d3eb4d8f307cc37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966517"
---
# <a name="how-to-search-for-tracked-service-instances"></a><span data-ttu-id="2ba97-102">Búsqueda de instancias de servicio supervisadas</span><span class="sxs-lookup"><span data-stu-id="2ba97-102">How to Search for Tracked Service Instances</span></span>
<span data-ttu-id="2ba97-103">Puede usar el **consulta** pestaña en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para buscar todas las instancias de servicio controladas.</span><span class="sxs-lookup"><span data-stu-id="2ba97-103">You can use the **Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for all tracked service instances.</span></span> <span data-ttu-id="2ba97-104">Para localizar instancias de servicio, puede buscar el nombre y la versión del ensamblado, el tiempo de inicio y fin de vigencia, el nombre o identificador de instancia de la clase de servicio, el nombre de host, el código de error y el estado de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-104">To locate service instances, you can search on the name and version of the assembly, the start and end times of its lifetime, the name or instance ID of the service class, host name, error code, and the state of the service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2ba97-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2ba97-105">Prerequisites</span></span>  
 <span data-ttu-id="2ba97-106">Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo Operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ba97-106">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-service-instances"></a><span data-ttu-id="2ba97-107">Procedimiento para buscar instancias de servicio controladas</span><span class="sxs-lookup"><span data-stu-id="2ba97-107">To search for tracked service instances</span></span>  

1. <span data-ttu-id="2ba97-108">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ba97-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="2ba97-109">En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2ba97-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="2ba97-110">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="2ba97-110">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="2ba97-111">En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio controladas** desde el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2ba97-111">In the **Query Expression** group, in the **Value** column, select **Tracked Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="2ba97-112">En el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (\*\*\\*\*\*), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2ba97-112">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="2ba97-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ba97-113">Item</span></span>           |                     <span data-ttu-id="2ba97-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ba97-114">Description</span></span>                      |
   |-------------------------|------------------------------------------------------|
   |    <span data-ttu-id="2ba97-115">**Nombre del ensamblado**</span><span class="sxs-lookup"><span data-stu-id="2ba97-115">**Assembly Name**</span></span>    |    <span data-ttu-id="2ba97-116">Nombre del ensamblado para la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-116">Name of the assembly for the service instance.</span></span>    |
   |  <span data-ttu-id="2ba97-117">**Versión del ensamblado**</span><span class="sxs-lookup"><span data-stu-id="2ba97-117">**Assembly Version**</span></span>   |           <span data-ttu-id="2ba97-118">Versión de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-118">Version of the service instance.</span></span>           |
   |      <span data-ttu-id="2ba97-119">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="2ba97-119">**End Time**</span></span>       |          <span data-ttu-id="2ba97-120">Fin del tiempo de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-120">End time of the service instance.</span></span>           |
   |     <span data-ttu-id="2ba97-121">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="2ba97-121">**Error Code**</span></span>      | <span data-ttu-id="2ba97-122">Cualquier código de error asociado a la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-122">Any error code associated with the service instance.</span></span> |
   |      <span data-ttu-id="2ba97-123">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2ba97-123">**Host Name**</span></span>      |        <span data-ttu-id="2ba97-124">Nombre de host de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-124">The host name of the service instance.</span></span>        |
   |   <span data-ttu-id="2ba97-125">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="2ba97-125">**Maximum Matches**</span></span>   |          <span data-ttu-id="2ba97-126">Número de coincidencias que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="2ba97-126">The number of matches to display.</span></span>           |
   |    <span data-ttu-id="2ba97-127">**Clase de servicio**</span><span class="sxs-lookup"><span data-stu-id="2ba97-127">**Service Class**</span></span>    |          <span data-ttu-id="2ba97-128">Clase de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-128">The class of the service instance.</span></span>          |
   | <span data-ttu-id="2ba97-129">**Id. de instancia de servicio**</span><span class="sxs-lookup"><span data-stu-id="2ba97-129">**Service Instance ID**</span></span> |               <span data-ttu-id="2ba97-130">Identificador de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-130">The service instance ID.</span></span>               |
   |    <span data-ttu-id="2ba97-131">**Nombre de servicio**</span><span class="sxs-lookup"><span data-stu-id="2ba97-131">**Service Name**</span></span>     |          <span data-ttu-id="2ba97-132">El nombre de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-132">The name of the service instance.</span></span>           |
   |     <span data-ttu-id="2ba97-133">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="2ba97-133">**Start Time**</span></span>      |       <span data-ttu-id="2ba97-134">Tiempo de inicio de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-134">The start time of the service instance.</span></span>        |
   |        <span data-ttu-id="2ba97-135">**State**</span><span class="sxs-lookup"><span data-stu-id="2ba97-135">**State**</span></span>        |          <span data-ttu-id="2ba97-136">Estado de la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="2ba97-136">The state of the service instance.</span></span>          |


6. <span data-ttu-id="2ba97-137">Completar la **valor** columna según corresponda para la selección que haya realizado en el **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="2ba97-137">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="2ba97-138">Seguir agregando líneas adicionales a la consulta según corresponda, completando la **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2ba97-138">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2ba97-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ba97-139">See Also</span></span>  
 [<span data-ttu-id="2ba97-140">Uso de la pestaña Consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="2ba97-140">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
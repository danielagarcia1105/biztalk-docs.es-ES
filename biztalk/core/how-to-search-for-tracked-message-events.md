---
title: "Búsqueda de eventos de mensajes controlados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a3597d0d68dbd79de6c23e7b6d4b222b9c8376
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-search-for-tracked-message-events"></a><span data-ttu-id="c6e98-102">Búsqueda de eventos de mensaje de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c6e98-102">How to Search for Tracked Message Events</span></span>
<span data-ttu-id="c6e98-103">Puede usar el **nueva consulta** pestaña en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para buscar eventos de mensajes controlados.</span><span class="sxs-lookup"><span data-stu-id="c6e98-103">You can use the **New Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for tracked message events.</span></span>  <span data-ttu-id="c6e98-104">Desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se puede habilitar el seguimiento del cuerpo y las propiedades de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c6e98-104">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console you can enable message body and message property tracking.</span></span> <span data-ttu-id="c6e98-105">En el panel Resultados de la consulta se puede ver información acerca del evento de mensaje, incluida la información de esquema, el tipo de evento, el identificador de instancia de servicio y todas las propiedades promocionadas para el mensaje generado.</span><span class="sxs-lookup"><span data-stu-id="c6e98-105">In the Query Results pane you can view information about the message event, including schema information, event type, service instance ID, and all the promoted properties for the generated message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6e98-106">Para ver el cuerpo del mensaje, puede invocar la **detalles del mensaje** menú contextual y vaya a la pestaña "Partes del mensaje", o guardar el mensaje desde la lista de resultados ver invocando **guardar en archivo** desde el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c6e98-106">In order to view the actual message body, you can invoke the **Message Details** context menu and go to the “Message Parts” tab, or save the message from the result list view by invoking **Save to File** from the context menu.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6e98-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c6e98-107">Prerequisites</span></span>  
 <span data-ttu-id="c6e98-108">Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo Operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6e98-108">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  
  
### <a name="to-search-for-tracked-message-items"></a><span data-ttu-id="c6e98-109">Para buscar elementos de mensaje supervisados</span><span class="sxs-lookup"><span data-stu-id="c6e98-109">To search for tracked message items</span></span>  
  
1.  <span data-ttu-id="c6e98-110">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6e98-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6e98-111">En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c6e98-111">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="c6e98-112">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="c6e98-112">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="c6e98-113">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **realiza el seguimiento de eventos de mensaje** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6e98-113">In the **Query Expression** group, in the **Value** column, select **Tracked Message Events** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="c6e98-114">En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c6e98-114">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="c6e98-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6e98-115">Item</span></span>|<span data-ttu-id="c6e98-116">Description</span><span class="sxs-lookup"><span data-stu-id="c6e98-116">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="c6e98-117">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="c6e98-117">**Creation Time**</span></span>|<span data-ttu-id="c6e98-118">Hora de creación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-118">The time the message was created.</span></span>|  
    |<span data-ttu-id="c6e98-119">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="c6e98-119">**Event Type**</span></span>|<span data-ttu-id="c6e98-120">El tipo de evento que se supervisa.</span><span class="sxs-lookup"><span data-stu-id="c6e98-120">The type of event being tracked.</span></span>|  
    |<span data-ttu-id="c6e98-121">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="c6e98-121">**Maximum Matches**</span></span>|<span data-ttu-id="c6e98-122">Número de coincidencias que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="c6e98-122">The number of matches to display.</span></span>|  
    |<span data-ttu-id="c6e98-123">**Entidad**</span><span class="sxs-lookup"><span data-stu-id="c6e98-123">**Party**</span></span>|<span data-ttu-id="c6e98-124">La organización que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-124">The organization that sent the message.</span></span>|  
    |<span data-ttu-id="c6e98-125">**Puerto**</span><span class="sxs-lookup"><span data-stu-id="c6e98-125">**Port**</span></span>|<span data-ttu-id="c6e98-126">El puerto usado para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-126">The port used to process the message.</span></span>|  
    |<span data-ttu-id="c6e98-127">**Nombre del esquema**</span><span class="sxs-lookup"><span data-stu-id="c6e98-127">**Schema Name**</span></span>|<span data-ttu-id="c6e98-128">Nombre del esquema que usa el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-128">Name of the schema used by the message.</span></span>|  
    |<span data-ttu-id="c6e98-129">**Id. de instancia de servicio**</span><span class="sxs-lookup"><span data-stu-id="c6e98-129">**Service Instance ID**</span></span>|<span data-ttu-id="c6e98-130">El identificador de instancia de servicio que se usa para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-130">The service instance ID used for the message.</span></span>|  
    |<span data-ttu-id="c6e98-131">**URI**</span><span class="sxs-lookup"><span data-stu-id="c6e98-131">**URI**</span></span>|<span data-ttu-id="c6e98-132">El URI que se usa para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e98-132">The URI used for the message.</span></span>|  
    |<span data-ttu-id="c6e98-133">**\<Seleccione un nombre de esquema de propiedades sometidas a seguimiento\>**</span><span class="sxs-lookup"><span data-stu-id="c6e98-133">**\<Select a Schema Name for Tracked Properties\>**</span></span>|<span data-ttu-id="c6e98-134">Si selecciona un esquema, las propiedades promocionadas de ese esquema se podrán usar en la consulta.</span><span class="sxs-lookup"><span data-stu-id="c6e98-134">When you select a schema, any promoted properties in that schema are eligible to be used in the query.</span></span>|  
  
6.  <span data-ttu-id="c6e98-135">Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="c6e98-135">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="c6e98-136">Seguir agregando líneas adicionales a la consulta según corresponda siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c6e98-136">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e98-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6e98-137">See Also</span></span>  
 [<span data-ttu-id="c6e98-138">Uso de la pestaña Consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="c6e98-138">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
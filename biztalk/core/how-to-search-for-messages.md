---
title: "Búsqueda de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-messages"></a><span data-ttu-id="c6722-102">Cómo buscar mensajes</span><span class="sxs-lookup"><span data-stu-id="c6722-102">How to Search for Messages</span></span>
<span data-ttu-id="c6722-103">Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar una clase específica de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c6722-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific class of messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6722-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c6722-104">Prerequisites</span></span>  
 <span data-ttu-id="c6722-105">Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6722-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-messages"></a><span data-ttu-id="c6722-106">Para buscar mensajes</span><span class="sxs-lookup"><span data-stu-id="c6722-106">To search for messages</span></span>  
  
1.  <span data-ttu-id="c6722-107">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c6722-107">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c6722-108">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c6722-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="c6722-109">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="c6722-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="c6722-110">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **mensajes** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6722-110">In the **Query Expression** group, in the **Value** column, select **Messages** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="c6722-111">En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c6722-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="c6722-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6722-112">Item</span></span>|<span data-ttu-id="c6722-113">Description</span><span class="sxs-lookup"><span data-stu-id="c6722-113">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="c6722-114">**Hora de creación**</span><span class="sxs-lookup"><span data-stu-id="c6722-114">**Creation Time**</span></span>|<span data-ttu-id="c6722-115">Permite buscar mensajes creados antes o después de la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="c6722-115">Find messages created before or after the specified date.</span></span>|  
    |<span data-ttu-id="c6722-116">**Adaptador con error**</span><span class="sxs-lookup"><span data-stu-id="c6722-116">**Error Adapter**</span></span>|<span data-ttu-id="c6722-117">Puede agrupar o filtrar mensajes por tipo de adaptador: archivo, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP o Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="c6722-117">You can group or filter messages by adapter type: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP, or Windows SharePoint Services.</span></span>|  
    |<span data-ttu-id="c6722-118">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="c6722-118">**Error Code**</span></span>|<span data-ttu-id="c6722-119">Permite agrupar o filtrar mensajes por código de error.</span><span class="sxs-lookup"><span data-stu-id="c6722-119">You can group or filter messages by error code.</span></span>|  
    |<span data-ttu-id="c6722-120">**Descripción del error**</span><span class="sxs-lookup"><span data-stu-id="c6722-120">**Error Description**</span></span>|<span data-ttu-id="c6722-121">Permite agrupar o filtrar mensajes por descripción del error.</span><span class="sxs-lookup"><span data-stu-id="c6722-121">You can group or filter messages by error description.</span></span>|  
    |<span data-ttu-id="c6722-122">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="c6722-122">**Host Name**</span></span>|<span data-ttu-id="c6722-123">Permite agrupar o filtrar mensajes por nombre de host.</span><span class="sxs-lookup"><span data-stu-id="c6722-123">You can group or filter messages by host name.</span></span>|  
    |<span data-ttu-id="c6722-124">**Estado de la instancia**</span><span class="sxs-lookup"><span data-stu-id="c6722-124">**Instance Status**</span></span>|<span data-ttu-id="c6722-125">El estado de la instancia de servicio que hace referencia al mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6722-125">The status of the service instance referencing the message.</span></span> <span data-ttu-id="c6722-126">Puede buscar todos los tipos siguientes de instancias: todas las instancias en ejecución, todas las instancias suspendidas, instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse, instancias programadas, suspendidos pero no reanudables instancias, o suspendidos y reanudables instancias.</span><span class="sxs-lookup"><span data-stu-id="c6722-126">You can search for all of the following types of instances: all running instances, all suspended instances, active instances, dehydrated instances, ready-to-run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="c6722-127">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="c6722-127">**Maximum Matches**</span></span>|<span data-ttu-id="c6722-128">Número de coincidencias que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="c6722-128">The number of matches to display.</span></span>|  
    |<span data-ttu-id="c6722-129">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="c6722-129">**Message ID**</span></span>|<span data-ttu-id="c6722-130">Permite agrupar o filtrar mensajes por Id. de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6722-130">You can group or filter messages by message ID.</span></span>|  
    |<span data-ttu-id="c6722-131">**Estado del mensaje**</span><span class="sxs-lookup"><span data-stu-id="c6722-131">**Message Status**</span></span>|<span data-ttu-id="c6722-132">Puede buscar mensajes con el siguiente estado: consumido, en proceso, suspendido, suspendido pero no reanudable, suspendido y reanudable, en cola, en cola pero en espera de procesarse, en cola pero programado para entregarse más tarde y en cola pero en espera de reintento.</span><span class="sxs-lookup"><span data-stu-id="c6722-132">You can search for messages with consumed, in process, suspended, suspended but not resumable, suspended and resumable, queued, queued but awaiting processing, queued but scheduled for later delivery, and queued but waiting to retry.</span></span>|  
    |<span data-ttu-id="c6722-133">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="c6722-133">**Message Type**</span></span>|<span data-ttu-id="c6722-134">Permite agrupar o filtrar mensajes por tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6722-134">You can group or filter messages by message type.</span></span>|  
    |<span data-ttu-id="c6722-135">**Clase de servicio**</span><span class="sxs-lookup"><span data-stu-id="c6722-135">**Service Class**</span></span>|<span data-ttu-id="c6722-136">Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="c6722-136">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="c6722-137">**Id. de instancia de servicio**</span><span class="sxs-lookup"><span data-stu-id="c6722-137">**Service Instance ID**</span></span>|<span data-ttu-id="c6722-138">Puede agrupar o filtrar mensajes por Id. de instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="c6722-138">You can group or filter messages by service instance ID.</span></span>|  
    |<span data-ttu-id="c6722-139">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="c6722-139">**Service Name**</span></span>|<span data-ttu-id="c6722-140">Permite agrupar o filtrar mensajes por nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="c6722-140">You can group or filter messages by service name.</span></span>|  
    |<span data-ttu-id="c6722-141">**Id. de tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="c6722-141">**Service Type ID**</span></span>|<span data-ttu-id="c6722-142">Puede agrupar o filtrar mensajes por Id. de tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c6722-142">You can group or filter messages by service type ID.</span></span>|  
    |<span data-ttu-id="c6722-143">**URI**</span><span class="sxs-lookup"><span data-stu-id="c6722-143">**URI**</span></span>|<span data-ttu-id="c6722-144">Permite agrupar o filtrar mensajes por URI.</span><span class="sxs-lookup"><span data-stu-id="c6722-144">You can group or filter messages by URI.</span></span>|  
  
6.  <span data-ttu-id="c6722-145">Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="c6722-145">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="c6722-146">Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c6722-146">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6722-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6722-147">See Also</span></span>  
 [<span data-ttu-id="c6722-148">Uso de la pestaña de consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="c6722-148">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
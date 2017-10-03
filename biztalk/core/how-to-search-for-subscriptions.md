---
title: "Cómo buscar suscripciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1830a4c1dddfa3dcfc2a1177b69410dd8ee0ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-subscriptions"></a><span data-ttu-id="f09dd-102">Cómo buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="f09dd-102">How to Search for Subscriptions</span></span>
<span data-ttu-id="f09dd-103">Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="f09dd-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for subscriptions.</span></span> <span data-ttu-id="f09dd-104">Esto resulta muy útil para revisar todas las suscripciones definidas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="f09dd-104">This is useful when you want to review all of the subscriptions defined in the system.</span></span> <span data-ttu-id="f09dd-105">Al solucionar problemas de enrutamiento, se pueden revisar suscripciones para ver si hay alguna con una configuración incorrecta (puesto que ésta sería la causa del problema de enrutamiento).</span><span class="sxs-lookup"><span data-stu-id="f09dd-105">When troubleshooting routing failures, you can review subscriptions to see if any of them are improperly configured, thereby causing the routing failure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f09dd-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f09dd-106">Prerequisites</span></span>  
 <span data-ttu-id="f09dd-107">Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f09dd-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-subscriptions"></a><span data-ttu-id="f09dd-108">Para buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="f09dd-108">To search for subscriptions</span></span>  
  
1.  <span data-ttu-id="f09dd-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f09dd-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="f09dd-110">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f09dd-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="f09dd-111">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="f09dd-111">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="f09dd-112">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **suscripciones** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f09dd-112">In the **Query Expression** group, in the **Value** column, select **Subscriptions** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="f09dd-113">En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f09dd-113">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="f09dd-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f09dd-114">Item</span></span>|<span data-ttu-id="f09dd-115">Description</span><span class="sxs-lookup"><span data-stu-id="f09dd-115">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="f09dd-116">**N.º máximo de coincidencias**</span><span class="sxs-lookup"><span data-stu-id="f09dd-116">**Maximum Matches**</span></span>|<span data-ttu-id="f09dd-117">Número de coincidencias que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="f09dd-117">The number of matches to display.</span></span>|  
    |<span data-ttu-id="f09dd-118">**Id. de instancia de servicio**</span><span class="sxs-lookup"><span data-stu-id="f09dd-118">**Service Instance ID**</span></span>|<span data-ttu-id="f09dd-119">Puede filtrar las suscripciones por Id. de instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="f09dd-119">You can filter subscriptions by service instance ID.</span></span>|  
    |<span data-ttu-id="f09dd-120">**Nombre del servicio**</span><span class="sxs-lookup"><span data-stu-id="f09dd-120">**Service Name**</span></span>|<span data-ttu-id="f09dd-121">Puede filtrar las suscripciones por nombre de servicio.</span><span class="sxs-lookup"><span data-stu-id="f09dd-121">You can filter subscriptions by service name.</span></span>|  
    |<span data-ttu-id="f09dd-122">**Tipo de suscripción**</span><span class="sxs-lookup"><span data-stu-id="f09dd-122">**Subscription Type**</span></span>|<span data-ttu-id="f09dd-123">Puede filtrar las suscripciones por suscripción de activación o suscripción de instancia.</span><span class="sxs-lookup"><span data-stu-id="f09dd-123">You can filter subscriptions by Activation Subscription or Instance Subscription.</span></span>|  
  
6.  <span data-ttu-id="f09dd-124">Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.</span><span class="sxs-lookup"><span data-stu-id="f09dd-124">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="f09dd-125">Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f09dd-125">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09dd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f09dd-126">See Also</span></span>  
 [<span data-ttu-id="f09dd-127">Uso de la pestaña de consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="f09dd-127">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)
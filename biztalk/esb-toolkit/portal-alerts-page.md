---
title: "Página de alertas del portal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba854c269db4a1d7eabb021a974fa9614abb7690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="portal-alerts-page"></a><span data-ttu-id="32159-102">Página de alertas del portal</span><span class="sxs-lookup"><span data-stu-id="32159-102">Portal Alerts Page</span></span>
<span data-ttu-id="32159-103">La figura 1 muestra la página de alertas, que contiene dos secciones:</span><span class="sxs-lookup"><span data-stu-id="32159-103">Figure 1 shows the Alerts page, which contains two sections:</span></span>  
  
-   <span data-ttu-id="32159-104">La sección principal muestra un vínculo para crear una nueva alerta y una lista de las alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="32159-104">The main section displays a link to create a new alert and a list of existing alerts.</span></span> <span data-ttu-id="32159-105">Cada alerta incluye un vínculo correspondiente que le permite suscribirse a la alerta.</span><span class="sxs-lookup"><span data-stu-id="32159-105">Each alert has a corresponding link that allows you to subscribe to the alert.</span></span> <span data-ttu-id="32159-106">También puede hacer clic en los iconos en la columna de acción para ver los detalles de la alerta, cree una nueva suscripción para la alerta y eliminar la alerta.</span><span class="sxs-lookup"><span data-stu-id="32159-106">You can also click the icons in the Action column to view details of the alert, create a new subscription for the alert, and delete the alert.</span></span>  
  
-   <span data-ttu-id="32159-107">El **Mis suscripciones** sección muestra una lista de las suscripciones que ha definido en el portal.</span><span class="sxs-lookup"><span data-stu-id="32159-107">The **My Subscriptions** section displays a list of subscriptions you have defined within the portal.</span></span> <span data-ttu-id="32159-108">Puede editar y cancelar la suscripción las suscripciones existentes mediante los vínculos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="32159-108">You can edit and unsubscribe your existing subscriptions using the links in this list.</span></span>  
  
 <span data-ttu-id="32159-109">![Página de alertas del portal](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="32159-109">![Portal Alerts Page](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span></span>  
  
 <span data-ttu-id="32159-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="32159-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="32159-111">**La página de alertas de Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="32159-111">**The ESB Management Portal Alerts page**</span></span>  
  
 <span data-ttu-id="32159-112">El servicio de alertas de ESB genera alertas en función de criterios que especifique que coinciden con los valores de las excepciones cuando llegan en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="32159-112">The ESB Alert Service generates alerts based on criteria you specify that match the values in exceptions as they arrive at the ESB Management Portal.</span></span> <span data-ttu-id="32159-113">Puede coincidir con y comparar un intervalo de campos de una excepción para controlar con precisión las alertas que coincidirá con cada posible tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="32159-113">You can match and compare a range of fields in an exception to control accurately which alerts will match each possible type of exception.</span></span> <span data-ttu-id="32159-114">El portal también permite crear suscripciones que se asignan a los distintos tipos de alertas que defina.</span><span class="sxs-lookup"><span data-stu-id="32159-114">The portal also allows you to create subscriptions that map to the different types of alerts you define.</span></span> <span data-ttu-id="32159-115">Estas suscripciones pueden notificar a los usuarios cuando se produzca la alerta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="32159-115">These subscriptions can notify users when the matching alert occurs.</span></span>  
  
 <span data-ttu-id="32159-116">En la lista siguiente se explica cómo puede usar las características de la página de alertas de Portal de administración de ESB:</span><span class="sxs-lookup"><span data-stu-id="32159-116">The following list explains how you can use the features of the ESB Management Portal Alerts page:</span></span>  
  
-   <span data-ttu-id="32159-117">Para crear una nueva alerta, haga clic en el **crear alerta** vínculo en la parte superior de la página para abrir la página Agregar alerta.</span><span class="sxs-lookup"><span data-stu-id="32159-117">To create a new alert, click the **Create Alert** link at the top of the page to open the Add Alert page.</span></span>  
  
-   <span data-ttu-id="32159-118">Para ver o modificar una alerta existente, haga clic en el icono de lupa en la columna de acción de la alerta en la sección principal de la página.</span><span class="sxs-lookup"><span data-stu-id="32159-118">To view or edit an existing alert, click the magnifying glass icon in the Action column for the alert in the main section of the page.</span></span> <span data-ttu-id="32159-119">Se abrirá la [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md).</span><span class="sxs-lookup"><span data-stu-id="32159-119">This opens the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md).</span></span>  
  
-   <span data-ttu-id="32159-120">Para suscribirse a una alerta existente, haga clic en el icono de suscripción de nuevo la columna acción situada junto a la alerta para abrir el [Agregar suscripción de alerta y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="32159-120">To subscribe to an existing alert, click the new subscription icon the Action column next to the alert to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="32159-121">Si abre esta página como un administrador mediante las opciones en el **administración** menú de la pestaña (en lugar de desde el **alertas** ficha), puede hacer clic en el icono de marca entre la columna acción situada junto a cualquiera de las alertas de la lista para eliminar las suscripciones de alerta y cualquier vinculadas.</span><span class="sxs-lookup"><span data-stu-id="32159-121">If you opened this page as an administrator using the options on the **Admin** tab menu (instead of from the **Alerts** tab), you can click the cross mark icon the Action column next to any of the alerts in the list to delete the alert and any linked subscriptions.</span></span>  
  
-   <span data-ttu-id="32159-122">Para editar una suscripción existente, haga clic en el **editar** vínculo situado junto a esa suscripción en la lista en la **Mis suscripciones** sección de la página para abrir el [Agregar suscripción de alertas y editar Páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="32159-122">To edit an existing subscription, click the **Edit** link next to that subscription in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
-   <span data-ttu-id="32159-123">Para quitar una suscripción existente, haga clic en el **Unsubscribe** vínculo situado junto a esa suscripción en la lista en la **Mis suscripciones** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="32159-123">To remove an existing subscription, click the **Unsubscribe** link next to that subscription in the list in the **My Subscriptions** section of the page.</span></span>  
  
-   <span data-ttu-id="32159-124">Para exportar toda la lista de alertas a Microsoft Excel, haga clic en **exportar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="32159-124">To export the entire list of alerts to Microsoft Excel, click **Export to Excel**.</span></span>
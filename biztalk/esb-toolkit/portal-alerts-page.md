---
title: Página de alertas del portal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252da9de050c228a7b2d8a4f549d2d084e2a2f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978709"
---
# <a name="portal-alerts-page"></a><span data-ttu-id="06988-102">Página de alertas del portal</span><span class="sxs-lookup"><span data-stu-id="06988-102">Portal Alerts Page</span></span>
<span data-ttu-id="06988-103">Figura 1 muestra la página de alertas, que contiene dos secciones:</span><span class="sxs-lookup"><span data-stu-id="06988-103">Figure 1 shows the Alerts page, which contains two sections:</span></span>  

- <span data-ttu-id="06988-104">La sección principal muestra un vínculo para crear una nueva alerta y una lista de las alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="06988-104">The main section displays a link to create a new alert and a list of existing alerts.</span></span> <span data-ttu-id="06988-105">Cada alerta tiene un vínculo correspondiente que le permite suscribirse a la alerta.</span><span class="sxs-lookup"><span data-stu-id="06988-105">Each alert has a corresponding link that allows you to subscribe to the alert.</span></span> <span data-ttu-id="06988-106">También puede hacer clic en los iconos en la columna de acción para ver los detalles de la alerta, cree una nueva suscripción para la alerta y eliminar la alerta.</span><span class="sxs-lookup"><span data-stu-id="06988-106">You can also click the icons in the Action column to view details of the alert, create a new subscription for the alert, and delete the alert.</span></span>  

- <span data-ttu-id="06988-107">El **Mis suscripciones** sección muestra una lista de suscripciones que se ha definido en el portal.</span><span class="sxs-lookup"><span data-stu-id="06988-107">The **My Subscriptions** section displays a list of subscriptions you have defined within the portal.</span></span> <span data-ttu-id="06988-108">Puede editar y cancelar la suscripción a las suscripciones existentes con los vínculos de esta lista.</span><span class="sxs-lookup"><span data-stu-id="06988-108">You can edit and unsubscribe your existing subscriptions using the links in this list.</span></span>  

  <span data-ttu-id="06988-109">![Página de alertas del portal](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="06988-109">![Portal Alerts Page](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")</span></span>  

  <span data-ttu-id="06988-110">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="06988-110">**Figure 1**</span></span>  

  <span data-ttu-id="06988-111">**La página de alertas de Portal de administración de ESB**</span><span class="sxs-lookup"><span data-stu-id="06988-111">**The ESB Management Portal Alerts page**</span></span>  

  <span data-ttu-id="06988-112">El servicio de alerta de ESB genera alertas basadas en criterios que especifique que coinciden con los valores de las excepciones cuando llegan en el Portal de administración de ESB.</span><span class="sxs-lookup"><span data-stu-id="06988-112">The ESB Alert Service generates alerts based on criteria you specify that match the values in exceptions as they arrive at the ESB Management Portal.</span></span> <span data-ttu-id="06988-113">Puede coincidir con y comparar un intervalo de campos de una excepción para controlar con precisión las alertas que coincidirá con cada posible tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="06988-113">You can match and compare a range of fields in an exception to control accurately which alerts will match each possible type of exception.</span></span> <span data-ttu-id="06988-114">El portal también permite crear suscripciones que se asignan a los distintos tipos de alertas que defina.</span><span class="sxs-lookup"><span data-stu-id="06988-114">The portal also allows you to create subscriptions that map to the different types of alerts you define.</span></span> <span data-ttu-id="06988-115">Estas suscripciones pueden notificar a los usuarios cuando se produzca la alerta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="06988-115">These subscriptions can notify users when the matching alert occurs.</span></span>  

  <span data-ttu-id="06988-116">En la lista siguiente se explica cómo puede usar las características de la página de alertas de Portal de administración de ESB:</span><span class="sxs-lookup"><span data-stu-id="06988-116">The following list explains how you can use the features of the ESB Management Portal Alerts page:</span></span>  

- <span data-ttu-id="06988-117">Para crear una nueva alerta, haga clic en el **crear alerta** vínculo en la parte superior de la página para abrir la página Agregar alerta.</span><span class="sxs-lookup"><span data-stu-id="06988-117">To create a new alert, click the **Create Alert** link at the top of the page to open the Add Alert page.</span></span>  

- <span data-ttu-id="06988-118">Para ver o editar una alerta existente, haga clic en el icono de lupa en la columna de acción de la alerta en la sección de la página principal.</span><span class="sxs-lookup"><span data-stu-id="06988-118">To view or edit an existing alert, click the magnifying glass icon in the Action column for the alert in the main section of the page.</span></span> <span data-ttu-id="06988-119">Se abrirá el [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md).</span><span class="sxs-lookup"><span data-stu-id="06988-119">This opens the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md).</span></span>  

- <span data-ttu-id="06988-120">Para suscribirse a una alerta existente, haga clic en el icono de suscripción de nuevo la columna de acción junto a la alerta para abrir el [Agregar suscripción de alerta y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="06988-120">To subscribe to an existing alert, click the new subscription icon the Action column next to the alert to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  

- <span data-ttu-id="06988-121">Si abre esta página como un administrador mediante las opciones en el **Admin** menú de la pestaña (en lugar de desde el **alertas** pestaña), puede hacer clic en el icono de marca de tachado en la columna acción situada junto a cualquiera de las alertas en la lista para eliminar las alertas y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="06988-121">If you opened this page as an administrator using the options on the **Admin** tab menu (instead of from the **Alerts** tab), you can click the cross mark icon the Action column next to any of the alerts in the list to delete the alert and any linked subscriptions.</span></span>  

- <span data-ttu-id="06988-122">Para editar una suscripción existente, haga clic en el **editar** vínculo situado junto a esa suscripción en la lista en el **Mis suscripciones** sección de la página para abrir el [Agregar suscripción de alerta y editar Las páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="06988-122">To edit an existing subscription, click the **Edit** link next to that subscription in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  

- <span data-ttu-id="06988-123">Para quitar una suscripción existente, haga clic en el **Unsubscribe** vínculo situado junto a esa suscripción en la lista en el **Mis suscripciones** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="06988-123">To remove an existing subscription, click the **Unsubscribe** link next to that subscription in the list in the **My Subscriptions** section of the page.</span></span>  

- <span data-ttu-id="06988-124">Para exportar toda la lista de alertas en Microsoft Excel, haga clic en **exportar a Excel**.</span><span class="sxs-lookup"><span data-stu-id="06988-124">To export the entire list of alerts to Microsoft Excel, click **Export to Excel**.</span></span>

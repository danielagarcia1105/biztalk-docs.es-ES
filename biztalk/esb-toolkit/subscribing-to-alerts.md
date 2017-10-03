---
title: Suscribirse a alertas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfa46b63-c1c7-47cd-86b0-557fd322dc8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02ef5f136002f5afca6e062362b92d25a20baa99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="subscribing-to-alerts"></a><span data-ttu-id="3e261-102">Suscribirse a alertas</span><span class="sxs-lookup"><span data-stu-id="3e261-102">Subscribing to Alerts</span></span>
### <a name="to-subscribe-to-an-alert"></a><span data-ttu-id="3e261-103">Para suscribirse a una alerta</span><span class="sxs-lookup"><span data-stu-id="3e261-103">To subscribe to an alert</span></span>  
  
1.  <span data-ttu-id="3e261-104">Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md) para ver una lista de las alertas existentes y las suscripciones actuales de estas alertas.</span><span class="sxs-lookup"><span data-stu-id="3e261-104">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="3e261-105">En la columna acción, haga clic en el **AddSubscriber** icono para una alerta existente.</span><span class="sxs-lookup"><span data-stu-id="3e261-105">In the Action column, click the **AddSubscriber** icon for an existing alert.</span></span> <span data-ttu-id="3e261-106">Se abrirá la [Agregar suscripción de alertas y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="3e261-106">This opens the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="3e261-107">El portal envía notificaciones de alerta a la dirección de correo electrónico asociada con la cuenta que use para acceder al portal.</span><span class="sxs-lookup"><span data-stu-id="3e261-107">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="3e261-108">Si desea usar una dirección de correo electrónico diferente, active la casilla de verificación junto a la **correo electrónico personalizado** cuadro de texto y, a continuación, escriba la dirección de correo electrónico preferida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3e261-108">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="3e261-109">Active la casilla de verificación en la **programación** sección si desea especificar un período cuando el portal debe enviar alertas a usted y, a continuación, especifique las horas de inicio y finalización para el período en el **Start Time** y **EndTime** listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="3e261-109">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="3e261-110">Si hay un período cuando no se podrá recibir y responder a alertas, escriba las fechas de inicio y finalización de la **negro de espera** cuadros.</span><span class="sxs-lookup"><span data-stu-id="3e261-110">If there is a period when you will be unable to receive and act upon alerts, type the start and end dates in the **Black-out Period** boxes.</span></span>  
  
6.  <span data-ttu-id="3e261-111">Seleccione un **intervalo** en **minutos** durante la que el portal de comparará las alertas emitidas y enviar sola cuando se producen varias instancias de la misma alerta.</span><span class="sxs-lookup"><span data-stu-id="3e261-111">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="3e261-112">Esto evita que un error rápidamente que se está produciendo desde la creación de un gran número de mensajes de alerta idénticos.</span><span class="sxs-lookup"><span data-stu-id="3e261-112">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="3e261-113">Haga clic en el **guardar** botón para crear la nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e261-113">Click the **Save** button to create the new subscription.</span></span>  
  
### <a name="to-edit-an-existing-alert-subscription"></a><span data-ttu-id="3e261-114">Para editar una suscripción de alerta existente</span><span class="sxs-lookup"><span data-stu-id="3e261-114">To edit an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="3e261-115">Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md) para ver una lista de las alertas existentes y las suscripciones actuales de estas alertas.</span><span class="sxs-lookup"><span data-stu-id="3e261-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="3e261-116">Haga clic en el **editar** vínculo situado junto a la suscripción que desea modificar en la lista en la **Mis suscripciones** sección de la página para abrir el [Agregar suscripción de alertas y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span><span class="sxs-lookup"><span data-stu-id="3e261-116">Click the **Edit** link next to the subscription you want to modify in the list in the **My Subscriptions** section of the page to open the [Add Alert Subscription and Edit Subscription Pages](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).</span></span>  
  
3.  <span data-ttu-id="3e261-117">El portal envía notificaciones de alerta a la dirección de correo electrónico asociada con la cuenta que use para acceder al portal.</span><span class="sxs-lookup"><span data-stu-id="3e261-117">The portal sends alert notifications to the e-mail address associated with the account you use to access the portal.</span></span> <span data-ttu-id="3e261-118">Si desea usar una dirección de correo electrónico diferente, active la casilla de verificación junto a la **correo electrónico personalizado** cuadro de texto y, a continuación, escriba la dirección de correo electrónico preferida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3e261-118">If you want to use a different e-mail address, select the check box next to the **Custom Email** text box, and then type the preferred e-mail address in the text box.</span></span>  
  
4.  <span data-ttu-id="3e261-119">Active la casilla de verificación en la **programación** sección si desea especificar un período cuando el portal debe enviar alertas a usted y, a continuación, especifique las horas de inicio y finalización para el período en el **Start Time** y **EndTime** listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="3e261-119">Select the check box in the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **EndTime** drop-down lists.</span></span>  
  
5.  <span data-ttu-id="3e261-120">Escriba las fechas de inicio y finalización de un **negro de espera** si hay un período cuando no se podrá recibir y responder a alertas.</span><span class="sxs-lookup"><span data-stu-id="3e261-120">Type the start and end dates for a **Black-out Period** if there is a period when you will be unable to receive and act upon alerts.</span></span>  
  
6.  <span data-ttu-id="3e261-121">Seleccione un **intervalo** en **minutos** durante el que el portal comparará las alertas emitidas y enviará solo cuando se producen varias instancias de la misma alerta.</span><span class="sxs-lookup"><span data-stu-id="3e261-121">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and will send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="3e261-122">Esto evita que un error rápidamente que se está produciendo desde la creación de un gran número de mensajes de alerta idénticos.</span><span class="sxs-lookup"><span data-stu-id="3e261-122">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  
  
7.  <span data-ttu-id="3e261-123">Haga clic en el **guardar** botón para actualizar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3e261-123">Click the **Save** button to update the subscription.</span></span>  
  
### <a name="to-delete-an-existing-alert-subscription"></a><span data-ttu-id="3e261-124">Para eliminar una suscripción de alerta existente</span><span class="sxs-lookup"><span data-stu-id="3e261-124">To delete an existing alert subscription</span></span>  
  
1.  <span data-ttu-id="3e261-125">Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md) para ver una lista de las alertas existentes y las suscripciones actuales de estas alertas.</span><span class="sxs-lookup"><span data-stu-id="3e261-125">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="3e261-126">Haga clic en el **eliminar** vínculo situado junto a la suscripción que desea eliminar en la lista en la **Mis suscripciones** sección de la página.</span><span class="sxs-lookup"><span data-stu-id="3e261-126">Click the **Delete** link next to the subscription you want to delete in the list in the **My Subscriptions** section of the page.</span></span>
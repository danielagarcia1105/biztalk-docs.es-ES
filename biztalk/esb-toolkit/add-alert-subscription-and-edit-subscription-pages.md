---
title: Agregar suscripción de alerta y editar las páginas de suscripción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b843bde8905d8b6803dda56a6370f70c934a610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013453"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a><span data-ttu-id="75243-102">Agregar suscripción de alerta y editar las páginas de suscripción</span><span class="sxs-lookup"><span data-stu-id="75243-102">Add Alert Subscription and Edit Subscription Pages</span></span>
<span data-ttu-id="75243-103">Las páginas Agregar suscripción de alerta y Editar suscripción son similares.</span><span class="sxs-lookup"><span data-stu-id="75243-103">The Add Alert Subscription and Edit Subscription pages are similar.</span></span> <span data-ttu-id="75243-104">Se diferencian en que la página Editar suscripción muestra el identificador de suscriptor (la cuenta de Microsoft Windows del usuario del portal actual) y tiene un conjunto diferente de botones.</span><span class="sxs-lookup"><span data-stu-id="75243-104">They differ in that the Edit Subscription page shows the subscriber ID (the Microsoft Windows account of the current portal user), and has a different set of buttons.</span></span> <span data-ttu-id="75243-105">Figura 1 muestra las páginas Agregar suscripción de alerta y Editar suscripción.</span><span class="sxs-lookup"><span data-stu-id="75243-105">Figure 1 shows the Add Alert Subscription and Edit Subscription pages.</span></span>  

 <span data-ttu-id="75243-106">![Agregar suscripción de alerta edición](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span><span class="sxs-lookup"><span data-stu-id="75243-106">![Add Alert Edit Subscription](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")</span></span>  

 <span data-ttu-id="75243-107">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="75243-107">**Figure 1**</span></span>  

 <span data-ttu-id="75243-108">**Las páginas de ESB Management Portal Agregar suscripción de alerta y Editar suscripción**</span><span class="sxs-lookup"><span data-stu-id="75243-108">**The ESB Management Portal Add Alert Subscription and Edit Subscription pages**</span></span>  

 <span data-ttu-id="75243-109">Las páginas Agregar suscripción de alerta y Editar suscripción le permiten especificar y modificar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="75243-109">The Add Alert Subscription and Edit Subscription pages allow you to specify and modify the following:</span></span>  

- <span data-ttu-id="75243-110">Una dirección de correo electrónico personalizado que se usará para la suscripción (en lugar de la dirección de correo electrónico de tu cuenta de Microsoft Windows)</span><span class="sxs-lookup"><span data-stu-id="75243-110">A custom e-mail address to use for the subscription (instead of your Microsoft Windows account e-mail address)</span></span>  

- <span data-ttu-id="75243-111">El período de tiempo cuando aceptará las notificaciones de alerta</span><span class="sxs-lookup"><span data-stu-id="75243-111">The time period when you will accept alert notifications</span></span>  

- <span data-ttu-id="75243-112">Un período "black" para eventos como vacaciones</span><span class="sxs-lookup"><span data-stu-id="75243-112">A "black-out" period for events such as vacations</span></span>  

- <span data-ttu-id="75243-113">El intervalo durante el que el portal no enviará alertas duplicadas</span><span class="sxs-lookup"><span data-stu-id="75243-113">The interval over which the portal will not send duplicate alerts</span></span>  

  <span data-ttu-id="75243-114">Puede hacer lo siguiente en las páginas Agregar suscripción de alerta y Editar suscripción:</span><span class="sxs-lookup"><span data-stu-id="75243-114">You can do the following on the Add Alert Subscription and Edit Subscription pages:</span></span>  

- <span data-ttu-id="75243-115">Active la casilla situada junto a la **correo electrónico personalizados** texto cuadro si desea usar una dirección de correo electrónico de la suscripción que es diferente a la dirección de correo electrónico de cuenta de Windows estándar y, a continuación, escriba la dirección de correo electrónico preferida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="75243-115">Select the check box next to the **Custom Email** text box if you want to use an e-mail address for the subscription that is different to your standard Windows account e-mail address, and then type the preferred e-mail address in the text box.</span></span>  

- <span data-ttu-id="75243-116">Active la casilla situada en la parte superior de la **programación** sección si desea especificar un período cuando el portal debe enviar alertas a usted y, a continuación, especifique las horas inicial y final para el período en el **Start Time** y **Hora de finalización** listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="75243-116">Select the check box at the top of the **Schedule** section if you want to specify a period when the portal should send alerts to you, and then specify the start and end times for the period in the **Start Time** and **End Time** drop-down lists.</span></span> <span data-ttu-id="75243-117">Alertas que se producen fuera de este período se ponen en cola y entregadas durante el período especificado.</span><span class="sxs-lookup"><span data-stu-id="75243-117">Alerts occurring outside this period are queued and delivered during the specified period.</span></span>  

- <span data-ttu-id="75243-118">Escriba la fecha de inicio y fecha de finalización de un **negro de espera** si hay un período cuando no será posible recibir y actuar en las alertas.</span><span class="sxs-lookup"><span data-stu-id="75243-118">Type the start date and end date for a **Black-out Period** if there is a period when you will be unable to receive and act on alerts.</span></span> <span data-ttu-id="75243-119">Use el formato mm/dd/aaaa para las dos fechas.</span><span class="sxs-lookup"><span data-stu-id="75243-119">Use the format mm/dd/yyyy for the two dates.</span></span>  

- <span data-ttu-id="75243-120">Seleccione un **intervalo** en **minutos** durante el que el portal de comparará las alertas emitidas y enviar sólo uno cuando se producen varias instancias de la misma alerta.</span><span class="sxs-lookup"><span data-stu-id="75243-120">Select an **Interval** in **Minutes** during which the portal will compare alerts raised and send only one when multiple instances of the same alert occur.</span></span> <span data-ttu-id="75243-121">Esto evita que un error que se producen rápidamente desde la creación de un gran número de mensajes de alerta idénticos.</span><span class="sxs-lookup"><span data-stu-id="75243-121">This prevents a rapidly occurring fault from creating a large number of identical alert messages.</span></span>  

- <span data-ttu-id="75243-122">Haga clic en el **guardar** botón para crear o actualizar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="75243-122">Click the **Save** button to create or update the subscription.</span></span>  

- <span data-ttu-id="75243-123">Haga clic en el **eliminar** botón (disponible solo en la página Editar suscripción) para eliminar la suscripción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="75243-123">Click the **Delete** button (available only on the Edit Subscription page) to delete the selected subscription.</span></span>  

- <span data-ttu-id="75243-124">Haga clic en el **cancelar** botón para volver a la [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md) sin crear ni modificar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="75243-124">Click the **Cancel** button to go back to the [Alert Viewer Page](../esb-toolkit/alert-viewer-page.md) without creating or modifying the subscription.</span></span>

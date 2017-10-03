---
title: "Administrar alertas (vista de administración) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27f8bf7d-15b7-448d-8c13-e4969b90d021
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5472e96414fe5141de27630ebe3c810d2df28c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-alerts-administration-view"></a><span data-ttu-id="1ab50-102">Administrar alertas (vista de administración)</span><span class="sxs-lookup"><span data-stu-id="1ab50-102">Manage Alerts (Administration View)</span></span>
<span data-ttu-id="1ab50-103">Figura 1 muestra la página de alertas en la vista de administración, que los administradores pueden usar para ver una lista de todas las alertas y un resumen de su actividad.</span><span class="sxs-lookup"><span data-stu-id="1ab50-103">Figure 1 shows the Alerts page in administration view, which administrators can use to view a list of all alerts and a summary of their activity.</span></span> <span data-ttu-id="1ab50-104">Una tabla muestra una fila para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-104">A table displays a row for each alert.</span></span> <span data-ttu-id="1ab50-105">Cada fila muestra el nombre de la alerta, el nombre del creador del estadísticas generales de la alerta (por ejemplo, el número de activaciones de alerta dentro de la última hora, día o mes), un recuento de los suscriptores para las alertas con un vínculo para ver una lista y una columna de las acciones que contiene un conjunto de cli iconos de ckable para realizar acciones en la alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-105">Each row shows the alert name, the name of the creator, general statistics for the alert (such as number of alert activations within the last hour, day, or month), a count of subscribers for the alerts with a link to view a list, and an Actions column containing a set of clickable icons to perform actions on the alert.</span></span>  
  
 <span data-ttu-id="1ab50-106">![Página de alertas administrar](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span><span class="sxs-lookup"><span data-stu-id="1ab50-106">![Manage Alerts Page](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8-ManageAlertsPage")</span></span>  
  
 <span data-ttu-id="1ab50-107">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="1ab50-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="1ab50-108">**La página de ESB Management Portal administrar alertas (vista de administración)**</span><span class="sxs-lookup"><span data-stu-id="1ab50-108">**The ESB Management Portal Manage Alerts (Administration view) page**</span></span>  
  
 <span data-ttu-id="1ab50-109">En la lista siguiente se explica cómo puede usar las características de la página Administrar alertas de ESB Management Portal:</span><span class="sxs-lookup"><span data-stu-id="1ab50-109">The following list explains how you can use the features of the ESB Management Portal Manage Alerts page:</span></span>  
  
-   <span data-ttu-id="1ab50-110">Haga clic en el **crear alerta** vínculo en la parte superior de la página para crear una nueva alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-110">Click the **Create Alert** link at the top of the page to create a new alert.</span></span>  
  
-   <span data-ttu-id="1ab50-111">Haga clic en el **exportar a Excel** vínculo para exportar la lista de alertas como una hoja de cálculo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1ab50-111">Click the **Export To Excel** link to export the list of alerts as a Microsoft Excel spreadsheet.</span></span>  
  
-   <span data-ttu-id="1ab50-112">Haga clic en el + **vista suscriptores** vínculo en una fila para mostrar una lista de suscriptores de la alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-112">Click the + **View Subscribers** link in a row to show a list of subscribers for the alert.</span></span> <span data-ttu-id="1ab50-113">La lista se expande en la fila, y aparece un icono de eliminación en la columna de acciones para cada uno de ellos que permite a los administradores quitar un suscriptor de la alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-113">The list expands within the row, and a delete icon appears in the Actions column for each one that allows administrators to remove a subscriber from the alert.</span></span> <span data-ttu-id="1ab50-114">Al mismo tiempo, el vínculo cambia a - **ocultar suscriptores**, lo que le permite contraer la lista de suscriptores.</span><span class="sxs-lookup"><span data-stu-id="1ab50-114">At the same time, the link changes to - **Hide Subscribers**, allowing you to collapse the list of subscribers.</span></span>  
  
-   <span data-ttu-id="1ab50-115">Haga clic en un icono en la columna de acciones que se va a realizar una tarea para las alertas de esa fila.</span><span class="sxs-lookup"><span data-stu-id="1ab50-115">Click an icon in the Actions column to perform a task for the alerts in that row.</span></span> <span data-ttu-id="1ab50-116">Los iconos (en el orden en que aparecen) y las tareas son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ab50-116">The icons (in the order they appear) and the tasks are the following:</span></span>  
  
    -   <span data-ttu-id="1ab50-117">**Ver detalles de la alerta.**</span><span class="sxs-lookup"><span data-stu-id="1ab50-117">**View alert details.**</span></span> <span data-ttu-id="1ab50-118">Este icono muestra los detalles de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1ab50-118">This icon displays details of the selected alert.</span></span>  
  
    -   <span data-ttu-id="1ab50-119">**Ver el historial de**.</span><span class="sxs-lookup"><span data-stu-id="1ab50-119">**View history**.</span></span> <span data-ttu-id="1ab50-120">Este icono muestra una tabla que contiene todas las activaciones de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1ab50-120">This icon displays a table containing all the activations for the selected alert.</span></span>  
  
    -   <span data-ttu-id="1ab50-121">**Agregar suscriptor**.</span><span class="sxs-lookup"><span data-stu-id="1ab50-121">**Add subscriber**.</span></span> <span data-ttu-id="1ab50-122">Este icono permite a los administradores agregar un suscriptor a la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1ab50-122">This icon allows administrators to add a subscriber to the selected alert.</span></span>  
  
    -   <span data-ttu-id="1ab50-123">**Modificar alerta**.</span><span class="sxs-lookup"><span data-stu-id="1ab50-123">**Edit alert**.</span></span> <span data-ttu-id="1ab50-124">Este vínculo permite a los administradores editar los detalles de alerta.</span><span class="sxs-lookup"><span data-stu-id="1ab50-124">This link allows administrators to edit the alert details.</span></span>  
  
    -   <span data-ttu-id="1ab50-125">**Eliminar alerta**.</span><span class="sxs-lookup"><span data-stu-id="1ab50-125">**Delete alert**.</span></span> <span data-ttu-id="1ab50-126">Este vínculo elimina las suscripciones de alerta y todos los asociados.</span><span class="sxs-lookup"><span data-stu-id="1ab50-126">This link deletes the alert and all associated subscriptions.</span></span>
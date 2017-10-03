---
title: Crear, ver y eliminar error mensaje alertas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9451ecb9cbeaf2077712f6e6b55a36dab7988c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a><span data-ttu-id="c0230-102">Crear, ver y eliminar las alertas de mensaje de error</span><span class="sxs-lookup"><span data-stu-id="c0230-102">Creating, Viewing, and Deleting Fault Message Alerts</span></span>
<span data-ttu-id="c0230-103">El Portal de administración de ESB pueden generar alertas cuando llegan los mensajes de error en el portal, basándose en una comparación de valores en el mensaje con los criterios especificados para la alerta.</span><span class="sxs-lookup"><span data-stu-id="c0230-103">The ESB Management Portal can generate alerts when fault messages arrive at the portal, based on a comparison of values in the message with criteria specified for the alert.</span></span> <span data-ttu-id="c0230-104">El portal también puede mantener una lista de notificaciones de alertas vinculado a una persona y los usuarios, y notificará a estos usuarios cuando proactivamente genera alertas.</span><span class="sxs-lookup"><span data-stu-id="c0230-104">The portal can also maintain a list of notifications linked to individual alerts and users, and it will notify these users when it proactively raises alerts.</span></span>  
  
### <a name="to-create-and-configure-a-new-alert"></a><span data-ttu-id="c0230-105">Para crear y configurar una nueva alerta</span><span class="sxs-lookup"><span data-stu-id="c0230-105">To create and configure a new alert</span></span>  
  
1.  <span data-ttu-id="c0230-106">Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md) para ver una lista de las alertas existentes y las suscripciones actuales de estas alertas.</span><span class="sxs-lookup"><span data-stu-id="c0230-106">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md) to see a list of existing alerts and your current subscriptions to these alerts.</span></span>  
  
2.  <span data-ttu-id="c0230-107">Haga clic en el **crear alertas** vínculo para abrir el [Agregar página alerta](../esb-toolkit/add-alert-page.md).</span><span class="sxs-lookup"><span data-stu-id="c0230-107">Click the **Create Alert** link to open the [Add Alert Page](../esb-toolkit/add-alert-page.md).</span></span>  
  
3.  <span data-ttu-id="c0230-108">En el **escriba el nombre de alerta** cuadro de texto, escriba un nombre para la nueva alerta.</span><span class="sxs-lookup"><span data-stu-id="c0230-108">In the **Enter Alert Name** text box, type a name for the new alert.</span></span>  
  
4.  <span data-ttu-id="c0230-109">En el **condiciones** sección de la página Agregar alerta, seleccione un campo (como **aplicación**, **tipo de Error**, o **gravedad de error**) en el **Criterios** lista desplegable; seleccione un tipo de comparación (como +, =,! =, > =, \<=, o **como**) en el **operador** lista desplegable; y tipo o seleccione un valor en el tercer cuadro de lista o de texto (denominado **valor**).</span><span class="sxs-lookup"><span data-stu-id="c0230-109">In the **Conditions** section of the Add Alert page, select a field (such as **Application**, **Error Type**, or **Fault Severity**) in the **Criteria** drop-down list; select a comparison type (such as +, =, !=, >=, \<=, or **like**) in the **Operator** drop-down list; and type or select a value from the third list or text box (named **Value**).</span></span> <span data-ttu-id="c0230-110">Al seleccionar un **criterios** valor, la página cambia para mostrar un cuadro de texto o una lista desplegable para el valor coincidente.</span><span class="sxs-lookup"><span data-stu-id="c0230-110">As you select a **Criteria** value, the page changes to display either a text box or a drop-down list for the matching value.</span></span> <span data-ttu-id="c0230-111">Todas las condiciones se combinan con el **AND** operador.</span><span class="sxs-lookup"><span data-stu-id="c0230-111">All conditions are combined using the **AND** operator.</span></span>  
  
5.  <span data-ttu-id="c0230-112">Haga clic en el **agregar** use el vínculo para agregar esta condición a la lista y, a continuación, repita el paso anterior para agregar más condiciones Si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c0230-112">Click the **Add** link to add this condition to the list, and then repeat the previous step to add more conditions if required.</span></span>  
  
6.  <span data-ttu-id="c0230-113">Haga clic en el **guardar** botón para crear una nueva alerta con el nombre especificado y condiciones.</span><span class="sxs-lookup"><span data-stu-id="c0230-113">Click the **Save** button to create a new alert with the specified name and conditions.</span></span>  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a><span data-ttu-id="c0230-114">Para ver los detalles de una alerta existente o eliminar una alerta existente</span><span class="sxs-lookup"><span data-stu-id="c0230-114">To view details of an existing alert or delete an existing alert</span></span>  
  
1.  <span data-ttu-id="c0230-115">Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md).</span><span class="sxs-lookup"><span data-stu-id="c0230-115">Open the [Portal Alerts Page](../esb-toolkit/portal-alerts-page.md).</span></span>  
  
2.  <span data-ttu-id="c0230-116">Para eliminar una alerta, haga clic en el **Eliminar alerta** icono en la columna de acción de una alerta existente.</span><span class="sxs-lookup"><span data-stu-id="c0230-116">To delete an alert, click the **Delete Alert** icon in the Action column of an existing alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0230-117">Los usuarios no administrativos pueden eliminar sólo las alertas para que sean propietarios, y de que hay actualmente ningún suscriptor.</span><span class="sxs-lookup"><span data-stu-id="c0230-117">Non-administrative users can delete only alerts for which they are an owner, and for which there are currently no subscribers.</span></span> <span data-ttu-id="c0230-118">Debe iniciar sesión en el portal como un administrador elimine otras alertas.</span><span class="sxs-lookup"><span data-stu-id="c0230-118">You must log on to the portal as an administrator to delete other alerts.</span></span>  
  
3.  <span data-ttu-id="c0230-119">Para ver los detalles de una alerta, haga clic en el **vista** icono en la columna de acción de una alerta existente.</span><span class="sxs-lookup"><span data-stu-id="c0230-119">To view details of an alert, click the **View** icon in the Action column of an existing alert.</span></span> <span data-ttu-id="c0230-120">Se abrirá la página de Visor de alertas.</span><span class="sxs-lookup"><span data-stu-id="c0230-120">This opens the Alert Viewer page.</span></span>  
  
4.  <span data-ttu-id="c0230-121">Haga clic en **exportar a Excel** para descargar la lista completa de las alertas en un formato que se puede ver en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c0230-121">Click **Export To Excel** to download the complete list of alerts in a format that you can view in Microsoft Excel.</span></span>
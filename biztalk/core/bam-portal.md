---
title: Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- activities [BAM], searching
- BAM portal
- BAM portal, features
- aggregations [BAM], BAM portal
- BAM portal, activity searches
- alerts, Alert Manager
- BAM portal, about BAM portal
- BAM, portals
- BAM portal, aggregations
ms.assetid: 593c9637-6b97-4ad8-8af7-2b49325acf10
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f86aad2a183653f00f1f7fc2533ac6956b2a85f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232084"
---
# <a name="bam-portal"></a><span data-ttu-id="b58d8-102">Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-102">BAM Portal</span></span>
<span data-ttu-id="b58d8-103">Los usuarios empresariales finales utilizan el portal de BAM para supervisar los indicadores clave de rendimiento (KPI), que miden el progreso hacia un objetivo empresarial, y otra información acerca de sus procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="b58d8-103">Business end users use the BAM portal to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="b58d8-104">Los analistas de negocios utilizan el portal de BAM para controlar la creación de modelos de observación, que son las definiciones de alto nivel de los requisitos de visibilidad dentro del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="b58d8-104">Business analysts use the BAM portal to oversee the creation of observation models, which are high-level definitions of the visibility requirements within the business process.</span></span> <span data-ttu-id="b58d8-105">Los administradores lo utilizan en un gran número de actividades de supervisión, que incluyen supervisar el estado del sistema de administración del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="b58d8-105">Administrators use it for a variety of monitoring activities, including monitoring the health of the business process management system.</span></span>  
  
## <a name="what-is-the-bam-portal"></a><span data-ttu-id="b58d8-106">¿Qué es el portal de BAM?</span><span class="sxs-lookup"><span data-stu-id="b58d8-106">What is the BAM portal?</span></span>  
 <span data-ttu-id="b58d8-107">El portal de BAM proporciona visibilidad en tiempo real, de extremo a extremo a un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="b58d8-107">The BAM portal provides real-time, end-to-end visibility into a business process.</span></span> <span data-ttu-id="b58d8-108">Es una característica basada en Web que consta de una colección de páginas de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b58d8-108">It is a Web-based feature that consists of a collection of ASP.NET pages.</span></span> <span data-ttu-id="b58d8-109">Puede personalizar BAM para mejorar el rendimiento y la experiencia de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b58d8-109">You can customize BAM to enhance the performance and experience for your users.</span></span>  
  
## <a name="why-use-the-bam-portal"></a><span data-ttu-id="b58d8-110">¿Por qué se utiliza el portal de BAM?</span><span class="sxs-lookup"><span data-stu-id="b58d8-110">Why use the BAM portal?</span></span>  
 <span data-ttu-id="b58d8-111">el portal de BAM permite efectuar búsquedas, agregar datos y establecer alertas en una vista de BAM, que constituye una perspectiva de los datos económicos.</span><span class="sxs-lookup"><span data-stu-id="b58d8-111">The BAM portal allows you to perform searches, aggregate data, and set alerts on a BAM view, which is a perspective on your business data.</span></span> <span data-ttu-id="b58d8-112">Esta visibilidad puede proporcionar la información necesaria de KPI para su empresa, o se puede utilizar como prueba de concepto antes de implementar otra solución, como extender una hoja de cálculo de Microsoft Office Excel, utilizar el informe de SQL o generar una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="b58d8-112">This visibility can provide the necessary KPI information for your business, or it can be used as proof of concept before you implement another solution such as extending a Microsoft Office Excel spreadsheet, using SQL Reporting, or building a custom user interface (UI).</span></span>  
  
## <a name="bam-portal-components"></a><span data-ttu-id="b58d8-113">Componentes del portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-113">BAM portal components</span></span>  
 <span data-ttu-id="b58d8-114">A continuación se muestra una breve descripción de los componentes del portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b58d8-114">Following is a brief description of the BAM portal components.</span></span> <span data-ttu-id="b58d8-115">Para obtener una descripción más detallada, consulte los temas enumerados en la sección Consulte también.</span><span class="sxs-lookup"><span data-stu-id="b58d8-115">For a more detailed description, see the topics in See Also.</span></span>  
  
### <a name="activity-searches"></a><span data-ttu-id="b58d8-116">Búsquedas de actividad</span><span class="sxs-lookup"><span data-stu-id="b58d8-116">Activity searches</span></span>  
 <span data-ttu-id="b58d8-117">El portal de BAM se utiliza para realizar búsquedas con respecto a los datos de BAM para encontrar una actividad específica de BAM.</span><span class="sxs-lookup"><span data-stu-id="b58d8-117">You use the BAM portal to perform searches against BAM data to find a specific BAM activity.</span></span> <span data-ttu-id="b58d8-118">Se crean consultas al agregar y quitar cláusulas de búsqueda que le permiten mostrar las actividades que coinciden con los criterios de los que desea recibir una alerta.</span><span class="sxs-lookup"><span data-stu-id="b58d8-118">You create queries by adding and removing search clauses that allow you to display those activities that match criteria for which you want to be alerted.</span></span>  
  
 <span data-ttu-id="b58d8-119">Las consultas se pueden guardar y volver a usar.</span><span class="sxs-lookup"><span data-stu-id="b58d8-119">Queries can be saved and reused.</span></span> <span data-ttu-id="b58d8-120">También pueden ser la base para una alerta, como una notificación cuando un pedido llega desde un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="b58d8-120">They can also be the basis for an alert, such as a notification when a purchase order arrives from a specific customer.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="b58d8-121">Agregaciones</span><span class="sxs-lookup"><span data-stu-id="b58d8-121">Aggregations</span></span>  
 <span data-ttu-id="b58d8-122">El portal le permite capturar una instantánea de los datos y mostrarlos en forma de diagrama gráfico y diagrama de tabla dinámica que lo acompaña.</span><span class="sxs-lookup"><span data-stu-id="b58d8-122">The portal allows you to capture a snapshot of data and display it in the form of a graphical chart and accompanying PivotTable chart.</span></span> <span data-ttu-id="b58d8-123">Estos datos le proporcionan visibilidad en el estado de ese proceso o del negocio en general.</span><span class="sxs-lookup"><span data-stu-id="b58d8-123">This data gives you visibility into the health of that process or the overall business.</span></span> <span data-ttu-id="b58d8-124">Por ejemplo, puede que un usuario desee ver un gráfico circular básico que muestre un desglose de 1.000 facturas recibidas en un día en lo que respecta a la fase de procesamiento que se alcanzado con cada factura (400 en “evaluación”, 400 rechazadas, 100 pagadas y 100 en “asignación de recursos”).</span><span class="sxs-lookup"><span data-stu-id="b58d8-124">For example, a user may wish to see a simple pie chart that shows a breakdown of the 1,000 invoices received in a day in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
 <span data-ttu-id="b58d8-125">Los datos que se presentan pueden ser la base para crear una alerta, como “Notifíqueme si alguna vez hay más de 500 facturas en la fase de 'evaluación' del proceso.”</span><span class="sxs-lookup"><span data-stu-id="b58d8-125">The data presented can be the basis for creating an alert, such as "Notify me if there are ever more than 500 invoices in the 'evaluation' stage of the process."</span></span>  
  
### <a name="alert-manager"></a><span data-ttu-id="b58d8-126">Administrador de alertas</span><span class="sxs-lookup"><span data-stu-id="b58d8-126">Alert Manager</span></span>  
 <span data-ttu-id="b58d8-127">El portal proporciona una interfaz de usuario para crear alertas y editar alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="b58d8-127">The portal provides a user interface for the creation of alerts and the editing of existing alerts.</span></span> <span data-ttu-id="b58d8-128">Las alertas llevan las condiciones que se van a supervisar desde la página Búsqueda de actividad o la página Agregaciones.</span><span class="sxs-lookup"><span data-stu-id="b58d8-128">Alerts take the conditions that are to be monitored from either the Activity Search or Aggregations page.</span></span> <span data-ttu-id="b58d8-129">El administrador de alertas es donde se cumplimentan las partes correspondientes de una alerta, como a quién se notifica, cómo se notifica (por ejemplo, mediante correo electrónico) o si otros usuarios podrán ver las alertas y suscribirse a ellas.</span><span class="sxs-lookup"><span data-stu-id="b58d8-129">The Alert Manager is where you fill in the relevant parts of an alert, such as who to notify, how (for example, through e-mail), and whether others can see and subscribe to the alert.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b58d8-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b58d8-130">In This Section</span></span>  
  
-   [<span data-ttu-id="b58d8-131">Componentes del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-131">Components of the BAM Portal</span></span>](../core/components-of-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-132">Planeación del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-132">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-133">Búsquedas de actividad en el Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-133">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-134">Agregaciones del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-134">Aggregations in the BAM Portal</span></span>](../core/aggregations-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-135">Alertas del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-135">Alerts in the BAM Portal</span></span>](../core/alerts-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-136">Accesibilidad para el Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-136">Accessibility for the BAM Portal</span></span>](../core/accessibility-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-137">Consideraciones de seguridad para el Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-137">Security Considerations for the BAM Portal</span></span>](../core/security-considerations-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="b58d8-138">Problemas conocidos del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="b58d8-138">Known Issues in the BAM Portal</span></span>](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a><span data-ttu-id="b58d8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b58d8-139">See Also</span></span>  
 <span data-ttu-id="b58d8-140">[Búsqueda de actividad en el Portal de BAM página](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="b58d8-140">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 <span data-ttu-id="b58d8-141">[Las agregaciones en el Portal de BAM página](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="b58d8-141">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="b58d8-142">Alert Manager en el Portal de BAM de página</span><span class="sxs-lookup"><span data-stu-id="b58d8-142">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)
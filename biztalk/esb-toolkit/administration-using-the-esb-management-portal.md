---
title: "Administración mediante el Portal de administración de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="administration-using-the-esb-management-portal"></a><span data-ttu-id="0e4af-102">Administración mediante el Portal de administración de ESB</span><span class="sxs-lookup"><span data-stu-id="0e4af-102">Administration Using the ESB Management Portal</span></span>
<span data-ttu-id="0e4af-103">El Portal de administración de ESB, incluido como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], es un sitio de ejemplo que muestra el uso de las métricas y las posibilidades que existen para extender el Kit de herramientas de ESB de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0e4af-103">The ESB Management Portal, included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], is a sample site that demonstrates the use of metrics and the possibilities that exist for extending the BizTalk ESB Toolkit.</span></span> <span data-ttu-id="0e4af-104">El portal proporciona un punto de partida desde el que puede crear su propio portal personalizado.</span><span class="sxs-lookup"><span data-stu-id="0e4af-104">The portal provides a starting point from which you can build your own customized portal.</span></span>  
  
 <span data-ttu-id="0e4af-105">El Portal de administración de ESB también es una herramienta de alta capacidad y útil que puede ayudar a maximizar el uso y la eficacia del sistema de administración de la excepción de ESB.</span><span class="sxs-lookup"><span data-stu-id="0e4af-105">The ESB Management Portal is also a highly capable and useful tool that can help to maximize the use and efficiency of the ESB exception management system.</span></span> <span data-ttu-id="0e4af-106">Además, el portal proporciona una interfaz de usuario para un servidor de registro subyacente de Universal Description, Discovery y Integration (UDDI) y capacidades de configuración gráfica para características como la auditoría, ver la información de historial, configurar alertas y notificaciones y permitir a los usuarios para suscribirse a alertas que indican errores que se produzcan en las aplicaciones de ESB.</span><span class="sxs-lookup"><span data-stu-id="0e4af-106">In addition, the portal provides a user interface for an underlying Universal Description, Discovery, and Integration (UDDI) registry server and graphical configuration capabilities for features such as auditing, viewing history information, configuring alerts and notifications, and allowing users to subscribe to alerts that indicate faults occurring in ESB applications.</span></span>  
  
 <span data-ttu-id="0e4af-107">En esta sección se describe las tareas comunes que puede realizar con el Portal de administración de ESB, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e4af-107">This section describes the common tasks you can accomplish using the ESB Management Portal, including the following:</span></span>  
  
-   [<span data-ttu-id="0e4af-108">Trabajar con excepciones y mensajes de error</span><span class="sxs-lookup"><span data-stu-id="0e4af-108">Working with Exceptions and Fault Messages</span></span>](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [<span data-ttu-id="0e4af-109">Configuración de alertas, notificaciones y suscripciones</span><span class="sxs-lookup"><span data-stu-id="0e4af-109">Configuring Alerts, Notifications, and Subscriptions</span></span>](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [<span data-ttu-id="0e4af-110">Ver y administrar auditoría e historial</span><span class="sxs-lookup"><span data-stu-id="0e4af-110">Viewing and Managing Auditing and History</span></span>](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [<span data-ttu-id="0e4af-111">Analizar las tendencias de errores mediante gráficos e informes</span><span class="sxs-lookup"><span data-stu-id="0e4af-111">Analyzing Fault Trends Using Charts and Reports</span></span>](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [<span data-ttu-id="0e4af-112">Ver y publicar los registros UDDI</span><span class="sxs-lookup"><span data-stu-id="0e4af-112">Viewing and Publishing UDDI Registrations</span></span>](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  <span data-ttu-id="0e4af-113">Para obtener una descripción detallada de las características individuales del Portal de administración de ESB, consulte [referencia de características de Portal de administración de ESB](../esb-toolkit/esb-management-portal-feature-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0e4af-113">For a detailed description of the individual features of the ESB Management Portal, see [ESB Management Portal Feature Reference](../esb-toolkit/esb-management-portal-feature-reference.md).</span></span>  
  
## <a name="esb-portal-technologies"></a><span data-ttu-id="0e4af-114">Tecnologías de Portal de ESB</span><span class="sxs-lookup"><span data-stu-id="0e4af-114">ESB Portal Technologies</span></span>  
 <span data-ttu-id="0e4af-115">El Portal de administración de ESB aprovecha las ventajas de las siguientes tecnologías:</span><span class="sxs-lookup"><span data-stu-id="0e4af-115">The ESB Management Portal takes advantage of the following technologies:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   <span data-ttu-id="0e4af-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0e4af-116">ASP.NET</span></span>
  
-   <span data-ttu-id="0e4af-117">[Biblioteca de información empresarial](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span><span class="sxs-lookup"><span data-stu-id="0e4af-117">[Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292)).</span></span> <span data-ttu-id="0e4af-118">El Portal de administración de ESB usa los siguientes ensamblados de Enterprise Library:</span><span class="sxs-lookup"><span data-stu-id="0e4af-118">The ESB Management Portal uses the following Enterprise Library assemblies:</span></span>  
  
    -   <span data-ttu-id="0e4af-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span><span class="sxs-lookup"><span data-stu-id="0e4af-119">**Microsoft.Practices.EnterpriseLibrary.Caching**</span></span>  
  
    -   <span data-ttu-id="0e4af-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span><span class="sxs-lookup"><span data-stu-id="0e4af-120">**Microsoft.Practices.EnterpriseLibrary.Common**</span></span>  
  
    -   <span data-ttu-id="0e4af-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span><span class="sxs-lookup"><span data-stu-id="0e4af-121">**Microsoft.Practices.EnterpriseLibrary.Data**</span></span>  
  
    -   <span data-ttu-id="0e4af-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="0e4af-122">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**</span></span>  
  
    -   <span data-ttu-id="0e4af-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span><span class="sxs-lookup"><span data-stu-id="0e4af-123">**Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**</span></span>  
  
    -   <span data-ttu-id="0e4af-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span><span class="sxs-lookup"><span data-stu-id="0e4af-124">**Microsoft.Practices.EnterpriseLibrary.Logging**</span></span>  
  
    -   <span data-ttu-id="0e4af-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span><span class="sxs-lookup"><span data-stu-id="0e4af-125">**Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**</span></span>  
  
    -   <span data-ttu-id="0e4af-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span><span class="sxs-lookup"><span data-stu-id="0e4af-126">**Microsoft.Practices.EnterpriseLibrary.Validation**</span></span>  
  
    -   <span data-ttu-id="0e4af-127">Microsoft.Practices.Unity</span><span class="sxs-lookup"><span data-stu-id="0e4af-127">Microsoft.Practices.Unity</span></span>  
  
-   <span data-ttu-id="0e4af-128">[Controles de gráfico de Microsoft](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) para Microsoft .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="0e4af-128">[Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4</span></span>  
  
<span data-ttu-id="0e4af-129">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] métrica seguimiento sólo se aplica a seguimiento de errores para el sistema de administración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="0e4af-129">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] metric tracking extends only to fault tracking for the exception management system.</span></span>
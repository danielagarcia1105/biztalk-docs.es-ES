---
title: "Mediante la página concentrador de grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50693ccc-a3b2-4ad0-9a05-d60dab404a07
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e035a363b71b70db390d88a8b0e32e2e9b531d92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-group-hub-page"></a><span data-ttu-id="2f281-102">Usar la página Concentrador de grupo</span><span class="sxs-lookup"><span data-stu-id="2f281-102">Using the Group Hub Page</span></span>
<span data-ttu-id="2f281-103">Al seleccionar la **grupo de BizTalk** nodo en la consola de administración de BizTalk Server, muestra la página concentrador de grupo de BizTalk Server en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="2f281-103">Selecting the **BizTalk Group** node in the BizTalk Server Administration Console, displays the BizTalk Server Group Hub page in the details pane.</span></span> <span data-ttu-id="2f281-104">La página Concentrador de grupo de BizTalk Server se divide en tres secciones que proporcionan una vista general del estado del sistema de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="2f281-104">The BizTalk Server Group Hub page is divided into three sections that provide an overall view of the health of your BizTalk Server system:</span></span>  
  
-   <span data-ttu-id="2f281-105">El **Introducción a la configuración** sección, situada en la parte superior de la página concentrador de grupo, indica el estado general del grupo de BizTalk, mostrando el estado de las aplicaciones, instancias de host, y los controladores de adaptador configurados en Este grupo.</span><span class="sxs-lookup"><span data-stu-id="2f281-105">The **Configuration Overview** section, located in the upper part of the Group Hub page, indicates the overall health of the BizTalk group by displaying the state of the applications, host instances, and adapter handlers configured in this group.</span></span>  
  
-   <span data-ttu-id="2f281-106">El **trabajo en curso** y **elementos suspendidos** secciones se encuentran en el medio de la página concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="2f281-106">The **Work in Progress**  and **Suspended Items** sections are located in the middle of the Group Hub page.</span></span>  
  
    -   <span data-ttu-id="2f281-107">El **trabajo en curso** sección muestra las instancias de servicio, las orquestaciones deshidratadas, puertos de reintentos e inactivos, instancias de servicio preparadas e instancias de servicio programadas en ejecución.</span><span class="sxs-lookup"><span data-stu-id="2f281-107">The **Work in Progress** section displays running service instances, dehydrated orchestrations, retrying and idle ports, ready service instances, and scheduled service instances.</span></span>  
  
    -   <span data-ttu-id="2f281-108">El **elementos suspendidos** sección muestra el número de instancias de servicio suspendidas y las instancias reanudables y no reanudables.</span><span class="sxs-lookup"><span data-stu-id="2f281-108">The **Suspended Items** section displays the number of suspended service instances, and resumable and non-resumable instances.</span></span>  
  
-   <span data-ttu-id="2f281-109">El **instancias de servicio suspendidas agrupadas** sección muestra las instancias de servicio suspendidas agrupadas por aplicación, nombre de servicio, código de error y URI.</span><span class="sxs-lookup"><span data-stu-id="2f281-109">The **Grouped Suspended Service Instances** section displays suspended service instances grouped by application, service name, error code, and URI.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f281-110">Los números que figuran en la página Concentrador de grupo son recuentos aproximados únicamente.</span><span class="sxs-lookup"><span data-stu-id="2f281-110">The numbers listed on the Group Hub page are approximate counts only.</span></span> <span data-ttu-id="2f281-111">Por ejemplo, el número mostrado debajo **instancias en ejecución** o **instancias de servicio suspendidas** no puede ser igual el número total de instancias de servicio o instancias de servicio suspendidas en ejecución Dado que el estado del sistema puede cambiar mientras se están generando las distintas estadísticas sobre la página del concentrador.</span><span class="sxs-lookup"><span data-stu-id="2f281-111">For example, the numbers displayed under **Running service instances** or **Suspended service instances** might not equal the total number of running service instances or suspended service instances because the state of the system could change while the various statistics on the Hub page are being generated.</span></span>  
  
-   <span data-ttu-id="2f281-112">El **instancias de servicio controladas** y **eventos de mensajes controlados** secciones ejecutan consultas en los eventos de mensaje y el estado de las instancias de servicio con una coincidencia máxima = 50.</span><span class="sxs-lookup"><span data-stu-id="2f281-112">The **Tracked Service Instances** and **Tracked Message Events** sections execute queries on message events and the state of service instances with a maximum match = 50.</span></span>  
  
    -   <span data-ttu-id="2f281-113">**Realiza el seguimiento de instancias de servicio** consulta busca instancias de servicio controladas.</span><span class="sxs-lookup"><span data-stu-id="2f281-113">**Tracked service instances** query searches for tracked service instances.</span></span>  
  
    -   <span data-ttu-id="2f281-114">**Instancias completas** consulta busca instancias de servicio controladas con el estado completado.</span><span class="sxs-lookup"><span data-stu-id="2f281-114">**Completed instances** query searches for tracked service instances with state equal to completed.</span></span>  
  
    -   <span data-ttu-id="2f281-115">**Instancias finalizadas** consulta busca instancias de servicio controladas con el estado finalizado.</span><span class="sxs-lookup"><span data-stu-id="2f281-115">**Terminated instances** query searches for tracked service instances with state equal to terminated.</span></span>  
  
    -   <span data-ttu-id="2f281-116">**Eventos de mensajes controlados** consulta busca eventos de seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2f281-116">**Tracked message events** query searches for tracked message events.</span></span>  
  
    -   <span data-ttu-id="2f281-117">**Eventos de error de transmisión** consulta busca eventos de mensajes de seguimiento con un tipo de evento de error de transmisión.</span><span class="sxs-lookup"><span data-stu-id="2f281-117">**Transmission failure events** query searches for tracked message events with an event type of transmission failure.</span></span>  
  
-   <span data-ttu-id="2f281-118">El **informes de estado de EDI** y **informes de estado de EDIINT** secciones, situadas en la parte inferior de la página concentrador de grupo, muestra cuatro informes acerca de intercambios EDI y otro sobre los intercambios AS2: el intercambio de EDI y estado de confirmación correlacionado informes, el informe de estado del lote, el informe de agregación de intercambio, el informe de agregación de conjunto de transacciones y el informe mensaje AS2 y estado de MDN correlacionado.</span><span class="sxs-lookup"><span data-stu-id="2f281-118">The **EDI Status Reports** and **EDIINT Status Reports** sections, located at the bottom of the Group Hub page, displays four reports about EDI interchanges and one about AS2 interchanges: the EDI Interchange and Correlated ACK Status reports, the Batch Status report, the Interchange Aggregation Report, the Transaction Set Aggregation Report, and the AS2 Message and Correlated MDN Status report.</span></span> <span data-ttu-id="2f281-119">Para obtener más información acerca de estos informes, consulte [EDI y los informes de estado de AS2](../core/edi-and-as2-status-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="2f281-119">For more information about these reports, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f281-120">Las secciones Informes de estado de EDI y de EDIINT solo se mostrarán si las funciones EDI/AS2 están configuradas para este grupo BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2f281-120">The EDI and EDIINT Status Report sections will only be displayed if the EDI/AS2 features are configured for this BizTalk group.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f281-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2f281-121">In This Section</span></span>  
  
-   [<span data-ttu-id="2f281-122">Estados de la instancia de servicio</span><span class="sxs-lookup"><span data-stu-id="2f281-122">Service Instance States</span></span>](../core/service-instance-states.md)  
  
-   [<span data-ttu-id="2f281-123">Investigación de orquestación, puerto y errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="2f281-123">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)  
  
-   [<span data-ttu-id="2f281-124">Uso de la pestaña de consulta de la consola de administración</span><span class="sxs-lookup"><span data-stu-id="2f281-124">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)  
  
-   [<span data-ttu-id="2f281-125">Datos de instancia y los mensajes de seguimiento de visualización</span><span class="sxs-lookup"><span data-stu-id="2f281-125">Viewing Tracked Message and Instance Data</span></span>](../core/viewing-tracked-message-and-instance-data.md)  
  
-   [<span data-ttu-id="2f281-126">Seguimiento de estado y actividad</span><span class="sxs-lookup"><span data-stu-id="2f281-126">Health and Activity Tracking</span></span>](../core/health-and-activity-tracking.md)
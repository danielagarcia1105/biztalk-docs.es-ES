---
title: Mostrar un EDI o informes de estado de AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0564a5c5d904a217ac406befebd3d7c742dc00c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="5b015-102">Mostrar un informe de estado de EDI o AS2</span><span class="sxs-lookup"><span data-stu-id="5b015-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="5b015-103">Al habilitar los informes de estado de EDI y AS2, tendrá acceso a los siguientes informes de estado:</span><span class="sxs-lookup"><span data-stu-id="5b015-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="5b015-104">Tipo de informe</span><span class="sxs-lookup"><span data-stu-id="5b015-104">Type of Report</span></span>|<span data-ttu-id="5b015-105">Informe de estado de nivel superior</span><span class="sxs-lookup"><span data-stu-id="5b015-105">Higher-level status report</span></span>|<span data-ttu-id="5b015-106">Informe de estado de nivel inferior</span><span class="sxs-lookup"><span data-stu-id="5b015-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="5b015-107">ENRUTAMIENTO</span><span class="sxs-lookup"><span data-stu-id="5b015-107">EDI</span></span>|<span data-ttu-id="5b015-108">Intercambio EDI y estado de confirmación correlacionado</span><span class="sxs-lookup"><span data-stu-id="5b015-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="5b015-109">-Detalles de la confirmación y del estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="5b015-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="5b015-110">: Detalles del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="5b015-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="5b015-111">: Contenido del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="5b015-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="5b015-112">ENRUTAMIENTO</span><span class="sxs-lookup"><span data-stu-id="5b015-112">EDI</span></span>|<span data-ttu-id="5b015-113">Estado del lote</span><span class="sxs-lookup"><span data-stu-id="5b015-113">Batch Status</span></span>|-|  
|<span data-ttu-id="5b015-114">ENRUTAMIENTO</span><span class="sxs-lookup"><span data-stu-id="5b015-114">EDI</span></span>|<span data-ttu-id="5b015-115">Informe de agregación de intercambio</span><span class="sxs-lookup"><span data-stu-id="5b015-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="5b015-116">ENRUTAMIENTO</span><span class="sxs-lookup"><span data-stu-id="5b015-116">EDI</span></span>|<span data-ttu-id="5b015-117">Informe de agregación de conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="5b015-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="5b015-118">ENVÍO/RECEPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5b015-118">AS2</span></span>|<span data-ttu-id="5b015-119">Mensaje AS2 y estado de MDN correlacionado</span><span class="sxs-lookup"><span data-stu-id="5b015-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="5b015-120">Contenido de mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="5b015-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="5b015-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5b015-121">Prerequisites</span></span>  
 <span data-ttu-id="5b015-122">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="5b015-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="5b015-123">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para personalizar los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="5b015-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
-   <span data-ttu-id="5b015-124">Si ha iniciado sesión como miembro del grupo de operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede mostrar informes de estado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5b015-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="5b015-125">Mostrar un informe de estado EDI o AS2</span><span class="sxs-lookup"><span data-stu-id="5b015-125">Display an EDI or AS2 status report</span></span>  
  
1.  <span data-ttu-id="5b015-126">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo.</span><span class="sxs-lookup"><span data-stu-id="5b015-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2.  <span data-ttu-id="5b015-127">En el **concentrador de grupo** pestaña de la **información general del grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, vaya a la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="5b015-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3.  <span data-ttu-id="5b015-128">Para mostrar la **intercambio EDI y estado de confirmación correlacionado** de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b015-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="5b015-129">Haga clic en **intercambio EDI y estado de confirmación correlacionado** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b015-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="5b015-130">Para ver los detalles de un intercambio y sus confirmaciones correlacionadas, haga clic en una entrada en los resultados de consulta de la **intercambio EDI y estado de confirmación correlacionado** de informes y, a continuación, haga clic en **confirmación y del estado de intercambio detalles**.</span><span class="sxs-lookup"><span data-stu-id="5b015-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
    3.  <span data-ttu-id="5b015-131">Para ver los detalles de un conjunto de transacciones, cierre el intercambio confirmación y del estado informe de detalles, vuelva a la **intercambio EDI y estado de confirmación correlacionado** informe de detalles.</span><span class="sxs-lookup"><span data-stu-id="5b015-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="5b015-132">Haga clic en una entrada en los resultados de la consulta y, a continuación, haga clic en **detalles de conjunto de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="5b015-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
    4.  <span data-ttu-id="5b015-133">Para ver los detalles acerca de los encabezados y la carga de un conjunto de transacciones, haga clic en una entrada en el **detalles de conjunto de transacciones** de informes y, a continuación, haga clic en **contenido de conjunto de transacciones de vista**.</span><span class="sxs-lookup"><span data-stu-id="5b015-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
    5.  <span data-ttu-id="5b015-134">Para mostrar datos sobre el intercambio que contiene el conjunto de transacciones, haga clic en una entrada en el **detalles de conjunto de transacciones** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**.</span><span class="sxs-lookup"><span data-stu-id="5b015-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="5b015-135">El intercambio que contiene el conjunto de transacciones se resaltará en el informe Estado de la confirmación y del intercambio.</span><span class="sxs-lookup"><span data-stu-id="5b015-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4.  <span data-ttu-id="5b015-136">Para mostrar la **estado del lote** de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b015-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="5b015-137">Haga clic en **estado del lote** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b015-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="5b015-138">Para mostrar los lotes completados asociados con una entrada por lotes en el **estado del lote** de informes, haga clic en la entrada y, a continuación, haga clic en **lotes completados**.</span><span class="sxs-lookup"><span data-stu-id="5b015-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
    3.  <span data-ttu-id="5b015-139">Para mostrar datos de un intercambio por lotes completado, haga clic en el intercambio en el **lote completado** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**.</span><span class="sxs-lookup"><span data-stu-id="5b015-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="5b015-140">La entrada del intercambio procesado por lotes se resaltará en el informe Estado de la confirmación y del intercambio.</span><span class="sxs-lookup"><span data-stu-id="5b015-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5.  <span data-ttu-id="5b015-141">Para mostrar la **informe de agregación de intercambio**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b015-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="5b015-142">Haga clic en **informe de agregación de intercambio** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b015-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6.  <span data-ttu-id="5b015-143">Para mostrar la **informe de agregación de conjunto de transacciones**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b015-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="5b015-144">Haga clic en **informe de agregación de conjunto de transacciones** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b015-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7.  <span data-ttu-id="5b015-145">Para mostrar la **mensaje AS2 y estado de MDN correlacionado** de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b015-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="5b015-146">Haga clic en **mensaje AS2 y estado de MDN correlacionado** en el **informes de estado de EDIINT** área no cliente de la **concentrador de grupo** ficha.</span><span class="sxs-lookup"><span data-stu-id="5b015-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="5b015-147">Para mostrar el estado del intercambio EDI en un mensaje AS2, haga clic en una entrada en el **mensaje AS2 y estado de MDN correlacionado** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**.</span><span class="sxs-lookup"><span data-stu-id="5b015-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b015-148">Para obtener más información sobre cómo se correlacionan los Estados EDI y estado de AS2, vea la sección "Correlacionar un mensaje de AS2 con la carga de la EDI" de [mensaje AS2 y el informe de estado de MDN correlacionado](../core/as2-message-and-correlated-mdn-status-report.md).</span><span class="sxs-lookup"><span data-stu-id="5b015-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
    3.  <span data-ttu-id="5b015-149">Para ver un mensaje AS2 en su formato, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **formato del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="5b015-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
    4.  <span data-ttu-id="5b015-150">Para mostrar un mensaje AS2 en formato descodificado, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **formato de mensaje descodificado**.</span><span class="sxs-lookup"><span data-stu-id="5b015-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
    5.  <span data-ttu-id="5b015-151">Para mostrar un mensaje MDN, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **mensaje Mdn**.</span><span class="sxs-lookup"><span data-stu-id="5b015-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b015-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b015-152">See Also</span></span>  
 <span data-ttu-id="5b015-153">[Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="5b015-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="5b015-154">[EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="5b015-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="5b015-155">[Habilitar informes de estado de AS2 y EDI](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="5b015-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="5b015-156">Configurar un informe de estado de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="5b015-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)
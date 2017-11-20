---
title: "Intercambio EDI y el informe de estado de confirmación correlacionado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5f4268badf9907eb90b090abe34a8355b3ab8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="f6ed1-102">Informe Intercambio EDI y estado de confirmación correlacionado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="f6ed1-103">Este informe muestra todos los intercambios EDI procesados por las canalizaciones de envío y recepción EDI, así como la confirmación correlacionada con dichos intercambios.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="f6ed1-104">Campos del informe de estado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="f6ed1-105">El informe Intercambio EDI y estado de confirmación correlacionado muestra la siguiente información relativa a los intercambios enviados o recibidos y a las confirmaciones correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
-   <span data-ttu-id="f6ed1-106">Entidad del remitente.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-106">Sender Party</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6ed1-107">La entidad del remitente se determinará de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-107">The sender party will be determined as follows:</span></span>  
    >   
    >  -   <span data-ttu-id="f6ed1-108">Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
    > -   <span data-ttu-id="f6ed1-109">Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
-   <span data-ttu-id="f6ed1-110">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="f6ed1-110">Receiver Party</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6ed1-111">El nombre de la entidad receptora se determinará de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-111">The receiver party name will be determined as follows:</span></span>  
    >   
    >  -   <span data-ttu-id="f6ed1-112">Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
    > -   <span data-ttu-id="f6ed1-113">Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
-   <span data-ttu-id="f6ed1-114">Id. de control</span><span class="sxs-lookup"><span data-stu-id="f6ed1-114">Control ID</span></span>  
  
-   <span data-ttu-id="f6ed1-115">Dirección</span><span class="sxs-lookup"><span data-stu-id="f6ed1-115">Direction</span></span>  
  
-   <span data-ttu-id="f6ed1-116">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="f6ed1-116">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="f6ed1-117">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="f6ed1-117">EDI encoding type</span></span>  
  
-   <span data-ttu-id="f6ed1-118">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="f6ed1-118">Interchange Status</span></span>  
  
-   <span data-ttu-id="f6ed1-119">Recuento de grupo</span><span class="sxs-lookup"><span data-stu-id="f6ed1-119">Group Count</span></span>  
  
-   <span data-ttu-id="f6ed1-120">Id. de puerto</span><span class="sxs-lookup"><span data-stu-id="f6ed1-120">Port ID</span></span>  
  
-   <span data-ttu-id="f6ed1-121">Alias de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="f6ed1-121">Sender Party Alias</span></span>  
  
-   <span data-ttu-id="f6ed1-122">Alias de entidad receptora</span><span class="sxs-lookup"><span data-stu-id="f6ed1-122">Receiver Party Alias</span></span>  
  
-   <span data-ttu-id="f6ed1-123">Identificador de correlación del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="f6ed1-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="f6ed1-124">Campos de Expresión de consulta para el informe de estado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="f6ed1-125">Para personalizar el informe Intercambio EDI y estado de confirmación correlacionado, cambie los campos de la expresión de consulta que determina los datos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="f6ed1-126">Están disponibles los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f6ed1-127">Campo Expresión de consulta</span><span class="sxs-lookup"><span data-stu-id="f6ed1-127">Query Expression Field</span></span>|<span data-ttu-id="f6ed1-128">Operadores potenciales</span><span class="sxs-lookup"><span data-stu-id="f6ed1-128">Potential Operators</span></span>|<span data-ttu-id="f6ed1-129">Valores potenciales</span><span class="sxs-lookup"><span data-stu-id="f6ed1-129">Potential Values</span></span>|<span data-ttu-id="f6ed1-130">¿Incluido de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="f6ed1-130">Included By Default?</span></span>|  
|<span data-ttu-id="f6ed1-131">Buscar</span><span class="sxs-lookup"><span data-stu-id="f6ed1-131">Search for</span></span>|<span data-ttu-id="f6ed1-132">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-132">Equals</span></span>|<span data-ttu-id="f6ed1-133">Estado de la confirmación y del intercambio</span><span class="sxs-lookup"><span data-stu-id="f6ed1-133">Interchange/ACK Status</span></span>|<span data-ttu-id="f6ed1-134">Sí (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-134">Yes (required)</span></span>|  
|<span data-ttu-id="f6ed1-135">Estado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-135">Status</span></span>|<span data-ttu-id="f6ed1-136">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-136">Equals</span></span><br /><br /> <span data-ttu-id="f6ed1-137">No es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-137">Not Equals</span></span>|<span data-ttu-id="f6ed1-138">Aceptado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-138">Accepted</span></span><br /><br /> <span data-ttu-id="f6ed1-139">Aceptado con errores</span><span class="sxs-lookup"><span data-stu-id="f6ed1-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="f6ed1-140">Enviado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-140">Sent</span></span><br /><br /> <span data-ttu-id="f6ed1-141">Todos</span><span class="sxs-lookup"><span data-stu-id="f6ed1-141">All</span></span><br /><br /> <span data-ttu-id="f6ed1-142">Confirmación esperada</span><span class="sxs-lookup"><span data-stu-id="f6ed1-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="f6ed1-143">Confirmación inesperada</span><span class="sxs-lookup"><span data-stu-id="f6ed1-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="f6ed1-144">Rechazado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-144">Rejected</span></span><br /><br /> <span data-ttu-id="f6ed1-145">(Estos valores se definen a continuación.)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-145">(These values are defined below.)</span></span>|<span data-ttu-id="f6ed1-146">Sí</span><span class="sxs-lookup"><span data-stu-id="f6ed1-146">Yes</span></span>|  
|<span data-ttu-id="f6ed1-147">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="f6ed1-147">Interchange Date Time</span></span>|<span data-ttu-id="f6ed1-148">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="f6ed1-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="f6ed1-149">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="f6ed1-149">Greater Than or Equals</span></span>|<span data-ttu-id="f6ed1-150">Fecha y hora específica</span><span class="sxs-lookup"><span data-stu-id="f6ed1-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="f6ed1-151">Hoy</span><span class="sxs-lookup"><span data-stu-id="f6ed1-151">Today</span></span><br /><br /> <span data-ttu-id="f6ed1-152">Hoy - 1</span><span class="sxs-lookup"><span data-stu-id="f6ed1-152">Today - 1</span></span>|<span data-ttu-id="f6ed1-153">Sí</span><span class="sxs-lookup"><span data-stu-id="f6ed1-153">Yes</span></span><br /><br /> <span data-ttu-id="f6ed1-154">Nota: se puede incluir más de una vez en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="f6ed1-155">N.º máximo de coincidencias</span><span class="sxs-lookup"><span data-stu-id="f6ed1-155">Maximum Matches</span></span>|<span data-ttu-id="f6ed1-156">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-156">Equals</span></span>|<span data-ttu-id="f6ed1-157">Entero (predeterminado de 50)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-157">Integer (default of 50)</span></span>|<span data-ttu-id="f6ed1-158">Sí</span><span class="sxs-lookup"><span data-stu-id="f6ed1-158">Yes</span></span>|  
|<span data-ttu-id="f6ed1-159">Id. de control</span><span class="sxs-lookup"><span data-stu-id="f6ed1-159">Control ID</span></span>|<span data-ttu-id="f6ed1-160">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-160">Equals</span></span>|<span data-ttu-id="f6ed1-161">Id. de control de intercambio</span><span class="sxs-lookup"><span data-stu-id="f6ed1-161">Interchange Control ID</span></span>|<span data-ttu-id="f6ed1-162">No</span><span class="sxs-lookup"><span data-stu-id="f6ed1-162">No</span></span>|  
|<span data-ttu-id="f6ed1-163">Dirección</span><span class="sxs-lookup"><span data-stu-id="f6ed1-163">Direction</span></span>|<span data-ttu-id="f6ed1-164">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-164">Equals</span></span>|<span data-ttu-id="f6ed1-165">All (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-165">All (default)</span></span><br /><br /> <span data-ttu-id="f6ed1-166">Receive</span><span class="sxs-lookup"><span data-stu-id="f6ed1-166">Receive</span></span><br /><br /> <span data-ttu-id="f6ed1-167">Send</span><span class="sxs-lookup"><span data-stu-id="f6ed1-167">Send</span></span>|<span data-ttu-id="f6ed1-168">No</span><span class="sxs-lookup"><span data-stu-id="f6ed1-168">No</span></span>|  
|<span data-ttu-id="f6ed1-169">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="f6ed1-169">Receiver Party</span></span>|<span data-ttu-id="f6ed1-170">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-170">Equals</span></span>|<span data-ttu-id="f6ed1-171">All (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-171">All (default)</span></span><br /><br /> <span data-ttu-id="f6ed1-172">Nombre de entidad específico</span><span class="sxs-lookup"><span data-stu-id="f6ed1-172">Specific party name</span></span>|<span data-ttu-id="f6ed1-173">No</span><span class="sxs-lookup"><span data-stu-id="f6ed1-173">No</span></span>|  
|<span data-ttu-id="f6ed1-174">Entidad del remitente.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-174">Sender Party</span></span>|<span data-ttu-id="f6ed1-175">Es igual a</span><span class="sxs-lookup"><span data-stu-id="f6ed1-175">Equals</span></span>|<span data-ttu-id="f6ed1-176">All (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f6ed1-176">All (default)</span></span><br /><br /> <span data-ttu-id="f6ed1-177">Nombre de entidad específico</span><span class="sxs-lookup"><span data-stu-id="f6ed1-177">Specific party name</span></span>|<span data-ttu-id="f6ed1-178">No</span><span class="sxs-lookup"><span data-stu-id="f6ed1-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="f6ed1-179">Definiciones de estado</span><span class="sxs-lookup"><span data-stu-id="f6ed1-179">Status Definitions</span></span>  
 <span data-ttu-id="f6ed1-180">Los valores de estado empleados en los informes de estado EDI tienen las definiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
-   <span data-ttu-id="f6ed1-181">Aceptado: intercambio válido</span><span class="sxs-lookup"><span data-stu-id="f6ed1-181">Accepted: Valid interchange</span></span>  
  
-   <span data-ttu-id="f6ed1-182">Aceptado con errores: se han registrado los errores en los segmentos</span><span class="sxs-lookup"><span data-stu-id="f6ed1-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
-   <span data-ttu-id="f6ed1-183">Enviado: el intercambio se envió correctamente</span><span class="sxs-lookup"><span data-stu-id="f6ed1-183">Sent: The interchange was sent successfully</span></span>  
  
-   <span data-ttu-id="f6ed1-184">Todo: mostrar un mensaje con cualquiera de los demás valores</span><span class="sxs-lookup"><span data-stu-id="f6ed1-184">All: Display a message with any of the other values</span></span>  
  
-   <span data-ttu-id="f6ed1-185">Confirmación esperada</span><span class="sxs-lookup"><span data-stu-id="f6ed1-185">Ack Expected</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6ed1-186">El campo Estado de intercambio del informe de estado Detalles de la confirmación y del estado del intercambio se establecerá como "Confirmación esperada" para un mensaje saliente al enviarlo si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] espera una confirmación técnica.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="f6ed1-187">Esto ocurre si el **TA1 esperado** propiedad se establece en **confirmaciones** página de la ficha de acuerdo unidireccional. El estado cambiará a "Aceptado" cuando se haya recibido y validado la confirmación técnica.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="f6ed1-188">Tenga en cuenta que esto solo sucede en el caso de una confirmación técnica, no de una confirmación funcional.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
-   <span data-ttu-id="f6ed1-189">Confirmación inesperada</span><span class="sxs-lookup"><span data-stu-id="f6ed1-189">Ack Not Expected</span></span>  
  
-   <span data-ttu-id="f6ed1-190">Rechazado: el intercambio no era válido debido a los errores.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="f6ed1-191">Otros informes mostrados desde este informe</span><span class="sxs-lookup"><span data-stu-id="f6ed1-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="f6ed1-192">Puede mostrar los siguientes informes de estado adicionales para un conjunto de transacciones mostrado en el informe Detalles de conjunto de transacciones:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="f6ed1-193">Para obtener acceso a los informes, haga clic con el botón secundario en un intercambio o una confirmación enumerados en el informe Intercambio EDI y estado de confirmación correlacionado y, a continuación, haga clic en el comando adecuado:</span><span class="sxs-lookup"><span data-stu-id="f6ed1-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="f6ed1-194">Estado de intercambio y el informe de estado de detalles de confirmación</span><span class="sxs-lookup"><span data-stu-id="f6ed1-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="f6ed1-195">Informe de estado de detalles de conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="f6ed1-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="f6ed1-196">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f6ed1-196">Next steps</span></span>
  
-   [<span data-ttu-id="f6ed1-197">Estado de intercambio y el informe de estado de detalles de confirmación</span><span class="sxs-lookup"><span data-stu-id="f6ed1-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="f6ed1-198">Informe de estado de detalles de conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="f6ed1-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="f6ed1-199">Informe de estado del contenido del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="f6ed1-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  

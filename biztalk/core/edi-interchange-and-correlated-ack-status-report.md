---
title: Intercambio EDI y el informe de estado de confirmación correlacionado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a94eeb97b731f38d5785ab733d50d0edaa1a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982941"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="e670b-102">Informe Intercambio EDI y estado de confirmación correlacionado</span><span class="sxs-lookup"><span data-stu-id="e670b-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="e670b-103">Este informe muestra todos los intercambios EDI procesados por las canalizaciones de envío y recepción EDI, así como la confirmación correlacionada con dichos intercambios.</span><span class="sxs-lookup"><span data-stu-id="e670b-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="e670b-104">Campos del informe de estado</span><span class="sxs-lookup"><span data-stu-id="e670b-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="e670b-105">El informe Intercambio EDI y estado de confirmación correlacionado muestra la siguiente información relativa a los intercambios enviados o recibidos y a las confirmaciones correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="e670b-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
- <span data-ttu-id="e670b-106">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="e670b-106">Sender Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e670b-107">La entidad del remitente se determinará de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="e670b-107">The sender party will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="e670b-108">Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.</span><span class="sxs-lookup"><span data-stu-id="e670b-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="e670b-109">Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e670b-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="e670b-110">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="e670b-110">Receiver Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e670b-111">El nombre de la entidad receptora se determinará de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="e670b-111">The receiver party name will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="e670b-112">Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.</span><span class="sxs-lookup"><span data-stu-id="e670b-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="e670b-113">Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e670b-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="e670b-114">Id. de control</span><span class="sxs-lookup"><span data-stu-id="e670b-114">Control ID</span></span>  
  
- <span data-ttu-id="e670b-115">Dirección</span><span class="sxs-lookup"><span data-stu-id="e670b-115">Direction</span></span>  
  
- <span data-ttu-id="e670b-116">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="e670b-116">Interchange Date Time</span></span>  
  
- <span data-ttu-id="e670b-117">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="e670b-117">EDI encoding type</span></span>  
  
- <span data-ttu-id="e670b-118">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="e670b-118">Interchange Status</span></span>  
  
- <span data-ttu-id="e670b-119">Número de grupos</span><span class="sxs-lookup"><span data-stu-id="e670b-119">Group Count</span></span>  
  
- <span data-ttu-id="e670b-120">Id. de puerto</span><span class="sxs-lookup"><span data-stu-id="e670b-120">Port ID</span></span>  
  
- <span data-ttu-id="e670b-121">Alias de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="e670b-121">Sender Party Alias</span></span>  
  
- <span data-ttu-id="e670b-122">Alias de entidad receptora</span><span class="sxs-lookup"><span data-stu-id="e670b-122">Receiver Party Alias</span></span>  
  
- <span data-ttu-id="e670b-123">Identificador de correlación del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="e670b-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="e670b-124">Campos de Expresión de consulta para el informe de estado</span><span class="sxs-lookup"><span data-stu-id="e670b-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="e670b-125">Para personalizar el informe Intercambio EDI y estado de confirmación correlacionado, cambie los campos de la expresión de consulta que determina los datos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="e670b-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="e670b-126">Están disponibles los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e670b-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="e670b-127">Campo Expresión de consulta</span><span class="sxs-lookup"><span data-stu-id="e670b-127">Query Expression Field</span></span>|<span data-ttu-id="e670b-128">Operadores potenciales</span><span class="sxs-lookup"><span data-stu-id="e670b-128">Potential Operators</span></span>|<span data-ttu-id="e670b-129">Valores potenciales</span><span class="sxs-lookup"><span data-stu-id="e670b-129">Potential Values</span></span>|<span data-ttu-id="e670b-130">¿Incluido de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="e670b-130">Included By Default?</span></span>|  
|<span data-ttu-id="e670b-131">Buscar</span><span class="sxs-lookup"><span data-stu-id="e670b-131">Search for</span></span>|<span data-ttu-id="e670b-132">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-132">Equals</span></span>|<span data-ttu-id="e670b-133">Estado de la confirmación y del intercambio</span><span class="sxs-lookup"><span data-stu-id="e670b-133">Interchange/ACK Status</span></span>|<span data-ttu-id="e670b-134">Sí (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e670b-134">Yes (required)</span></span>|  
|<span data-ttu-id="e670b-135">Estado</span><span class="sxs-lookup"><span data-stu-id="e670b-135">Status</span></span>|<span data-ttu-id="e670b-136">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-136">Equals</span></span><br /><br /> <span data-ttu-id="e670b-137">No es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-137">Not Equals</span></span>|<span data-ttu-id="e670b-138">Aceptado</span><span class="sxs-lookup"><span data-stu-id="e670b-138">Accepted</span></span><br /><br /> <span data-ttu-id="e670b-139">Aceptado con errores</span><span class="sxs-lookup"><span data-stu-id="e670b-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="e670b-140">Enviado</span><span class="sxs-lookup"><span data-stu-id="e670b-140">Sent</span></span><br /><br /> <span data-ttu-id="e670b-141">All</span><span class="sxs-lookup"><span data-stu-id="e670b-141">All</span></span><br /><br /> <span data-ttu-id="e670b-142">Confirmación esperada</span><span class="sxs-lookup"><span data-stu-id="e670b-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="e670b-143">Confirmación inesperada</span><span class="sxs-lookup"><span data-stu-id="e670b-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="e670b-144">Rechazado</span><span class="sxs-lookup"><span data-stu-id="e670b-144">Rejected</span></span><br /><br /> <span data-ttu-id="e670b-145">(Estos valores se definen a continuación.)</span><span class="sxs-lookup"><span data-stu-id="e670b-145">(These values are defined below.)</span></span>|<span data-ttu-id="e670b-146">Sí</span><span class="sxs-lookup"><span data-stu-id="e670b-146">Yes</span></span>|  
|<span data-ttu-id="e670b-147">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="e670b-147">Interchange Date Time</span></span>|<span data-ttu-id="e670b-148">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="e670b-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="e670b-149">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="e670b-149">Greater Than or Equals</span></span>|<span data-ttu-id="e670b-150">Fecha y hora específica</span><span class="sxs-lookup"><span data-stu-id="e670b-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="e670b-151">Hoy</span><span class="sxs-lookup"><span data-stu-id="e670b-151">Today</span></span><br /><br /> <span data-ttu-id="e670b-152">Hoy - 1</span><span class="sxs-lookup"><span data-stu-id="e670b-152">Today - 1</span></span>|<span data-ttu-id="e670b-153">Sí</span><span class="sxs-lookup"><span data-stu-id="e670b-153">Yes</span></span><br /><br /> <span data-ttu-id="e670b-154">Nota: se puede incluir más de una vez en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="e670b-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="e670b-155">N.º máximo de coincidencias</span><span class="sxs-lookup"><span data-stu-id="e670b-155">Maximum Matches</span></span>|<span data-ttu-id="e670b-156">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-156">Equals</span></span>|<span data-ttu-id="e670b-157">Entero (predeterminado de 50)</span><span class="sxs-lookup"><span data-stu-id="e670b-157">Integer (default of 50)</span></span>|<span data-ttu-id="e670b-158">Sí</span><span class="sxs-lookup"><span data-stu-id="e670b-158">Yes</span></span>|  
|<span data-ttu-id="e670b-159">Id. de control</span><span class="sxs-lookup"><span data-stu-id="e670b-159">Control ID</span></span>|<span data-ttu-id="e670b-160">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-160">Equals</span></span>|<span data-ttu-id="e670b-161">Id. de control de intercambio</span><span class="sxs-lookup"><span data-stu-id="e670b-161">Interchange Control ID</span></span>|<span data-ttu-id="e670b-162">no</span><span class="sxs-lookup"><span data-stu-id="e670b-162">No</span></span>|  
|<span data-ttu-id="e670b-163">Dirección</span><span class="sxs-lookup"><span data-stu-id="e670b-163">Direction</span></span>|<span data-ttu-id="e670b-164">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-164">Equals</span></span>|<span data-ttu-id="e670b-165">Todos (opción predeterminada)</span><span class="sxs-lookup"><span data-stu-id="e670b-165">All (default)</span></span><br /><br /> <span data-ttu-id="e670b-166">Receive</span><span class="sxs-lookup"><span data-stu-id="e670b-166">Receive</span></span><br /><br /> <span data-ttu-id="e670b-167">Send</span><span class="sxs-lookup"><span data-stu-id="e670b-167">Send</span></span>|<span data-ttu-id="e670b-168">no</span><span class="sxs-lookup"><span data-stu-id="e670b-168">No</span></span>|  
|<span data-ttu-id="e670b-169">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="e670b-169">Receiver Party</span></span>|<span data-ttu-id="e670b-170">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-170">Equals</span></span>|<span data-ttu-id="e670b-171">Todos (opción predeterminada)</span><span class="sxs-lookup"><span data-stu-id="e670b-171">All (default)</span></span><br /><br /> <span data-ttu-id="e670b-172">Nombre de entidad específico</span><span class="sxs-lookup"><span data-stu-id="e670b-172">Specific party name</span></span>|<span data-ttu-id="e670b-173">no</span><span class="sxs-lookup"><span data-stu-id="e670b-173">No</span></span>|  
|<span data-ttu-id="e670b-174">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="e670b-174">Sender Party</span></span>|<span data-ttu-id="e670b-175">Es igual a</span><span class="sxs-lookup"><span data-stu-id="e670b-175">Equals</span></span>|<span data-ttu-id="e670b-176">Todos (opción predeterminada)</span><span class="sxs-lookup"><span data-stu-id="e670b-176">All (default)</span></span><br /><br /> <span data-ttu-id="e670b-177">Nombre de entidad específico</span><span class="sxs-lookup"><span data-stu-id="e670b-177">Specific party name</span></span>|<span data-ttu-id="e670b-178">no</span><span class="sxs-lookup"><span data-stu-id="e670b-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="e670b-179">Definiciones de estado</span><span class="sxs-lookup"><span data-stu-id="e670b-179">Status Definitions</span></span>  
 <span data-ttu-id="e670b-180">Los valores de estado empleados en los informes de estado EDI tienen las definiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e670b-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
- <span data-ttu-id="e670b-181">Aceptado: intercambio válido</span><span class="sxs-lookup"><span data-stu-id="e670b-181">Accepted: Valid interchange</span></span>  
  
- <span data-ttu-id="e670b-182">Aceptado con errores: se han registrado los errores en los segmentos</span><span class="sxs-lookup"><span data-stu-id="e670b-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
- <span data-ttu-id="e670b-183">Enviado: el intercambio se envió correctamente</span><span class="sxs-lookup"><span data-stu-id="e670b-183">Sent: The interchange was sent successfully</span></span>  
  
- <span data-ttu-id="e670b-184">Todo: mostrar un mensaje con cualquiera de los demás valores</span><span class="sxs-lookup"><span data-stu-id="e670b-184">All: Display a message with any of the other values</span></span>  
  
- <span data-ttu-id="e670b-185">Confirmación esperada</span><span class="sxs-lookup"><span data-stu-id="e670b-185">Ack Expected</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e670b-186">El campo Estado de intercambio del informe de estado Detalles de la confirmación y del estado del intercambio se establecerá como "Confirmación esperada" para un mensaje saliente al enviarlo si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] espera una confirmación técnica.</span><span class="sxs-lookup"><span data-stu-id="e670b-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="e670b-187">Esto se produce si el **TA1 esperado** propiedad está establecida **confirmaciones** página de la pestaña del acuerdo unidireccional. El estado cambiará a "Aceptado" cuando se haya recibido y validado la confirmación técnica.</span><span class="sxs-lookup"><span data-stu-id="e670b-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="e670b-188">Tenga en cuenta que esto solo sucede en el caso de una confirmación técnica, no de una confirmación funcional.</span><span class="sxs-lookup"><span data-stu-id="e670b-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
- <span data-ttu-id="e670b-189">Confirmación inesperada</span><span class="sxs-lookup"><span data-stu-id="e670b-189">Ack Not Expected</span></span>  
  
- <span data-ttu-id="e670b-190">Rechazado: el intercambio no era válido debido a los errores.</span><span class="sxs-lookup"><span data-stu-id="e670b-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="e670b-191">Otros informes mostrados desde este informe</span><span class="sxs-lookup"><span data-stu-id="e670b-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="e670b-192">Puede mostrar los siguientes informes de estado adicionales para un conjunto de transacciones mostrado en el informe Detalles de conjunto de transacciones:</span><span class="sxs-lookup"><span data-stu-id="e670b-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="e670b-193">Para obtener acceso a los informes, haga clic con el botón secundario en un intercambio o una confirmación enumerados en el informe Intercambio EDI y estado de confirmación correlacionado y, a continuación, haga clic en el comando adecuado:</span><span class="sxs-lookup"><span data-stu-id="e670b-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="e670b-194">Detalles de la confirmación y del estado del intercambio (informe de estado)</span><span class="sxs-lookup"><span data-stu-id="e670b-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="e670b-195">Informe de estado de detalles del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="e670b-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="e670b-196">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e670b-196">Next steps</span></span>
  
-   [<span data-ttu-id="e670b-197">Detalles de la confirmación y del estado del intercambio (informe de estado)</span><span class="sxs-lookup"><span data-stu-id="e670b-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="e670b-198">Informe de estado de detalles del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="e670b-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="e670b-199">Informe de estado del contenido del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="e670b-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  

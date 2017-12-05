---
title: "Cómo se almacenan los datos para los mensajes EDI entrantes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8cbcb96-c0af-4f41-b844-f0e684a4af7c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a395e691835f3e21622ebf5f29c2845361fb36
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-data-is-stored-for-inbound-edi-messages"></a><span data-ttu-id="f7304-102">Cómo se almacenan los datos correspondientes a mensajes EDI de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-102">How Data Is Stored for Inbound EDI Messages</span></span>
<span data-ttu-id="f7304-103">Para generar una entrada del informe de estado correspondiente a un intercambio de entrada y a la confirmación enviada como respuesta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7304-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does the following to generate a status report entry for an inbound interchange and the acknowledgment sent in response to it:</span></span>  
  
1.  <span data-ttu-id="f7304-104">Cuando la canalización de recepción EDI envía el XML del mensaje de entrada al cuadro de mensajes, esta canalización crea las siguientes entradas en el almacén de datos de informes de estado con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7304-104">When inbound message XML is sent by the EDI receive pipeline to the MessageBox, the receive pipeline creates the following entries in the status reporting data store with the following values:</span></span>  
  
    -   <span data-ttu-id="f7304-105">Una entrada de informe de estado por cada intercambio recibido, cuyo estado se establece como Aceptado/Parcialmente aceptado/Rechazado</span><span class="sxs-lookup"><span data-stu-id="f7304-105">One status report entry for each interchange received, with Status set to Accepted/Partially Accepted/Rejected</span></span>  
  
    -   <span data-ttu-id="f7304-106">Una entrada de informe de estado por cada confirmación técnica (intercambio), una por intercambio, cuyo estado se establece como Generado</span><span class="sxs-lookup"><span data-stu-id="f7304-106">One status report entry for each technical (interchange) acknowledgment, one per interchange, with Status set to Generated</span></span>  
  
    -   <span data-ttu-id="f7304-107">Una entrada de informe de estado por cada confirmación funcional, una por grupo en X12 y una para todos los grupos en EDIFACT, cuyo estado se establece como Generado.</span><span class="sxs-lookup"><span data-stu-id="f7304-107">One status report entry for each functional acknowledgment, one per group in X12 and one for all groups in EDIFACT, with Status set to Generated.</span></span>  
  
2.  <span data-ttu-id="f7304-108">Una vez que la canalización de envío haya enviado las confirmaciones al socio comercial, la canalización de envío EDI actualiza las entradas de estado de confirmación de intercambio y de estado de confirmación funcional a Enviado, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f7304-108">After the send pipeline has sent the acknowledgments to the trading partner, the EDI send pipeline updates the Interchange ACK status and Functional ACK status entries to Sent, as appropriate.</span></span> <span data-ttu-id="f7304-109">No se realizan cambios en la entrada de estado del intercambio.</span><span class="sxs-lookup"><span data-stu-id="f7304-109">No changes are made to the Interchange status entry.</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-inbound-interchanges"></a><span data-ttu-id="f7304-110">Datos almacenados por la canalización de recepción correspondientes a los intercambios de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-110">Data Stored by the Receive Pipeline for Inbound Interchanges</span></span>  
 <span data-ttu-id="f7304-111">La canalización de recepción crea un registro en el almacén de datos de informes de estado para cada intercambio que recibe.</span><span class="sxs-lookup"><span data-stu-id="f7304-111">The receive pipeline creates a record in the status report data store for each interchange that it receives.</span></span> <span data-ttu-id="f7304-112">Los datos almacenados incluyen:</span><span class="sxs-lookup"><span data-stu-id="f7304-112">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f7304-113">Tipo de registro = Estado de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-113">Record Type = Interchange Status</span></span>  
  
-   <span data-ttu-id="f7304-114">Dirección de intercambio = Recepción</span><span class="sxs-lookup"><span data-stu-id="f7304-114">Interchange Direction = Receive</span></span>  
  
-   <span data-ttu-id="f7304-115">Receptor del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-115">Interchange Receiver = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-116">Remitente del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-116">Interchange Sender = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-117">Fecha del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-117">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-118">Hora del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-118">Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-119">Id. de control de intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-119">Interchange Control ID = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-120">Estado del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-120">Interchange Status: Update Data</span></span>  
  
-   <span data-ttu-id="f7304-121">Número de grupos en el intercambio = Datos actualizados (En EDIFACT los grupos son opcionales; si no se encuentran, el valor es "No aplicable”)</span><span class="sxs-lookup"><span data-stu-id="f7304-121">Count of Groups in Interchange = Update Data (In EDIFACT Groups are optional and if not present, valued as ‘Not Applicable’)</span></span>  
  
-   <span data-ttu-id="f7304-122">Id. del puerto de recepción del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-122">Interchange Receive Port ID = Update Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-technical-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="f7304-123">Datos almacenados por la canalización de recepción correspondientes a cada confirmación técnica generada en respuesta a un intercambio de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-123">Data Stored by the Receive Pipeline for Each Technical Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="f7304-124">La canalización de envío crea un registro en el almacén de datos de informes de estado para cada confirmación técnica que envía.</span><span class="sxs-lookup"><span data-stu-id="f7304-124">The send pipeline creates a record in the status report data store for each technical acknowledgment that it sends.</span></span> <span data-ttu-id="f7304-125">La confirmación técnica es TA1 para X12 y el mensaje CONTRL con solo el segmento UCI para EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="f7304-125">The technical acknowledgement is the TA1 for X12 and the CONTRL message with only the UCI Segment for EDIFACT.</span></span> <span data-ttu-id="f7304-126">La mayoría de los datos necesarios para la entrada están disponibles a partir de los segmentos de encabezado y finalizador del intercambio (ISA/IEA o UNB/UNZ).</span><span class="sxs-lookup"><span data-stu-id="f7304-126">Most data required for the entry is available from the interchange header/trailer segments (ISA/IEA or UNB/UNZ).</span></span> <span data-ttu-id="f7304-127">Otros datos están disponibles a partir de las propiedades del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f7304-127">Other data is available from send port properties.</span></span> <span data-ttu-id="f7304-128">Los datos almacenados incluyen:</span><span class="sxs-lookup"><span data-stu-id="f7304-128">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f7304-129">Tipo de registro = Estado de confirmación del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-129">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="f7304-130">Dirección de confirmación del intercambio = Recepción</span><span class="sxs-lookup"><span data-stu-id="f7304-130">Interchange ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="f7304-131">Receptor del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-131">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-132">Remitente del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-132">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-133">Fecha del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-133">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-134">Id. de control del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-134">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-135">Estado de confirmación del intercambio = \< esperado o no aplicable\>.</span><span class="sxs-lookup"><span data-stu-id="f7304-135">Interchange ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="f7304-136">Si la confirmación técnica está configurada o tiene un valor asignado en el intercambio de entrada, el estado es Esperado.</span><span class="sxs-lookup"><span data-stu-id="f7304-136">If the technical ACK is configured or valued in the incoming interchange, status = Expected.</span></span> <span data-ttu-id="f7304-137">En caso contrario, el estado es No aplicable.</span><span class="sxs-lookup"><span data-stu-id="f7304-137">Otherwise, status = Not Applicable.</span></span>  
  
-   <span data-ttu-id="f7304-138">Id. de Control de confirmación del intercambio = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-138">Interchange ACK Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-139">Fecha de confirmación del intercambio = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-139">Interchange ACK Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-140">Hora de confirmación del intercambio = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-140">Interchange ACK Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-141">Código de confirmación/acción = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-141">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-142">Código de nota de confirmación = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-142">ACK Note Code = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-technical-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="f7304-143">Datos actualizados por la canalización de envío correspondientes a cada confirmación técnica generada en respuesta a intercambios de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-143">Data Updated by the Send Pipeline for Each Technical Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="f7304-144">Para cada confirmación técnica que envía la canalización de envío, se actualiza la entrada del informe de estado correspondiente al intercambio recibido correlacionado.</span><span class="sxs-lookup"><span data-stu-id="f7304-144">For each technical acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="f7304-145">Los sobres de intercambio que la canalización de envío crea serán el origen de los datos.</span><span class="sxs-lookup"><span data-stu-id="f7304-145">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="f7304-146">El ensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos UCI y TA1 de la confirmación entrante, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f7304-146">The EDI Assembler locates records in the data store using data in the UCI and TA1 Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f7304-147">Campos en la confirmación</span><span class="sxs-lookup"><span data-stu-id="f7304-147">Fields in ACK</span></span>|<span data-ttu-id="f7304-148">Campos en el almacén de datos</span><span class="sxs-lookup"><span data-stu-id="f7304-148">Fields in Data store</span></span>|<span data-ttu-id="f7304-149">Comentario</span><span class="sxs-lookup"><span data-stu-id="f7304-149">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f7304-150">Id. del remitente del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-150">Interchange Sender ID</span></span>|<span data-ttu-id="f7304-151">Receptor del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-151">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="f7304-152">Id. del receptor del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-152">Interchange Receiver ID</span></span>|<span data-ttu-id="f7304-153">Remitente del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-153">Interchange Sender</span></span>|-|  
|-|<span data-ttu-id="f7304-154">Fecha de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-154">Interchange Date</span></span>|-|  
|<span data-ttu-id="f7304-155">Número de Control de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-155">Interchange Control Number</span></span>|<span data-ttu-id="f7304-156">Id. de control de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-156">Interchange Control ID</span></span>|-|  
|-|<span data-ttu-id="f7304-157">Dirección de intercambio = Recepción</span><span class="sxs-lookup"><span data-stu-id="f7304-157">Interchange Direction = Receive</span></span>|<span data-ttu-id="f7304-158">Necesario en el escenario de intercambio conservado para la unicidad</span><span class="sxs-lookup"><span data-stu-id="f7304-158">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="f7304-159">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="f7304-159">Record Type</span></span>|<span data-ttu-id="f7304-160">Estado de confirmación del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-160">Interchange ACK Status</span></span>|-|  
  
 <span data-ttu-id="f7304-161">Los datos almacenados incluyen:</span><span class="sxs-lookup"><span data-stu-id="f7304-161">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f7304-162">Tipo de registro = Estado de confirmación del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-162">Record Type = Interchange ACK Status</span></span>  
  
-   <span data-ttu-id="f7304-163">Dirección de confirmación del intercambio = Envío – Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-163">Interchange ACK Direction = Send- Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-164">Estado de confirmación del intercambio = Procesado o Enviado – Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-164">Interchange ACK Status = Processed or Sent – Update Data</span></span>  
  
-   <span data-ttu-id="f7304-165">Receptor del intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-165">Interchange Receiver = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-166">Remitente del intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-166">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-167">Fecha del intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-167">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-168">Id. de control de intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-168">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-169">Id. de control de confirmación del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-169">Interchange ACK Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f7304-170">Fecha de confirmación del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-170">Interchange ACK Date = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-171">Hora de confirmación del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-171">Interchange ACK Time = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-172">Código de acción o confirmación = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-172">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-173">Código de nota de confirmación = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-173">ACK Note Code = Existing Data</span></span>  
  
## <a name="data-stored-by-the-receive-pipeline-for-each-functional-acknowledgment-generated-in-response-to-an-inbound-interchange"></a><span data-ttu-id="f7304-174">Datos almacenados por la canalización de recepción correspondientes a cada confirmación funcional generada en respuesta a un intercambio de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-174">Data Stored by the Receive Pipeline for Each Functional Acknowledgment Generated in Response to an Inbound Interchange</span></span>  
 <span data-ttu-id="f7304-175">La canalización de envío crea un registro en el almacén de datos de informes de estado para cada confirmación funcional que envía.</span><span class="sxs-lookup"><span data-stu-id="f7304-175">The send pipeline creates a record in the status report data store for each functional acknowledgment that it sends.</span></span> <span data-ttu-id="f7304-176">La canalización de envío crea un registro de cada confirmación funcional enviada (como respuesta a un intercambio recibido) en el almacén de datos de informes de estado.</span><span class="sxs-lookup"><span data-stu-id="f7304-176">The send pipeline creates a record of each functional acknowledgment sent (in response to an interchange received) in the status report data store.</span></span> <span data-ttu-id="f7304-177">Si no se encuentra ningún grupo en EDIFACT, se creará aún así una confirmación funcional.</span><span class="sxs-lookup"><span data-stu-id="f7304-177">If no group is present in EDIFACT, one functional ACK will still be created.</span></span> <span data-ttu-id="f7304-178">La entrada del informe de estado de confirmación funcional se rellenará a partir del encabezado o el finalizador del grupo funcional (GS/GE o UNG/UNE).</span><span class="sxs-lookup"><span data-stu-id="f7304-178">The functional ACK status report entry will be populated from the functional group header/trailer (GS/GE or UNG/UNE).</span></span> <span data-ttu-id="f7304-179">La confirmación técnica es 997 para X12 y el mensaje CONTRL completo para EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="f7304-179">The technical acknowledge is the 997 for X12 and the full CONTRL message for EDIFACT.</span></span> <span data-ttu-id="f7304-180">Los datos almacenados incluyen:</span><span class="sxs-lookup"><span data-stu-id="f7304-180">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f7304-181">Tipo de registro = Estado de la confirmación funcional</span><span class="sxs-lookup"><span data-stu-id="f7304-181">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f7304-182">Dirección de confirmación funcional = Recepción</span><span class="sxs-lookup"><span data-stu-id="f7304-182">Functional ACK Direction = Receive</span></span>  
  
-   <span data-ttu-id="f7304-183">Estado de confirmación funcional = \< esperado o no aplicable\>.</span><span class="sxs-lookup"><span data-stu-id="f7304-183">Functional ACK Status = \< Expected or Not Applicable\>.</span></span> <span data-ttu-id="f7304-184">Si la ficha de confirmación funcional en PAM está seleccionada, el estado se establecerá como Esperado.</span><span class="sxs-lookup"><span data-stu-id="f7304-184">If the functional acknowledgment tab in PAM is selected, status will set to Expected.</span></span> <span data-ttu-id="f7304-185">En caso contrario, el estado se establecerá como No aplicable.</span><span class="sxs-lookup"><span data-stu-id="f7304-185">Otherwise, status will be set to Not Applicable.</span></span>  
  
-   <span data-ttu-id="f7304-186">Receptor del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-186">Interchange Receiver = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-187">Remitente del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-187">Interchange Sender = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-188">Fecha del intercambio = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-188">Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-189">Id. de control del intercambio = Datos actualizados (necesarios para la correlación)</span><span class="sxs-lookup"><span data-stu-id="f7304-189">Interchange Control ID = Update Data (required for correlation)</span></span>  
  
-   <span data-ttu-id="f7304-190">Número de control de grupo = Datos actualizados (necesarios para la correlación.</span><span class="sxs-lookup"><span data-stu-id="f7304-190">Group Control Number = Update Data (required for correlation.</span></span> <span data-ttu-id="f7304-191">En EDIFACT si no se encuentran segmentos de grupo, el valor de este campo se asigna mediante UNH.1)</span><span class="sxs-lookup"><span data-stu-id="f7304-191">In EDIFACT if no group segments present this field is valued using UNH.1)</span></span>  
  
-   <span data-ttu-id="f7304-192">Código de Id. funcional = Datos actualizados (sin valor en EDIFACT cuando no se encuentra un grupo)</span><span class="sxs-lookup"><span data-stu-id="f7304-192">Functional ID Code = Update Data (not valued in EDIFACT if group is not present)</span></span>  
  
-   <span data-ttu-id="f7304-193">Número de conjuntos de transacciones = Datos (en EDIFACT esto se asigna a UNE.1 cuando se encuentran UNG/UNE o a UNZ.1 en caso de que no se encuentren segmentos de grupo)</span><span class="sxs-lookup"><span data-stu-id="f7304-193">Count of Transaction Sets = Data (in EDIFACT this is mapped to UNE.1 while UNG/UNE are present or UNZ.1 if no group segments are present)</span></span>  
  
-   <span data-ttu-id="f7304-194">Identificador de Control de intercambio de confirmación funcional = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-194">Functional ACK Interchange Control ID= \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-195">Fecha de intercambio de confirmación funcional = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-195">Functional ACK Interchange Date = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-196">Hora de intercambio de confirmación funcional = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-196">Functional ACK Interchange Time = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-197">Número de conjuntos de transacciones entregados = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-197">Count of Transaction Sets Delivered = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-198">Número de conjuntos de transacciones aceptados = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-198">Count of Transaction Sets Accepted = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-199">Código de confirmación/acción = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-199">ACK/Action Code = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-200">Código de Error de sintaxis/error = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-200">Error/Syntax Error Code  = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-201">Adicionales X12 código de Error de confirmación 2 = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-201">Additional X12 ACK Error Code 2 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-202">X12 adicionales 3 de código de Error de confirmación = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-202">Additional X12 ACK Error Code 3 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-203">X12 adicionales 4 de código de Error de confirmación = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-203">Additional X12 ACK Error Code 4 = \<not valued\></span></span>  
  
-   <span data-ttu-id="f7304-204">X12 adicional 5 de código de Error de confirmación = \<sin valor\></span><span class="sxs-lookup"><span data-stu-id="f7304-204">Additional X12 ACK Error Code 5 = \<not valued\></span></span>  
  
## <a name="data-updated-by-the-send-pipeline-for-each-functional-acknowledgment-generated-in-response-to-inbound-interchanges"></a><span data-ttu-id="f7304-205">Datos actualizados por la canalización de envío correspondientes a cada confirmación funcional generada en respuesta a intercambios de entrada</span><span class="sxs-lookup"><span data-stu-id="f7304-205">Data Updated by the Send Pipeline for Each Functional Acknowledgment Generated in Response to Inbound Interchanges</span></span>  
 <span data-ttu-id="f7304-206">Para cada confirmación funcional que envía la canalización de envío, se actualiza la entrada del informe de estado correspondiente al intercambio recibido correlacionado.</span><span class="sxs-lookup"><span data-stu-id="f7304-206">For each functional acknowledgment that the send pipeline sends, it updates the status report entry for the correlated received interchange.</span></span> <span data-ttu-id="f7304-207">Los sobres de intercambio que la canalización de envío crea serán el origen de los datos.</span><span class="sxs-lookup"><span data-stu-id="f7304-207">The source for the data will be the Interchange envelopes created by the Send Pipeline.</span></span>  
  
 <span data-ttu-id="f7304-208">El ensamblador EDI localiza los registros en el almacén de datos mediante los datos que figuran en los segmentos de intercambio y de encabezado de grupo de la confirmación entrante, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f7304-208">The EDI Assembler locates records in the data store using data in the Interchange and Group Header Segments of the incoming acknowledgment, as follows:</span></span>  
  
|<span data-ttu-id="f7304-209">Campos en la confirmación</span><span class="sxs-lookup"><span data-stu-id="f7304-209">Fields in ACK</span></span>|<span data-ttu-id="f7304-210">Campos en el almacén de datos</span><span class="sxs-lookup"><span data-stu-id="f7304-210">Fields in Data store</span></span>|<span data-ttu-id="f7304-211">Comentario</span><span class="sxs-lookup"><span data-stu-id="f7304-211">Comment</span></span>|  
|-------------------|--------------------------|-------------|  
|<span data-ttu-id="f7304-212">Id. del remitente del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-212">Interchange Sender ID</span></span>|<span data-ttu-id="f7304-213">Receptor del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-213">Interchange Receiver</span></span>|-|  
|<span data-ttu-id="f7304-214">Id. del receptor del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-214">Interchange Receiver ID</span></span>|<span data-ttu-id="f7304-215">Remitente del intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-215">Interchange Sender</span></span>|-|  
|<span data-ttu-id="f7304-216">Fecha de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-216">Interchange Date</span></span>|<span data-ttu-id="f7304-217">Fecha de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-217">Interchange Date</span></span>|-|  
|<span data-ttu-id="f7304-218">Número de Control de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-218">Interchange Control Number</span></span>|<span data-ttu-id="f7304-219">Id. de control de intercambio</span><span class="sxs-lookup"><span data-stu-id="f7304-219">Interchange Control ID</span></span>|-|  
|<span data-ttu-id="f7304-220">Número de control de grupo</span><span class="sxs-lookup"><span data-stu-id="f7304-220">Group Control Number</span></span>|<span data-ttu-id="f7304-221">Número de control de grupo</span><span class="sxs-lookup"><span data-stu-id="f7304-221">Group Control Number</span></span>|<span data-ttu-id="f7304-222">Opcional en EDIFACT</span><span class="sxs-lookup"><span data-stu-id="f7304-222">Optional in EDIFACT</span></span>|  
|-|<span data-ttu-id="f7304-223">Dirección de intercambio = Recepción</span><span class="sxs-lookup"><span data-stu-id="f7304-223">Interchange Direction = Receive</span></span>|<span data-ttu-id="f7304-224">Necesario en el escenario de intercambio conservado para la unicidad</span><span class="sxs-lookup"><span data-stu-id="f7304-224">Required in preserved interchange scenario for uniqueness</span></span>|  
|<span data-ttu-id="f7304-225">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="f7304-225">Record Type</span></span>|<span data-ttu-id="f7304-226">Estado de confirmación funcional</span><span class="sxs-lookup"><span data-stu-id="f7304-226">Functional ACK Status</span></span>|-|  
  
 <span data-ttu-id="f7304-227">Los datos almacenados incluyen:</span><span class="sxs-lookup"><span data-stu-id="f7304-227">The data stored includes:</span></span>  
  
-   <span data-ttu-id="f7304-228">Tipo de registro = Estado de la confirmación funcional</span><span class="sxs-lookup"><span data-stu-id="f7304-228">Record Type = Functional ACK Status</span></span>  
  
-   <span data-ttu-id="f7304-229">Dirección de confirmación funcional = Envío – Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-229">Functional ACK Direction = Send – Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-230">Estado de la confirmación funcional = Enviado/Procesado – Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-230">Functional ACK Status = Sent/Processed – Update Data</span></span>  
  
-   <span data-ttu-id="f7304-231">Receptor del intercambio = datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-231">Interchange Receiver =  Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-232">Remitente del intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-232">Interchange Sender = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-233">Fecha del intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-233">Interchange Date = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-234">Id. de control de intercambio = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-234">Interchange Control ID = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-235">Número de control de grupo = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-235">Group Control Number = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-236">Código de Id. funcional = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-236">Functional ID Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-237">Número de conjuntos de transacciones = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-237">Count of Transaction Sets = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-238">Id. de control de intercambio de reconocimiento funcional = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-238">Functional ACK Interchange Control ID= Update Data</span></span>  
  
-   <span data-ttu-id="f7304-239">Fecha de intercambio de reconocimiento funcional = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-239">Functional ACK Interchange Date = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-240">Hora de intercambio de confirmación funcional = Datos actualizados</span><span class="sxs-lookup"><span data-stu-id="f7304-240">Functional ACK Interchange Time = Update Data</span></span>  
  
-   <span data-ttu-id="f7304-241">Número de conjuntos de transacciones recibidos = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-241">Count of Transaction Sets Received = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-242">Número de conjuntos de transacciones aceptados = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-242">Count of Transaction Sets Accepted = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-243">Código de acción o confirmación = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-243">ACK/Action Code = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-244">Código de error de sintaxis/Error = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-244">Error/Syntax Error Code  = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-245">Adicionales X12 código de Error de confirmación 2 = datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-245">Additional X12 ACK Error Code 2 = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-246">Adicionales X12 código de Error 3 de confirmación = datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-246">Additional X12 ACK Error Code 3 = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-247">X12 adicionales 4 de código de Error de confirmación = datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-247">Additional X12 ACK Error Code 4 = Existing Data</span></span>  
  
-   <span data-ttu-id="f7304-248">Código de error 5 de confirmación X12 adicional = Datos existentes</span><span class="sxs-lookup"><span data-stu-id="f7304-248">Additional X12 ACK Error Code 5 = Existing Data</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7304-249">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7304-249">See Also</span></span>  
 <span data-ttu-id="f7304-250">[Cómo se almacenan los datos para informes de estado de AS2 y EDI](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="f7304-250">[How Data Is Stored for EDI and AS2 Status Reports](../core/how-data-is-stored-for-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="f7304-251">Cómo se almacenan los datos correspondientes a mensajes EDI de salida</span><span class="sxs-lookup"><span data-stu-id="f7304-251">How Data Is Stored for Outbound EDI Messages</span></span>](../core/how-data-is-stored-for-outbound-edi-messages.md)
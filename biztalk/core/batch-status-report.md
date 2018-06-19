---
title: Informe de estado de lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c033f58432c8ae5a2d87b87b56223b8f64a7201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231804"
---
# <a name="batch-status-report"></a><span data-ttu-id="7314e-102">Informe de estado de lotes</span><span class="sxs-lookup"><span data-stu-id="7314e-102">Batch Status Report</span></span>
<span data-ttu-id="7314e-103">Este informe muestra la actividad de instancias de la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="7314e-103">This report shows the activity of instances of the batching orchestration.</span></span> <span data-ttu-id="7314e-104">Cada fila del informe indica el estado de los lotes que se van a procesar mediante una única instancia de la orquestación por lotes.</span><span class="sxs-lookup"><span data-stu-id="7314e-104">Each row in the report indicates the status of the batches being processed by a single instance of the batching orchestration.</span></span>  
  
 <span data-ttu-id="7314e-105">No se notifica el estado de los lotes conservados en el informe de estado de lotes, pero se notifica en el informe de estado de confirmación o de intercambio.</span><span class="sxs-lookup"><span data-stu-id="7314e-105">The status of preserved batches is not reported in the Batch Status Report, but is reported in the Interchange/ACK Status report.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="7314e-106">Campos del informe de estado</span><span class="sxs-lookup"><span data-stu-id="7314e-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="7314e-107">El informe de estado de lotes muestra la siguiente información para los intercambios por lotes:</span><span class="sxs-lookup"><span data-stu-id="7314e-107">The Batch Status Report displays the following information for batched interchanges:</span></span>  
  
-   <span data-ttu-id="7314e-108">Estado del lote</span><span class="sxs-lookup"><span data-stu-id="7314e-108">Batch Status</span></span>  
  
-   <span data-ttu-id="7314e-109">Nombre de lote</span><span class="sxs-lookup"><span data-stu-id="7314e-109">Batch Name</span></span>  
  
-   <span data-ttu-id="7314e-110">Nombre de entidad de destino</span><span class="sxs-lookup"><span data-stu-id="7314e-110">Destination Party Name</span></span>  
  
-   <span data-ttu-id="7314e-111">Hora de activación</span><span class="sxs-lookup"><span data-stu-id="7314e-111">Activation Time</span></span>  
  
-   <span data-ttu-id="7314e-112">Repeticiones de lotes</span><span class="sxs-lookup"><span data-stu-id="7314e-112">Batch Occurrence</span></span>  
  
-   <span data-ttu-id="7314e-113">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="7314e-113">EDI Encoding Type</span></span>  
  
-   <span data-ttu-id="7314e-114">Tipo de lote</span><span class="sxs-lookup"><span data-stu-id="7314e-114">Batch Type</span></span>  
  
-   <span data-ttu-id="7314e-115">Destino de lote</span><span class="sxs-lookup"><span data-stu-id="7314e-115">Batch Target</span></span>  
  
-   <span data-ttu-id="7314e-116">Número de elementos de lote: el número de elementos por lotes ha acumulado la instancia de orquestación de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="7314e-116">Batch Element Count: how many batch elements have been accumulated by the batching orchestration instance</span></span>  
  
-   <span data-ttu-id="7314e-117">Número de elementos rechazados</span><span class="sxs-lookup"><span data-stu-id="7314e-117">Rejected Elements Count</span></span>  
  
-   <span data-ttu-id="7314e-118">Última acción: Puede ser lote activado, lanzamiento programado, lanzamiento basado en el recuento, lanzamiento de invalidación Manual, lanzamiento detenido/terminado del lote, elemento agregado o versión externo</span><span class="sxs-lookup"><span data-stu-id="7314e-118">Latest Action: Can be Batch Activated, Scheduled Release, Count Based Release, Manual Override Release, Batch Terminated/Stop Release, Element Added, or External Release</span></span>  
  
-   <span data-ttu-id="7314e-119">Número de Control de intercambio</span><span class="sxs-lookup"><span data-stu-id="7314e-119">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="7314e-120">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="7314e-120">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="7314e-121">Tamaño del lote (en caracteres) (no se muestra de forma predeterminada)</span><span class="sxs-lookup"><span data-stu-id="7314e-121">Batch Size (in characters) (not displayed by default)</span></span>  
  
## <a name="view-related-interchanges-status-reports"></a><span data-ttu-id="7314e-122">Ver informes de estado de intercambios relacionados</span><span class="sxs-lookup"><span data-stu-id="7314e-122">View Related Interchanges Status Reports</span></span>  
 <span data-ttu-id="7314e-123">Si hace clic con el botón secundario en un intercambio o confirmación que se enumera en el informe de estado de lotes, puede visualizar los detalles sobre los intercambios relacionados con el lote.</span><span class="sxs-lookup"><span data-stu-id="7314e-123">If you right-click an interchange or acknowledgment listed in the Batch Status Report, you can display details about the interchanges related to the batch.</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="7314e-124">Campos de Expresión de consulta para el informe de estado</span><span class="sxs-lookup"><span data-stu-id="7314e-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="7314e-125">Para personalizar el informe de estado de lotes, cambie los campos de la expresión de consulta que determina los datos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="7314e-125">You can customize the Batch Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="7314e-126">Están disponibles los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7314e-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="7314e-127">Campo Expresión de consulta</span><span class="sxs-lookup"><span data-stu-id="7314e-127">Query Expression Field</span></span>|<span data-ttu-id="7314e-128">Operadores potenciales</span><span class="sxs-lookup"><span data-stu-id="7314e-128">Potential Operators</span></span>|<span data-ttu-id="7314e-129">Valores potenciales</span><span class="sxs-lookup"><span data-stu-id="7314e-129">Potential Values</span></span>|<span data-ttu-id="7314e-130">¿Incluido de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="7314e-130">Included By Default?</span></span>|  
|<span data-ttu-id="7314e-131">Buscar</span><span class="sxs-lookup"><span data-stu-id="7314e-131">Search for</span></span>|<span data-ttu-id="7314e-132">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-132">Equals</span></span>|<span data-ttu-id="7314e-133">Estado del lote</span><span class="sxs-lookup"><span data-stu-id="7314e-133">Batch Status</span></span>|<span data-ttu-id="7314e-134">Sí (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="7314e-134">Yes (required)</span></span>|  
|<span data-ttu-id="7314e-135">Estado del lote</span><span class="sxs-lookup"><span data-stu-id="7314e-135">Batch Status</span></span>|<span data-ttu-id="7314e-136">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-136">Equals</span></span><br /><br /> <span data-ttu-id="7314e-137">No es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-137">Not Equals</span></span>|<span data-ttu-id="7314e-138">Define: La instancia de proceso por lotes está configurada pero fecha y hora de inicio es posterior a la hora de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="7314e-138">Defined: The batch instance is configured but the start date time is later than the current date time.</span></span><br /><br /> <span data-ttu-id="7314e-139">Activo (predeterminado): la instancia de lotes se configura y recopilan conjuntos de transacciones para un lote.</span><span class="sxs-lookup"><span data-stu-id="7314e-139">Active (default): The batch instance is configured and is collecting transaction sets for a batch.</span></span> <span data-ttu-id="7314e-140">La fecha y hora de inicio es anterior a las actuales.</span><span class="sxs-lookup"><span data-stu-id="7314e-140">The start date time is earlier than the current date time.</span></span><br /><br /> <span data-ttu-id="7314e-141">Fecha de publicación: Se ha cumplido los criterios de lanzamiento y se ha enviado el lote o que la orquestación del lote se ha detenido antes de procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7314e-141">Released: The release criteria has been met, and the batch has been sent, or that the batch orchestration was stopped before any messages were processed.</span></span><br /><br /> <span data-ttu-id="7314e-142">Completado: Se ha cumplido los criterios de versión, pero no se ha enviado el lote.</span><span class="sxs-lookup"><span data-stu-id="7314e-142">Completed: The release criteria has been met, but the batch has not been sent.</span></span><br /><br /> <span data-ttu-id="7314e-143">Todo: Mostrar cualquier instancia de lotes que se encuentra en uno de los estados anteriores.</span><span class="sxs-lookup"><span data-stu-id="7314e-143">All: Display any batch instance that is in one of the above states.</span></span>|<span data-ttu-id="7314e-144">Sí</span><span class="sxs-lookup"><span data-stu-id="7314e-144">Yes</span></span>|  
|<span data-ttu-id="7314e-145">N.º máximo de coincidencias</span><span class="sxs-lookup"><span data-stu-id="7314e-145">Maximum Matches</span></span>|<span data-ttu-id="7314e-146">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-146">Equals</span></span>|<span data-ttu-id="7314e-147">Entero (predeterminado de 50)</span><span class="sxs-lookup"><span data-stu-id="7314e-147">Integer (default of 50)</span></span>|<span data-ttu-id="7314e-148">Sí</span><span class="sxs-lookup"><span data-stu-id="7314e-148">Yes</span></span>|  
|<span data-ttu-id="7314e-149">Fecha y hora de activación</span><span class="sxs-lookup"><span data-stu-id="7314e-149">Activation Date Time</span></span>|<span data-ttu-id="7314e-150">Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="7314e-150">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="7314e-151">Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="7314e-151">Greater Than or Equals</span></span>|<span data-ttu-id="7314e-152">Fecha/hora</span><span class="sxs-lookup"><span data-stu-id="7314e-152">Date Time</span></span><br /><br /> <span data-ttu-id="7314e-153">Hoy</span><span class="sxs-lookup"><span data-stu-id="7314e-153">Today</span></span><br /><br /> <span data-ttu-id="7314e-154">Hoy en día - 5</span><span class="sxs-lookup"><span data-stu-id="7314e-154">Today - 5</span></span>|<span data-ttu-id="7314e-155">No</span><span class="sxs-lookup"><span data-stu-id="7314e-155">No</span></span><br /><br /> <span data-ttu-id="7314e-156">Nota: se puede incluir más de una vez en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="7314e-156">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="7314e-157">Nombre de lote</span><span class="sxs-lookup"><span data-stu-id="7314e-157">Batch Name</span></span>|<span data-ttu-id="7314e-158">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-158">Equals</span></span>|<span data-ttu-id="7314e-159">Todo (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7314e-159">All (Default)</span></span><br /><br /> <span data-ttu-id="7314e-160">Nombre de lote específico</span><span class="sxs-lookup"><span data-stu-id="7314e-160">Specific batch name</span></span>|<span data-ttu-id="7314e-161">No</span><span class="sxs-lookup"><span data-stu-id="7314e-161">No</span></span>|  
|<span data-ttu-id="7314e-162">Entidad de destino</span><span class="sxs-lookup"><span data-stu-id="7314e-162">Destination Party</span></span>|<span data-ttu-id="7314e-163">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-163">Equals</span></span>|<span data-ttu-id="7314e-164">All (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7314e-164">All (default)</span></span><br /><br /> <span data-ttu-id="7314e-165">Nombre de entidad específico</span><span class="sxs-lookup"><span data-stu-id="7314e-165">Specific party name</span></span>|<span data-ttu-id="7314e-166">No</span><span class="sxs-lookup"><span data-stu-id="7314e-166">No</span></span>|  
|<span data-ttu-id="7314e-167">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="7314e-167">EDI encoding type</span></span>|<span data-ttu-id="7314e-168">Es igual a</span><span class="sxs-lookup"><span data-stu-id="7314e-168">Equals</span></span>|<span data-ttu-id="7314e-169">X12</span><span class="sxs-lookup"><span data-stu-id="7314e-169">X12</span></span><br /><br /> <span data-ttu-id="7314e-170">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="7314e-170">EDIFACT</span></span><br /><br /> <span data-ttu-id="7314e-171">All (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7314e-171">All (default)</span></span>|<span data-ttu-id="7314e-172">No</span><span class="sxs-lookup"><span data-stu-id="7314e-172">No</span></span>|  
  

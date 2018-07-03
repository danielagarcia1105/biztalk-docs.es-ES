---
title: Estado de intercambio y el informe de estado de los detalles de confirmación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3201bc969bc053e9a128cbb0e65a42a2714480c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999029"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="13ff0-102">Detalles de la confirmación y del estado del intercambio (informe de estado)</span><span class="sxs-lookup"><span data-stu-id="13ff0-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="13ff0-103">Este informe de estado muestra detalles de un intercambio, así como de su confirmación (técnica) del intercambio y de las confirmaciones funcionales correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="13ff0-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="13ff0-104">Mostrar este informe haciendo clic en un intercambio dentro del informe de estado de confirmación y del intercambio y, a continuación, haga clic en **detalles de confirmación y del estado de intercambio**.</span><span class="sxs-lookup"><span data-stu-id="13ff0-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="13ff0-105">Este informe proporciona las siguientes vistas diferencias para el intercambio y las confirmaciones correlacionadas:</span><span class="sxs-lookup"><span data-stu-id="13ff0-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="13ff0-106">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="13ff0-106">Interchange Status</span></span>  
 <span data-ttu-id="13ff0-107">En esta vista se incluye una tabla donde se muestran los valores de los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="13ff0-107">This view provides a table showing the values for the following fields:</span></span>  
  
- <span data-ttu-id="13ff0-108">Id. de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="13ff0-108">Sender party ID</span></span>  
  
- <span data-ttu-id="13ff0-109">Id. de entidad receptora</span><span class="sxs-lookup"><span data-stu-id="13ff0-109">Receiver party ID</span></span>  
  
- <span data-ttu-id="13ff0-110">Id. de control</span><span class="sxs-lookup"><span data-stu-id="13ff0-110">Control ID</span></span>  
  
- <span data-ttu-id="13ff0-111">Nombre de la entidad receptora</span><span class="sxs-lookup"><span data-stu-id="13ff0-111">Receiver party name</span></span>  
  
- <span data-ttu-id="13ff0-112">Nombre de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="13ff0-112">Sender party name</span></span>  
  
- <span data-ttu-id="13ff0-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="13ff0-113">Direction</span></span>  
  
- <span data-ttu-id="13ff0-114">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="13ff0-114">Interchange Date Time</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="13ff0-115">Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA.</span><span class="sxs-lookup"><span data-stu-id="13ff0-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="13ff0-116">Si la fecha es inferior a 75, se mostrará como 20AA.</span><span class="sxs-lookup"><span data-stu-id="13ff0-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="13ff0-117">Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la fecha de intercambio se indicará en el informe como 11/13/1999.</span><span class="sxs-lookup"><span data-stu-id="13ff0-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="13ff0-118">Número de grupos</span><span class="sxs-lookup"><span data-stu-id="13ff0-118">Group count</span></span>  
  
- <span data-ttu-id="13ff0-119">Id. de puerto</span><span class="sxs-lookup"><span data-stu-id="13ff0-119">Port ID</span></span>  
  
- <span data-ttu-id="13ff0-120">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="13ff0-120">Interchange Status</span></span>  
  
- <span data-ttu-id="13ff0-121">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="13ff0-121">EDI encoding type</span></span>  
  
- <span data-ttu-id="13ff0-122">Id. de correlación del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="13ff0-122">Transaction Set Correlation Id</span></span>  
  
  <span data-ttu-id="13ff0-123">Si hay una confirmación técnica habilitada para una entidad como receptora de un intercambio (en la página Configuración de la validación y el procesamiento de confirmación del cuadro de diálogo Propiedades de EDI), BizTalk Server espera que se devuelva una confirmación técnica (intercambio) en respuesta al intercambio que envía.</span><span class="sxs-lookup"><span data-stu-id="13ff0-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="13ff0-124">Cuando crea inicialmente una entrada de estado de intercambio para un intercambio de salida, especificará Confirmación esperada en el campo Estado de intercambio.</span><span class="sxs-lookup"><span data-stu-id="13ff0-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="13ff0-125">Cuando recibe una confirmación técnica y la correlaciona con el intercambio original, actualizará este campo para indicar que ha recibido la confirmación.</span><span class="sxs-lookup"><span data-stu-id="13ff0-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="13ff0-126">Estado de confirmación del intercambio</span><span class="sxs-lookup"><span data-stu-id="13ff0-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="13ff0-127">En esta vista se muestran valores de estado para una confirmación del intercambio (técnica):</span><span class="sxs-lookup"><span data-stu-id="13ff0-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="13ff0-128">Identificador de control de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="13ff0-129">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="13ff0-129">Receiver party</span></span>  
  
-   <span data-ttu-id="13ff0-130">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="13ff0-130">Sender party</span></span>  
  
-   <span data-ttu-id="13ff0-131">Dirección</span><span class="sxs-lookup"><span data-stu-id="13ff0-131">Direction</span></span>  
  
-   <span data-ttu-id="13ff0-132">Fecha de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="13ff0-133">Hora de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="13ff0-134">Estado de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-134">Ack Status</span></span>  
  
-   <span data-ttu-id="13ff0-135">Código de estado</span><span class="sxs-lookup"><span data-stu-id="13ff0-135">Status Code</span></span>  
  
-   <span data-ttu-id="13ff0-136">Código de nota de confirmación 1</span><span class="sxs-lookup"><span data-stu-id="13ff0-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="13ff0-137">Código de nota de confirmación 2</span><span class="sxs-lookup"><span data-stu-id="13ff0-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="13ff0-138">Confirmaciones funcionales</span><span class="sxs-lookup"><span data-stu-id="13ff0-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="13ff0-139">En esta vista se muestran valores de estado para una confirmación funcional:</span><span class="sxs-lookup"><span data-stu-id="13ff0-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="13ff0-140">Número de control de grupo</span><span class="sxs-lookup"><span data-stu-id="13ff0-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="13ff0-141">Entidad receptora</span><span class="sxs-lookup"><span data-stu-id="13ff0-141">Receiver party</span></span>  
  
-   <span data-ttu-id="13ff0-142">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="13ff0-142">Sender party</span></span>  
  
-   <span data-ttu-id="13ff0-143">Dirección</span><span class="sxs-lookup"><span data-stu-id="13ff0-143">Direction</span></span>  
  
-   <span data-ttu-id="13ff0-144">Estado</span><span class="sxs-lookup"><span data-stu-id="13ff0-144">Status</span></span>  
  
-   <span data-ttu-id="13ff0-145">Código de estado</span><span class="sxs-lookup"><span data-stu-id="13ff0-145">Status Code</span></span>  
  
-   <span data-ttu-id="13ff0-146">Código Id. funcional</span><span class="sxs-lookup"><span data-stu-id="13ff0-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="13ff0-147">Recuento de TS</span><span class="sxs-lookup"><span data-stu-id="13ff0-147">TS Count</span></span>  
  
-   <span data-ttu-id="13ff0-148">Identificador de control de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="13ff0-149">Fecha de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="13ff0-150">Hora de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="13ff0-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="13ff0-151">Número de conjuntos de transacciones entregados</span><span class="sxs-lookup"><span data-stu-id="13ff0-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="13ff0-152">Recuento de conjuntos de transacciones aceptados</span><span class="sxs-lookup"><span data-stu-id="13ff0-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="13ff0-153">Código de error 1</span><span class="sxs-lookup"><span data-stu-id="13ff0-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="13ff0-154">Código de error 2</span><span class="sxs-lookup"><span data-stu-id="13ff0-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="13ff0-155">Código de error 3</span><span class="sxs-lookup"><span data-stu-id="13ff0-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="13ff0-156">Código de error 4</span><span class="sxs-lookup"><span data-stu-id="13ff0-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="13ff0-157">ErrorCode 5</span><span class="sxs-lookup"><span data-stu-id="13ff0-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="13ff0-158">Hora de recepción</span><span class="sxs-lookup"><span data-stu-id="13ff0-158">Time Received</span></span>
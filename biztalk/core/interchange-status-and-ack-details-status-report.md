---
title: Estado de intercambio y el informe de estado de confirmación detalles | Documentos de Microsoft
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
ms.openlocfilehash: 7cc596a99d1a49b01ccc417abccb73d12ed34ad5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257644"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="47ede-102">Detalles de la confirmación y del estado del intercambio (informe de estado)</span><span class="sxs-lookup"><span data-stu-id="47ede-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="47ede-103">Este informe de estado muestra detalles de un intercambio, así como de su confirmación (técnica) del intercambio y de las confirmaciones funcionales correlacionadas.</span><span class="sxs-lookup"><span data-stu-id="47ede-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="47ede-104">Mostrar este informe con el botón secundario de un intercambio en el informe de estado de confirmación y del intercambio y, a continuación, haga clic en **detalles de confirmación y del estado de intercambio**.</span><span class="sxs-lookup"><span data-stu-id="47ede-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="47ede-105">Este informe proporciona las siguientes vistas diferencias para el intercambio y las confirmaciones correlacionadas:</span><span class="sxs-lookup"><span data-stu-id="47ede-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="47ede-106">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="47ede-106">Interchange Status</span></span>  
 <span data-ttu-id="47ede-107">En esta vista se incluye una tabla donde se muestran los valores de los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47ede-107">This view provides a table showing the values for the following fields:</span></span>  
  
-   <span data-ttu-id="47ede-108">Id. de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="47ede-108">Sender party ID</span></span>  
  
-   <span data-ttu-id="47ede-109">Id. de entidad receptora</span><span class="sxs-lookup"><span data-stu-id="47ede-109">Receiver party ID</span></span>  
  
-   <span data-ttu-id="47ede-110">Id. de control</span><span class="sxs-lookup"><span data-stu-id="47ede-110">Control ID</span></span>  
  
-   <span data-ttu-id="47ede-111">Nombre de la entidad receptora</span><span class="sxs-lookup"><span data-stu-id="47ede-111">Receiver party name</span></span>  
  
-   <span data-ttu-id="47ede-112">Nombre de entidad remitente</span><span class="sxs-lookup"><span data-stu-id="47ede-112">Sender party name</span></span>  
  
-   <span data-ttu-id="47ede-113">Dirección</span><span class="sxs-lookup"><span data-stu-id="47ede-113">Direction</span></span>  
  
-   <span data-ttu-id="47ede-114">Fecha y hora de intercambio</span><span class="sxs-lookup"><span data-stu-id="47ede-114">Interchange Date Time</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47ede-115">Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA.</span><span class="sxs-lookup"><span data-stu-id="47ede-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="47ede-116">Si la fecha es inferior a 75, se mostrará como 20AA.</span><span class="sxs-lookup"><span data-stu-id="47ede-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
    >   
    >  <span data-ttu-id="47ede-117">Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la fecha de intercambio se indicará en el informe como 11/13/1999.</span><span class="sxs-lookup"><span data-stu-id="47ede-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
-   <span data-ttu-id="47ede-118">Número de grupos</span><span class="sxs-lookup"><span data-stu-id="47ede-118">Group count</span></span>  
  
-   <span data-ttu-id="47ede-119">Id. de puerto</span><span class="sxs-lookup"><span data-stu-id="47ede-119">Port ID</span></span>  
  
-   <span data-ttu-id="47ede-120">Estado del intercambio</span><span class="sxs-lookup"><span data-stu-id="47ede-120">Interchange Status</span></span>  
  
-   <span data-ttu-id="47ede-121">Tipo de codificación EDI</span><span class="sxs-lookup"><span data-stu-id="47ede-121">EDI encoding type</span></span>  
  
-   <span data-ttu-id="47ede-122">Id. de correlación del conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="47ede-122">Transaction Set Correlation Id</span></span>  
  
 <span data-ttu-id="47ede-123">Si hay una confirmación técnica habilitada para una entidad como receptora de un intercambio (en la página Configuración de la validación y el procesamiento de confirmación del cuadro de diálogo Propiedades de EDI), BizTalk Server espera que se devuelva una confirmación técnica (intercambio) en respuesta al intercambio que envía.</span><span class="sxs-lookup"><span data-stu-id="47ede-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="47ede-124">Cuando crea inicialmente una entrada de estado de intercambio para un intercambio de salida, especificará Confirmación esperada en el campo Estado de intercambio.</span><span class="sxs-lookup"><span data-stu-id="47ede-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="47ede-125">Cuando recibe una confirmación técnica y la correlaciona con el intercambio original, actualizará este campo para indicar que ha recibido la confirmación.</span><span class="sxs-lookup"><span data-stu-id="47ede-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="47ede-126">Estado de confirmación del intercambio</span><span class="sxs-lookup"><span data-stu-id="47ede-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="47ede-127">En esta vista se muestran valores de estado para una confirmación del intercambio (técnica):</span><span class="sxs-lookup"><span data-stu-id="47ede-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="47ede-128">Identificador de control de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="47ede-129">Entidad receptora.</span><span class="sxs-lookup"><span data-stu-id="47ede-129">Receiver party</span></span>  
  
-   <span data-ttu-id="47ede-130">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="47ede-130">Sender party</span></span>  
  
-   <span data-ttu-id="47ede-131">Dirección</span><span class="sxs-lookup"><span data-stu-id="47ede-131">Direction</span></span>  
  
-   <span data-ttu-id="47ede-132">Fecha de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="47ede-133">Hora de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="47ede-134">Estado de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-134">Ack Status</span></span>  
  
-   <span data-ttu-id="47ede-135">Código de estado</span><span class="sxs-lookup"><span data-stu-id="47ede-135">Status Code</span></span>  
  
-   <span data-ttu-id="47ede-136">Código de nota de confirmación 1</span><span class="sxs-lookup"><span data-stu-id="47ede-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="47ede-137">Código de nota de confirmación 2</span><span class="sxs-lookup"><span data-stu-id="47ede-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="47ede-138">Confirmaciones funcionales</span><span class="sxs-lookup"><span data-stu-id="47ede-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="47ede-139">En esta vista se muestran valores de estado para una confirmación funcional:</span><span class="sxs-lookup"><span data-stu-id="47ede-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="47ede-140">Número de control de grupo</span><span class="sxs-lookup"><span data-stu-id="47ede-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="47ede-141">Entidad receptora.</span><span class="sxs-lookup"><span data-stu-id="47ede-141">Receiver party</span></span>  
  
-   <span data-ttu-id="47ede-142">Entidad remitente</span><span class="sxs-lookup"><span data-stu-id="47ede-142">Sender party</span></span>  
  
-   <span data-ttu-id="47ede-143">Dirección</span><span class="sxs-lookup"><span data-stu-id="47ede-143">Direction</span></span>  
  
-   <span data-ttu-id="47ede-144">Estado</span><span class="sxs-lookup"><span data-stu-id="47ede-144">Status</span></span>  
  
-   <span data-ttu-id="47ede-145">Código de estado</span><span class="sxs-lookup"><span data-stu-id="47ede-145">Status Code</span></span>  
  
-   <span data-ttu-id="47ede-146">Código Id. funcional</span><span class="sxs-lookup"><span data-stu-id="47ede-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="47ede-147">Recuento de TS</span><span class="sxs-lookup"><span data-stu-id="47ede-147">TS Count</span></span>  
  
-   <span data-ttu-id="47ede-148">Identificador de control de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="47ede-149">Fecha de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="47ede-150">Hora de intercambio de confirmación</span><span class="sxs-lookup"><span data-stu-id="47ede-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="47ede-151">Número de conjuntos de transacciones entregados</span><span class="sxs-lookup"><span data-stu-id="47ede-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="47ede-152">Número de conjuntos aceptados</span><span class="sxs-lookup"><span data-stu-id="47ede-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="47ede-153">ErrorCode 1</span><span class="sxs-lookup"><span data-stu-id="47ede-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="47ede-154">ErrorCode 2</span><span class="sxs-lookup"><span data-stu-id="47ede-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="47ede-155">ErrorCode 3</span><span class="sxs-lookup"><span data-stu-id="47ede-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="47ede-156">ErrorCode 4</span><span class="sxs-lookup"><span data-stu-id="47ede-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="47ede-157">ErrorCode 5</span><span class="sxs-lookup"><span data-stu-id="47ede-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="47ede-158">Hora de recepción</span><span class="sxs-lookup"><span data-stu-id="47ede-158">Time Received</span></span>
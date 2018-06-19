---
title: Campo repetible segmentos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a801e39fac0e0bdf0cfb9ee88811703fd1c4373d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206332"
---
# <a name="repeatable-field-segments"></a><span data-ttu-id="c09cb-102">Segmentos de campo repetible</span><span class="sxs-lookup"><span data-stu-id="c09cb-102">Repeatable Field Segments</span></span>
<span data-ttu-id="c09cb-103">La tabla de segmentos en la base de datos de Access de HL7 contiene una columna para el último campo de segmentos (ADD, RDT y QPD) que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se define como repeatable (**Last_field_repeatable**  =  **True**).</span><span class="sxs-lookup"><span data-stu-id="c09cb-103">The Segments table in the HL7 Access database contains a column for the last field of segments (ADD, RDT, and QPD) that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) defines as repeatable (**Last_field_repeatable** = **True**).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c09cb-104">no se admite agregar.</span><span class="sxs-lookup"><span data-stu-id="c09cb-104"> does not support ADD.</span></span> <span data-ttu-id="c09cb-105">Sin embargo, RDT y QPD están presentes para las tablas de consulta y responden con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="c09cb-105">However, both RDT and QPD are present to query tables and respond with table values.</span></span> <span data-ttu-id="c09cb-106">El ejemplo siguiente se muestra cómo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] controla estas columnas.</span><span class="sxs-lookup"><span data-stu-id="c09cb-106">The following sample demonstrates how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] handles these columns.</span></span>  
  
 <span data-ttu-id="c09cb-107">Un cliente envía la consulta siguiente e indica que el cliente desea recibir una respuesta inmediata estableciendo **prioridad RCP-1-respuesta** a "**I**":</span><span class="sxs-lookup"><span data-stu-id="c09cb-107">A client submits the following query and indicates that the client wants an immediate response by setting **RCP-1-Response priority** to "**I**":</span></span>  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 <span data-ttu-id="c09cb-108">El servidor responde un minuto más adelante con el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="c09cb-108">The server responds one minute later with the following message:</span></span>  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 <span data-ttu-id="c09cb-109">En el ejemplo, verá que QPD y RDT se personalizado o definido por el sitio.</span><span class="sxs-lookup"><span data-stu-id="c09cb-109">From the example, you see that QPD and RDT are custom/site defined.</span></span> <span data-ttu-id="c09cb-110">La especificación de HL7 define segmentos QPD y RDT como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="c09cb-110">The HL7 specification defines QPD and RDT segments as follows.</span></span>  
  
## <a name="qpd---query-parameter-definition"></a><span data-ttu-id="c09cb-111">QPD: definición de parámetro de consulta</span><span class="sxs-lookup"><span data-stu-id="c09cb-111">QPD - Query Parameter Definition</span></span>  
 <span data-ttu-id="c09cb-112">En la tabla siguiente se muestra cómo la especificación de HL7 define QPD.</span><span class="sxs-lookup"><span data-stu-id="c09cb-112">The following table shows how the HL7 specification defines QPD.</span></span>  
  
|<span data-ttu-id="c09cb-113">SEQ</span><span class="sxs-lookup"><span data-stu-id="c09cb-113">SEQ</span></span>|<span data-ttu-id="c09cb-114">LEN</span><span class="sxs-lookup"><span data-stu-id="c09cb-114">LEN</span></span>|<span data-ttu-id="c09cb-115">DT</span><span class="sxs-lookup"><span data-stu-id="c09cb-115">DT</span></span>|<span data-ttu-id="c09cb-116">PARTICIPACIÓN</span><span class="sxs-lookup"><span data-stu-id="c09cb-116">OPT</span></span>|<span data-ttu-id="c09cb-117">RP / #</span><span class="sxs-lookup"><span data-stu-id="c09cb-117">RP/#</span></span>|<span data-ttu-id="c09cb-118">TBL #</span><span class="sxs-lookup"><span data-stu-id="c09cb-118">TBL#</span></span>|<span data-ttu-id="c09cb-119">ELEMENTO #</span><span class="sxs-lookup"><span data-stu-id="c09cb-119">ITEM#</span></span>|<span data-ttu-id="c09cb-120">NOMBRE DEL ELEMENTO</span><span class="sxs-lookup"><span data-stu-id="c09cb-120">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="c09cb-121">1</span><span class="sxs-lookup"><span data-stu-id="c09cb-121">1</span></span>|<span data-ttu-id="c09cb-122">250</span><span class="sxs-lookup"><span data-stu-id="c09cb-122">250</span></span>|<span data-ttu-id="c09cb-123">CE</span><span class="sxs-lookup"><span data-stu-id="c09cb-123">CE</span></span>|<span data-ttu-id="c09cb-124">L</span><span class="sxs-lookup"><span data-stu-id="c09cb-124">R</span></span>||<span data-ttu-id="c09cb-125">0471</span><span class="sxs-lookup"><span data-stu-id="c09cb-125">0471</span></span>|<span data-ttu-id="c09cb-126">01375</span><span class="sxs-lookup"><span data-stu-id="c09cb-126">01375</span></span>|<span data-ttu-id="c09cb-127">Nombre de la consulta de mensaje</span><span class="sxs-lookup"><span data-stu-id="c09cb-127">Message Query Name</span></span>|  
|<span data-ttu-id="c09cb-128">2</span><span class="sxs-lookup"><span data-stu-id="c09cb-128">2</span></span>|<span data-ttu-id="c09cb-129">32</span><span class="sxs-lookup"><span data-stu-id="c09cb-129">32</span></span>|<span data-ttu-id="c09cb-130">ST</span><span class="sxs-lookup"><span data-stu-id="c09cb-130">ST</span></span>|<span data-ttu-id="c09cb-131">C</span><span class="sxs-lookup"><span data-stu-id="c09cb-131">C</span></span>|||<span data-ttu-id="c09cb-132">00696</span><span class="sxs-lookup"><span data-stu-id="c09cb-132">00696</span></span>|<span data-ttu-id="c09cb-133">Etiqueta de consulta</span><span class="sxs-lookup"><span data-stu-id="c09cb-133">Query Tag</span></span>|  
|<span data-ttu-id="c09cb-134">3-n</span><span class="sxs-lookup"><span data-stu-id="c09cb-134">3-n</span></span>|<span data-ttu-id="c09cb-135">256</span><span class="sxs-lookup"><span data-stu-id="c09cb-135">256</span></span>|<span data-ttu-id="c09cb-136">Varía</span><span class="sxs-lookup"><span data-stu-id="c09cb-136">Varies</span></span>||||<span data-ttu-id="c09cb-137">01435</span><span class="sxs-lookup"><span data-stu-id="c09cb-137">01435</span></span>|<span data-ttu-id="c09cb-138">Parámetros de usuario en los campos sucesivas</span><span class="sxs-lookup"><span data-stu-id="c09cb-138">User parameters in successive fields</span></span>|  
  
## <a name="rdt---table-row-data"></a><span data-ttu-id="c09cb-139">RDT - datos de las filas de tabla</span><span class="sxs-lookup"><span data-stu-id="c09cb-139">RDT - Table Row Data</span></span>  
 <span data-ttu-id="c09cb-140">En la tabla siguiente se muestra cómo la especificación de HL7 define RDT.</span><span class="sxs-lookup"><span data-stu-id="c09cb-140">The following table shows how the HL7 specification defines RDT.</span></span>  
  
|<span data-ttu-id="c09cb-141">SEQ</span><span class="sxs-lookup"><span data-stu-id="c09cb-141">SEQ</span></span>|<span data-ttu-id="c09cb-142">LEN</span><span class="sxs-lookup"><span data-stu-id="c09cb-142">LEN</span></span>|<span data-ttu-id="c09cb-143">DT</span><span class="sxs-lookup"><span data-stu-id="c09cb-143">DT</span></span>|<span data-ttu-id="c09cb-144">PARTICIPACIÓN</span><span class="sxs-lookup"><span data-stu-id="c09cb-144">OPT</span></span>|<span data-ttu-id="c09cb-145">RP / #</span><span class="sxs-lookup"><span data-stu-id="c09cb-145">RP/#</span></span>|<span data-ttu-id="c09cb-146">TBL #</span><span class="sxs-lookup"><span data-stu-id="c09cb-146">TBL#</span></span>|<span data-ttu-id="c09cb-147">ELEMENTO #</span><span class="sxs-lookup"><span data-stu-id="c09cb-147">ITEM#</span></span>|<span data-ttu-id="c09cb-148">NOMBRE DEL ELEMENTO</span><span class="sxs-lookup"><span data-stu-id="c09cb-148">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="c09cb-149">1-n</span><span class="sxs-lookup"><span data-stu-id="c09cb-149">1-n</span></span>|<span data-ttu-id="c09cb-150">Variable</span><span class="sxs-lookup"><span data-stu-id="c09cb-150">Variable</span></span>|<span data-ttu-id="c09cb-151">Variable</span><span class="sxs-lookup"><span data-stu-id="c09cb-151">Variable</span></span>|<span data-ttu-id="c09cb-152">L</span><span class="sxs-lookup"><span data-stu-id="c09cb-152">R</span></span>|||<span data-ttu-id="c09cb-153">00703</span><span class="sxs-lookup"><span data-stu-id="c09cb-153">00703</span></span>|<span data-ttu-id="c09cb-154">Valor de la columna</span><span class="sxs-lookup"><span data-stu-id="c09cb-154">Column Value</span></span>|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="c09cb-155">interpreta QPD y RDT como valores definidos por el sitio que se pueden repetir.</span><span class="sxs-lookup"><span data-stu-id="c09cb-155"> interprets QPD and RDT as site-defined values that can repeat.</span></span> <span data-ttu-id="c09cb-156">Puesto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se soluciona los tipos de datos y otros detalles, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] trata QPD.3 y RDT.1 como tipos de datos de cadena en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="c09cb-156">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fix the data types and other details, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats QPD.3 and RDT.1 as String data types in the schemas.</span></span> <span data-ttu-id="c09cb-157">Tendrá que modificar estos esquemas, dependiendo de sus propias condiciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="c09cb-157">You may have to modify these schemas depending on your own site conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09cb-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="c09cb-158">See Also</span></span>  
 [<span data-ttu-id="c09cb-159">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="c09cb-159">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
---
title: Segmentos de campo repetibles | Microsoft Docs
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
ms.openlocfilehash: 9651b8d3414f792b81633cafbe41dd66559df04c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981981"
---
# <a name="repeatable-field-segments"></a><span data-ttu-id="4c783-102">Segmentos de campo repetibles</span><span class="sxs-lookup"><span data-stu-id="4c783-102">Repeatable Field Segments</span></span>
<span data-ttu-id="4c783-103">La tabla de segmentos en la base de datos de Access de HL7 contiene una columna para el último campo de segmentos (ADD, RDT y QPD) dicho Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se define como repetible (**Last_field_repeatable**  =  **True**).</span><span class="sxs-lookup"><span data-stu-id="4c783-103">The Segments table in the HL7 Access database contains a column for the last field of segments (ADD, RDT, and QPD) that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) defines as repeatable (**Last_field_repeatable** = **True**).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4c783-104"> no se admite agregar.</span><span class="sxs-lookup"><span data-stu-id="4c783-104"> does not support ADD.</span></span> <span data-ttu-id="4c783-105">Sin embargo, RDT y QPD están presentes en las tablas de consulta y responden con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="4c783-105">However, both RDT and QPD are present to query tables and respond with table values.</span></span> <span data-ttu-id="4c783-106">El ejemplo siguiente se muestra cómo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] controla estas columnas.</span><span class="sxs-lookup"><span data-stu-id="4c783-106">The following sample demonstrates how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] handles these columns.</span></span>  
  
 <span data-ttu-id="4c783-107">Un cliente envía la consulta siguiente e indica que el cliente desea recibir una respuesta inmediata estableciendo **prioridad RCP-1-Response** a "**me**":</span><span class="sxs-lookup"><span data-stu-id="4c783-107">A client submits the following query and indicates that the client wants an immediate response by setting **RCP-1-Response priority** to "**I**":</span></span>  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 <span data-ttu-id="4c783-108">El servidor responde a un minuto más tarde con el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="4c783-108">The server responds one minute later with the following message:</span></span>  
  
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
  
 <span data-ttu-id="4c783-109">En el ejemplo, verá que QPD y RDT son personalizados o definido por el sitio.</span><span class="sxs-lookup"><span data-stu-id="4c783-109">From the example, you see that QPD and RDT are custom/site defined.</span></span> <span data-ttu-id="4c783-110">La especificación de HL7 define QPD y RDT segmentos como sigue.</span><span class="sxs-lookup"><span data-stu-id="4c783-110">The HL7 specification defines QPD and RDT segments as follows.</span></span>  
  
## <a name="qpd---query-parameter-definition"></a><span data-ttu-id="4c783-111">QPD - definición de parámetro de consulta</span><span class="sxs-lookup"><span data-stu-id="4c783-111">QPD - Query Parameter Definition</span></span>  
 <span data-ttu-id="4c783-112">En la tabla siguiente se muestra cómo la especificación de HL7 define QPD.</span><span class="sxs-lookup"><span data-stu-id="4c783-112">The following table shows how the HL7 specification defines QPD.</span></span>  
  
|<span data-ttu-id="4c783-113">SEQ</span><span class="sxs-lookup"><span data-stu-id="4c783-113">SEQ</span></span>|<span data-ttu-id="4c783-114">LEN</span><span class="sxs-lookup"><span data-stu-id="4c783-114">LEN</span></span>|<span data-ttu-id="4c783-115">DT</span><span class="sxs-lookup"><span data-stu-id="4c783-115">DT</span></span>|<span data-ttu-id="4c783-116">PARTICIPAR</span><span class="sxs-lookup"><span data-stu-id="4c783-116">OPT</span></span>|<span data-ttu-id="4c783-117">RP / #</span><span class="sxs-lookup"><span data-stu-id="4c783-117">RP/#</span></span>|<span data-ttu-id="4c783-118">TBL #</span><span class="sxs-lookup"><span data-stu-id="4c783-118">TBL#</span></span>|<span data-ttu-id="4c783-119">ELEMENTO #</span><span class="sxs-lookup"><span data-stu-id="4c783-119">ITEM#</span></span>|<span data-ttu-id="4c783-120">NOMBRE DEL ELEMENTO</span><span class="sxs-lookup"><span data-stu-id="4c783-120">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="4c783-121">1</span><span class="sxs-lookup"><span data-stu-id="4c783-121">1</span></span>|<span data-ttu-id="4c783-122">250</span><span class="sxs-lookup"><span data-stu-id="4c783-122">250</span></span>|<span data-ttu-id="4c783-123">CE</span><span class="sxs-lookup"><span data-stu-id="4c783-123">CE</span></span>|<span data-ttu-id="4c783-124">R</span><span class="sxs-lookup"><span data-stu-id="4c783-124">R</span></span>||<span data-ttu-id="4c783-125">0471</span><span class="sxs-lookup"><span data-stu-id="4c783-125">0471</span></span>|<span data-ttu-id="4c783-126">01375</span><span class="sxs-lookup"><span data-stu-id="4c783-126">01375</span></span>|<span data-ttu-id="4c783-127">Nombre de la consulta de mensaje</span><span class="sxs-lookup"><span data-stu-id="4c783-127">Message Query Name</span></span>|  
|<span data-ttu-id="4c783-128">2</span><span class="sxs-lookup"><span data-stu-id="4c783-128">2</span></span>|<span data-ttu-id="4c783-129">32</span><span class="sxs-lookup"><span data-stu-id="4c783-129">32</span></span>|<span data-ttu-id="4c783-130">ST</span><span class="sxs-lookup"><span data-stu-id="4c783-130">ST</span></span>|<span data-ttu-id="4c783-131">C</span><span class="sxs-lookup"><span data-stu-id="4c783-131">C</span></span>|||<span data-ttu-id="4c783-132">00696</span><span class="sxs-lookup"><span data-stu-id="4c783-132">00696</span></span>|<span data-ttu-id="4c783-133">Etiqueta de consulta</span><span class="sxs-lookup"><span data-stu-id="4c783-133">Query Tag</span></span>|  
|<span data-ttu-id="4c783-134">3-n</span><span class="sxs-lookup"><span data-stu-id="4c783-134">3-n</span></span>|<span data-ttu-id="4c783-135">256</span><span class="sxs-lookup"><span data-stu-id="4c783-135">256</span></span>|<span data-ttu-id="4c783-136">Varía</span><span class="sxs-lookup"><span data-stu-id="4c783-136">Varies</span></span>||||<span data-ttu-id="4c783-137">01435</span><span class="sxs-lookup"><span data-stu-id="4c783-137">01435</span></span>|<span data-ttu-id="4c783-138">Parámetros de usuario en sucesivas campos</span><span class="sxs-lookup"><span data-stu-id="4c783-138">User parameters in successive fields</span></span>|  
  
## <a name="rdt---table-row-data"></a><span data-ttu-id="4c783-139">RDT - datos de la fila de tabla</span><span class="sxs-lookup"><span data-stu-id="4c783-139">RDT - Table Row Data</span></span>  
 <span data-ttu-id="4c783-140">En la tabla siguiente se muestra cómo la especificación de HL7 define RDT.</span><span class="sxs-lookup"><span data-stu-id="4c783-140">The following table shows how the HL7 specification defines RDT.</span></span>  
  
|<span data-ttu-id="4c783-141">SEQ</span><span class="sxs-lookup"><span data-stu-id="4c783-141">SEQ</span></span>|<span data-ttu-id="4c783-142">LEN</span><span class="sxs-lookup"><span data-stu-id="4c783-142">LEN</span></span>|<span data-ttu-id="4c783-143">DT</span><span class="sxs-lookup"><span data-stu-id="4c783-143">DT</span></span>|<span data-ttu-id="4c783-144">PARTICIPAR</span><span class="sxs-lookup"><span data-stu-id="4c783-144">OPT</span></span>|<span data-ttu-id="4c783-145">RP / #</span><span class="sxs-lookup"><span data-stu-id="4c783-145">RP/#</span></span>|<span data-ttu-id="4c783-146">TBL #</span><span class="sxs-lookup"><span data-stu-id="4c783-146">TBL#</span></span>|<span data-ttu-id="4c783-147">ELEMENTO #</span><span class="sxs-lookup"><span data-stu-id="4c783-147">ITEM#</span></span>|<span data-ttu-id="4c783-148">NOMBRE DEL ELEMENTO</span><span class="sxs-lookup"><span data-stu-id="4c783-148">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="4c783-149">1-n</span><span class="sxs-lookup"><span data-stu-id="4c783-149">1-n</span></span>|<span data-ttu-id="4c783-150">Variable</span><span class="sxs-lookup"><span data-stu-id="4c783-150">Variable</span></span>|<span data-ttu-id="4c783-151">Variable</span><span class="sxs-lookup"><span data-stu-id="4c783-151">Variable</span></span>|<span data-ttu-id="4c783-152">R</span><span class="sxs-lookup"><span data-stu-id="4c783-152">R</span></span>|||<span data-ttu-id="4c783-153">00703</span><span class="sxs-lookup"><span data-stu-id="4c783-153">00703</span></span>|<span data-ttu-id="4c783-154">Valor de columna</span><span class="sxs-lookup"><span data-stu-id="4c783-154">Column Value</span></span>|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4c783-155"> interpreta QPD y RDT como valores definidos por el sitio que se pueden repetir.</span><span class="sxs-lookup"><span data-stu-id="4c783-155"> interprets QPD and RDT as site-defined values that can repeat.</span></span> <span data-ttu-id="4c783-156">Puesto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no soluciona los tipos de datos y otros detalles, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] trata QPD.3 y RDT.1 como tipos de datos de cadena en los esquemas.</span><span class="sxs-lookup"><span data-stu-id="4c783-156">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fix the data types and other details, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats QPD.3 and RDT.1 as String data types in the schemas.</span></span> <span data-ttu-id="4c783-157">Es posible que deba modificar estos esquemas según las condiciones de su propio sitio.</span><span class="sxs-lookup"><span data-stu-id="4c783-157">You may have to modify these schemas depending on your own site conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c783-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c783-158">See Also</span></span>  
 [<span data-ttu-id="4c783-159">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="4c783-159">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
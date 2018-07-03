---
title: HL7 2.5 carpetas y eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 662ef767-5504-4ff5-8820-994e9cf674ea
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66bcd4c6dd5acbe8a6d2f649e387da8177c9618c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992805"
---
# <a name="hl7-25-folders-and-events"></a><span data-ttu-id="2aa2e-102">HL7 2.5 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="2aa2e-102">HL7 2.5 Folders and Events</span></span>
<span data-ttu-id="2aa2e-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente de instalación dentro de la carpeta de HL7 versión 2.5 para mensajes codificados en HL7.</span><span class="sxs-lookup"><span data-stu-id="2aa2e-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.5 folder for HL7-encoded messages.</span></span> <span data-ttu-id="2aa2e-104">Estas subcarpetas contienen los esquemas utilizados por el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="2aa2e-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="2aa2e-105">Los nombres de subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="2aa2e-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="2aa2e-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="2aa2e-106">Subfolder</span></span>|<span data-ttu-id="2aa2e-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="2aa2e-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="2aa2e-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="2aa2e-108">Patient Administration</span></span>|<span data-ttu-id="2aa2e-109">A01-A62, K21-K24 Q21-Q24</span><span class="sxs-lookup"><span data-stu-id="2aa2e-109">A01-A62,K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="2aa2e-110">Administración de personal</span><span class="sxs-lookup"><span data-stu-id="2aa2e-110">Personnel Management</span></span>|<span data-ttu-id="2aa2e-111">B01-B08, K25, Q25</span><span class="sxs-lookup"><span data-stu-id="2aa2e-111">B01-B08,K25,Q25</span></span>|  
|<span data-ttu-id="2aa2e-112">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="2aa2e-112">Observation Reporting</span></span>|<span data-ttu-id="2aa2e-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span><span class="sxs-lookup"><span data-stu-id="2aa2e-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span></span>|  
|<span data-ttu-id="2aa2e-114">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="2aa2e-114">Patient Referral</span></span>|<span data-ttu-id="2aa2e-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="2aa2e-115">I01-I15</span></span>|  
|<span data-ttu-id="2aa2e-116">Consulta</span><span class="sxs-lookup"><span data-stu-id="2aa2e-116">Query</span></span>|<span data-ttu-id="2aa2e-117">J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, P11, RESPUESTA A P13, RESPUESTA A P15 Q17, R07 R09, Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="2aa2e-117">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09,Q11,Q13,Q15-Q17, R07-R09,Z75-Z99</span></span>|  
|<span data-ttu-id="2aa2e-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="2aa2e-118">Master Files</span></span>|<span data-ttu-id="2aa2e-119">M01 M12</span><span class="sxs-lookup"><span data-stu-id="2aa2e-119">M01-M12</span></span>|  
|<span data-ttu-id="2aa2e-120">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="2aa2e-120">Order Entry</span></span>|<span data-ttu-id="2aa2e-121">O01 O36, Q06, P26 Q31, RAR, RDR, RER, RGR, ROR, V01 V04, Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="2aa2e-121">O01-O36,Q06,Q26-Q31,RAR,RDR,RER,RGR,ROR,V01-V04,Z73-Z74</span></span>|  
|<span data-ttu-id="2aa2e-122">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2aa2e-122">Application Management</span></span>|<span data-ttu-id="2aa2e-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="2aa2e-123">N01-N02</span></span>|  
|<span data-ttu-id="2aa2e-124">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="2aa2e-124">Financial Management</span></span>|<span data-ttu-id="2aa2e-125">P01 P03, P05-06, P10 P12</span><span class="sxs-lookup"><span data-stu-id="2aa2e-125">P01-P03,P05-06,P10-P12</span></span>|  
|<span data-ttu-id="2aa2e-126">Atención al paciente</span><span class="sxs-lookup"><span data-stu-id="2aa2e-126">Patient Care</span></span>|<span data-ttu-id="2aa2e-127">PC1-PC9, PCA-PCH, PCJ, PCL</span><span class="sxs-lookup"><span data-stu-id="2aa2e-127">PC1-PC9,PCA-PCH,PCJ,PCL</span></span>|  
|<span data-ttu-id="2aa2e-128">Programación</span><span class="sxs-lookup"><span data-stu-id="2aa2e-128">Scheduling</span></span>|<span data-ttu-id="2aa2e-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="2aa2e-129">S01-S26</span></span>|  
|<span data-ttu-id="2aa2e-130">Administración de registros médicos o información</span><span class="sxs-lookup"><span data-stu-id="2aa2e-130">Medical Records/Information Management</span></span>|<span data-ttu-id="2aa2e-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="2aa2e-131">T01-T12</span></span>|  
|<span data-ttu-id="2aa2e-132">Automatización del laboratorio clínica</span><span class="sxs-lookup"><span data-stu-id="2aa2e-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="2aa2e-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="2aa2e-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2aa2e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aa2e-134">See Also</span></span>  
 <span data-ttu-id="2aa2e-135">[Eventos y las subcarpetas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="2aa2e-136">[HL7 2.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="2aa2e-137">[HL7 2.2 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="2aa2e-138">[HL7 2.3 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="2aa2e-139">[HL7 2.3.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="2aa2e-140">[HL7 2.4 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="2aa2e-140">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="2aa2e-141">HL7 2.5 carpetas y eventos &#91;hl7&#93;</span><span class="sxs-lookup"><span data-stu-id="2aa2e-141">HL7 2.5 Folders and Events &#91;hl7&#93;</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
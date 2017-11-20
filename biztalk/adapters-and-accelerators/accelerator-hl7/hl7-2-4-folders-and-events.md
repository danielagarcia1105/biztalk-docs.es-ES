---
title: HL7 2,4 carpetas y eventos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: c8855311-40c7-4338-ba07-5112c253fafd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9196b0b69eb3730de8ad3ef383a1cde8564e5002
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-24-folders-and-events"></a><span data-ttu-id="8b4ff-102">HL7 2,4 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="8b4ff-102">HL7 2.4 Folders and Events</span></span>
<span data-ttu-id="8b4ff-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de la versión 2.4 HL7 para mensajes con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for HL7-encoded messages.</span></span> <span data-ttu-id="8b4ff-104">Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="8b4ff-105">Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="8b4ff-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="8b4ff-106">Subfolder</span></span>|<span data-ttu-id="8b4ff-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="8b4ff-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="8b4ff-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="8b4ff-108">Patient Administration</span></span>|<span data-ttu-id="8b4ff-109">A01-A62, K21-K24, Q21-Q24</span><span class="sxs-lookup"><span data-stu-id="8b4ff-109">A01-A62, K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="8b4ff-110">Administración del personal</span><span class="sxs-lookup"><span data-stu-id="8b4ff-110">Personnel Management</span></span>|<span data-ttu-id="8b4ff-111">B01-B06, K25, Q25</span><span class="sxs-lookup"><span data-stu-id="8b4ff-111">B01-B06, K25,Q25</span></span>|  
|<span data-ttu-id="8b4ff-112">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="8b4ff-112">Observation Reporting</span></span>|<span data-ttu-id="8b4ff-113">R01-R02, R04, C01-C12, P07-P09 R21, W01 W02</span><span class="sxs-lookup"><span data-stu-id="8b4ff-113">C01-C12, P07-P09, R01-R02,R04, R21, W01-W02</span></span>|  
|<span data-ttu-id="8b4ff-114">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="8b4ff-114">Patient Referral</span></span>|<span data-ttu-id="8b4ff-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="8b4ff-115">I01-I15</span></span>|  
|<span data-ttu-id="8b4ff-116">Query</span><span class="sxs-lookup"><span data-stu-id="8b4ff-116">Query</span></span>|<span data-ttu-id="8b4ff-117">J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, PREGUNTA 11, RESPUESTA A P13, RESPUESTA A P15-Q17, R07 R09, Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="8b4ff-117">J01,J02,K11,K13,K15,  Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="8b4ff-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="8b4ff-118">Master Files</span></span>|<span data-ttu-id="8b4ff-119">M01-M12, MFA</span><span class="sxs-lookup"><span data-stu-id="8b4ff-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="8b4ff-120">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="8b4ff-120">Order Entry</span></span>|<span data-ttu-id="8b4ff-121">O01 O22, Q06, Q30 P26, RAR, RDR, RER, RGR, ERROR, V01 V04, Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="8b4ff-121">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73- Z74</span></span>|  
|<span data-ttu-id="8b4ff-122">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8b4ff-122">Application Management</span></span>|<span data-ttu-id="8b4ff-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="8b4ff-123">N01-N02</span></span>|  
|<span data-ttu-id="8b4ff-124">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="8b4ff-124">Financial Management</span></span>|<span data-ttu-id="8b4ff-125">P01-P06, P10</span><span class="sxs-lookup"><span data-stu-id="8b4ff-125">P01-P06, P10</span></span>|  
|<span data-ttu-id="8b4ff-126">Atención del paciente</span><span class="sxs-lookup"><span data-stu-id="8b4ff-126">Patient Care</span></span>|<span data-ttu-id="8b4ff-127">PC1-PCH, PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="8b4ff-127">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="8b4ff-128">Programación</span><span class="sxs-lookup"><span data-stu-id="8b4ff-128">Scheduling</span></span>|<span data-ttu-id="8b4ff-129">S26 S01</span><span class="sxs-lookup"><span data-stu-id="8b4ff-129">S01-S26</span></span>|  
|<span data-ttu-id="8b4ff-130">Administración de registros/información médica</span><span class="sxs-lookup"><span data-stu-id="8b4ff-130">Medical Records/Information Management</span></span>|<span data-ttu-id="8b4ff-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="8b4ff-131">T01-T12</span></span>|  
|<span data-ttu-id="8b4ff-132">Automatización de clínicos de laboratorio</span><span class="sxs-lookup"><span data-stu-id="8b4ff-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="8b4ff-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="8b4ff-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b4ff-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b4ff-134">See Also</span></span>  
 <span data-ttu-id="8b4ff-135">[Eventos y las subcarpetas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ff-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="8b4ff-136">[HL7 2.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ff-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="8b4ff-137">[HL7 2.2 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ff-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="8b4ff-138">[HL7 2.3 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ff-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="8b4ff-139">[HL7 2.3.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ff-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 [<span data-ttu-id="8b4ff-140">HL7 2,5 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="8b4ff-140">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
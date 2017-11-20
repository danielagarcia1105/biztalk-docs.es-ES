---
title: HL7 2.3 carpetas y eventos | Documentos de Microsoft
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
ms.assetid: 555a8620-a714-4102-80ba-1424d60387bf
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a396fca582defb8601bdda23280f92d0acbd90be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-23-folders-and-events"></a><span data-ttu-id="57dce-102">HL7 2.3 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="57dce-102">HL7 2.3 Folders and Events</span></span>
<span data-ttu-id="57dce-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de la versión 2.3 HL7 para mensajes con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="57dce-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3 folder for HL7-encoded messages.</span></span> <span data-ttu-id="57dce-104">Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="57dce-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="57dce-105">Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="57dce-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="57dce-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="57dce-106">Subfolder</span></span>|<span data-ttu-id="57dce-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="57dce-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="57dce-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="57dce-108">Patient Administration</span></span>|<span data-ttu-id="57dce-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="57dce-109">A01-A51</span></span>|  
|<span data-ttu-id="57dce-110">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="57dce-110">Observation Reporting</span></span>|<span data-ttu-id="57dce-111">C01-C12, P07-P09, R01-R06, W01 W02</span><span class="sxs-lookup"><span data-stu-id="57dce-111">C01-C12, P07-P09, R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="57dce-112">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="57dce-112">Patient Referral</span></span>|<span data-ttu-id="57dce-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="57dce-113">I01-I15</span></span>|  
|<span data-ttu-id="57dce-114">Archivo maestro</span><span class="sxs-lookup"><span data-stu-id="57dce-114">Master File</span></span>|<span data-ttu-id="57dce-115">M01 M11</span><span class="sxs-lookup"><span data-stu-id="57dce-115">M01-M11</span></span>|  
|<span data-ttu-id="57dce-116">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="57dce-116">Order Entry</span></span>|<span data-ttu-id="57dce-117">O01 O02, Q06, RAR, RDR, RER, RGR, ERROR, V04 V01</span><span class="sxs-lookup"><span data-stu-id="57dce-117">O01-O02,Q06, RAR,RDR,RER,RGR,ROR, V01-V04</span></span>|  
|<span data-ttu-id="57dce-118">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="57dce-118">Financial Management</span></span>|<span data-ttu-id="57dce-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="57dce-119">P01-P06</span></span>|  
|<span data-ttu-id="57dce-120">Atención del paciente</span><span class="sxs-lookup"><span data-stu-id="57dce-120">Patient Care</span></span>|<span data-ttu-id="57dce-121">PC1-PCH, PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="57dce-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="57dce-122">Query</span><span class="sxs-lookup"><span data-stu-id="57dce-122">Query</span></span>|<span data-ttu-id="57dce-123">CNQ, Q01-Q03, Q05</span><span class="sxs-lookup"><span data-stu-id="57dce-123">CNQ, Q01-Q03, Q05</span></span>|  
|<span data-ttu-id="57dce-124">Programación</span><span class="sxs-lookup"><span data-stu-id="57dce-124">Scheduling</span></span>|<span data-ttu-id="57dce-125">S26 S01</span><span class="sxs-lookup"><span data-stu-id="57dce-125">S01-S26</span></span>|  
|<span data-ttu-id="57dce-126">Historiales médicos y administración de la información</span><span class="sxs-lookup"><span data-stu-id="57dce-126">Medical Records and Information Management</span></span>|<span data-ttu-id="57dce-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="57dce-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57dce-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="57dce-128">See Also</span></span>  
 <span data-ttu-id="57dce-129">[Eventos y las subcarpetas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="57dce-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="57dce-130">[HL7 2.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="57dce-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="57dce-131">[HL7 2.2 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="57dce-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="57dce-132">[HL7 2.3.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="57dce-132">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="57dce-133">[HL7 2,4 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="57dce-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="57dce-134">HL7 2,5 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="57dce-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
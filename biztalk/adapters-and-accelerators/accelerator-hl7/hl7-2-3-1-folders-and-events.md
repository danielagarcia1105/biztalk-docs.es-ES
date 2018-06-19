---
title: HL7 2.3.1 carpetas y eventos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: 5cab1b7e-fdce-4b4b-bbd6-1da67fcf6a74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad51a024348c12c4097af29419698ced7c9c0c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204756"
---
# <a name="hl7-231-folders-and-events"></a><span data-ttu-id="c5c35-102">HL7 2.3.1 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="c5c35-102">HL7 2.3.1 Folders and Events</span></span>
<span data-ttu-id="c5c35-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de versión 2.3.1 HL7 para mensajes con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="c5c35-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for HL7-encoded messages.</span></span> <span data-ttu-id="c5c35-104">Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="c5c35-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="c5c35-105">Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="c5c35-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="c5c35-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="c5c35-106">Subfolder</span></span>|<span data-ttu-id="c5c35-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="c5c35-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="c5c35-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="c5c35-108">Patient Administration</span></span>|<span data-ttu-id="c5c35-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="c5c35-109">A01-A51</span></span>|  
|<span data-ttu-id="c5c35-110">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="c5c35-110">Observation Reporting</span></span>|<span data-ttu-id="c5c35-111">C01-C12, P06-P09, R01-R06, W01 W02</span><span class="sxs-lookup"><span data-stu-id="c5c35-111">C01-C12,P06-P09,R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="c5c35-112">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="c5c35-112">Patient Referral</span></span>|<span data-ttu-id="c5c35-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="c5c35-113">I01-I15</span></span>|  
|<span data-ttu-id="c5c35-114">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="c5c35-114">Master Files</span></span>|<span data-ttu-id="c5c35-115">M01-M11, MFA</span><span class="sxs-lookup"><span data-stu-id="c5c35-115">M01-M11, MFA</span></span>|  
|<span data-ttu-id="c5c35-116">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="c5c35-116">Order Entry</span></span>|<span data-ttu-id="c5c35-117">O01 O02, Q06, R0R, RAR, RDR, RER, RGR, V04 V01</span><span class="sxs-lookup"><span data-stu-id="c5c35-117">O01-O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="c5c35-118">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="c5c35-118">Financial Management</span></span>|<span data-ttu-id="c5c35-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="c5c35-119">P01-P06</span></span>|  
|<span data-ttu-id="c5c35-120">Atención del paciente</span><span class="sxs-lookup"><span data-stu-id="c5c35-120">Patient Care</span></span>|<span data-ttu-id="c5c35-121">PC1-PCH, PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="c5c35-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="c5c35-122">Query</span><span class="sxs-lookup"><span data-stu-id="c5c35-122">Query</span></span>|<span data-ttu-id="c5c35-123">CNQ, Q01-Q05, Q07-Q09, R07 R09</span><span class="sxs-lookup"><span data-stu-id="c5c35-123">CNQ, Q01-Q05, Q07-Q09, R07-R09</span></span>|  
|<span data-ttu-id="c5c35-124">Programación</span><span class="sxs-lookup"><span data-stu-id="c5c35-124">Schedule</span></span>|<span data-ttu-id="c5c35-125">S26 S01</span><span class="sxs-lookup"><span data-stu-id="c5c35-125">S01-S26</span></span>|  
|<span data-ttu-id="c5c35-126">Administración de registros/información médica</span><span class="sxs-lookup"><span data-stu-id="c5c35-126">Medical Records/Information Management</span></span>|<span data-ttu-id="c5c35-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="c5c35-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5c35-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5c35-128">See Also</span></span>  
 <span data-ttu-id="c5c35-129">[Eventos y las subcarpetas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c5c35-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="c5c35-130">[HL7 2.1 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c5c35-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="c5c35-131">[HL7 2.2 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c5c35-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="c5c35-132">[HL7 2.3 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c5c35-132">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="c5c35-133">[HL7 2,4 carpetas y eventos](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c5c35-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="c5c35-134">HL7 2,5 carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="c5c35-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
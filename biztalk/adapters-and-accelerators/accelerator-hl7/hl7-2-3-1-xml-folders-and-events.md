---
title: HL7 2.3.1 XML carpetas y eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bbe1d472f844d57c7770ec4ae425fc6aef44a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991733"
---
# <a name="hl7-231-xml-folders-and-events"></a><span data-ttu-id="9fd13-102">HL7 2.3.1 XML carpetas y eventos</span><span class="sxs-lookup"><span data-stu-id="9fd13-102">HL7 2.3.1 XML Folders and Events</span></span>
<span data-ttu-id="9fd13-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente de instalación dentro de la carpeta de HL7 versión 2.3.1 para mensajes codificados en XML.</span><span class="sxs-lookup"><span data-stu-id="9fd13-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for XML-encoded messages.</span></span> <span data-ttu-id="9fd13-104">Estas subcarpetas contienen los esquemas utilizados por el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="9fd13-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="9fd13-105">Los nombres de subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="9fd13-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="9fd13-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="9fd13-106">Subfolder</span></span>|<span data-ttu-id="9fd13-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="9fd13-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="9fd13-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="9fd13-108">Patient Administration</span></span>|<span data-ttu-id="9fd13-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="9fd13-109">A01-A51</span></span>|  
|<span data-ttu-id="9fd13-110">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="9fd13-110">Order Entry</span></span>|<span data-ttu-id="9fd13-111">O01, O02, Q06, R0R, RAR, RDR, RER, RGR, V01 V04</span><span class="sxs-lookup"><span data-stu-id="9fd13-111">O01,O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="9fd13-112">Consulta</span><span class="sxs-lookup"><span data-stu-id="9fd13-112">Query</span></span>|<span data-ttu-id="9fd13-113">CNQ, Q01-Q03 Q05, Q07-Q09 R07, R08, R09</span><span class="sxs-lookup"><span data-stu-id="9fd13-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07,R08,R09</span></span>|  
|<span data-ttu-id="9fd13-114">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="9fd13-114">Financial Management</span></span>|<span data-ttu-id="9fd13-115">P01 P06</span><span class="sxs-lookup"><span data-stu-id="9fd13-115">P01-P06</span></span>|  
|<span data-ttu-id="9fd13-116">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="9fd13-116">Observation Reporting</span></span>|<span data-ttu-id="9fd13-117">C01 C12, P06, P07, P09, R01 R06, W01, W02</span><span class="sxs-lookup"><span data-stu-id="9fd13-117">C01-C12,P06,P07,P09,R01-R06, W01,W02</span></span>|  
|<span data-ttu-id="9fd13-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="9fd13-118">Master Files</span></span>|<span data-ttu-id="9fd13-119">M01-M11, MFA</span><span class="sxs-lookup"><span data-stu-id="9fd13-119">M01-M11, MFA</span></span>|  
|<span data-ttu-id="9fd13-120">Administración de registros médicos o información</span><span class="sxs-lookup"><span data-stu-id="9fd13-120">Medical Records/Information Management</span></span>|<span data-ttu-id="9fd13-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="9fd13-121">T01-T12</span></span>|  
|<span data-ttu-id="9fd13-122">Programación</span><span class="sxs-lookup"><span data-stu-id="9fd13-122">Schedule</span></span>|<span data-ttu-id="9fd13-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="9fd13-123">S01-S26</span></span>|  
|<span data-ttu-id="9fd13-124">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="9fd13-124">Patient Referral</span></span>|<span data-ttu-id="9fd13-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="9fd13-125">I01-I15</span></span>|  
|<span data-ttu-id="9fd13-126">Atención al paciente</span><span class="sxs-lookup"><span data-stu-id="9fd13-126">Patient Care</span></span>|<span data-ttu-id="9fd13-127">PC1-PCH, PCJ, PCK, PCL</span><span class="sxs-lookup"><span data-stu-id="9fd13-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="9fd13-128">Administración de red</span><span class="sxs-lookup"><span data-stu-id="9fd13-128">Network Management</span></span>|<span data-ttu-id="9fd13-129">N01, N02</span><span class="sxs-lookup"><span data-stu-id="9fd13-129">N01,N02</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fd13-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fd13-130">See Also</span></span>  
 [<span data-ttu-id="9fd13-131">Uso de esquemas de HL7 2.XML</span><span class="sxs-lookup"><span data-stu-id="9fd13-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
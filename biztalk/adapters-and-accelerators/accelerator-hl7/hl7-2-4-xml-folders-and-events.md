---
title: Eventos y las carpetas de HL7 2.4 XML | Microsoft Docs
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
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7665a5101f5b49abd9ba087bd07cf799384c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993293"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="6ca2a-102">Eventos y las carpetas de HL7 2.4 XML</span><span class="sxs-lookup"><span data-stu-id="6ca2a-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="6ca2a-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente de instalación dentro de la carpeta de HL7 versión 2.4 para mensajes codificados en XML.</span><span class="sxs-lookup"><span data-stu-id="6ca2a-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="6ca2a-104">Estas subcarpetas contienen los esquemas utilizados por el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="6ca2a-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="6ca2a-105">Los nombres de subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="6ca2a-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="6ca2a-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="6ca2a-106">Sub folder</span></span>|<span data-ttu-id="6ca2a-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="6ca2a-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="6ca2a-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="6ca2a-108">Patient Administration</span></span>|<span data-ttu-id="6ca2a-109">A01 A62, K21, K22, K23, K24, Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="6ca2a-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="6ca2a-110">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="6ca2a-110">Order Entry</span></span>|<span data-ttu-id="6ca2a-111">O01 O22, Q06, P26 Q30, RAR, RDR, RER, RGR, ROR, V01 V04, Z73, Z74</span><span class="sxs-lookup"><span data-stu-id="6ca2a-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="6ca2a-112">Consulta</span><span class="sxs-lookup"><span data-stu-id="6ca2a-112">Query</span></span>|<span data-ttu-id="6ca2a-113">J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, P11, RESPUESTA A P13, RESPUESTA A P15 Q17, R07 R09, Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="6ca2a-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="6ca2a-114">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="6ca2a-114">Financial Management</span></span>|<span data-ttu-id="6ca2a-115">P01 ~ P06, P10</span><span class="sxs-lookup"><span data-stu-id="6ca2a-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="6ca2a-116">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="6ca2a-116">Observation Reporting</span></span>|<span data-ttu-id="6ca2a-117">C01 C12, P07, P08, P09, R01, R02, R04, R21, W01, W02</span><span class="sxs-lookup"><span data-stu-id="6ca2a-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="6ca2a-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="6ca2a-118">Master Files</span></span>|<span data-ttu-id="6ca2a-119">M01-M12, MFA</span><span class="sxs-lookup"><span data-stu-id="6ca2a-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="6ca2a-120">Administración de registros médicos o información</span><span class="sxs-lookup"><span data-stu-id="6ca2a-120">Medical Records/Information Management</span></span>|<span data-ttu-id="6ca2a-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="6ca2a-121">T01-T12</span></span>|  
|<span data-ttu-id="6ca2a-122">Programación</span><span class="sxs-lookup"><span data-stu-id="6ca2a-122">Scheduling</span></span>|<span data-ttu-id="6ca2a-123">S01 S26</span><span class="sxs-lookup"><span data-stu-id="6ca2a-123">S01-S26</span></span>|  
|<span data-ttu-id="6ca2a-124">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="6ca2a-124">Patient Referral</span></span>|<span data-ttu-id="6ca2a-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="6ca2a-125">I01-I15</span></span>|  
|<span data-ttu-id="6ca2a-126">Atención al paciente</span><span class="sxs-lookup"><span data-stu-id="6ca2a-126">Patient Care</span></span>|<span data-ttu-id="6ca2a-127">PC1-PCH, PCJ, PCK, PCL</span><span class="sxs-lookup"><span data-stu-id="6ca2a-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="6ca2a-128">Automatización del laboratorio clínica</span><span class="sxs-lookup"><span data-stu-id="6ca2a-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="6ca2a-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="6ca2a-129">U01-U13</span></span>|  
|<span data-ttu-id="6ca2a-130">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6ca2a-130">Application Management</span></span>|<span data-ttu-id="6ca2a-131">N01, N02</span><span class="sxs-lookup"><span data-stu-id="6ca2a-131">N01,N02</span></span>|  
|<span data-ttu-id="6ca2a-132">Administración de personal</span><span class="sxs-lookup"><span data-stu-id="6ca2a-132">Personnel Management</span></span>|<span data-ttu-id="6ca2a-133">B01-B06, K25, Q25</span><span class="sxs-lookup"><span data-stu-id="6ca2a-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ca2a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ca2a-134">See Also</span></span>  
 [<span data-ttu-id="6ca2a-135">Uso de esquemas de HL7 2.XML</span><span class="sxs-lookup"><span data-stu-id="6ca2a-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
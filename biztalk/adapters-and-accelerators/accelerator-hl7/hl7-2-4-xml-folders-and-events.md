---
title: Eventos y las carpetas de 2,4 XML de HL7 | Documentos de Microsoft
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
ms.openlocfilehash: 10c9445a1d5c7978b526fd0347dc6defa3214640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204812"
---
# <a name="hl7-24-xml-folders-and-events"></a><span data-ttu-id="05794-102">Eventos y las carpetas de 2,4 XML HL7</span><span class="sxs-lookup"><span data-stu-id="05794-102">HL7 2.4 XML Folders and Events</span></span>
<span data-ttu-id="05794-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de la versión 2.4 HL7 para mensajes codificados en XML.</span><span class="sxs-lookup"><span data-stu-id="05794-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for XML-encoded messages.</span></span> <span data-ttu-id="05794-104">Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="05794-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="05794-105">Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="05794-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="05794-106">Subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="05794-106">Sub folder</span></span>|<span data-ttu-id="05794-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="05794-107">Events</span></span>|  
|----------------|------------|  
|<span data-ttu-id="05794-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="05794-108">Patient Administration</span></span>|<span data-ttu-id="05794-109">A01 A62, K21, K22, K23, K24, Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="05794-109">A01-A62, K21,K22,K23,K24,Q21-Q24</span></span>|  
|<span data-ttu-id="05794-110">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="05794-110">Order Entry</span></span>|<span data-ttu-id="05794-111">O01 O22, Q06, Q30 P26, RAR, RDR, RER, RGR, ERROR, V01 V04, Z73, Z74</span><span class="sxs-lookup"><span data-stu-id="05794-111">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73, Z74</span></span>|  
|<span data-ttu-id="05794-112">Query</span><span class="sxs-lookup"><span data-stu-id="05794-112">Query</span></span>|<span data-ttu-id="05794-113">J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, PREGUNTA 11, RESPUESTA A P13, RESPUESTA A P15-Q17, R07 R09, Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="05794-113">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="05794-114">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="05794-114">Financial Management</span></span>|<span data-ttu-id="05794-115">P01 ~ P06, P10</span><span class="sxs-lookup"><span data-stu-id="05794-115">P01~P06, P10</span></span>|  
|<span data-ttu-id="05794-116">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="05794-116">Observation Reporting</span></span>|<span data-ttu-id="05794-117">C01 C12, P07, P08, P09, R01, R02, R04, R21, W01, W02</span><span class="sxs-lookup"><span data-stu-id="05794-117">C01-C12, P07,P08,P09, R01,R02,R04, R21, W01, W02</span></span>|  
|<span data-ttu-id="05794-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="05794-118">Master Files</span></span>|<span data-ttu-id="05794-119">M01-M12, MFA</span><span class="sxs-lookup"><span data-stu-id="05794-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="05794-120">Administración de registros/información médica</span><span class="sxs-lookup"><span data-stu-id="05794-120">Medical Records/Information Management</span></span>|<span data-ttu-id="05794-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="05794-121">T01-T12</span></span>|  
|<span data-ttu-id="05794-122">Programación</span><span class="sxs-lookup"><span data-stu-id="05794-122">Scheduling</span></span>|<span data-ttu-id="05794-123">S26 S01</span><span class="sxs-lookup"><span data-stu-id="05794-123">S01-S26</span></span>|  
|<span data-ttu-id="05794-124">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="05794-124">Patient Referral</span></span>|<span data-ttu-id="05794-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="05794-125">I01-I15</span></span>|  
|<span data-ttu-id="05794-126">Atención del paciente</span><span class="sxs-lookup"><span data-stu-id="05794-126">Patient Care</span></span>|<span data-ttu-id="05794-127">PC1-PCH, PCJ, PCK, PCL</span><span class="sxs-lookup"><span data-stu-id="05794-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="05794-128">Automatización de clínicos de laboratorio</span><span class="sxs-lookup"><span data-stu-id="05794-128">Clinical Laboratory Automation</span></span>|<span data-ttu-id="05794-129">U01 U13</span><span class="sxs-lookup"><span data-stu-id="05794-129">U01-U13</span></span>|  
|<span data-ttu-id="05794-130">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="05794-130">Application Management</span></span>|<span data-ttu-id="05794-131">N01, N02</span><span class="sxs-lookup"><span data-stu-id="05794-131">N01,N02</span></span>|  
|<span data-ttu-id="05794-132">Administración del personal</span><span class="sxs-lookup"><span data-stu-id="05794-132">Personnel Management</span></span>|<span data-ttu-id="05794-133">B01-B06, K25, Q25</span><span class="sxs-lookup"><span data-stu-id="05794-133">B01-B06, K25,Q25</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05794-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="05794-134">See Also</span></span>  
 [<span data-ttu-id="05794-135">Uso de esquemas XML de HL7 2.</span><span class="sxs-lookup"><span data-stu-id="05794-135">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
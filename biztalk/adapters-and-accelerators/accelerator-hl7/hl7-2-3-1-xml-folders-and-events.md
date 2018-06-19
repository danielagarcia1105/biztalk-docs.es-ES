---
title: HL7 2.3.1 eventos y las carpetas XML | Documentos de Microsoft
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
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204324"
---
# <a name="hl7-231-xml-folders-and-events"></a><span data-ttu-id="7db79-102">HL7 2.3.1 eventos y las carpetas XML</span><span class="sxs-lookup"><span data-stu-id="7db79-102">HL7 2.3.1 XML Folders and Events</span></span>
<span data-ttu-id="7db79-103">En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de versión 2.3.1 HL7 para mensajes codificados en XML.</span><span class="sxs-lookup"><span data-stu-id="7db79-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for XML-encoded messages.</span></span> <span data-ttu-id="7db79-104">Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="7db79-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="7db79-105">Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="7db79-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="7db79-106">Subcarpeta</span><span class="sxs-lookup"><span data-stu-id="7db79-106">Subfolder</span></span>|<span data-ttu-id="7db79-107">Eventos</span><span class="sxs-lookup"><span data-stu-id="7db79-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="7db79-108">Administración de pacientes</span><span class="sxs-lookup"><span data-stu-id="7db79-108">Patient Administration</span></span>|<span data-ttu-id="7db79-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="7db79-109">A01-A51</span></span>|  
|<span data-ttu-id="7db79-110">Entrada de pedido</span><span class="sxs-lookup"><span data-stu-id="7db79-110">Order Entry</span></span>|<span data-ttu-id="7db79-111">O01, O02, Q06, R0R, RAR, RDR, RER, RGR, V04 V01</span><span class="sxs-lookup"><span data-stu-id="7db79-111">O01,O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="7db79-112">Query</span><span class="sxs-lookup"><span data-stu-id="7db79-112">Query</span></span>|<span data-ttu-id="7db79-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07, R08, R09</span><span class="sxs-lookup"><span data-stu-id="7db79-113">CNQ, Q01-Q03, Q05, Q07-Q09, R07,R08,R09</span></span>|  
|<span data-ttu-id="7db79-114">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="7db79-114">Financial Management</span></span>|<span data-ttu-id="7db79-115">P01 P06</span><span class="sxs-lookup"><span data-stu-id="7db79-115">P01-P06</span></span>|  
|<span data-ttu-id="7db79-116">Informes de observación</span><span class="sxs-lookup"><span data-stu-id="7db79-116">Observation Reporting</span></span>|<span data-ttu-id="7db79-117">C01 C12, P06, P07, P09, R01 R06, W01, W02</span><span class="sxs-lookup"><span data-stu-id="7db79-117">C01-C12,P06,P07,P09,R01-R06, W01,W02</span></span>|  
|<span data-ttu-id="7db79-118">Archivos maestros</span><span class="sxs-lookup"><span data-stu-id="7db79-118">Master Files</span></span>|<span data-ttu-id="7db79-119">M01-M11, MFA</span><span class="sxs-lookup"><span data-stu-id="7db79-119">M01-M11, MFA</span></span>|  
|<span data-ttu-id="7db79-120">Administración de registros/información médica</span><span class="sxs-lookup"><span data-stu-id="7db79-120">Medical Records/Information Management</span></span>|<span data-ttu-id="7db79-121">T01 T12</span><span class="sxs-lookup"><span data-stu-id="7db79-121">T01-T12</span></span>|  
|<span data-ttu-id="7db79-122">Programación</span><span class="sxs-lookup"><span data-stu-id="7db79-122">Schedule</span></span>|<span data-ttu-id="7db79-123">S26 S01</span><span class="sxs-lookup"><span data-stu-id="7db79-123">S01-S26</span></span>|  
|<span data-ttu-id="7db79-124">Referencia de pacientes</span><span class="sxs-lookup"><span data-stu-id="7db79-124">Patient Referral</span></span>|<span data-ttu-id="7db79-125">I01 I15</span><span class="sxs-lookup"><span data-stu-id="7db79-125">I01-I15</span></span>|  
|<span data-ttu-id="7db79-126">Atención del paciente</span><span class="sxs-lookup"><span data-stu-id="7db79-126">Patient Care</span></span>|<span data-ttu-id="7db79-127">PC1-PCH, PCJ, PCK, PCL</span><span class="sxs-lookup"><span data-stu-id="7db79-127">PC1-PCH, PCJ,PCK,PCL</span></span>|  
|<span data-ttu-id="7db79-128">Administración de red</span><span class="sxs-lookup"><span data-stu-id="7db79-128">Network Management</span></span>|<span data-ttu-id="7db79-129">N01, N02</span><span class="sxs-lookup"><span data-stu-id="7db79-129">N01,N02</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7db79-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7db79-130">See Also</span></span>  
 [<span data-ttu-id="7db79-131">Uso de esquemas XML de HL7 2.</span><span class="sxs-lookup"><span data-stu-id="7db79-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)
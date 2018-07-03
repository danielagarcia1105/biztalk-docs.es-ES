---
title: Implementación de PIP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs
- PIPs, element-level constraints
- Document Type Definitions (DTDs)
- PIPs, schemas
- examples, schemas
- schemas, examples
- PIPs, about PIPs
- element-level constraints
- PIPs, DTDs
- schemas, PIPs
- XML Schema Definition files (XSDs)
- Partner Interface Processes (PIPs)
- DTDs, XSDs
- schemas, XSDs
ms.assetid: 0d964223-e0b6-4377-b26a-5fdc89ec81f4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba85938e2e0da2b8ee09de476c81acdf202b449c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983005"
---
# <a name="pip-implementation"></a><span data-ttu-id="f6c92-102">Implementación de PIP</span><span class="sxs-lookup"><span data-stu-id="f6c92-102">PIP Implementation</span></span>
<span data-ttu-id="f6c92-103">Procesos de interfaz de socio (PIP) RosettaNet definir procesos empresariales entre socios comerciales en una cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="f6c92-103">RosettaNet Partner Interface Processes (PIPs) define business processes between trading partners in a supply chain.</span></span> <span data-ttu-id="f6c92-104">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona un conjunto de PIP de cuadro y puede crear PIP adicionales.</span><span class="sxs-lookup"><span data-stu-id="f6c92-104">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides a set of PIPs out-of-the-box and you can create additional PIPs.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f6c92-105"> es compatible con todos los PIP definido por la organización RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="f6c92-105"> supports all PIPs defined by the RosettaNet organization.</span></span>  
  
 <span data-ttu-id="f6c92-106">Para obtener más información, consulte [PIP de RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-106">For more information, see [RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).</span></span>  
  
## <a name="schemas-in-btarn"></a><span data-ttu-id="f6c92-107">Esquemas de BTARN</span><span class="sxs-lookup"><span data-stu-id="f6c92-107">Schemas in BTARN</span></span>  
 <span data-ttu-id="f6c92-108">RosettaNet especifica todos los esquemas de mensaje PIP en forma de definiciones de tipo de documento (DTD).</span><span class="sxs-lookup"><span data-stu-id="f6c92-108">RosettaNet specifies all PIP message schemas in the form of Document Type Definitions (DTDs).</span></span> <span data-ttu-id="f6c92-109">Socios comerciales que participan en el intercambio de documentos de negocio deben cumplir estas DTD.</span><span class="sxs-lookup"><span data-stu-id="f6c92-109">Trading partners who participate in the business-document exchange must comply with these DTDs.</span></span> <span data-ttu-id="f6c92-110">Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa estas DTD como archivos de definición de esquemas XML (XSD), porque Microsoft BizTalk Server representa documentos mediante XSD, no las DTD.</span><span class="sxs-lookup"><span data-stu-id="f6c92-110">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements these DTDs as XML Schema Definition files (XSDs), because Microsoft  BizTalk Server represents documents by using XSDs, not DTDs.</span></span> <span data-ttu-id="f6c92-111">XSD sustituyen a las DTD en términos de funcionalidad y puede representar la mayoría de la información proporcionada en las instrucciones del mensaje de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="f6c92-111">XSDs supersede DTDs in terms of functionality, and can represent most of the information provided in the message guidelines natively.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f6c92-112"> También es compatible con pepitas de próxima generación, recientemente publicadas por la organización RosettaNet, que usan las especificaciones de XSD.</span><span class="sxs-lookup"><span data-stu-id="f6c92-112"> also supports next-generation PIPs, recently published by the RosettaNet organization, that use XSD specifications.</span></span>  
  
 <span data-ttu-id="f6c92-113">Para implementar un PIP nuevo, debe convertir DTD de PIP en XSD.</span><span class="sxs-lookup"><span data-stu-id="f6c92-113">To implement a new PIP, you must convert the PIP's DTD into an XSD.</span></span> <span data-ttu-id="f6c92-114">Descargar la DTD asociada con el PIP desde el sitio RosettaNet Web en [ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859).</span><span class="sxs-lookup"><span data-stu-id="f6c92-114">You download the DTD associated with the PIP from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span> <span data-ttu-id="f6c92-115">A continuación, cree un [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesar el perfil de configuración según el PIP.</span><span class="sxs-lookup"><span data-stu-id="f6c92-115">You then create a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] process configuration profile based on the PIP.</span></span> <span data-ttu-id="f6c92-116">Para obtener más información, consulte [incorpora un nuevo proceso de interfaz de socio](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-116">For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
 <span data-ttu-id="f6c92-117">Puede crear un nuevo perfil de configuración de proceso basado en un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="f6c92-117">You can create a new process configuration profile based on an existing profile.</span></span> <span data-ttu-id="f6c92-118">Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-118">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span> <span data-ttu-id="f6c92-119">Puede crear varios contratos basados en el mismo perfil de configuración de proceso entre los mismos asociados.</span><span class="sxs-lookup"><span data-stu-id="f6c92-119">You can create multiple agreements based on the same process configuration profile between the same partners.</span></span> <span data-ttu-id="f6c92-120">Sin embargo, solo puede activar una de ellas a la vez.</span><span class="sxs-lookup"><span data-stu-id="f6c92-120">However, you can only activate one of them at a time.</span></span> <span data-ttu-id="f6c92-121">Para crear y activar un acuerdo, vea [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-121">To create and activate an agreement, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f6c92-122"> implementa XSD con las restricciones de la directriz de mensaje de RosettaNet para los siguientes encabezados de RosettaNet:</span><span class="sxs-lookup"><span data-stu-id="f6c92-122"> implements XSDs with the RosettaNet message-guideline constraints for the following RosettaNet headers:</span></span>  
  
-   <span data-ttu-id="f6c92-123">Preámbulo para RNIF 1.1 y RNIF 2.01</span><span class="sxs-lookup"><span data-stu-id="f6c92-123">Preamble for RNIF 1.1 and RNIF 2.01</span></span>  
  
-   <span data-ttu-id="f6c92-124">Encabezado de servicio para RNIF 1.1 y RNIF 2.0</span><span class="sxs-lookup"><span data-stu-id="f6c92-124">Service header for RNIF 1.1 and RNIF 2.0</span></span>  
  
-   <span data-ttu-id="f6c92-125">Encabezado de entrega para RNIF 2.0</span><span class="sxs-lookup"><span data-stu-id="f6c92-125">Delivery header for RNIF 2.0</span></span>  
  
-   <span data-ttu-id="f6c92-126">Contenido del servicio para todos los mensajes de señal de RNIF 1.1 y RNIF 2.01.</span><span class="sxs-lookup"><span data-stu-id="f6c92-126">Service content for all signal messages of RNIF 1.1 and RNIF 2.01.</span></span>  
  
## <a name="sample-schemas"></a><span data-ttu-id="f6c92-127">Esquemas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6c92-127">Sample Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="f6c92-128"> el programa de instalación instala un conjunto de PIP en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas.</span><span class="sxs-lookup"><span data-stu-id="f6c92-128"> setup installs a set of PIPs in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span> <span data-ttu-id="f6c92-129">Estos son solo con fines de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f6c92-129">These are for sample purposes only.</span></span> <span data-ttu-id="f6c92-130">Antes de usarlos en producción, se recomienda que comparar estos esquemas con las especificaciones de PIP de RosettaNet publicadas más reciente y directrices de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f6c92-130">Before using them in production, it is highly recommended that you compare these schemas against the latest published RosettaNet PIP specifications and message guidelines.</span></span> <span data-ttu-id="f6c92-131">BTARN admite la implementación de todos los PIP de RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="f6c92-131">BTARN supports implementation of all RosettaNet PIPs.</span></span>  
  
## <a name="element-level-constraints-in-btarn"></a><span data-ttu-id="f6c92-132">Restricciones de nivel de elemento en BTARN</span><span class="sxs-lookup"><span data-stu-id="f6c92-132">Element-Level Constraints in BTARN</span></span>  
 <span data-ttu-id="f6c92-133">En BTARN, implemente las restricciones de nivel de elemento especificadas en los documentos de instrucciones del mensaje PIP con valores de configuración de proceso.</span><span class="sxs-lookup"><span data-stu-id="f6c92-133">In BTARN, you implement the element-level constraints specified in the PIP message-guideline documents as process configuration settings.</span></span> <span data-ttu-id="f6c92-134">Los componentes en tiempo de ejecución usa la configuración del proceso para determinar cómo procesar un PIP específico.</span><span class="sxs-lookup"><span data-stu-id="f6c92-134">Runtime components use the process configuration to determine how to process a specific PIP.</span></span>  
  
 <span data-ttu-id="f6c92-135">Para implementar un PIP nuevo, debe aplicar las restricciones de la directriz de mensaje para el PIP mediante la creación de un nuevo perfil de configuración de proceso.</span><span class="sxs-lookup"><span data-stu-id="f6c92-135">To implement a new PIP, you must apply the message guideline constraints for the PIP by creating a new process configuration profile.</span></span> <span data-ttu-id="f6c92-136">Para ello, en la consola de administración de BTARN.</span><span class="sxs-lookup"><span data-stu-id="f6c92-136">You do this in the BTARN Management Console.</span></span> <span data-ttu-id="f6c92-137">Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-137">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="f6c92-138">El perfil de configuración de proceso se asigna a la especificación de PIP de RosettaNet, como se muestra en [mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f6c92-138">The process configuration profile maps to the RosettaNet PIP specification as shown in [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c92-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6c92-139">See Also</span></span>  
 <span data-ttu-id="f6c92-140">[Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="f6c92-140">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 <span data-ttu-id="f6c92-141">[Acuerdos de socios comerciales](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span><span class="sxs-lookup"><span data-stu-id="f6c92-141">[Trading Partner Agreements](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span></span>  
 [<span data-ttu-id="f6c92-142">PIP de RosettaNet</span><span class="sxs-lookup"><span data-stu-id="f6c92-142">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)

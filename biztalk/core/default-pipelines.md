---
title: Predeterminado canalizaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="default-pipelines"></a><span data-ttu-id="1a32f-102">Canalizaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="1a32f-102">Default Pipelines</span></span>
<span data-ttu-id="1a32f-103">Cuando crea una nueva aplicación, las canalizaciones predeterminadas se crean e implementan de forma predeterminada y aparecen en el ensamblado Microsoft.BizTalk.DefaultPipelines, en la carpeta \References, de todos los proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1a32f-103">When you create a new application, the default pipelines are created and deployed by default and appear in the Microsoft.BizTalk.DefaultPipelines assembly in the \References folder for every BizTalk project.</span></span> <span data-ttu-id="1a32f-104">Las canalizaciones predeterminadas no pueden modificarse en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="1a32f-104">The default pipelines cannot be modified in Pipeline Designer.</span></span> <span data-ttu-id="1a32f-105">Estas canalizaciones se pueden seleccionar al configurar un puerto de envío o una ubicación de recepción en el Explorador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1a32f-105">These pipelines can be selected when configuring a send port or receive location in BizTalk Explorer.</span></span> <span data-ttu-id="1a32f-106">En este tema se describen  las canalizaciones predeterminadas y cuándo deben utilizarse.</span><span class="sxs-lookup"><span data-stu-id="1a32f-106">This topic describes the default pipelines and when to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a32f-107">Las canalizaciones de recepción XML y de envío XML no admiten documentos XML de más de 4 gigabytes.</span><span class="sxs-lookup"><span data-stu-id="1a32f-107">The XML receive and XML send pipelines do not support XML documents larger than 4 gigabytes.</span></span>  
  
## <a name="passthrureceive-pipeline"></a><span data-ttu-id="1a32f-108">Canalización PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="1a32f-108">PassThruReceive pipeline</span></span>  
 <span data-ttu-id="1a32f-109">La canalización de recepción de paso a través no tiene componentes.</span><span class="sxs-lookup"><span data-stu-id="1a32f-109">The pass-through receive pipeline has no components.</span></span> <span data-ttu-id="1a32f-110">Se utiliza para escenarios de paso a través simples cuando no es necesario ningún procesamiento de carga de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a32f-110">It is used for simple pass-through scenarios when no message payload processing is necessary.</span></span> <span data-ttu-id="1a32f-111">Esta canalización se utiliza generalmente cuando se conocen el origen y el destino del mensaje y éste no requiere validación, codificación o desensamblado.</span><span class="sxs-lookup"><span data-stu-id="1a32f-111">This pipeline is generally used when the source and the destination of the message are known, and the message requires no validation, encoding, or disassembling.</span></span> <span data-ttu-id="1a32f-112">Esta canalización suele utilizarse conjuntamente con la canalización de envío de paso a través.</span><span class="sxs-lookup"><span data-stu-id="1a32f-112">This pipeline is commonly used in conjunction with the pass-through send pipeline.</span></span>  
  
 <span data-ttu-id="1a32f-113">Dado que no contiene un desensamblador, la canalización de recepción de paso a través no puede ser utilizada para enrutar mensajes hacia orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="1a32f-113">Because it does not contain a disassembler, the pass-through receive pipeline cannot be used to route messages to orchestrations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a32f-114">La canalización de recepción de paso a través no admite promoción de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1a32f-114">The pass-through receive pipeline does not support property promotion.</span></span>  
  
## <a name="passthrutransmit-pipeline"></a><span data-ttu-id="1a32f-115">Canalización PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="1a32f-115">PassThruTransmit pipeline</span></span>  
 <span data-ttu-id="1a32f-116">La canalización de envío de paso a través no tiene componentes.</span><span class="sxs-lookup"><span data-stu-id="1a32f-116">The pass-through-send pipeline has no components.</span></span> <span data-ttu-id="1a32f-117">Esta canalización se utiliza generalmente cuando no es necesario procesar documentos antes de enviar el mensaje a un destino.</span><span class="sxs-lookup"><span data-stu-id="1a32f-117">This pipeline is generally used when no document processing is necessary before sending the message to a destination.</span></span>  
  
## <a name="xmlreceive-pipeline"></a><span data-ttu-id="1a32f-118">Canalización XMLReceive</span><span class="sxs-lookup"><span data-stu-id="1a32f-118">XMLReceive pipeline</span></span>  
 <span data-ttu-id="1a32f-119">La canalización de recepción XML consta de las siguientes fases:</span><span class="sxs-lookup"><span data-stu-id="1a32f-119">The XML receive pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="1a32f-120">**Descodificar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-120">**Decode.**</span></span> <span data-ttu-id="1a32f-121">Vacía</span><span class="sxs-lookup"><span data-stu-id="1a32f-121">Empty</span></span>  
  
-   <span data-ttu-id="1a32f-122">**Desensamblar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-122">**Disassemble.**</span></span> <span data-ttu-id="1a32f-123">Contiene el componente de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1a32f-123">Contains the XML Disassembler component</span></span>  
  
-   <span data-ttu-id="1a32f-124">**Validar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-124">**Validate.**</span></span> <span data-ttu-id="1a32f-125">Vacía</span><span class="sxs-lookup"><span data-stu-id="1a32f-125">Empty</span></span>  
  
-   <span data-ttu-id="1a32f-126">**ResolveParty.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-126">**ResolveParty.**</span></span> <span data-ttu-id="1a32f-127">Ejecute el componente de resolución de entidades, que resuelve el sujeto del certificado o el Id. de seguridad del remitente para el Id. de entidad.</span><span class="sxs-lookup"><span data-stu-id="1a32f-127">Runs the Party Resolution component, which resolves the certificate subject or the source security ID to the party ID.</span></span>  
  
## <a name="xmltransmit-pipeline"></a><span data-ttu-id="1a32f-128">Canalización XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="1a32f-128">XMLTransmit pipeline</span></span>  
 <span data-ttu-id="1a32f-129">La canalización de envío XML consta de las siguientes fases:</span><span class="sxs-lookup"><span data-stu-id="1a32f-129">The XML send pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="1a32f-130">**Preensamblar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-130">**Pre-assemble.**</span></span> <span data-ttu-id="1a32f-131">Vacía</span><span class="sxs-lookup"><span data-stu-id="1a32f-131">Empty</span></span>  
  
-   <span data-ttu-id="1a32f-132">**Ensamblar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-132">**Assemble.**</span></span> <span data-ttu-id="1a32f-133">Contiene el componente de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="1a32f-133">Contains the XML Assembler component</span></span>  
  
-   <span data-ttu-id="1a32f-134">**Codificar.**</span><span class="sxs-lookup"><span data-stu-id="1a32f-134">**Encode.**</span></span> <span data-ttu-id="1a32f-135">Vacía</span><span class="sxs-lookup"><span data-stu-id="1a32f-135">Empty</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a32f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a32f-136">See Also</span></span>  
 <span data-ttu-id="1a32f-137">[Tipos de canalizaciones](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="1a32f-137">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="1a32f-138">[Tipos de componentes de canalización](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="1a32f-138">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="1a32f-139">[Plantillas de canalización](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="1a32f-139">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="1a32f-140">[Componentes de canalización](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="1a32f-140">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="1a32f-141">Acerca de las canalizaciones, fases y componentes</span><span class="sxs-lookup"><span data-stu-id="1a32f-141">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)
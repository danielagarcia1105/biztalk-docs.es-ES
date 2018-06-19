---
title: Referencia de Microsoft.BizTalk.DefaultPipelines | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ad7cad78e3e8606371a5fa49673297cf590ddbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263412"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a><span data-ttu-id="be00b-102">Referencia de Microsoft.BizTalk.DefaultPipelines</span><span class="sxs-lookup"><span data-stu-id="be00b-102">Microsoft.BizTalk.DefaultPipelines Reference</span></span>
<span data-ttu-id="be00b-103">El **Microsoft.BizTalk.DefaultPipelines** espacio de nombres contiene las siguientes canalizaciones:</span><span class="sxs-lookup"><span data-stu-id="be00b-103">The **Microsoft.BizTalk.DefaultPipelines** namespace contains the following pipelines:</span></span>  
  
-   <span data-ttu-id="be00b-104">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="be00b-104">XMLReceive</span></span>  
  
-   <span data-ttu-id="be00b-105">PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="be00b-105">PassThruReceive</span></span>  
  
-   <span data-ttu-id="be00b-106">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="be00b-106">XMLTransmit</span></span>  
  
-   <span data-ttu-id="be00b-107">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="be00b-107">PassThruTransmit</span></span>  
  
 <span data-ttu-id="be00b-108">Una canalización es un componente de software que define y vincula una o varias fases para procesar los mensajes recibidos o enviados mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be00b-108">A pipeline is a software component that defines and links one or more stages for processing messages received or sent by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="be00b-109">Las canalizaciones incluyen funciones, como la codificación o descodificación, el ensamblado o desensamblado, y el cifrado o descifrado.</span><span class="sxs-lookup"><span data-stu-id="be00b-109">The stages include functions such as encoding or decoding, disassembling or assembling, and decrypting or encrypting.</span></span> <span data-ttu-id="be00b-110">Estas funciones se implementan en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="be00b-110">These functions are implemented in a specific order.</span></span> <span data-ttu-id="be00b-111">La herramienta Diseñador de canalizaciones se utiliza para crear canalizaciones de recepción y de envío.</span><span class="sxs-lookup"><span data-stu-id="be00b-111">You can use Pipeline Designer to create receive and send pipelines.</span></span>  
  
 <span data-ttu-id="be00b-112">Las referencias predeterminadas de canalización incluidas en un proyecto de BizTalk pueden procesar todos los tipos de documentos mediante el **PassThruReceive** y **PassThruTransmit** canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="be00b-112">The default pipeline references included in a BizTalk project can process all types of documents using the **PassThruReceive** and **PassThruTransmit** pipelines.</span></span>  
  
 <span data-ttu-id="be00b-113">En las listas siguientes se muestran los componentes predeterminados de las canalizaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="be00b-113">The following lists show the default components in the default pipelines.</span></span> <span data-ttu-id="be00b-114">En estas listas también se indica el orden predeterminado de los componentes de cada canalización.</span><span class="sxs-lookup"><span data-stu-id="be00b-114">These lists also indicate the default order of the components in each pipeline.</span></span> <span data-ttu-id="be00b-115">Si fuera necesario, puede agregar y eliminar componentes.</span><span class="sxs-lookup"><span data-stu-id="be00b-115">You can add and delete components if necessary.</span></span>  
  
 <span data-ttu-id="be00b-116">Los componentes predeterminados de la canalización XMLReceive predeterminada son:</span><span class="sxs-lookup"><span data-stu-id="be00b-116">The default components in the default XMLReceive pipeline are:</span></span>  
  
-   <span data-ttu-id="be00b-117">Descifrador</span><span class="sxs-lookup"><span data-stu-id="be00b-117">Decrypter</span></span>  
  
-   <span data-ttu-id="be00b-118">Descodificador</span><span class="sxs-lookup"><span data-stu-id="be00b-118">Decoder</span></span>  
  
-   <span data-ttu-id="be00b-119">Desensamblador</span><span class="sxs-lookup"><span data-stu-id="be00b-119">Disassembler</span></span>  
  
-   <span data-ttu-id="be00b-120">Validador</span><span class="sxs-lookup"><span data-stu-id="be00b-120">Validator</span></span>  
  
-   <span data-ttu-id="be00b-121">Resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="be00b-121">Party Resolution</span></span>  
  
 <span data-ttu-id="be00b-122">Los componentes predeterminados de la canalización XMLTransmit predeterminada son:</span><span class="sxs-lookup"><span data-stu-id="be00b-122">The default components in the default XMLTransmit pipeline are:</span></span>  
  
-   <span data-ttu-id="be00b-123">Ensamblador</span><span class="sxs-lookup"><span data-stu-id="be00b-123">Assembler</span></span>  
  
-   <span data-ttu-id="be00b-124">Codificador</span><span class="sxs-lookup"><span data-stu-id="be00b-124">Encoder</span></span>  
  
-   <span data-ttu-id="be00b-125">Cifrador</span><span class="sxs-lookup"><span data-stu-id="be00b-125">Encrypter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be00b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="be00b-126">See Also</span></span>  
 <span data-ttu-id="be00b-127">[Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="be00b-127">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="be00b-128">Referencias de Namespace de BizTalk incluidos en los proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="be00b-128">About BizTalk Namespace References Included in BizTalk Projects</span></span>](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)
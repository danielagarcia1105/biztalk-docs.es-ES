---
title: Procesos públicos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6634a5d5871deac48fad1defbd79fae8f5f384ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210028"
---
# <a name="public-processes"></a><span data-ttu-id="c1153-102">Procesos públicos</span><span class="sxs-lookup"><span data-stu-id="c1153-102">Public Processes</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="c1153-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implementa procesos empresariales que implican la integración con socios comerciales como procesos públicos.</span><span class="sxs-lookup"><span data-stu-id="c1153-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="c1153-104">Implementa los procesos empresariales internos de una organización como procesos privados.</span><span class="sxs-lookup"><span data-stu-id="c1153-104">It implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="c1153-105">Uso de procesos públicos y privados aísla control (en el proceso público) RosettaNet Implementation Framework (RNIF) desde el procesamiento de contenido de servicio y la integración de back-end (en el proceso privado).</span><span class="sxs-lookup"><span data-stu-id="c1153-105">Using public and private processes isolates RosettaNet Implementation Framework (RNIF) handling (in the public process) from the service content processing and back-end integration (in the private process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="c1153-106">implementa procesos públicos como orquestaciones de BizTalk de larga duración.</span><span class="sxs-lookup"><span data-stu-id="c1153-106"> implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="c1153-107">Una orquestación de proceso público se ejecuta en el lado del iniciador y otra, en el lado del servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c1153-107">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="c1153-108">El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación proporciona versiones de iniciador y el contestador orquestaciones de proceso público para RNIF 1.1 y RNIF 2.01.</span><span class="sxs-lookup"><span data-stu-id="c1153-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span>  
  
 <span data-ttu-id="c1153-109">Estas orquestaciones de proceso público implementan todos los procesos RNIF.</span><span class="sxs-lookup"><span data-stu-id="c1153-109">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="c1153-110">Los procesos públicos ocultan la complejidad de RNIF del resto de los componentes.</span><span class="sxs-lookup"><span data-stu-id="c1153-110">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="c1153-111">Además de aplicar el flujo de mensajes compatible con RNIF, el proceso público también determina la configuración de seguimiento predeterminada y proporciona información de estado de proceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1153-111">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at run time.</span></span> <span data-ttu-id="c1153-112">No se procesa el contenido del servicio de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c1153-112">It does not process the service content of a message.</span></span> <span data-ttu-id="c1153-113">Esto hace en el proceso privado.</span><span class="sxs-lookup"><span data-stu-id="c1153-113">The private process does this.</span></span>  
  
 <span data-ttu-id="c1153-114">Cada acuerdo de socio comercial hace referencia a un único proceso público para iniciar o responder a las acciones del proceso de interfaz de socio (PIP).</span><span class="sxs-lookup"><span data-stu-id="c1153-114">Each trading partner agreement references a single public process to initiate or respond to Partner Interface Process (PIP) actions.</span></span> <span data-ttu-id="c1153-115">Sin embargo, los procesos públicos son independientes del PIP.</span><span class="sxs-lookup"><span data-stu-id="c1153-115">However, the public processes are PIP-agnostic.</span></span>  
  
 <span data-ttu-id="c1153-116">Las especificaciones de RosettaNet dictan el diseño del proceso público.</span><span class="sxs-lookup"><span data-stu-id="c1153-116">The RosettaNet specifications dictate the design of the public process.</span></span> <span data-ttu-id="c1153-117">Se recomienda que no modifique un proceso público.</span><span class="sxs-lookup"><span data-stu-id="c1153-117">It is recommended that you do not modify a public process.</span></span> <span data-ttu-id="c1153-118">La orquestación de proceso público es una versión y firmados.</span><span class="sxs-lookup"><span data-stu-id="c1153-118">The public-process orchestration is versioned and signed.</span></span> <span data-ttu-id="c1153-119">Si modifica un proceso público, ya no será compatible con RNIF.</span><span class="sxs-lookup"><span data-stu-id="c1153-119">If you modify a public process, it will no longer be RNIF-compliant.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1153-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1153-120">In This Section</span></span>  
  
-   [<span data-ttu-id="c1153-121">Iniciador de proceso público</span><span class="sxs-lookup"><span data-stu-id="c1153-121">Initiator Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [<span data-ttu-id="c1153-122">Proceso público de servicio de respuesta</span><span class="sxs-lookup"><span data-stu-id="c1153-122">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)
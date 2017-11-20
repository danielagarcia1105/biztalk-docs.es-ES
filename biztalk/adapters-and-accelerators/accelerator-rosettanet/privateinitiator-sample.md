---
title: Ejemplo PrivateInitiator | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d33b164033cdd3b966ed1f0e77dd551cd56076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="privateinitiator-sample"></a><span data-ttu-id="61ce8-102">Ejemplo de PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="61ce8-102">PrivateInitiator Sample</span></span>
<span data-ttu-id="61ce8-103">El ejemplo PrivateInitiator.odx contiene el código para el proceso de iniciador privada instalado por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61ce8-103">The PrivateInitiator.odx sample contains the code for the initiator private process installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="61ce8-104">Se trata de un proceso privado genérico que envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado SQL basado en el adaptador de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="61ce8-104">This is a generic private process that sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="61ce8-105">De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala el ejemplo en \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateInitiator.</span><span class="sxs-lookup"><span data-stu-id="61ce8-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateInitiator.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="61ce8-106">Contenido del ejemplo</span><span class="sxs-lookup"><span data-stu-id="61ce8-106">Sample Contents</span></span>  
 <span data-ttu-id="61ce8-107">El proceso privada de iniciador es el proceso empresarial que es interno al iniciador.</span><span class="sxs-lookup"><span data-stu-id="61ce8-107">The initiator private process is the business process that is internal to the initiator.</span></span> <span data-ttu-id="61ce8-108">El proceso privado proporciona integración de back-end entre el proceso público de iniciador y el programa de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="61ce8-108">The private process provides back-end integration between the initiator public process and the back-end line-of-business program.</span></span> <span data-ttu-id="61ce8-109">El proceso privado de iniciador se comunica con el proceso público para iniciar mensajes.</span><span class="sxs-lookup"><span data-stu-id="61ce8-109">The initiator private process communicates with the public process to initiate messages.</span></span>  
  
 <span data-ttu-id="61ce8-110">El proceso privado iniciador es único para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="61ce8-110">The initiator private process is unique for each implementation.</span></span> <span data-ttu-id="61ce8-111">Puede personalizar el ejemplo PrivateInitiator.odx según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="61ce8-111">You can customize the PrivateInitiator.odx sample for your purposes.</span></span> <span data-ttu-id="61ce8-112">Debe tener cuidado de que se no afecta negativamente al funcionamiento del proceso iniciador pública.</span><span class="sxs-lookup"><span data-stu-id="61ce8-112">You must be careful that you do not adversely affect the functioning of the initiator public process.</span></span>  
  
 <span data-ttu-id="61ce8-113">Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso iniciador privada](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span><span class="sxs-lookup"><span data-stu-id="61ce8-113">For more information, including a description of the message flow, see [Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ce8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="61ce8-114">See Also</span></span>  
 <span data-ttu-id="61ce8-115">[Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="61ce8-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="61ce8-116">Procesos privados</span><span class="sxs-lookup"><span data-stu-id="61ce8-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)
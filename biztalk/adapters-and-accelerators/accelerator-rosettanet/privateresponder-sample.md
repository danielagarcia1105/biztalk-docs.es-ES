---
title: Ejemplo de PrivateResponder | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de3428aa9971ba62b682494cd94c6bb74bcab53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="privateresponder-sample"></a><span data-ttu-id="7706f-102">Ejemplo de PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="7706f-102">PrivateResponder Sample</span></span>
<span data-ttu-id="7706f-103">El ejemplo PrivateResponder.odx contiene el código para el proceso de servicio de respuesta privado instalado por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7706f-103">The PrivateResponder.odx sample contains the code for the responder private process installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="7706f-104">Este proceso privada genérica envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado SQL basado en el adaptador de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="7706f-104">This generic private process sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="7706f-105">De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala el ejemplo en \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="7706f-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="7706f-106">Contenido del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7706f-106">Sample Contents</span></span>  
 <span data-ttu-id="7706f-107">El proceso privada del servicio de respuesta es el proceso empresarial que es interno para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7706f-107">The responder private process is the business process that is internal to the responder.</span></span> <span data-ttu-id="7706f-108">El proceso privado proporciona integración de back-end entre el proceso público de servicio de respuesta y el programa de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="7706f-108">The private process provides back-end integration between the responder public process and the back-end line-of-business program.</span></span> <span data-ttu-id="7706f-109">El proceso privado Respondedor se comunica con el proceso público para responder a mensajes.</span><span class="sxs-lookup"><span data-stu-id="7706f-109">The responder private process communicates with the public process to respond to messages.</span></span>  
  
 <span data-ttu-id="7706f-110">El proceso privada del servicio de respuesta es único para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="7706f-110">The responder private process is unique for each implementation.</span></span> <span data-ttu-id="7706f-111">Puede personalizar el ejemplo PrivateResponder.odx según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="7706f-111">You can customize the PrivateResponder.odx sample for your purposes.</span></span> <span data-ttu-id="7706f-112">Debe tener cuidado de que se no afecta negativamente al funcionamiento del proceso de servicio de respuesta pública.</span><span class="sxs-lookup"><span data-stu-id="7706f-112">You must be careful that you do not adversely affect the functioning of the responder public process.</span></span>  
  
 <span data-ttu-id="7706f-113">Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado de servicio de respuesta](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span><span class="sxs-lookup"><span data-stu-id="7706f-113">For more information, including a description of the message flow, see [Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7706f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7706f-114">See Also</span></span>  
 <span data-ttu-id="7706f-115">[Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="7706f-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="7706f-116">Procesos privados</span><span class="sxs-lookup"><span data-stu-id="7706f-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)
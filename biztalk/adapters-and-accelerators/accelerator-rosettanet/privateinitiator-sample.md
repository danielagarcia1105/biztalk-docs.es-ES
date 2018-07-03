---
title: Ejemplo de PrivateInitiator | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab84d145939191a8bdbca9afb44d04fdf24b3e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011285"
---
# <a name="privateinitiator-sample"></a><span data-ttu-id="3f143-102">Ejemplo de PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="3f143-102">PrivateInitiator Sample</span></span>
<span data-ttu-id="3f143-103">El ejemplo PrivateInitiator.odx contiene el código para el proceso privado del iniciador instalado por Microsoft® BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3f143-103">The PrivateInitiator.odx sample contains the code for the initiator private process installed by Microsoft® BizTalk Server.</span></span> <span data-ttu-id="3f143-104">Se trata de un proceso privado genérico que envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado basado en el adaptador de SQL de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="3f143-104">This is a generic private process that sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="3f143-105">De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el ejemplo de \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateInitiator.</span><span class="sxs-lookup"><span data-stu-id="3f143-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateInitiator.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="3f143-106">Contenido del ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f143-106">Sample Contents</span></span>  
 <span data-ttu-id="3f143-107">Proceso privado del iniciador es el proceso empresarial que es interno al iniciador.</span><span class="sxs-lookup"><span data-stu-id="3f143-107">The initiator private process is the business process that is internal to the initiator.</span></span> <span data-ttu-id="3f143-108">Proceso privado proporciona integración de back-end entre el proceso público del iniciador y el programa de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="3f143-108">The private process provides back-end integration between the initiator public process and the back-end line-of-business program.</span></span> <span data-ttu-id="3f143-109">Proceso privado del iniciador se comunica con el proceso público para iniciar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f143-109">The initiator private process communicates with the public process to initiate messages.</span></span>  
  
 <span data-ttu-id="3f143-110">Proceso privado del iniciador es único para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="3f143-110">The initiator private process is unique for each implementation.</span></span> <span data-ttu-id="3f143-111">Puede personalizar el ejemplo PrivateInitiator.odx para sus fines.</span><span class="sxs-lookup"><span data-stu-id="3f143-111">You can customize the PrivateInitiator.odx sample for your purposes.</span></span> <span data-ttu-id="3f143-112">Debe asegurarse de que se no afectar el funcionamiento del proceso público del iniciador.</span><span class="sxs-lookup"><span data-stu-id="3f143-112">You must be careful that you do not adversely affect the functioning of the initiator public process.</span></span>  
  
 <span data-ttu-id="3f143-113">Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span><span class="sxs-lookup"><span data-stu-id="3f143-113">For more information, including a description of the message flow, see [Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f143-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f143-114">See Also</span></span>  
 <span data-ttu-id="3f143-115">[Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="3f143-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="3f143-116">Procesos privados</span><span class="sxs-lookup"><span data-stu-id="3f143-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)
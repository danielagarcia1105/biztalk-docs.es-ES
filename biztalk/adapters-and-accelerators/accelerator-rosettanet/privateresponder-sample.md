---
title: Ejemplo de PrivateResponder | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2e44157c1b7a4e545bad23c5d9b6dcd9fa87cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986871"
---
# <a name="privateresponder-sample"></a><span data-ttu-id="60f94-102">Ejemplo de PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="60f94-102">PrivateResponder Sample</span></span>
<span data-ttu-id="60f94-103">El ejemplo PrivateResponder.odx contiene el código para el proceso de Respondedor privado instalado por Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60f94-103">The PrivateResponder.odx sample contains the code for the responder private process installed by Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="60f94-104">Este proceso privado genérico envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado basado en el adaptador de SQL de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="60f94-104">This generic private process sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="60f94-105">De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el ejemplo de \< *unidad*>: \Program archivos\\Microsoft BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="60f94-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\Microsoft  BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="60f94-106">Contenido del ejemplo</span><span class="sxs-lookup"><span data-stu-id="60f94-106">Sample Contents</span></span>  
 <span data-ttu-id="60f94-107">El proceso privado del Respondedor es el proceso empresarial que es interno para el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="60f94-107">The responder private process is the business process that is internal to the responder.</span></span> <span data-ttu-id="60f94-108">Proceso privado proporciona integración de back-end entre el proceso público del servicio de respuesta y el programa de línea de negocio de back-end.</span><span class="sxs-lookup"><span data-stu-id="60f94-108">The private process provides back-end integration between the responder public process and the back-end line-of-business program.</span></span> <span data-ttu-id="60f94-109">El proceso privado del Respondedor se comunica con el proceso público para responder a mensajes.</span><span class="sxs-lookup"><span data-stu-id="60f94-109">The responder private process communicates with the public process to respond to messages.</span></span>  
  
 <span data-ttu-id="60f94-110">El proceso privado del Respondedor es único para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="60f94-110">The responder private process is unique for each implementation.</span></span> <span data-ttu-id="60f94-111">Puede personalizar el ejemplo PrivateResponder.odx para sus fines.</span><span class="sxs-lookup"><span data-stu-id="60f94-111">You can customize the PrivateResponder.odx sample for your purposes.</span></span> <span data-ttu-id="60f94-112">Se debe tener cuidado de que no afectar negativamente a que funcione el proceso público del Respondedor.</span><span class="sxs-lookup"><span data-stu-id="60f94-112">You must be careful that you do not adversely affect the functioning of the responder public process.</span></span>  
  
 <span data-ttu-id="60f94-113">Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado del Respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span><span class="sxs-lookup"><span data-stu-id="60f94-113">For more information, including a description of the message flow, see [Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f94-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f94-114">See Also</span></span>  
 <span data-ttu-id="60f94-115">[Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="60f94-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="60f94-116">Procesos privados</span><span class="sxs-lookup"><span data-stu-id="60f94-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)
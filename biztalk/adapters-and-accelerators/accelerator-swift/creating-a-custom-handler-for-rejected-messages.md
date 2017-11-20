---
title: Crear un controlador personalizado para rechazado mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7c2f678bde1d438f352b749eed76b5aa0ab5d7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a><span data-ttu-id="27f42-102">Crear un controlador personalizado para mensajes rechazados</span><span class="sxs-lookup"><span data-stu-id="27f42-102">Creating a Custom Handler for Rejected Messages</span></span>
<span data-ttu-id="27f42-103">Si se rechaza un mensaje en la fase de comprobación o la aprobación, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] devuelve el mensaje a la primera fase definida para el flujo de trabajo (que en este caso es siempre de reparación, incluso si Create es la primera fase del flujo de trabajo).</span><span class="sxs-lookup"><span data-stu-id="27f42-103">If you reject a message in the verification or approval stage, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] returns the message to the first stage defined for the workflow (which in this case is always repair, even if Create is the first stage in the workflow).</span></span> <span data-ttu-id="27f42-104">Sin embargo, si la primera fase del flujo de trabajo rechaza el mensaje, la orquestación de reparación publica el mensaje en el cuadro de mensajes con propiedades promocionadas que indica que la orquestación MrsrRepair rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="27f42-104">However, if the first stage of the workflow rejects the message, the repair orchestration publishes the message to the MessageBox with promoted properties indicating that the MrsrRepair orchestration rejected the message.</span></span> <span data-ttu-id="27f42-105">Para controlar estos mensajes, puede crear un controlador personalizado (orquestación) que se suscribe a estas propiedades promocionadas y procesa los mensajes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="27f42-105">To handle these messages, you can create a custom handler (orchestration) that subscribes to these promoted properties and processes the messages as required.</span></span>  
  
 <span data-ttu-id="27f42-106">Un mensaje puede producir un error en la orquestación MrsrRepair por distintos motivos.</span><span class="sxs-lookup"><span data-stu-id="27f42-106">A message can fail in the MrsrRepair orchestration for multiple reasons.</span></span> <span data-ttu-id="27f42-107">Cuando lo hace, la orquestación promociona las propiedades en la siguiente tabla y asigna estas propiedades, el valor o uno de los valores, que se muestra en la columna derecha de la tabla.</span><span class="sxs-lookup"><span data-stu-id="27f42-107">When it does, the orchestration promotes the properties in the following table, and assigns these properties the value, or one of the values, shown in the right column of the table.</span></span>  
  
|<span data-ttu-id="27f42-108">Propiedad</span><span class="sxs-lookup"><span data-stu-id="27f42-108">Property</span></span>|<span data-ttu-id="27f42-109">Valores</span><span class="sxs-lookup"><span data-stu-id="27f42-109">Values</span></span>|  
|--------------|------------|  
|<span data-ttu-id="27f42-110">BTS. Operación</span><span class="sxs-lookup"><span data-stu-id="27f42-110">BTS.Operation</span></span>|<span data-ttu-id="27f42-111">A4SWIFT_MRSRFailed</span><span class="sxs-lookup"><span data-stu-id="27f42-111">A4SWIFT_MRSRFailed</span></span>|  
|<span data-ttu-id="27f42-112">A4SWIFT_MRSRFailedReason</span><span class="sxs-lookup"><span data-stu-id="27f42-112">A4SWIFT_MRSRFailedReason</span></span>|<span data-ttu-id="27f42-113">Timeout</span><span class="sxs-lookup"><span data-stu-id="27f42-113">Timeout</span></span><br /><br /> <span data-ttu-id="27f42-114">Rechazado (significa que se ha rechazado el mensaje desde la primera fase)</span><span class="sxs-lookup"><span data-stu-id="27f42-114">Rejected (means the message has been rejected from the first stage)</span></span><br /><br /> <span data-ttu-id="27f42-115">CantRepairInInfoPath</span><span class="sxs-lookup"><span data-stu-id="27f42-115">CantRepairInInfoPath</span></span>|  
|<span data-ttu-id="27f42-116">A4SWIFT_MRSRLastStage</span><span class="sxs-lookup"><span data-stu-id="27f42-116">A4SWIFT_MRSRLastStage</span></span>|<span data-ttu-id="27f42-117">\<nombre de la última fase (función) que el mensaje estaba en antes de desistir ></span><span class="sxs-lookup"><span data-stu-id="27f42-117">\<name of last stage (role) that the message was in before failing></span></span>|  
|<span data-ttu-id="27f42-118">A4SWIFT_MRSRDepartment</span><span class="sxs-lookup"><span data-stu-id="27f42-118">A4SWIFT_MRSRDepartment</span></span>|<span data-ttu-id="27f42-119">\<nombre de departamento ></span><span class="sxs-lookup"><span data-stu-id="27f42-119">\<name of department></span></span>|
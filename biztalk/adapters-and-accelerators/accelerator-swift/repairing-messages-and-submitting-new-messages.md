---
title: Reparación de mensajes y envío de mensajes nuevos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569ab44588c2bd89c3533af8cc765e58f743a229
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003317"
---
# <a name="repairing-messages-and-submitting-new-messages"></a><span data-ttu-id="a322d-102">Reparación de mensajes y envío de mensajes nuevos</span><span class="sxs-lookup"><span data-stu-id="a322d-102">Repairing Messages and Submitting New Messages</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a322d-103"> Reparación de mensajes y nuevo envío permite reparar un mensaje que no se pudo validar XML o el motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="a322d-103"> Message Repair and New Submission enables you to repair a message that has failed XML or Business Rules Engine validation.</span></span> <span data-ttu-id="a322d-104">El proceso de reparación incluye pasos de comprobación y aprobación que garantizar la precisión y la adecuación de la reparación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a322d-104">The repair process includes verification and approval steps that ensure the accuracy and appropriateness of the message repair.</span></span> <span data-ttu-id="a322d-105">Este proceso se realiza mediante Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en el sitio MRSR.</span><span class="sxs-lookup"><span data-stu-id="a322d-105">This process is performed using Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms within MRSR site.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a322d-106"> También le permite enviar un mensaje nuevo con este proceso.</span><span class="sxs-lookup"><span data-stu-id="a322d-106"> also enables you to submit a new message using this process.</span></span> <span data-ttu-id="a322d-107">Un creador envía el mensaje y el flujo de trabajo puede incluir un taller de reparación, un comprobador y aprobador realiza las mismas tareas como en la reparación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a322d-107">A creator submits the message, and the workflow can include a repairer, a verifier, and an approver performing the same tasks as in message repair.</span></span>  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a322d-108"> garantiza la seguridad de este proceso mediante la asignación de usuarios diferentes para realizar cada tarea.</span><span class="sxs-lookup"><span data-stu-id="a322d-108"> ensures the security of this process by assigning different users to perform each task.</span></span> <span data-ttu-id="a322d-109">Asignar la reparación correspondiente, compruebe o aprobar rol a cada uno de estos usuarios, y cada usuario debe usar un certificado específico para realizar la tarea.</span><span class="sxs-lookup"><span data-stu-id="a322d-109">You assign the appropriate repair, verify, or approve role to each of these users, and each user must use a specific certificate to perform the task.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a322d-110"> también admite el uso de los departamentos de TI en el procesamiento de mensajes enviados y reparados.</span><span class="sxs-lookup"><span data-stu-id="a322d-110"> also supports the use of departments in processing repaired and submitted messages.</span></span> <span data-ttu-id="a322d-111">Cada departamento implica un flujo de trabajo específico de las tareas realizadas en un conjunto específico de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a322d-111">Each department involves a specific workflow of tasks performed on a specific set of messages.</span></span> <span data-ttu-id="a322d-112">En cualquiera de la creación, reparación, compruebe o aprobar los pasos, al enviar el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] llama a la validación del BRE y comprueba que el usuario es miembro del departamento apropiado.</span><span class="sxs-lookup"><span data-stu-id="a322d-112">In any of the create, repair, verify, or approve steps, when you submit the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] calls BRE validation and verifies that the user is a member of the appropriate department.</span></span> <span data-ttu-id="a322d-113">Para obtener más información acerca de reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a322d-113">For more information about message repair and new submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span>  
  
 <span data-ttu-id="a322d-114">Si recibe un mensaje sin analizar, reparación de mensajes y nuevo envío muestra el mensaje y una descripción del error en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar y le permite imprimir el mensaje o guardarlo en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a322d-114">If you receive an unparsed message, Message Repair and New Submission displays the message and a description of the failure in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, and enables you to print the message or save it to a file.</span></span> <span data-ttu-id="a322d-115">Puede reparar y volver a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a322d-115">You can then repair and resubmit the message.</span></span> <span data-ttu-id="a322d-116">Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no llamar a la validación del BRE o comprobar la pertenencia a un departamento cuando se envía un mensaje sin analizar que se ha reparado.</span><span class="sxs-lookup"><span data-stu-id="a322d-116">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not call BRE validation or check membership in a department when you submit an unparsed message that you have repaired.</span></span> <span data-ttu-id="a322d-117">Además, un mensaje sin analizar reenviado no comprobado o aprobado.</span><span class="sxs-lookup"><span data-stu-id="a322d-117">In addition, a resubmitted unparsed message is not verified or approved.</span></span> <span data-ttu-id="a322d-118">Para obtener más información acerca de los mensajes sin analizar, consulte [reparación de mensajes sin analizar](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a322d-118">For more information about unparsed messages, see [Repairing Unparsed Messages](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).</span></span>  
  
 <span data-ttu-id="a322d-119">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="a322d-119">This section contains:</span></span>  
  
-   [<span data-ttu-id="a322d-120">Reparación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a322d-120">Repairing a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [<span data-ttu-id="a322d-121">Comprobación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a322d-121">Verifying a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [<span data-ttu-id="a322d-122">Aprobación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a322d-122">Approving a Message</span></span>](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [<span data-ttu-id="a322d-123">Administración de un mensaje sin analizar</span><span class="sxs-lookup"><span data-stu-id="a322d-123">Handling an Unparsed Message</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [<span data-ttu-id="a322d-124">Creación y envío de un mensaje nuevo</span><span class="sxs-lookup"><span data-stu-id="a322d-124">Creating and Submitting a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [<span data-ttu-id="a322d-125">Creación de una plantilla de mensaje</span><span class="sxs-lookup"><span data-stu-id="a322d-125">Creating a New Message Template</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)
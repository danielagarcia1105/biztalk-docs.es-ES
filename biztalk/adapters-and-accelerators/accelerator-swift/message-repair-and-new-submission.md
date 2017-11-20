---
title: "Reparación y nuevo envío de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages
- resubmitting messages
- errors, messages
- messages, errors
- messages, resubmitting
ms.assetid: 5bc6bfa2-8210-4dd3-89bb-5455e294ca92
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bc15351848fe68d6ef54c31fc6d58c075bb1c58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-and-new-submission"></a><span data-ttu-id="de5a7-102">Reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="de5a7-102">Message Repair and New Submission</span></span>
<span data-ttu-id="de5a7-103">La característica de reparación de mensajes y nuevo envío de [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona una manera para que pueda reparar MT y MX mensajes que no superan la validación.</span><span class="sxs-lookup"><span data-stu-id="de5a7-103">The Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides a way for you to repair MT and MX messages that fail validation.</span></span> <span data-ttu-id="de5a7-104">Mediante el sitio de SharePoint de MRSR (implementado por el usuario), puede ver cómo el mensaje de error de validación.</span><span class="sxs-lookup"><span data-stu-id="de5a7-104">Using the MRSR SharePoint site (deployed by user), you can see how the message failed validation.</span></span> <span data-ttu-id="de5a7-105">En el sitio MRSR, puede abrir el mensaje en un formulario de InfoPath que permite identificar el error, repare el mensaje y enviarlo para volver a procesar.</span><span class="sxs-lookup"><span data-stu-id="de5a7-105">From MRSR site, you can open the message in an InfoPath form that enables you to identify the error, repair the message, and submit it for reprocessing.</span></span>  
  
 <span data-ttu-id="de5a7-106">Reparación de mensajes y nuevo envío admite la reparación de mensajes basada en roles.</span><span class="sxs-lookup"><span data-stu-id="de5a7-106">Message Repair and New Submission supports role-based message repair.</span></span> <span data-ttu-id="de5a7-107">Un flujo de trabajo de reparación completa incluye la aprobación, comprobación y reparación.</span><span class="sxs-lookup"><span data-stu-id="de5a7-107">A full repair workflow includes repair, verification, and approval.</span></span> <span data-ttu-id="de5a7-108">Un flujo de trabajo de reparación se asocia a un departamento que define los roles (o fases) del flujo de trabajo y configura un usuario de A4SWIFT para cada rol.</span><span class="sxs-lookup"><span data-stu-id="de5a7-108">A repair workflow is associated with a department that defines the roles (or stages) of the workflow and configures an A4SWIFT user for each role.</span></span> <span data-ttu-id="de5a7-109">Cada función de reparación tiene una vista de sitio MRSR independiente adaptada para el rol.</span><span class="sxs-lookup"><span data-stu-id="de5a7-109">Each repair role has a separate MRSR site view tailored to the role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="de5a7-110">realiza la validación y cada usuario de A4SWIFT realizar una firma de función en el mensaje, mediante un certificado, para garantizar un proceso seguro.</span><span class="sxs-lookup"><span data-stu-id="de5a7-110"> performs validation, and each A4SWIFT user performing a role signs the message, using a certificate, to ensure a secure process.</span></span>  
  
 <span data-ttu-id="de5a7-111">Además de reparación de mensajes, A4SWIFT le permite enviar un mensaje nuevo con un mejor [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario.</span><span class="sxs-lookup"><span data-stu-id="de5a7-111">In addition to message repair, A4SWIFT enables you to submit a new message using an enhanced [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="de5a7-112">Un cuarto usuario de A4SWIFT, un creador, realiza esta función.</span><span class="sxs-lookup"><span data-stu-id="de5a7-112">A fourth A4SWIFT user, a creator, performs this function.</span></span> <span data-ttu-id="de5a7-113">El proceso también realiza la validación y puede incluir funciones de reparación, verificación y aprobación para garantizar el envío con éxito.</span><span class="sxs-lookup"><span data-stu-id="de5a7-113">The process also performs validation, and can involve repair, verification, and approval roles to ensure successful submission.</span></span> <span data-ttu-id="de5a7-114">A4SWIFT controla nuevo envío de mensajes a través de un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman la misma manera que controla un mensaje reparado.</span><span class="sxs-lookup"><span data-stu-id="de5a7-114">A4SWIFT handles new message submission through an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form the same way that it handles a repaired message.</span></span>  
  
 <span data-ttu-id="de5a7-115">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="de5a7-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="de5a7-116">Proceso de reparación de mensajes</span><span class="sxs-lookup"><span data-stu-id="de5a7-116">Message Repair Process</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-process.md)  
  
-   [<span data-ttu-id="de5a7-117">Crear Roles y departamentos de reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="de5a7-117">Creating Departments and Roles for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="de5a7-118">Uso de un formulario de InfoPath para reparar un mensaje o envíe un mensaje nuevo</span><span class="sxs-lookup"><span data-stu-id="de5a7-118">Using an InfoPath Form to Repair a Message or Submit a New Message</span></span>](../../adapters-and-accelerators/accelerator-swift/using-an-infopath-form-to-repair-a-message-or-submit-a-new-message.md)  
  
-   [<span data-ttu-id="de5a7-119">Procesamiento especial en la reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="de5a7-119">Special Processing in Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="de5a7-120">Reparación de mensajes sin analizar</span><span class="sxs-lookup"><span data-stu-id="de5a7-120">Repairing Unparsed Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)  
  
-   [<span data-ttu-id="de5a7-121">Reparación de mensajes y nuevo procesamiento de servicio de envío</span><span class="sxs-lookup"><span data-stu-id="de5a7-121">Message Repair and New Submission Service Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-service-processing.md)
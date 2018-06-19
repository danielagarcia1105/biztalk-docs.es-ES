---
title: Seguridad de InfoPath | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ec5478af7c404840bf1c5c80be5520e405bd26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209660"
---
# <a name="infopath-security"></a><span data-ttu-id="6fb7f-102">Seguridad de InfoPath</span><span class="sxs-lookup"><span data-stu-id="6fb7f-102">InfoPath Security</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="6fb7f-103">[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 utiliza firmas XML para permitirle firmar digitalmente un formulario con un certificado digital.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-103"> [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 uses XML Signatures to let you digitally sign a form using a digital certificate.</span></span> <span data-ttu-id="6fb7f-104">Las firmas XML define un estándar para las firmas digitales basado en XML que usan para ayudar a proteger los datos contenidos en documentos XML.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-104">XML Signatures defines a standard for XML-based digital signatures that you use to help secure the data contained in XML documents.</span></span> <span data-ttu-id="6fb7f-105">Las firmas XML es un estándar regido por el World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="6fb7f-105">XML Signatures is a standard governed by the World Wide Web Consortium (W3C).</span></span>  
  
 <span data-ttu-id="6fb7f-106">Una firma digital es una marca de electrónica, basado en el cifrado segura de autenticación en una macro o documento.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-106">A digital signature is an electronic, encryption-based, secure stamp of authentication on a macro or document.</span></span> <span data-ttu-id="6fb7f-107">Al firmar digitalmente un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, la instancia XML especificada a través del formulario se "marca" con una firma digital (firma público resumen de datos de clave y firmados se escribe en un nodo dedicado en el archivo XML).</span><span class="sxs-lookup"><span data-stu-id="6fb7f-107">When digitally signing an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, the XML instance entered through the form is "stamped" with a digital signature (the signature public key and signed data digest is written to a dedicated node in the XML).</span></span> <span data-ttu-id="6fb7f-108">Esta firma confirma que el documento XML original creado por el firmante y no se han modificado.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-108">This signature confirms that the XML document originated from the signer and has not been altered.</span></span> [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]<span data-ttu-id="6fb7f-109">proporciona no segura, puede comprobar la firma, firma parcial, cosigning y contrafirmar mediante la compatibilidad mejorada de firma digital.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-109"> provides verifiable, non-repudiable signing, partial signing, cosigning and countersigning through enhanced digital signature support.</span></span>  
  
 <span data-ttu-id="6fb7f-110">SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionada por A4SWIFT utilizar el método countersigning de firma digital para permitir que las firmas de countersigners estar apilados unos encima de otros.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-110">The SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms generated with the FormGenerator utility provided by A4SWIFT use the countersigning method of digital signing to let signatures of countersigners to be stacked on top of each other.</span></span> <span data-ttu-id="6fb7f-111">Esta pila firma countersigning modela el proceso de crear o editar un mensaje SWIFT, que tengan el mensaje revisado y aprobado por uno o más revisores y aprobadores y finalmente enviar ese mensaje después de todas las fases de un flujo de trabajo centrado en los usuarios haya firmado.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-111">This countersigning signature stack models the human-oriented process of creating or editing a SWIFT message, having the message reviewed and approved by one or more reviewers and approvers, and finally submitting that message only after all stages in a workflow have signed off.</span></span>  
  
 <span data-ttu-id="6fb7f-112">Talleres de reparación, revisores o aprobadores firmar el mensaje independientemente de si aprobarlo o rechazarlo.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-112">Repairers, reviewers, or approvers sign the message regardless of whether they approve or reject it.</span></span> <span data-ttu-id="6fb7f-113">La firma significa la autenticidad de la respuesta y no implica necesariamente una decisión "aceptada".</span><span class="sxs-lookup"><span data-stu-id="6fb7f-113">The signature signifies authenticity of the response and does not necessarily signify an "accepted" decision.</span></span>  
  
 <span data-ttu-id="6fb7f-114">Cuando el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] se envía el formulario, comprueba la validez de los mensajes y que el usuario firma el formulario está en el rol correcto.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-114">When the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form is submitted, it checks messages for validity and that the user signing the form is in the correct role.</span></span>  
  
 <span data-ttu-id="6fb7f-115">Si se rechaza el mensaje en cualquier fase de un flujo de trabajo (además de la reparación), el mensaje se envía a la etapa de reparación.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-115">If the message is rejected at any stage in a workflow (besides repair), the message is sent back to the repair stage.</span></span> <span data-ttu-id="6fb7f-116">Si se rechaza el mensaje en la fase de taller de reparación o creador, reparación de mensajes y nuevo envío envía el mensaje a la instancia de orquestación de reparación de mensajes y nuevo envío con propiedades específicas de marcar el mensaje como rechazado.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-116">If the message is rejected at the repairer or creator stage, Message Repair and New Submission sends the message back to the Message Repair and New Submission orchestration instance with specific properties marking the message as rejected.</span></span>  
  
 <span data-ttu-id="6fb7f-117">Esta sección describe cómo reparación de mensajes y nuevo envío controla las firmas digitales en función de las capacidades definidas para un rol.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-117">This section describes how Message Repair and New Submission handles the digital signatures based on the capabilities defined for a role.</span></span> <span data-ttu-id="6fb7f-118">La combinación de rol y capacidad se denomina una "fase" en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-118">The role and capability combination is called a "stage" in the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fb7f-119">La función "crear" está limitada a un creador de único entre todos los departamentos.</span><span class="sxs-lookup"><span data-stu-id="6fb7f-119">The "create" role is limited to a single creator across all departments.</span></span>  
  
 <span data-ttu-id="6fb7f-120">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="6fb7f-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="6fb7f-121">Crear y etapas de reparación</span><span class="sxs-lookup"><span data-stu-id="6fb7f-121">Create and Repair Stages</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [<span data-ttu-id="6fb7f-122">Regenerar la fase de comprobación</span><span class="sxs-lookup"><span data-stu-id="6fb7f-122">Rekey Verification Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [<span data-ttu-id="6fb7f-123">Fase de aprobación</span><span class="sxs-lookup"><span data-stu-id="6fb7f-123">Approval Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [<span data-ttu-id="6fb7f-124">Distribución de certificados digitales</span><span class="sxs-lookup"><span data-stu-id="6fb7f-124">Distributing Digital Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)
---
title: Seguridad de InfoPath | Microsoft Docs
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
ms.openlocfilehash: ef3b1eff57f225d90e7f491f0a8f48ef88f00463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983581"
---
# <a name="infopath-security"></a><span data-ttu-id="05435-102">Seguridad de InfoPath</span><span class="sxs-lookup"><span data-stu-id="05435-102">InfoPath Security</span></span>
<span data-ttu-id="05435-103">Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 usa las firmas XML para permitirle firmar digitalmente un formulario mediante un certificado digital.</span><span class="sxs-lookup"><span data-stu-id="05435-103">Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 uses XML Signatures to let you digitally sign a form using a digital certificate.</span></span> <span data-ttu-id="05435-104">Las firmas XML define un estándar para las firmas digitales basado en XML que usan para ayudar a proteger los datos contenidos en documentos XML.</span><span class="sxs-lookup"><span data-stu-id="05435-104">XML Signatures defines a standard for XML-based digital signatures that you use to help secure the data contained in XML documents.</span></span> <span data-ttu-id="05435-105">Las firmas XML es un estándar que se rige por el World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="05435-105">XML Signatures is a standard governed by the World Wide Web Consortium (W3C).</span></span>  
  
 <span data-ttu-id="05435-106">Una firma digital es una marca de segura, electrónica basado en el cifrado de autenticación en una macro o documento.</span><span class="sxs-lookup"><span data-stu-id="05435-106">A digital signature is an electronic, encryption-based, secure stamp of authentication on a macro or document.</span></span> <span data-ttu-id="05435-107">Al firmar digitalmente un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, la instancia XML especificada a través del formulario se "marca" con una firma digital (el público de firma síntesis de datos de clave y firmados se escriben en un nodo dedicado en el archivo XML).</span><span class="sxs-lookup"><span data-stu-id="05435-107">When digitally signing an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, the XML instance entered through the form is "stamped" with a digital signature (the signature public key and signed data digest is written to a dedicated node in the XML).</span></span> <span data-ttu-id="05435-108">Esta firma confirma que el documento XML proviene del firmante y no ha sido alterado.</span><span class="sxs-lookup"><span data-stu-id="05435-108">This signature confirms that the XML document originated from the signer and has not been altered.</span></span> [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]<span data-ttu-id="05435-109"> Proporciona segura, puede comprobar la firma, firma parcial, cosigning y contrafirmar mediante la compatibilidad con la firma digital mejorada.</span><span class="sxs-lookup"><span data-stu-id="05435-109"> provides verifiable, non-repudiable signing, partial signing, cosigning and countersigning through enhanced digital signature support.</span></span>  
  
 <span data-ttu-id="05435-110">SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionada por A4SWIFT utilizan el método countersigning de firma digital para permitir que las firmas de countersigners a se apilan unas sobre otras.</span><span class="sxs-lookup"><span data-stu-id="05435-110">The SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms generated with the FormGenerator utility provided by A4SWIFT use the countersigning method of digital signing to let signatures of countersigners to be stacked on top of each other.</span></span> <span data-ttu-id="05435-111">Esta pila firma countersigning modela el proceso orientado al usuario de creación o edición de un mensaje SWIFT, que tengan el mensaje revisado y aprobado por uno o más revisores y aprobadores y, por último, enviar dicho mensaje sólo después de todas las etapas de un flujo de trabajo haya firmado.</span><span class="sxs-lookup"><span data-stu-id="05435-111">This countersigning signature stack models the human-oriented process of creating or editing a SWIFT message, having the message reviewed and approved by one or more reviewers and approvers, and finally submitting that message only after all stages in a workflow have signed off.</span></span>  
  
 <span data-ttu-id="05435-112">Los aprobadores, los revisores o reparadores firmar el mensaje, independientemente de si aprobar o rechazar.</span><span class="sxs-lookup"><span data-stu-id="05435-112">Repairers, reviewers, or approvers sign the message regardless of whether they approve or reject it.</span></span> <span data-ttu-id="05435-113">La firma significa la autenticidad de la respuesta y no indican necesariamente una decisión "aceptada".</span><span class="sxs-lookup"><span data-stu-id="05435-113">The signature signifies authenticity of the response and does not necessarily signify an "accepted" decision.</span></span>  
  
 <span data-ttu-id="05435-114">Cuando el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] se envía el formulario, comprobaciones de validez de los mensajes y que el usuario que firma el formulario está en el rol correcto.</span><span class="sxs-lookup"><span data-stu-id="05435-114">When the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form is submitted, it checks messages for validity and that the user signing the form is in the correct role.</span></span>  
  
 <span data-ttu-id="05435-115">Si se rechaza el mensaje en cualquier etapa del flujo de trabajo (además de reparación), el mensaje se envía a la etapa de reparación.</span><span class="sxs-lookup"><span data-stu-id="05435-115">If the message is rejected at any stage in a workflow (besides repair), the message is sent back to the repair stage.</span></span> <span data-ttu-id="05435-116">Si se rechaza el mensaje en la fase de creador o taller de reparación, reparación de mensajes y nuevo envío envía el mensaje a la instancia de orquestación de reparación de mensajes y nuevo envío con las propiedades específicas de marcar el mensaje como rechazado.</span><span class="sxs-lookup"><span data-stu-id="05435-116">If the message is rejected at the repairer or creator stage, Message Repair and New Submission sends the message back to the Message Repair and New Submission orchestration instance with specific properties marking the message as rejected.</span></span>  
  
 <span data-ttu-id="05435-117">En esta sección se describe cómo controla las firmas digitales en función de las capacidades definidas para un rol de la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="05435-117">This section describes how Message Repair and New Submission handles the digital signatures based on the capabilities defined for a role.</span></span> <span data-ttu-id="05435-118">La combinación de rol y la capacidad se denomina una "fase" en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="05435-118">The role and capability combination is called a "stage" in the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05435-119">La función "crear" está limitada a un creador de único entre todos los departamentos.</span><span class="sxs-lookup"><span data-stu-id="05435-119">The "create" role is limited to a single creator across all departments.</span></span>  
  
 <span data-ttu-id="05435-120">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="05435-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="05435-121">Crear y etapas de reparación</span><span class="sxs-lookup"><span data-stu-id="05435-121">Create and Repair Stages</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [<span data-ttu-id="05435-122">Fase de comprobación de regeneración de claves</span><span class="sxs-lookup"><span data-stu-id="05435-122">Rekey Verification Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [<span data-ttu-id="05435-123">Fase de aprobación</span><span class="sxs-lookup"><span data-stu-id="05435-123">Approval Stage</span></span>](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [<span data-ttu-id="05435-124">Distribución de certificados digitales</span><span class="sxs-lookup"><span data-stu-id="05435-124">Distributing Digital Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)
---
title: "Creación y reparación de fases | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb87112775b9664badf319796e1a6243cf6eb082
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-repairing-stages"></a><span data-ttu-id="ba871-102">Creación y reparación de fases</span><span class="sxs-lookup"><span data-stu-id="ba871-102">Creating and Repairing Stages</span></span>
<span data-ttu-id="ba871-103">La primera etapa en cualquier flujo de trabajo puede ser una fase Create o reparación, es decir, los roles que tienen una capacidad que se define como crean o reparación.</span><span class="sxs-lookup"><span data-stu-id="ba871-103">The first stage in any workflow can be either a Create or Repair stage, that is, roles that have a capability defined as create or repair.</span></span> <span data-ttu-id="ba871-104">El mensaje se origina desde BizTalk MessageBox como un mensaje de error o un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario crea manualmente un mensaje a través de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.</span><span class="sxs-lookup"><span data-stu-id="ba871-104">The message originates from the BizTalk MessageBox as a failed message or an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user manually creates a message through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms.</span></span>  
  
 <span data-ttu-id="ba871-105">El creador del mensaje o taller de reparación original es el primer firmante digital del mensaje y agrega su firma digital para el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario después de crear o reparar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ba871-105">The original message creator or repairer is the first digital signer of the message, and adds his or her digital signature to the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form after creating or repairing the message.</span></span> <span data-ttu-id="ba871-106">Esta primera firma no sólo demuestra la identidad del creador del mensaje o taller de reparación, sino que también bloquea el contenido del mensaje en su estado actual.</span><span class="sxs-lookup"><span data-stu-id="ba871-106">This first signature not only proves the identity of the message creator or repairer, but also locks the contents of the message in its current state.</span></span> <span data-ttu-id="ba871-107">Si se modifica el mensaje después de la primera firma, la pila de firma digital se rompe y advertencias se muestran al usuario que indica que las firmas digitales en el formulario no son válidas.</span><span class="sxs-lookup"><span data-stu-id="ba871-107">If the message is altered after the first signing, the digital signature stack is broken and warnings are shown to the user stating that the digital signatures on the form are invalid.</span></span>
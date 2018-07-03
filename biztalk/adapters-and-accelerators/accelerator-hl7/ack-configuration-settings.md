---
title: Opciones de configuración de ACK | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06cedaee1ca0ad574920cfb646f69d63157c8e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968061"
---
# <a name="ack-configuration-settings"></a><span data-ttu-id="749f5-102">Opciones de configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="749f5-102">ACK Configuration Settings</span></span>
<span data-ttu-id="749f5-103">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] analizador genera las confirmaciones según la configuración de administración de socios comerciales (TPM).</span><span class="sxs-lookup"><span data-stu-id="749f5-103">The Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] parser generates acknowledgments based on Trading Partner Management (TPM) settings.</span></span> <span data-ttu-id="749f5-104">La configuración de confirmación (ACK) es dependiente de la información del partner.</span><span class="sxs-lookup"><span data-stu-id="749f5-104">The acknowledgment (ACK) settings are dependent on partner information.</span></span> <span data-ttu-id="749f5-105">No se utiliza el tipo de esquema.</span><span class="sxs-lookup"><span data-stu-id="749f5-105">Schema type is not used.</span></span> <span data-ttu-id="749f5-106">Cuando [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe un mensaje de confirmación con el campo MSH15 AL, unidades de búsqueda o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede enviar una confirmación para este mensaje en función del resultado de analizar el encabezado de la confirmación y la configuración de TPM.</span><span class="sxs-lookup"><span data-stu-id="749f5-106">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK message with the MSH15 field containing AL, SU or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] may send an ACK for this message based on the result of parsing the ACK header and TPM configuration.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="749f5-107"> Recupera la configuración de confirmación asociado y devuelve uno de cinco los siguientes:</span><span class="sxs-lookup"><span data-stu-id="749f5-107"> retrieves the partner ACK settings and returns one of the following five values:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="749f5-108">La especificación de HL7 exige que utilice elementos 1 a 4 y para rellenar el campo MSH15 de un mensaje de confirmación que genera.</span><span class="sxs-lookup"><span data-stu-id="749f5-108">The HL7 specification mandates that you use items 1 through 4 and to populate the MSH15 field of an ACK message that you generate.</span></span> <span data-ttu-id="749f5-109">Es el elemento 5 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-específico y denota no para generar una confirmación.</span><span class="sxs-lookup"><span data-stu-id="749f5-109">Item 5 is [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-specific and denotes not to generate an ACK.</span></span>  
  
1.  <span data-ttu-id="749f5-110">AL – siempre</span><span class="sxs-lookup"><span data-stu-id="749f5-110">AL – Always</span></span>  
  
2.  <span data-ttu-id="749f5-111">NE: nunca</span><span class="sxs-lookup"><span data-stu-id="749f5-111">NE – Never</span></span>  
  
3.  <span data-ttu-id="749f5-112">Unidades de búsqueda: correcto</span><span class="sxs-lookup"><span data-stu-id="749f5-112">SU – Success</span></span>  
  
4.  <span data-ttu-id="749f5-113">ER: Error</span><span class="sxs-lookup"><span data-stu-id="749f5-113">ER – Error</span></span>  
  
5.  <span data-ttu-id="749f5-114">NO – no generan una confirmación</span><span class="sxs-lookup"><span data-stu-id="749f5-114">NO – Do not generate an ACK</span></span>  
  
## <a name="ack-configuration-inconsistency"></a><span data-ttu-id="749f5-115">Incoherencia de configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="749f5-115">ACK configuration inconsistency</span></span>  
 <span data-ttu-id="749f5-116">En el caso de una incoherencia entre los valores dentro de la instancia de mensaje MSH15 y MSH16 campos y la configuración de interfaz de usuario de configuración de ACK [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación cuando uno de los dos desencadenadores de generación de confirmación lo requieren.</span><span class="sxs-lookup"><span data-stu-id="749f5-116">In the case of inconsistency between the ACK configuration user interface settings and values inside the message instance MSH15 and MSH16 fields, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK when one of the two ACK generation triggers require it.</span></span> <span data-ttu-id="749f5-117">En el caso de otras incoherencias, los datos de la instancia invalidará la configuración en la interfaz de usuario de configuración.</span><span class="sxs-lookup"><span data-stu-id="749f5-117">In the case of other inconsistencies, the data in the instance will override the setting in the configuration user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749f5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="749f5-118">See Also</span></span>  
 <span data-ttu-id="749f5-119">[Configuración de confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="749f5-119">[Configuring Message Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span></span>  
 [<span data-ttu-id="749f5-120">Creación y procesamiento de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="749f5-120">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
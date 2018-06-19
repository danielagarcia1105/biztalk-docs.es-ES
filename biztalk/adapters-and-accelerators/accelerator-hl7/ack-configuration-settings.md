---
title: Opciones de configuración de confirmación | Documentos de Microsoft
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
ms.openlocfilehash: 93dea42fd084f22b4644f0acbb21860d69f75027
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204412"
---
# <a name="ack-configuration-settings"></a><span data-ttu-id="aeebb-102">Opciones de configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="aeebb-102">ACK Configuration Settings</span></span>
<span data-ttu-id="aeebb-103">El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] analizador genera las confirmaciones en función de la configuración de administración de socios comerciales (TPM).</span><span class="sxs-lookup"><span data-stu-id="aeebb-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] parser generates acknowledgments based on Trading Partner Management (TPM) settings.</span></span> <span data-ttu-id="aeebb-104">La configuración de confirmación (ACK) es dependiente de la información de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="aeebb-104">The acknowledgment (ACK) settings are dependent on partner information.</span></span> <span data-ttu-id="aeebb-105">No se utiliza el tipo de esquema.</span><span class="sxs-lookup"><span data-stu-id="aeebb-105">Schema type is not used.</span></span> <span data-ttu-id="aeebb-106">Cuando [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe un mensaje de confirmación con el campo MSH15 AL, SU o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede enviar una confirmación para este mensaje en función del resultado de analizar el encabezado de confirmación y la configuración de TPM.</span><span class="sxs-lookup"><span data-stu-id="aeebb-106">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK message with the MSH15 field containing AL, SU or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] may send an ACK for this message based on the result of parsing the ACK header and TPM configuration.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="aeebb-107">Recupera la configuración de confirmación asociado y devuelve uno de los cinco valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="aeebb-107"> retrieves the partner ACK settings and returns one of the following five values:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aeebb-108">La especificación de HL7 exige que utiliza elementos 1 a 4 y para rellenar el campo MSH15 de un mensaje de confirmación que genera.</span><span class="sxs-lookup"><span data-stu-id="aeebb-108">The HL7 specification mandates that you use items 1 through 4 and to populate the MSH15 field of an ACK message that you generate.</span></span> <span data-ttu-id="aeebb-109">Elemento 5 es [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-específico y denota no para generar una confirmación.</span><span class="sxs-lookup"><span data-stu-id="aeebb-109">Item 5 is [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-specific and denotes not to generate an ACK.</span></span>  
  
1.  <span data-ttu-id="aeebb-110">AL – siempre</span><span class="sxs-lookup"><span data-stu-id="aeebb-110">AL – Always</span></span>  
  
2.  <span data-ttu-id="aeebb-111">NE: nunca</span><span class="sxs-lookup"><span data-stu-id="aeebb-111">NE – Never</span></span>  
  
3.  <span data-ttu-id="aeebb-112">SU: correcto</span><span class="sxs-lookup"><span data-stu-id="aeebb-112">SU – Success</span></span>  
  
4.  <span data-ttu-id="aeebb-113">ER: Error</span><span class="sxs-lookup"><span data-stu-id="aeebb-113">ER – Error</span></span>  
  
5.  <span data-ttu-id="aeebb-114">NO – no generan una confirmación</span><span class="sxs-lookup"><span data-stu-id="aeebb-114">NO – Do not generate an ACK</span></span>  
  
## <a name="ack-configuration-inconsistency"></a><span data-ttu-id="aeebb-115">Incoherencia de configuración de confirmación</span><span class="sxs-lookup"><span data-stu-id="aeebb-115">ACK configuration inconsistency</span></span>  
 <span data-ttu-id="aeebb-116">En el caso de incoherencia entre los valores dentro de la instancia de mensaje MSH15 y MSH16 campos y la configuración de la interfaz de usuario de confirmación configuración [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación cuando uno de los dos desencadenadores de generación de confirmación lo requieren.</span><span class="sxs-lookup"><span data-stu-id="aeebb-116">In the case of inconsistency between the ACK configuration user interface settings and values inside the message instance MSH15 and MSH16 fields, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK when one of the two ACK generation triggers require it.</span></span> <span data-ttu-id="aeebb-117">En el caso de otras incoherencias, los datos de la instancia sobrescribirá la configuración en la interfaz de usuario de configuración.</span><span class="sxs-lookup"><span data-stu-id="aeebb-117">In the case of other inconsistencies, the data in the instance will override the setting in the configuration user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeebb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="aeebb-118">See Also</span></span>  
 <span data-ttu-id="aeebb-119">[Configurar confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="aeebb-119">[Configuring Message Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span></span>  
 [<span data-ttu-id="aeebb-120">Creación y procesamiento de confirmaciones</span><span class="sxs-lookup"><span data-stu-id="aeebb-120">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
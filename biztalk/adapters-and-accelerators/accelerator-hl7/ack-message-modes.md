---
title: Modos de mensaje de confirmación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204404"
---
# <a name="ack-message-modes"></a><span data-ttu-id="fd4ba-102">Modos de mensaje de confirmación</span><span class="sxs-lookup"><span data-stu-id="fd4ba-102">ACK Message Modes</span></span>
<span data-ttu-id="fd4ba-103">Para los mensajes de confirmación (ACK), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determina el modo de confirmación y los valores que se usará para rellenar los campos MSH15 y MSH16 de la confirmación de que desea generar.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-103">For acknowledgment (ACK) messages, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) determines the acknowledgment mode and values to use for populating MSH15 and MSH16 fields of the ACK you want to generate.</span></span> <span data-ttu-id="fd4ba-104">Estos valores están presentes en la configuración de administración de socios comerciales (TPM).</span><span class="sxs-lookup"><span data-stu-id="fd4ba-104">These values are present in the Trading Partner Management (TPM) configuration.</span></span> <span data-ttu-id="fd4ba-105">Los valores siguientes son posibles para el modo de confirmación:</span><span class="sxs-lookup"><span data-stu-id="fd4ba-105">The following values are possible for ACK mode:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4ba-106">En la lista siguiente, la especificación de HL7 exige elementos 1 a 3 y que contienen valores MSH15 y MSH16.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-106">In the following list, the HL7 specification mandates items 1 through 3 and that they contain MSH15 and MSH16 values.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="fd4ba-107">define el elemento 4 para indicar que no se debe generar una confirmación.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-107"> defines item 4 to signify that an acknowledgment should not be generated.</span></span>  
  
1.  <span data-ttu-id="fd4ba-108">Original: una confirmación enviado después de validar el encabezado y el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-108">Original - One ACK sent after validating the header and body.</span></span> <span data-ttu-id="fd4ba-109">Este modo implica la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-109">This mode involves schema validation.</span></span>  
  
2.  <span data-ttu-id="fd4ba-110">Mejorado - dos mensajes de confirmación enviados:</span><span class="sxs-lookup"><span data-stu-id="fd4ba-110">Enhanced - Two ACK messages sent:</span></span>  
  
    -   <span data-ttu-id="fd4ba-111">Aceptar confirmación – el sistema receptor envía este tipo de confirmación después de la validación del encabezado.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-111">Accept ACK – The receiving system sends this type of ACK after validation of the header.</span></span> <span data-ttu-id="fd4ba-112">Esta confirmación señala a la aplicación iniciadora que el mensaje se compromete a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-112">This ACK signals to the initiating application that the message is committed to the database.</span></span>  
  
    -   <span data-ttu-id="fd4ba-113">Sistema de recepción de confirmación-la aplicación envía este tipo de confirmación después de la validación del mensaje completo, incluido el encabezado y el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-113">Application ACK- The receiving system sends this type of ACK after complete message validation, including the header and the body.</span></span>  
  
3.  <span data-ttu-id="fd4ba-114">Aplazado - dos mensajes de confirmación enviados.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-114">Deferred - Two ACK messages sent.</span></span>  
  
    -   <span data-ttu-id="fd4ba-115">Modo original: El sistema receptor envía este tipo de confirmación después de la validación del encabezado y cuerpo.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-115">Original Mode: The receiving system sends this type of ACK after validation of the header and body.</span></span> <span data-ttu-id="fd4ba-116">Este modo implica la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-116">This mode involves schema validation.</span></span>  
  
    -   <span data-ttu-id="fd4ba-117">Modo diferido: La aplicación de línea de negocio reconoce el mensaje después de procesarlo.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-117">Deferred Mode: The line-of-business application acknowledges the message after processing it.</span></span> <span data-ttu-id="fd4ba-118">La aplicación entrega el mensaje diferido a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], que lo procesa como un mensaje independiente y lo entrega al destino.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-118">The application delivers the deferred message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], which process it as a stand-alone message and delivers it to the destination.</span></span>  
  
4.  <span data-ttu-id="fd4ba-119">Estático - un correctamente o en caso de error enviado de confirmación.</span><span class="sxs-lookup"><span data-stu-id="fd4ba-119">Static - An on success or on failure ACK sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4ba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd4ba-120">See Also</span></span>  
 <span data-ttu-id="fd4ba-121">[Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="fd4ba-121">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="fd4ba-122">[Guía de programación](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="fd4ba-122">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 <span data-ttu-id="fd4ba-123">[Modelo de proceso de confirmación](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span><span class="sxs-lookup"><span data-stu-id="fd4ba-123">[ACK Process Model](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md) </span></span>  
 [<span data-ttu-id="fd4ba-124">Confirmaciones estáticas</span><span class="sxs-lookup"><span data-stu-id="fd4ba-124">Static Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)
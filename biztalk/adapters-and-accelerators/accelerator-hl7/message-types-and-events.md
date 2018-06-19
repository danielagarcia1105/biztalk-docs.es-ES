---
title: Tipos y eventos de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9880da0ca5fea84c5a2b3d6e9f3a43ace41970
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205956"
---
# <a name="message-types-and-events"></a><span data-ttu-id="3d51a-102">Eventos y los tipos de mensaje</span><span class="sxs-lookup"><span data-stu-id="3d51a-102">Message Types and Events</span></span>
<span data-ttu-id="3d51a-103">El estándar HL7 agrupan mensajes relacionados con un agrupamiento de eventos reales juntos como *tipo de mensaje* ADT.</span><span class="sxs-lookup"><span data-stu-id="3d51a-103">The HL7 standard has grouped messages that relate to a particular grouping of real-world events together as *message type* ADT.</span></span> <span data-ttu-id="3d51a-104">Estos mensajes implican los eventos de desencadenador, como administración de pacientes.</span><span class="sxs-lookup"><span data-stu-id="3d51a-104">These messages involve trigger events, such as patient administration.</span></span> <span data-ttu-id="3d51a-105">Versión 2.4 del estándar HL7 define más de 100 tipos de mensajes, cada uno de los cuales el HL7 organización le ha asignado un código de tipo de mensaje de tres caracteres únicos.</span><span class="sxs-lookup"><span data-stu-id="3d51a-105">Version 2.4 of the HL7 standard defines more than 100 message types, each of which the HL7 organization has assigned a unique three-character message type code.</span></span> <span data-ttu-id="3d51a-106">Tal y como han evolucionado versiones del estándar HL7, la organización de HL7 ha agregado nuevos tipos de mensajes para proporcionar nuevas capacidades.</span><span class="sxs-lookup"><span data-stu-id="3d51a-106">As versions of the HL7 standard have evolved, the HL7 organization has added new message types to provide new capabilities.</span></span>  
  
 <span data-ttu-id="3d51a-107">Todos los tipos de mensaje contienen eventos de mensaje, también denominados *eventos*.</span><span class="sxs-lookup"><span data-stu-id="3d51a-107">All message types contain message events, also called *events*.</span></span> <span data-ttu-id="3d51a-108">Se puede considerar un evento como un único tipo de mensaje agrupado dentro de un tipo de mensaje determinado.</span><span class="sxs-lookup"><span data-stu-id="3d51a-108">You can think of an event as a unique type of message grouped within a particular message type.</span></span> <span data-ttu-id="3d51a-109">Por ejemplo, la notificación de administración/visita (evento de mensaje A01) y la descarga/End visite (evento de mensaje A03) son mensajes únicos contenidos por el tipo de mensaje de administración de paciente (ADT).</span><span class="sxs-lookup"><span data-stu-id="3d51a-109">For example, the Admin/Visit Notification (message event A01) and Discharge/End Visit (message event A03) are unique messages contained by the Patient Administration message type (ADT).</span></span> <span data-ttu-id="3d51a-110">La organización de HL7 asignó a cada evento de mensaje de un código de evento único de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="3d51a-110">The HL7 organization has assigned each message event a unique three-character event code.</span></span>  
  
 <span data-ttu-id="3d51a-111">Tipo de solo mensaje puede contener un evento de mensaje determinado.</span><span class="sxs-lookup"><span data-stu-id="3d51a-111">Only one message type can contain a particular message event.</span></span> <span data-ttu-id="3d51a-112">Tipos de mensaje pueden contener varios eventos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3d51a-112">Message types can contain multiple message events.</span></span> <span data-ttu-id="3d51a-113">Sin embargo, la estructura de un evento de mensaje determinado puede variar entre las versiones del estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="3d51a-113">However, the structure of a particular message event can vary between versions of the HL7 standard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d51a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d51a-114">See Also</span></span>  
 <span data-ttu-id="3d51a-115">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3d51a-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3d51a-116">[Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3d51a-116">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="3d51a-117">[Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3d51a-117">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="3d51a-118">[Desencadenar eventos y mensajes](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3d51a-118">[Trigger Events and Messages](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span></span>  
 [<span data-ttu-id="3d51a-119">Mensajería HL7</span><span class="sxs-lookup"><span data-stu-id="3d51a-119">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
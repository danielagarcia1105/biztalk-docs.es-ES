---
title: Modos de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfce63f527dbe9643228b3b47a509b404e78c510
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009141"
---
# <a name="message-modes"></a><span data-ttu-id="3e024-102">Modos de mensaje</span><span class="sxs-lookup"><span data-stu-id="3e024-102">Message Modes</span></span>
<span data-ttu-id="3e024-103">Hay dos conceptos básicos que subyacen a todos los mensajes de HL7.</span><span class="sxs-lookup"><span data-stu-id="3e024-103">There are two basic concepts that underlie all HL7 messages.</span></span> <span data-ttu-id="3e024-104">Estos conceptos de direcciones distintas formas en que pueden interactuar sistemas independientes que intercambiar datos y proporcionan una estructura que admita los requisitos de interoperabilidad con el tiempo dentro de un sistema distribuido de atención médica.</span><span class="sxs-lookup"><span data-stu-id="3e024-104">These concepts address different ways in which independent systems that exchange data can interact, and provide a structure that supports the requirements of interoperability over time within a distributed health care system.</span></span> <span data-ttu-id="3e024-105">Los conceptos descritos a continuación definen los temas subyacentes tras el diseño de HL7:</span><span class="sxs-lookup"><span data-stu-id="3e024-105">The concepts listed below define the underlying themes behind the HL7 design:</span></span>  
  
- <span data-ttu-id="3e024-106">**Modo de mensajería**.</span><span class="sxs-lookup"><span data-stu-id="3e024-106">**Messaging Mode**.</span></span> <span data-ttu-id="3e024-107">El reconocimiento de los tres objetivos fundamentales para el intercambio de información: para difundir información (declarativo), para solicitar información (interrogative) y para solicitar que el sistema tome las acciones (imperativo).</span><span class="sxs-lookup"><span data-stu-id="3e024-107">The recognition of three fundamental purposes for information exchange: to broadcast information (declarative), to request information (interrogative), and to request that the system take an action (imperative).</span></span> <span data-ttu-id="3e024-108">Cada uno de estos propósitos tiene sus requisitos específicos y el patrón de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3e024-108">Each of these purposes has its particular requirements and pattern of message flow.</span></span>  
  
- <span data-ttu-id="3e024-109">**Modo de confirmación**.</span><span class="sxs-lookup"><span data-stu-id="3e024-109">**Acknowledgment Mode**.</span></span> <span data-ttu-id="3e024-110">La necesidad de admitir estrechamente y escasamente acoplado estilos de mensajería.</span><span class="sxs-lookup"><span data-stu-id="3e024-110">The need to support tightly and loosely coupled styles of messaging.</span></span> <span data-ttu-id="3e024-111">Los modos de confirmación para HL7 habilitar una aplicación de envío para solicitar una respuesta desde el receptor, o para habilitar la red subyacente garantizar la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3e024-111">The acknowledgment modes for HL7 enable a sending application either to require a response from the receiver, or to enable the underlying network to guarantee message delivery.</span></span>  
  
- <span data-ttu-id="3e024-112">**Localización**.</span><span class="sxs-lookup"><span data-stu-id="3e024-112">**Localization**.</span></span> <span data-ttu-id="3e024-113">La necesidad de admitir requisitos locales específicos al permitir que las entidades introducir material específica del sitio en las especificaciones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3e024-113">The need to support specific local requirements by allowing entities to introduce site-specific material into message specifications.</span></span>  
  
- <span data-ttu-id="3e024-114">**Evolución**.</span><span class="sxs-lookup"><span data-stu-id="3e024-114">**Evolution**.</span></span> <span data-ttu-id="3e024-115">La necesidad de admitir sitios con muchas interfaces y muchas aplicaciones habilitando la interoperabilidad entre versiones estándares.</span><span class="sxs-lookup"><span data-stu-id="3e024-115">The need to support sites with many interfaces and many applications by enabling interoperability between standard versions.</span></span> <span data-ttu-id="3e024-116">Esto permite que las entidades a las actualizaciones de interfaz de fase, en lugar de requerir actualizaciones simultáneas de todas las interfaces.</span><span class="sxs-lookup"><span data-stu-id="3e024-116">This enables entities to stage interface upgrades, as opposed to requiring simultaneous upgrades of all interfaces.</span></span>  
  
  <span data-ttu-id="3e024-117">Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admite los requisitos anteriores:</span><span class="sxs-lookup"><span data-stu-id="3e024-117">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support the above requirements:</span></span>  
  
- <span data-ttu-id="3e024-118">Modos de confirmación de HL7.</span><span class="sxs-lookup"><span data-stu-id="3e024-118">HL7 acknowledgment modes.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="3e024-119"> admite el modo de confirmación original pasando las confirmaciones de la aplicación al remitente del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="3e024-119"> supports the original acknowledgment mode by passing application acknowledgments back to the original message sender.</span></span>  
  
- <span data-ttu-id="3e024-120">Diferentes modos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3e024-120">Different messaging modes.</span></span> <span data-ttu-id="3e024-121">Esto permite la difusión a varios destinos y une las consultas a la respuesta de consultas asociado.</span><span class="sxs-lookup"><span data-stu-id="3e024-121">This enables broadcast to multiple destinations, and ties together queries to the associated query response.</span></span>  
  
- <span data-ttu-id="3e024-122">Compatibilidad con varias versiones, incluido XML y las codificaciones están delimitados por canalización.</span><span class="sxs-lookup"><span data-stu-id="3e024-122">Support for multiple versions, including XML and pipe-delimited encodings.</span></span>  
  
- <span data-ttu-id="3e024-123">Asignación entre las versiones de HL7 para habilitar diversos entornos y las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="3e024-123">Mapping between HL7 versions to enable diverse environments and upgrades.</span></span>  
  
- <span data-ttu-id="3e024-124">Localización (personalización) dentro de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="3e024-124">Localization (customization) within orchestration.</span></span>  
  
- <span data-ttu-id="3e024-125">Herramientas para admitir la depuración y la evaluación de las nuevas interfaces.</span><span class="sxs-lookup"><span data-stu-id="3e024-125">Tools to support debugging and evaluation of new interfaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e024-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e024-126">See Also</span></span>  
 <span data-ttu-id="3e024-127">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3e024-127">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3e024-128">[Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3e024-128">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="3e024-129">[Uso de esquemas de HL7 2.Xml](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3e024-129">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="3e024-130">[Tipos de mensajes y eventos](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="3e024-130">[Message Types and Events](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span></span>  
 [<span data-ttu-id="3e024-131">Mensajería de HL7</span><span class="sxs-lookup"><span data-stu-id="3e024-131">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
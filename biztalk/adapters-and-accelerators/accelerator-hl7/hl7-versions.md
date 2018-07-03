---
title: HL7 Versiones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3806ed8db2272068ff60c6656b73cdf4a726bd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005901"
---
# <a name="hl7-versions"></a><span data-ttu-id="1afe3-102">Versiones de HL7</span><span class="sxs-lookup"><span data-stu-id="1afe3-102">HL7 Versions</span></span>
<span data-ttu-id="1afe3-103">HL7 versión 2 es una familia de estándares estrechamente relacionados, en lugar de un único estándar.</span><span class="sxs-lookup"><span data-stu-id="1afe3-103">HL7 Version 2 is a family of closely related standards rather than a single standard.</span></span> <span data-ttu-id="1afe3-104">La organización de HL7 ha diseñado estos estándares para ser hacia arriba compatibles a través de la aplicación de las reglas de compatibilidad entre versiones de HL7.</span><span class="sxs-lookup"><span data-stu-id="1afe3-104">The HL7 organization has designed these standards to be upwards compatible through the application of the HL7 inter-version compatibility rules.</span></span> <span data-ttu-id="1afe3-105">Estas reglas garantizan que, dentro de los confines de la versión 2, una interfaz definida en las reglas de una versión de HL7 seguirán funcionando en la definición de las versiones de sucesor.</span><span class="sxs-lookup"><span data-stu-id="1afe3-105">These rules guarantee that, within the confines of Version 2, an interface defined under the rules of an HL7 version will still function within the definition of successor versions.</span></span> <span data-ttu-id="1afe3-106">Para que un sistema receptor podrá aceptar mensajes de las versiones posteriores sin interrumpir su implementación y el envío de un sistema podrá continuar enviando mensajes a los receptores que admiten las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1afe3-106">So that a receiving system will be able to accept messages from later versions without breaking its implementation and a sending system will be able to continue to send messages to receivers who support later versions.</span></span>  
  
 <span data-ttu-id="1afe3-107">Es importante tener en cuenta que Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="1afe3-107">It is important to note that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span></span>  
  
- <span data-ttu-id="1afe3-108">Admite todas las versiones de HL7 en directo desde la versión 2.1 a través de la versión 2.5</span><span class="sxs-lookup"><span data-stu-id="1afe3-108">Supports all live HL7 versions from Version 2.1 through Version 2.5</span></span>  
  
- <span data-ttu-id="1afe3-109">Proporciona la funcionalidad necesaria para la asignación entre las versiones de HL7 y permite la interoperabilidad de varias versiones en un único sitio</span><span class="sxs-lookup"><span data-stu-id="1afe3-109">Provides the functionality needed to map between HL7 versions, and enables the interoperability of multiple versions at a single site</span></span>  
  
- <span data-ttu-id="1afe3-110">Admite la localización de admitiendo los segmentos de Z y permite la asignación entre las interpretaciones alternativas o usos de los mensajes estándares</span><span class="sxs-lookup"><span data-stu-id="1afe3-110">Supports localization by supporting Z segments, and enables mapping between alternate interpretations or uses of the standard messages</span></span>  
  
  <span data-ttu-id="1afe3-111">Es importante tener en cuenta la diferencia entre las versiones del estándar de mensajería:</span><span class="sxs-lookup"><span data-stu-id="1afe3-111">It is important to note the difference between the versions of the messaging standard:</span></span>  
  
- <span data-ttu-id="1afe3-112">Versión 1 funcionaba como una prueba de concepto</span><span class="sxs-lookup"><span data-stu-id="1afe3-112">Version 1 functioned as a proof of concept</span></span>  
  
- <span data-ttu-id="1afe3-113">Versión 2 le proporciona una colección de especificaciones de mensaje para admitir el intercambio de mensajes entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1afe3-113">Version 2 provides a collection of message specifications to support message exchange between applications</span></span>  
  
- <span data-ttu-id="1afe3-114">Versión 3 proporcionará un conjunto integrado de especificaciones para admitir una variedad de necesidades de interoperabilidad basados en modelo</span><span class="sxs-lookup"><span data-stu-id="1afe3-114">Version 3 will provide a model-based integrated set of specifications to support a range of interoperability needs</span></span>  
  
  <span data-ttu-id="1afe3-115">En esencia, versión 2 se centra en un método pragmático para proporcionar a los usuarios con las especificaciones que necesitan para llevar a cabo las tareas especificadas, aunque versión 3 se centra en garantizar la coherencia y extensibilidad a largo plazo para el cuerpo de las especificaciones de mensaje que se toma como un entero.</span><span class="sxs-lookup"><span data-stu-id="1afe3-115">In essence, Version 2 focuses on a pragmatic approach to providing users with the specifications they need to carry out specified tasks, while Version 3 focuses on assuring consistency and long-term extensibility for the body of message specifications taken as a whole.</span></span>  
  
  <span data-ttu-id="1afe3-116">La arquitectura de documento clínico proporciona una extensión importante para el estándar HL7 mediante la introducción de estándares para la representación de documentos clínicos mediante XML.</span><span class="sxs-lookup"><span data-stu-id="1afe3-116">The Clinical Document Architecture provides a significant extension to the HL7 standard by introducing standards for the representation of clinical documents using XML.</span></span>  
  
  <span data-ttu-id="1afe3-117">En la tabla siguiente se muestra la progresión de desarrollo estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="1afe3-117">The following table shows the HL7 standard development progression.</span></span>  
  
|<span data-ttu-id="1afe3-118">Evento</span><span class="sxs-lookup"><span data-stu-id="1afe3-118">Event</span></span>|<span data-ttu-id="1afe3-119">Year</span><span class="sxs-lookup"><span data-stu-id="1afe3-119">Year</span></span>|<span data-ttu-id="1afe3-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="1afe3-120">Details</span></span>|  
|-----------|----------|-------------|  
|<span data-ttu-id="1afe3-121">Fundada de HL7</span><span class="sxs-lookup"><span data-stu-id="1afe3-121">HL7 Founded</span></span>|<span data-ttu-id="1afe3-122">1987</span><span class="sxs-lookup"><span data-stu-id="1afe3-122">1987</span></span>|<span data-ttu-id="1afe3-123">La primera reunión, en Stanford, CA, que incluye a 12 asistentes.</span><span class="sxs-lookup"><span data-stu-id="1afe3-123">The first meeting, in Stanford, CA, included 12 attendees.</span></span>|  
|<span data-ttu-id="1afe3-124">V1.0</span><span class="sxs-lookup"><span data-stu-id="1afe3-124">V1.0</span></span>|<span data-ttu-id="1afe3-125">1987</span><span class="sxs-lookup"><span data-stu-id="1afe3-125">1987</span></span>|<span data-ttu-id="1afe3-126">Borrador presentado a HL7 pleno reunión.</span><span class="sxs-lookup"><span data-stu-id="1afe3-126">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="1afe3-127">VERSIÓN 2.0</span><span class="sxs-lookup"><span data-stu-id="1afe3-127">V2.0</span></span>|<span data-ttu-id="1afe3-128">1988</span><span class="sxs-lookup"><span data-stu-id="1afe3-128">1988</span></span>|<span data-ttu-id="1afe3-129">Borrador presentado a HL7 pleno reunión.</span><span class="sxs-lookup"><span data-stu-id="1afe3-129">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="1afe3-130">V2.1 publicado</span><span class="sxs-lookup"><span data-stu-id="1afe3-130">V2.1 published</span></span>|<span data-ttu-id="1afe3-131">1990</span><span class="sxs-lookup"><span data-stu-id="1afe3-131">1990</span></span>|<span data-ttu-id="1afe3-132">La primera ampliamente implementado versión</span><span class="sxs-lookup"><span data-stu-id="1afe3-132">The first widely implemented version</span></span>|  
|<span data-ttu-id="1afe3-133">V2.2 publicar</span><span class="sxs-lookup"><span data-stu-id="1afe3-133">V2.2 published</span></span>|<span data-ttu-id="1afe3-134">1994</span><span class="sxs-lookup"><span data-stu-id="1afe3-134">1994</span></span>||  
|<span data-ttu-id="1afe3-135">V.2.3 publicado</span><span class="sxs-lookup"><span data-stu-id="1afe3-135">V.2.3 published</span></span>|<span data-ttu-id="1afe3-136">1997</span><span class="sxs-lookup"><span data-stu-id="1afe3-136">1997</span></span>|<span data-ttu-id="1afe3-137">ANSI aprobado</span><span class="sxs-lookup"><span data-stu-id="1afe3-137">ANSI approved</span></span>|  
|<span data-ttu-id="1afe3-138">V2.3.1 publicado</span><span class="sxs-lookup"><span data-stu-id="1afe3-138">V2.3.1 published</span></span>|<span data-ttu-id="1afe3-139">1999</span><span class="sxs-lookup"><span data-stu-id="1afe3-139">1999</span></span>|<span data-ttu-id="1afe3-140">ANSI aprobado</span><span class="sxs-lookup"><span data-stu-id="1afe3-140">ANSI approved</span></span>|  
|<span data-ttu-id="1afe3-141">V2.4 publicado</span><span class="sxs-lookup"><span data-stu-id="1afe3-141">V2.4 published</span></span>|<span data-ttu-id="1afe3-142">2000</span><span class="sxs-lookup"><span data-stu-id="1afe3-142">2000</span></span>|<span data-ttu-id="1afe3-143">ANSI aprobado</span><span class="sxs-lookup"><span data-stu-id="1afe3-143">ANSI approved</span></span>|  
|<span data-ttu-id="1afe3-144">Arquitectura de documento clínico</span><span class="sxs-lookup"><span data-stu-id="1afe3-144">Clinical Document Architecture</span></span>|<span data-ttu-id="1afe3-145">2000</span><span class="sxs-lookup"><span data-stu-id="1afe3-145">2000</span></span>|<span data-ttu-id="1afe3-146">ANSI aprobado</span><span class="sxs-lookup"><span data-stu-id="1afe3-146">ANSI approved</span></span>|  
|<span data-ttu-id="1afe3-147">Versión 2.5 publicado</span><span class="sxs-lookup"><span data-stu-id="1afe3-147">V2.5 published</span></span>|<span data-ttu-id="1afe3-148">2003</span><span class="sxs-lookup"><span data-stu-id="1afe3-148">2003</span></span>|<span data-ttu-id="1afe3-149">Completar la aprobación de HL7, enviado a ANSI para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="1afe3-149">Completed approval within HL7, submitted to ANSI for approval.</span></span>|  
|<span data-ttu-id="1afe3-150">V3.0 en curso</span><span class="sxs-lookup"><span data-stu-id="1afe3-150">V3.0 in progress</span></span>|<span data-ttu-id="1afe3-151">2003</span><span class="sxs-lookup"><span data-stu-id="1afe3-151">2003</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="1afe3-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="1afe3-152">See Also</span></span>  
 <span data-ttu-id="1afe3-153">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="1afe3-153">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="1afe3-154">[Uso de esquemas de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1afe3-154">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="1afe3-155">[Uso de esquemas de HL7 2.Xml](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1afe3-155">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="1afe3-156">[Modos de mensaje](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span><span class="sxs-lookup"><span data-stu-id="1afe3-156">[Message Modes](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span></span>  
 [<span data-ttu-id="1afe3-157">Mensajería de HL7</span><span class="sxs-lookup"><span data-stu-id="1afe3-157">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)
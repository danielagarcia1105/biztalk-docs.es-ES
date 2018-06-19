---
title: Partes del mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205084"
---
# <a name="message-parts"></a><span data-ttu-id="c1ce7-102">Partes de mensaje</span><span class="sxs-lookup"><span data-stu-id="c1ce7-102">Message Parts</span></span>
<span data-ttu-id="c1ce7-103">Un mensaje HL7 contiene las siguientes partes: segmentos, los campos de datos, componentes y, opcionalmente, subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-103">An HL7 message contains the following parts: segments, data fields, components, and optionally subcomponents.</span></span> <span data-ttu-id="c1ce7-104">Los mensajes de HL7 tienen la siguiente estructura jerárquica:</span><span class="sxs-lookup"><span data-stu-id="c1ce7-104">HL7 messages have the following hierarchical structure:</span></span>  
  
 <span data-ttu-id="c1ce7-105">Segment</span><span class="sxs-lookup"><span data-stu-id="c1ce7-105">Segment</span></span>  
  
 <span data-ttu-id="c1ce7-106">Campo de datos</span><span class="sxs-lookup"><span data-stu-id="c1ce7-106">Data Field</span></span>  
  
 <span data-ttu-id="c1ce7-107">Componente</span><span class="sxs-lookup"><span data-stu-id="c1ce7-107">Component</span></span>  
  
 <span data-ttu-id="c1ce7-108">Subcomponente (opcional)</span><span class="sxs-lookup"><span data-stu-id="c1ce7-108">Subcomponent (optional)</span></span>  
  
 <span data-ttu-id="c1ce7-109">**Segmentos**</span><span class="sxs-lookup"><span data-stu-id="c1ce7-109">**Segments**</span></span>  
  
 <span data-ttu-id="c1ce7-110">Un segmento es una agrupación lógica de campos de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-110">A segment is a logical grouping of data fields.</span></span> <span data-ttu-id="c1ce7-111">Segmentos se encuentran en el nivel más alto (profundidad 1) de la jerarquía de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-111">Segments are at the highest level (depth 1) of the message hierarchy.</span></span> <span data-ttu-id="c1ce7-112">Cada segmento tiene un nombre que incluye un valor literal de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-112">Each segment has a name that includes a three-character literal value.</span></span> <span data-ttu-id="c1ce7-113">En la tabla siguiente se muestra ejemplos de nombres de segmento contenidos los tipos de mensaje ADT.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-113">The following table shows examples of segment names contained by ADT message types.</span></span>  
  
|<span data-ttu-id="c1ce7-114">Código de segmento</span><span class="sxs-lookup"><span data-stu-id="c1ce7-114">Segment code</span></span>|<span data-ttu-id="c1ce7-115">Description</span><span class="sxs-lookup"><span data-stu-id="c1ce7-115">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c1ce7-116">MSH</span><span class="sxs-lookup"><span data-stu-id="c1ce7-116">MSH</span></span>|<span data-ttu-id="c1ce7-117">Encabezado de mensaje</span><span class="sxs-lookup"><span data-stu-id="c1ce7-117">Message Header</span></span>|  
|<span data-ttu-id="c1ce7-118">EVN</span><span class="sxs-lookup"><span data-stu-id="c1ce7-118">EVN</span></span>|<span data-ttu-id="c1ce7-119">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="c1ce7-119">Event Type</span></span>|  
|<span data-ttu-id="c1ce7-120">PID</span><span class="sxs-lookup"><span data-stu-id="c1ce7-120">PID</span></span>|<span data-ttu-id="c1ce7-121">Información del paciente</span><span class="sxs-lookup"><span data-stu-id="c1ce7-121">Patient Information</span></span>|  
  
 <span data-ttu-id="c1ce7-122">Mensajes HL7 tienen un *encabezado del mensaje* y *cuerpo*.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-122">HL7 messages have a *message header* and *body*.</span></span> <span data-ttu-id="c1ce7-123">Los segmentos de MSH definen el encabezado del mensaje y todos los demás tipos de segmentos forman el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-123">The MSH segments define the header of the message and all other types of segments form the body of the message.</span></span>  
  
 <span data-ttu-id="c1ce7-124">**Campos de datos**</span><span class="sxs-lookup"><span data-stu-id="c1ce7-124">**Data Fields**</span></span>  
  
 <span data-ttu-id="c1ce7-125">Un campo de datos es una cadena de caracteres que se producen en profundidad 2 de la jerarquía de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-125">A data field is a string of characters that occur at depth 2 of the message hierarchy.</span></span> <span data-ttu-id="c1ce7-126">Tipos de datos definen campos de datos: simples y complejos.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-126">Data types define data fields: Simple and Complex.</span></span>  
  
 <span data-ttu-id="c1ce7-127">En el ejemplo siguiente se muestra la estructura del mensaje jerárquica de los segmentos de MSH y EVN que contiene los campos de datos MSH.1 y EVN.1:</span><span class="sxs-lookup"><span data-stu-id="c1ce7-127">The following example shows the hierarchical message structure of the MSH and EVN segments containing the MSH.1 and EVN.1 data fields:</span></span>  
  
 <span data-ttu-id="c1ce7-128">MSH</span><span class="sxs-lookup"><span data-stu-id="c1ce7-128">MSH</span></span>  
  
 <span data-ttu-id="c1ce7-129">MSH.1</span><span class="sxs-lookup"><span data-stu-id="c1ce7-129">MSH.1</span></span>  
  
 <span data-ttu-id="c1ce7-130">EVN</span><span class="sxs-lookup"><span data-stu-id="c1ce7-130">EVN</span></span>  
  
 <span data-ttu-id="c1ce7-131">EVN.1</span><span class="sxs-lookup"><span data-stu-id="c1ce7-131">EVN.1</span></span>  
  
 <span data-ttu-id="c1ce7-132">**Componentes y subcomponentes**</span><span class="sxs-lookup"><span data-stu-id="c1ce7-132">**Components and Subcomponents**</span></span>  
  
 <span data-ttu-id="c1ce7-133">Componentes y subcomponentes más contienen los datos en los campos de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-133">Components and subcomponents further contain the data within data fields.</span></span> <span data-ttu-id="c1ce7-134">Pueden repetir los componentes y subcomponentes dentro del mismo campo.</span><span class="sxs-lookup"><span data-stu-id="c1ce7-134">Components and subcomponents can repeat within the same field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ce7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ce7-135">See Also</span></span>  
 <span data-ttu-id="c1ce7-136">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c1ce7-136">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="c1ce7-137">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="c1ce7-137">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="c1ce7-138">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="c1ce7-138">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
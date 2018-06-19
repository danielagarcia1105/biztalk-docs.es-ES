---
title: Degradación de propiedades en componentes de canalización de ensamblador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af634d302f01b18c91ebdbb7533673e8b9c545c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268836"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a><span data-ttu-id="9ab3a-102">Degradación de propiedades en componentes de canalización de ensamblador</span><span class="sxs-lookup"><span data-stu-id="9ab3a-102">Property Demotion in Assembler Pipeline Components</span></span>
<span data-ttu-id="9ab3a-103">Puede utilizar la degradación de la propiedad para copiar un valor de propiedad del contexto del mensaje en el contenido del mensaje, su encabezado o finalizador.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-103">You can use property demotion to copy a property value from the message context into the message content or to its header or trailer.</span></span> <span data-ttu-id="9ab3a-104">La degradación de propiedad se consigue utilizando una expresión XPath que se especifica en el documento o en el esquema de encabezado o finalizador.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-104">You accomplish property demotion by using an XPath expression specified in the document or in the header and trailer schema.</span></span>  
  
 <span data-ttu-id="9ab3a-105">Al escribir datos del valor datetime de la propiedad de contexto en el documento que se obtiene, BizTalk Server supone que todos los datos de datetime tienen el formato UTC.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-105">When writing datetime data from the context property into the resulting document, BizTalk Server assumes that all datetime data is in UTC format.</span></span>  
  
 <span data-ttu-id="9ab3a-106">El formato que se utiliza para escribir propiedades en los datos viene determinado por el tipo de datos XSD como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-106">The format used to write properties into the data is determined by the XSD data type as shown in the following table.</span></span>  
  
|<span data-ttu-id="9ab3a-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9ab3a-107">Data type</span></span>|<span data-ttu-id="9ab3a-108">Formato</span><span class="sxs-lookup"><span data-stu-id="9ab3a-108">Format</span></span>|  
|---------------|------------|  
|<span data-ttu-id="9ab3a-109">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="9ab3a-109">xs:datetime</span></span>|<span data-ttu-id="9ab3a-110">aaaa-MM-ddTHH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span></span>|  
|<span data-ttu-id="9ab3a-111">xs:date</span><span class="sxs-lookup"><span data-stu-id="9ab3a-111">xs:date</span></span>|<span data-ttu-id="9ab3a-112">aaaa-MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-112">yyyy-MM-ddZ</span></span>|  
|<span data-ttu-id="9ab3a-113">xs:gDay</span><span class="sxs-lookup"><span data-stu-id="9ab3a-113">xs:gDay</span></span>|<span data-ttu-id="9ab3a-114">---ddZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-114">---ddZ</span></span>|  
|<span data-ttu-id="9ab3a-115">xs:gMonth</span><span class="sxs-lookup"><span data-stu-id="9ab3a-115">xs:gMonth</span></span>|<span data-ttu-id="9ab3a-116">--MM: Z</span><span class="sxs-lookup"><span data-stu-id="9ab3a-116">--MM—Z</span></span>|  
|<span data-ttu-id="9ab3a-117">xs:gMonthDay</span><span class="sxs-lookup"><span data-stu-id="9ab3a-117">xs:gMonthDay</span></span>|<span data-ttu-id="9ab3a-118">--MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-118">--MM-ddZ</span></span>|  
|<span data-ttu-id="9ab3a-119">xs:gYear</span><span class="sxs-lookup"><span data-stu-id="9ab3a-119">xs:gYear</span></span>|<span data-ttu-id="9ab3a-120">aaaaZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-120">yyyyZ</span></span>|  
|<span data-ttu-id="9ab3a-121">xs:gYearMonth</span><span class="sxs-lookup"><span data-stu-id="9ab3a-121">xs:gYearMonth</span></span>|<span data-ttu-id="9ab3a-122">aaaa-MMZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-122">yyyy-MMZ</span></span>|  
|<span data-ttu-id="9ab3a-123">xs:time</span><span class="sxs-lookup"><span data-stu-id="9ab3a-123">xs:time</span></span>|<span data-ttu-id="9ab3a-124">HH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="9ab3a-124">HH:mm:ss.fffffffZ</span></span>|  
  
## <a name="property-demotion-and-envelopes"></a><span data-ttu-id="9ab3a-125">Degradación de propiedades y sobres</span><span class="sxs-lookup"><span data-stu-id="9ab3a-125">Property Demotion and Envelopes</span></span>  
 <span data-ttu-id="9ab3a-126">A menudo, resulta útil degradar valores de un espacio de nombres de sistema o de varios (o de uno de sus propios espacios de nombres) al ensamblar archivos en un sobre.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-126">It is often useful to demote values from one or more of the system namespaces -- or one of your own namespaces -- when assembling files within an envelope.</span></span> <span data-ttu-id="9ab3a-127">Entre otros escenarios comunes, se incluyen:</span><span class="sxs-lookup"><span data-stu-id="9ab3a-127">Some common scenarios include:</span></span>  
  
-   <span data-ttu-id="9ab3a-128">Se desea incluir el nombre de archivo original enviado al sistema en mensajes de salida para que los sistemas de servidor puedan efectuar un seguimiento del origen de los datos.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-128">You want to include the original file name submitted to the system in outbound messages so back-end systems can track the origin of data.</span></span>  
  
-   <span data-ttu-id="9ab3a-129">Se desea escribir datos del mensaje de cuerpo al encabezado.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-129">You want to write data from the body message to the header.</span></span> <span data-ttu-id="9ab3a-130">Por ejemplo, para un pedido, podría resultar útil escribir el nombre de envío en un sobre para sistemas de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-130">For example, for a purchase order it might be useful to write the ship to name to the envelope for down-stream systems.</span></span>  
  
-   <span data-ttu-id="9ab3a-131">Se desea combinar varios campos distintos en el encabezado sin escribir código personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-131">You want to combine many different fields into the header without writing custom code.</span></span> <span data-ttu-id="9ab3a-132">La degradación de propiedades del ensamblador de XML o de archivo sin formato puede llevar a cabo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-132">Property demotion in the Xml assembler or flat file assembler can do the job.</span></span>  
  
 <span data-ttu-id="9ab3a-133">Es importante recordar que los componentes de ensamblador de XML y de archivo sin formato permiten especificar el esquema que se va a utilizar para el cuerpo del documento y el sobre.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-133">It is important to remember that the XML and flat file assembler components both allow you to specify which schema to use for the envelope and document body.</span></span> <span data-ttu-id="9ab3a-134">Puede seleccionar los mismos esquemas utilizados en el desensamblado o crear un nuevo esquema de sobre con campos distintos.</span><span class="sxs-lookup"><span data-stu-id="9ab3a-134">You can choose the same schemas used in disassembly or create a new envelope schema with different fields.</span></span>  
  
 <span data-ttu-id="9ab3a-135">Para obtener un ejemplo de estos conceptos, vea [EnvelopeProcessing (ejemplo de BizTalk Server)](../core/envelopeprocessing-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9ab3a-135">For an example of these concepts, see [EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab3a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ab3a-136">See Also</span></span>  
 <span data-ttu-id="9ab3a-137">[Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9ab3a-137">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="9ab3a-138">Cómo configurar el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="9ab3a-138">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)
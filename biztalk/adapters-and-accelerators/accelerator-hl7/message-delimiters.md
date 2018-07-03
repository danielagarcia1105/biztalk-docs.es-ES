---
title: Delimitadores de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3339ded8edf46f7c5b96317cdf7a3ec822ec808b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001501"
---
# <a name="message-delimiters"></a><span data-ttu-id="cd517-102">Delimitadores de mensaje</span><span class="sxs-lookup"><span data-stu-id="cd517-102">Message Delimiters</span></span>
<span data-ttu-id="cd517-103">Eventos de mensaje definidos por los estándares de HL7 adoptan la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd517-103">Message events defined by HL7 standards take the following form:</span></span>  
  
- <span data-ttu-id="cd517-104">**Archivos planos**.</span><span class="sxs-lookup"><span data-stu-id="cd517-104">**Flat files**.</span></span> <span data-ttu-id="cd517-105">Eventos de mensaje definidos por las versiones de HL7 2.4 y anteriores adoptan la forma de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="cd517-105">Message events defined by HL7 versions 2.4 and earlier take the form of flat files.</span></span>  
  
- <span data-ttu-id="cd517-106">**XML**.</span><span class="sxs-lookup"><span data-stu-id="cd517-106">**XML**.</span></span> <span data-ttu-id="cd517-107">Eventos de mensaje definidos por las versiones de HL7 2.xml XML y la versión 3 adoptan la forma de archivos XML.</span><span class="sxs-lookup"><span data-stu-id="cd517-107">Message events defined by HL7 versions 2.XML and version 3 take the form of XML files.</span></span>  
  
  <span data-ttu-id="cd517-108">Puesto que el estándar HL7 no sigue el formato posicional, usa los delimitadores para definir el segmento, campo, componente y niveles de subcomponentes de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="cd517-108">Since the HL7 standard does not follow positional format, it uses delimiters to define the segment, field, component, and subcomponent levels of flat files.</span></span> <span data-ttu-id="cd517-109">En la tabla siguiente se enumera los delimitadores predeterminados utilizados por los archivos sin formato de HL7.</span><span class="sxs-lookup"><span data-stu-id="cd517-109">The following table lists the default delimiters used by HL7 flat files.</span></span>  
  
|<span data-ttu-id="cd517-110">Delimitador</span><span class="sxs-lookup"><span data-stu-id="cd517-110">Delimiter</span></span>|<span data-ttu-id="cd517-111">Valor</span><span class="sxs-lookup"><span data-stu-id="cd517-111">Value</span></span>|<span data-ttu-id="cd517-112">Uso</span><span class="sxs-lookup"><span data-stu-id="cd517-112">Usage</span></span>|  
|---------------|-----------|-----------|  
|<span data-ttu-id="cd517-113">Terminador de segmento</span><span class="sxs-lookup"><span data-stu-id="cd517-113">Segment terminator</span></span>|<span data-ttu-id="cd517-114">\<CR\></span><span class="sxs-lookup"><span data-stu-id="cd517-114">\<cr\></span></span>|<span data-ttu-id="cd517-115">Un retorno de carro finaliza un registro de segmento.</span><span class="sxs-lookup"><span data-stu-id="cd517-115">A carriage return terminates a segment record.</span></span> <span data-ttu-id="cd517-116">No se puede cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="cd517-116">You cannot change this value.</span></span>|  
|<span data-ttu-id="cd517-117">Separador de campos</span><span class="sxs-lookup"><span data-stu-id="cd517-117">Field separator</span></span>|<span data-ttu-id="cd517-118">&#124;</span><span class="sxs-lookup"><span data-stu-id="cd517-118">&#124;</span></span>|<span data-ttu-id="cd517-119">Un carácter de barra vertical separa dos campos de datos adyacentes en un segmento.</span><span class="sxs-lookup"><span data-stu-id="cd517-119">A pipe character separates two adjacent data fields within a segment.</span></span> <span data-ttu-id="cd517-120">Este carácter separa también el identificador de segmento del primer campo de datos en cada segmento.</span><span class="sxs-lookup"><span data-stu-id="cd517-120">This character also separates the segment ID from the first data field in each segment.</span></span>|  
|<span data-ttu-id="cd517-121">Separador de componentes</span><span class="sxs-lookup"><span data-stu-id="cd517-121">Component separator</span></span>|^|<span data-ttu-id="cd517-122">Un carácter de hat separa los componentes adyacentes de datos de los campos donde lo permite el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="cd517-122">A hat character separates adjacent components of data fields where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="cd517-123">Separador de subcomponente</span><span class="sxs-lookup"><span data-stu-id="cd517-123">Subcomponent separator</span></span>|&|<span data-ttu-id="cd517-124">Un carácter de y comercial separa adyacentes subcomponentes de datos de los campos donde lo permite el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="cd517-124">An ampersand character separates adjacent subcomponents of data fields where allowed by the HL7 standard.</span></span> <span data-ttu-id="cd517-125">Si no hay ningún subcomponentes, a continuación, puede omitir este carácter.</span><span class="sxs-lookup"><span data-stu-id="cd517-125">If there are no subcomponents, then you can omit this character.</span></span>|  
|<span data-ttu-id="cd517-126">Separador de repeticiones</span><span class="sxs-lookup"><span data-stu-id="cd517-126">Repetition separator</span></span>|~|<span data-ttu-id="cd517-127">Un carácter de tilde separa varias repeticiones de componentes o subcomponentes en un campo donde lo permite el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="cd517-127">A tilde character separates multiple occurrences of components or subcomponents in a field where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="cd517-128">Carácter de escape</span><span class="sxs-lookup"><span data-stu-id="cd517-128">Escape character</span></span>|<span data-ttu-id="cd517-129">\|Utilice un carácter de escape con cualquier campo que se ajusta a un tipo de datos ST, TX o FT, o con el componente de tipo de datos de ED (cuarto) de datos.</span><span class="sxs-lookup"><span data-stu-id="cd517-129">\|You use an escape character with any field that conforms to an ST, TX, or FT data type, or with the data (fourth) component of the ED data type.</span></span> <span data-ttu-id="cd517-130">Si no existe ningún carácter de escape en un mensaje, puede omitir este carácter.</span><span class="sxs-lookup"><span data-stu-id="cd517-130">If no escape characters exist in a message, you can omit this character.</span></span> <span data-ttu-id="cd517-131">Sin embargo, se debe incluir si usas subcomponentes en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd517-131">However, you must include it if you use subcomponents in the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd517-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd517-132">See Also</span></span>  
 <span data-ttu-id="cd517-133">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cd517-133">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="cd517-134">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="cd517-134">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="cd517-135">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="cd517-135">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
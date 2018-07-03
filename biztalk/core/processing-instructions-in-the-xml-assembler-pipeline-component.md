---
title: Instrucciones de procesamiento en el componente de canalización de ensamblador XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df3b56a3703e56dd4b3f474b4846999bae9858f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016110"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="f0bfd-102">Instrucciones de procesamiento en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="f0bfd-102">Processing Instructions in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="f0bfd-103">Las instrucciones de procesamiento proporcionan información a la aplicación que procesa un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-103">Processing instructions provide information to the application that processes an XML document.</span></span> <span data-ttu-id="f0bfd-104">Dicha información puede incluir instrucciones sobre cómo procesar el documento, cómo mostrarlo, etc.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-104">Such information may include instructions about how to process the document, how to display it, and so on.</span></span>  
  
 <span data-ttu-id="f0bfd-105">Las instrucciones de procesamiento se agregan a un documento XML mediante el **agregar instrucciones de procesamiento** propiedad (o su equivalente **XMLNorm.ProcessingInstructionOption** propiedad en el contexto del mensaje).</span><span class="sxs-lookup"><span data-stu-id="f0bfd-105">Processing instructions are added to an XML document by the **Add processing instructions** property (or the equivalent **XMLNorm.ProcessingInstructionOption** property on the message context).</span></span> <span data-ttu-id="f0bfd-106">Texto de la instrucción de procesamiento se especifica con el **agregar texto de instrucciones de procesamiento** propiedad (o su equivalente **XMLNorm.ProcessingInstruction** propiedad en el contexto del mensaje).</span><span class="sxs-lookup"><span data-stu-id="f0bfd-106">Processing instruction text is specified with the **Add processing instructions text** property (or the equivalent **XMLNorm.ProcessingInstruction** property on the message context).</span></span>  
  
 <span data-ttu-id="f0bfd-107">El **agregar instrucciones de procesamiento** propiedad (o **XMLNorm.ProcessingInstructionOption** propiedad) tiene tres valores posibles, que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-107">The **Add processing instructions** property (or **XMLNorm.ProcessingInstructionOption** property) has three possible values, which are described in the following table.</span></span>  
  
|<span data-ttu-id="f0bfd-108">Valor</span><span class="sxs-lookup"><span data-stu-id="f0bfd-108">Value</span></span>|<span data-ttu-id="f0bfd-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f0bfd-109">Value</span></span>|<span data-ttu-id="f0bfd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0bfd-110">Description</span></span>|  
|-----------|-----------|-----------------|  
|<span data-ttu-id="f0bfd-111">Anexar</span><span class="sxs-lookup"><span data-stu-id="f0bfd-111">Append</span></span>|<span data-ttu-id="f0bfd-112">0</span><span class="sxs-lookup"><span data-stu-id="f0bfd-112">0</span></span>|<span data-ttu-id="f0bfd-113">Las nuevas instrucciones de procesamiento del ensamblador XML se agregan a las ya existentes al principio del documento.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-113">New processing instructions from the XML Assembler are appended to the processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="f0bfd-114">Crear nuevo</span><span class="sxs-lookup"><span data-stu-id="f0bfd-114">Create new</span></span>|<span data-ttu-id="f0bfd-115">1</span><span class="sxs-lookup"><span data-stu-id="f0bfd-115">1</span></span>|<span data-ttu-id="f0bfd-116">Las nuevas instrucciones de procesamiento del ensamblador XML sobrescriben las ya existentes al principio del documento.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-116">New processing instructions from the XML Assembler overwrite existing processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="f0bfd-117">Omitir</span><span class="sxs-lookup"><span data-stu-id="f0bfd-117">Ignore</span></span>|<span data-ttu-id="f0bfd-118">2</span><span class="sxs-lookup"><span data-stu-id="f0bfd-118">2</span></span>|<span data-ttu-id="f0bfd-119">Se quitan las instrucciones de procesamiento que se encuentran al principio del documento.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-119">Processing instructions at the beginning of the document are removed.</span></span>|  
  
 <span data-ttu-id="f0bfd-120">Las dos instrucciones de procesamiento (o propiedades de contexto de mensaje) especificadas en el contexto de un mensaje adquieren prioridad sobre las dos propiedades especificadas en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-120">The pair of processing instructions (or message context properties) specified on a message context take precedence over the property pair specified in Pipeline Designer.</span></span> <span data-ttu-id="f0bfd-121">Por ejemplo, si **XMLNorm.ProcessingInstructionOption** se especifica como **crear nuevo** (1) y **XMLNorm.ProcessingInstruction** no se especifica un procesamiento vacío instrucción reemplazará una instrucción de procesamiento existente.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-121">For example, if **XMLNorm.ProcessingInstructionOption** is specified as **Create new** (1) and **XMLNorm.ProcessingInstruction** is not specified, an empty processing instruction will replace an existing processing instruction.</span></span>  
  
 <span data-ttu-id="f0bfd-122">Como otro ejemplo, si **XMLNorm.ProcessingInstruction** se especifica pero **XMLNorm.ProcessingInstructionOption** no lo es, se utiliza ninguna de las propiedades del contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-122">As another example, if **XMLNorm.ProcessingInstruction** is specified but **XMLNorm.ProcessingInstructionOption** is not, none of the properties from the message context are used.</span></span> <span data-ttu-id="f0bfd-123">En este caso, se utilizan las instrucciones de procesamiento del Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-123">In this case, the processing instructions from Pipeline Designer are used.</span></span>  
  
 <span data-ttu-id="f0bfd-124">De forma predeterminada, **agregar instrucciones de procesamiento** está establecido en **Append**, y **agregar texto de instrucciones de procesamiento** está vacío.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-124">By default, **Add processing instructions** is set to **Append**, and **Add processing instructions text** is empty.</span></span>  
  
## <a name="processing-properties-and-envelopes"></a><span data-ttu-id="f0bfd-125">Propiedades de procesamiento y sobres</span><span class="sxs-lookup"><span data-stu-id="f0bfd-125">Processing Properties and Envelopes</span></span>  
 <span data-ttu-id="f0bfd-126">Las instrucciones de procesamiento no se mantienen para los sobres por lo que la siguiente combinación de valores de ensamblador de archivo sin formato hace que solo el sobre más externo tenga la instrucción de procesamiento:</span><span class="sxs-lookup"><span data-stu-id="f0bfd-126">Because processing instructions are not preserved for the envelopes, the following combination of flat file assembler settings results in only the outermost envelope having the processing instruction:</span></span>  
  
- <span data-ttu-id="f0bfd-127">**Procesando ámbito de instrucción** propiedad establecida en "Envelope".</span><span class="sxs-lookup"><span data-stu-id="f0bfd-127">**Processing instruction scope** property set to "Envelope."</span></span>  
  
- <span data-ttu-id="f0bfd-128">**Agregar instrucciones de procesamiento** propiedad establecida en "Agregar".</span><span class="sxs-lookup"><span data-stu-id="f0bfd-128">**Add processing instructions** property set to "Append."</span></span>  
  
  <span data-ttu-id="f0bfd-129">El sobre utilizará la instrucción de procesamiento especificada en el ensamblador **texto de instrucciones de procesamiento de agregar** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-129">The envelope would use the processing instruction specified in the assembler's **Add Processing instructions text** property.</span></span>  
  
  <span data-ttu-id="f0bfd-130">Las instrucciones de procesamiento que existen en los sobres externos o internos no estarán presentes en los mensajes de salida, tal como se especificó en el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="f0bfd-130">Any existing processing instructions in either the outer or inner envelope(s), as specified in the incoming message, will not be present in the output message(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0bfd-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0bfd-131">See Also</span></span>  
 <span data-ttu-id="f0bfd-132">[Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f0bfd-132">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="f0bfd-133">[Cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f0bfd-133">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="f0bfd-134">Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="f0bfd-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
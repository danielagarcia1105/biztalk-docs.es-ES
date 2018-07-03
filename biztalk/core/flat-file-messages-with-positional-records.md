---
title: Mensajes de archivo sin formato con registros posicionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3cee44a9fbb3cdce4b75da765caf3fbf8f265d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990757"
---
# <a name="flat-file-messages-with-positional-records"></a><span data-ttu-id="8f4cc-102">Mensajes de archivo sin formato con registros posicionales</span><span class="sxs-lookup"><span data-stu-id="8f4cc-102">Flat File Messages with Positional Records</span></span>
<span data-ttu-id="8f4cc-103">Los registros posicionales dentro de un mensaje de instancia de archivo sin formato contienen campos (elementos de datos) y cada uno de ellos tiene una longitud predefinida.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-103">Positional records within a flat file instance message contain individual fields (items of data) that are each of a predefined length.</span></span> <span data-ttu-id="8f4cc-104">Los campos se analizan según estas longitudes.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-104">The fields are parsed according to these lengths.</span></span> <span data-ttu-id="8f4cc-105">Por ejemplo, considere el siguiente registro posicional de un mensaje de instancia de archivo sin formato que contiene una dirección de envío (la primera línea muestra el número de caracteres reservados para cada campo).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-105">For example, consider the following positional record from a flat file instance message, which contains a ship to address (the first line shows the number of characters reserved for each field).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 <span data-ttu-id="8f4cc-106">Una definición razonable para este registro en un esquema de archivo sin formato se puede describir como un registro posicional llamado shipTo que contiene los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f4cc-106">A reasonable definition for this record in a flat file schema can be described as a positional record named shipTo that contains the following fields:</span></span>  
  
- <span data-ttu-id="8f4cc-107">Un atributo denominado country/region, alineado a la izquierda, de 10 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-107">An attribute named country/region that is left-aligned, 10 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="8f4cc-108">Un elemento denominado name, alineado a la izquierda, de 20 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-108">An element named name that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="8f4cc-109">Un elemento denominado street, alineado a la izquierda, de 20 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-109">An element named street that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="8f4cc-110">Un elemento denominado city, alineado a la izquierda, de 15 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-110">An element named city that is left-aligned, 15 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="8f4cc-111">Un elemento denominado state, alineado a la izquierda, de 2 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-111">An element named state that is left-aligned, 2 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="8f4cc-112">Un elemento denominado zip, alineado a la izquierda, de 5 caracteres de longitud y con un desplazamiento de caracteres de cero.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-112">An element named zip that is left-aligned, 5 characters in length, with a one character offset.</span></span>  
  
  <span data-ttu-id="8f4cc-113">Según estas definiciones de registros y campos, el desensamblador de archivos sin formato creará el siguiente XML equivalente de este registro.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-113">Given these record and field definitions, the flat file disassembler will produce the following XML equivalent of this record.</span></span>  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 <span data-ttu-id="8f4cc-114">Existen varias cuestiones que es necesario tener en cuenta en relación con los registros posicionales, y que afectan a la forma de analizar el registro cuando se recibe y a la forma de construirlo cuando se envía, entre ellas:</span><span class="sxs-lookup"><span data-stu-id="8f4cc-114">There are a number of considerations related to positional records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
- <span data-ttu-id="8f4cc-115">El carácter utilizado para rellenar la parte no utilizada de cada campo, conocido como carácter controlador.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-115">The character used to fill the unused portion of each field, known as the pad character.</span></span> <span data-ttu-id="8f4cc-116">Para obtener más información, consulte [relleno de los campos](../core/field-padding.md).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-116">For more information, see [Field Padding](../core/field-padding.md).</span></span>  
  
- <span data-ttu-id="8f4cc-117">Una etiqueta opcional dentro del registro para distinguir el registro de otros similares.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-117">An optional tag within the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="8f4cc-118">Normalmente, las etiquetas se encuentran al comienzo del registro, aunque se pueden situar en cualquier parte del mismo.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-118">Tags usually occur at the beginning of the record but allowable anywhere within it.</span></span> <span data-ttu-id="8f4cc-119">Para obtener más información, consulte [tratar las etiquetas en los registros posicionales](../core/tag-handling-in-positional-records.md).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-119">For more information, see [Tag Handling in Positional Records](../core/tag-handling-in-positional-records.md).</span></span> <span data-ttu-id="8f4cc-120">Los registros posicionales se pueden definir de modo que tengan o no tengan etiquetas, pero una vez definidos, deben contener o no etiquetas según la definición establecida.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-120">Positional records can be defined to have a tag or not have a tag, but once defined, the tag must be present or not, based on the definition.</span></span>  
  
- <span data-ttu-id="8f4cc-121">Modo de justificar los datos en un campo de longitud fija con respecto a los caracteres controladores existentes.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-121">How data is justified within a fixed length field, relative to the accompanying pad characters.</span></span> <span data-ttu-id="8f4cc-122">Para obtener más información, consulte [justificación de campos](../core/field-justification.md).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-122">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
- <span data-ttu-id="8f4cc-123">Registros posicionales anidados dentro de otros registros posicionales o delimitados.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-123">Positional records nested within other positional or delimited records.</span></span> <span data-ttu-id="8f4cc-124">Para obtener más información, consulte [registros posicionales anidados](../core/nested-positional-records.md).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-124">For more information, see [Nested Positional Records](../core/nested-positional-records.md).</span></span>  
  
- <span data-ttu-id="8f4cc-125">Registros posicionales con longitudes de campo especificadas como un número determinado de bytes en vez de como un número específico de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-125">Positional records with field lengths specified as a specific number of bytes rather than a specific number of characters.</span></span> <span data-ttu-id="8f4cc-126">Para obtener más información, consulte [contar posiciones en Bytes](../core/position-counting-in-bytes.md).</span><span class="sxs-lookup"><span data-stu-id="8f4cc-126">For more information, see [Position Counting in Bytes](../core/position-counting-in-bytes.md).</span></span>  
  
  <span data-ttu-id="8f4cc-127">Para ayudarle a comprender mejor cómo trabajar con archivos sin formato posicionales, consulte los ejemplos en las carpetas FlatFileReceive y FlatFileSend que se encuentran en \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler\\.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-127">To help you better understand how to work with positional flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f4cc-128">Si el archivo sin formato contiene registros delimitados y posicionales, debe establecer el **estructura** propiedad del nodo raíz a **delimitado** y **estructura** propiedad de los subordinados a cualquiera de los nodos Registro **delimitado** o **posicional** según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-128">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f4cc-129">Los campos de los registros posicionales tienen una limitación de 50.000.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8f4cc-129">Fields in positional records have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4cc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f4cc-130">See Also</span></span>  
 <span data-ttu-id="8f4cc-131">[Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="8f4cc-131">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="8f4cc-132">Cómo crear esquemas para mensajes de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="8f4cc-132">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)
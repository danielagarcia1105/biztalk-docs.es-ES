---
title: Mensajes de archivo sin formato con registros delimitados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dc9eb0253e2bfe8824f6395e1c619c23f0e551
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22246716"
---
# <a name="flat-file-messages-with-delimited-records"></a><span data-ttu-id="ff444-102">Mensajes de archivo sin formato con registros delimitados</span><span class="sxs-lookup"><span data-stu-id="ff444-102">Flat File Messages with Delimited Records</span></span>
<span data-ttu-id="ff444-103">Los registros delimitados de un mensaje de instancia de archivo sin formato contienen registros o campos individuales (elementos de datos) anidados, separados con un carácter o un conjunto de caracteres predefinido.</span><span class="sxs-lookup"><span data-stu-id="ff444-103">Delimited records within a flat file instance message contain nested records and/or individual fields (items of data) that are separated by a predefined character or set of characters.</span></span> <span data-ttu-id="ff444-104">Los campos se analizan según estos delimitadores de separación.</span><span class="sxs-lookup"><span data-stu-id="ff444-104">The fields are parsed according to these separating delimiters.</span></span> <span data-ttu-id="ff444-105">Por ejemplo, considere los siguientes registros delimitados de un mensaje de instancia de archivo sin formato con dos elementos de línea de un pedido hipotético:</span><span class="sxs-lookup"><span data-stu-id="ff444-105">For example, consider the following delimited records from a flat file instance message, which contain two line items from a hypothetical purchase order:</span></span>  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 <span data-ttu-id="ff444-106">Una definición aceptable de este registro de esquema de archivo sin formato sería la que se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="ff444-106">A reasonable definition for this record in a flat file schema can be described as follows:</span></span>  
  
-   <span data-ttu-id="ff444-107">Un registro delimitado denominado "items" con el delimitador secundario (,), el prefijo de orden secundario y la etiqueta ITEMS.</span><span class="sxs-lookup"><span data-stu-id="ff444-107">A delimited record named items with child delimiter (,), child order prefix, and the tag ITEMS.</span></span>  
  
    -   <span data-ttu-id="ff444-108">A delimitados, repitiendo registro con el nombre de elemento con el delimitador secundario &#124;, infijo de orden secundario y la etiqueta de elemento.</span><span class="sxs-lookup"><span data-stu-id="ff444-108">A delimited, repeating record named item with child delimiter &#124;, child order infix, and the tag ITEM.</span></span>  
  
    -   <span data-ttu-id="ff444-109">Un atributo denominado "partNum".</span><span class="sxs-lookup"><span data-stu-id="ff444-109">An attribute named "partNum".</span></span>  
  
    -   <span data-ttu-id="ff444-110">Un elemento denominado "productName".</span><span class="sxs-lookup"><span data-stu-id="ff444-110">An element named "productName".</span></span>  
  
    -   <span data-ttu-id="ff444-111">Un elemento denominado "quantity".</span><span class="sxs-lookup"><span data-stu-id="ff444-111">An element named "quantity".</span></span>  
  
    -   <span data-ttu-id="ff444-112">Un elemento denominado "USPrice".</span><span class="sxs-lookup"><span data-stu-id="ff444-112">An element named "USPrice".</span></span>  
  
    -   <span data-ttu-id="ff444-113">Un elemento denominado "powerSource".</span><span class="sxs-lookup"><span data-stu-id="ff444-113">An element named "powerSource".</span></span>  
  
-   <span data-ttu-id="ff444-114">Un elemento opcional denominado "shipDate".</span><span class="sxs-lookup"><span data-stu-id="ff444-114">An optional element named "shipDate".</span></span>  
  
 <span data-ttu-id="ff444-115">Según estas definiciones de registros y campos, el desensamblador de archivos sin formato crea los siguientes equivalentes XML de los registros.</span><span class="sxs-lookup"><span data-stu-id="ff444-115">Given these record and field definitions, the flat file disassembler produces the following XML equivalent of these records.</span></span>  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 <span data-ttu-id="ff444-116">Existen varias cuestiones que es necesario tener en cuenta con relación a los registros delimitados y que afectan a cómo se analiza el registro cuando se recibe y cómo se crea cuando se envía, entre ellas:</span><span class="sxs-lookup"><span data-stu-id="ff444-116">There are a number of considerations related to delimited records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
-   <span data-ttu-id="ff444-117">El carácter o los caracteres utilizados para que se invalide su interpretación como delimitadores de modo que se consideren parte de los datos.</span><span class="sxs-lookup"><span data-stu-id="ff444-117">The character or characters used to override the interpretation of delimiters so that they are treated as part of the data.</span></span> <span data-ttu-id="ff444-118">Para obtener más información, consulte [formas de interpretar los caracteres especiales como parte de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-118">For more information, see [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span>  
  
-   <span data-ttu-id="ff444-119">Una etiqueta opcional al principio del registro para distinguir el registro de otros similares.</span><span class="sxs-lookup"><span data-stu-id="ff444-119">An optional tag at the beginning of the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="ff444-120">Para obtener más información, consulte [tratamiento de las etiquetas en los registros delimitados](../core/tag-handling-in-delimited-records.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-120">For more information, see [Tag Handling in Delimited Records](../core/tag-handling-in-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="ff444-121">Cómo se justifican los datos en los campos con una longitud mínima con respecto a los caracteres controladores existentes.</span><span class="sxs-lookup"><span data-stu-id="ff444-121">How data is justified within fields with minimum lengths, relative to the accompanying pad characters.</span></span> <span data-ttu-id="ff444-122">Para obtener más información, consulte [relleno de los campos](../core/field-padding.md), [justificación de los campos](../core/field-justification.md), y [mínimo campo longitudes de los registros delimitados](../core/minimum-field-lengths-within-delimited-records.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-122">For more information, see [Field Padding](../core/field-padding.md), [Field Justification](../core/field-justification.md), and [Minimum Field Lengths Within Delimited Records](../core/minimum-field-lengths-within-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="ff444-123">Registros posicionales anidados dentro de otros registros delimitados.</span><span class="sxs-lookup"><span data-stu-id="ff444-123">Positional records nested within other delimited records.</span></span> <span data-ttu-id="ff444-124">Para obtener más información, consulte [registros delimitados y posicionales anidados](../core/nested-positional-and-delimited-records.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-124">For more information, see [Nested Positional and Delimited Records](../core/nested-positional-and-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="ff444-125">Cómo se justifican los datos en un campos de longitud fija con respecto a los caracteres controladores existentes.</span><span class="sxs-lookup"><span data-stu-id="ff444-125">How data is justified within a fixed length field, relative to its accompanying pad characters.</span></span> <span data-ttu-id="ff444-126">Para obtener más información, consulte [justificación de los campos](../core/field-justification.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-126">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
-   <span data-ttu-id="ff444-127">Consideraciones acerca de la posición de los delimitadores respecto a los datos que delimitan.</span><span class="sxs-lookup"><span data-stu-id="ff444-127">Considerations concerning the positioning of delimiters relate to the data that they delimit.</span></span> <span data-ttu-id="ff444-128">Para obtener más información, consulte [consideraciones acerca del orden secundario](../core/child-order-considerations.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-128">For more information, see [Child Order Considerations](../core/child-order-considerations.md).</span></span>  
  
-   <span data-ttu-id="ff444-129">Conservar y suprimir los delimitadores cuando se reciben y envían mensajes de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="ff444-129">Preservation and suppression of delimiters when flat file messages are received and sent.</span></span> <span data-ttu-id="ff444-130">Para obtener más información, consulte [conservar y suprimir delimitadores](../core/delimiter-preservation-and-suppression.md).</span><span class="sxs-lookup"><span data-stu-id="ff444-130">For more information, see [Delimiter Preservation and Suppression](../core/delimiter-preservation-and-suppression.md).</span></span>  
  
 <span data-ttu-id="ff444-131">Para ayudarle a comprender mejor cómo trabajar con archivos sin formato delimitados, vea los ejemplos disponibles en las carpetas FlatFileReceive y FlatFileSend que se encuentran en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.</span><span class="sxs-lookup"><span data-stu-id="ff444-131">To help you better understand how to work with delimited flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff444-132">Si el archivo sin formato contiene registros delimitados y posicionales, debe establecer el **estructura** propiedad del nodo raíz a **delimitado** y **estructura** propiedad de los subordinados a cualquiera de los nodos Registro **delimitado** o **posicional** según corresponda.</span><span class="sxs-lookup"><span data-stu-id="ff444-132">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff444-133">Los campos delimitados de los archivos sin formato tienen un límite de 50.000.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ff444-133">Delimited fields in flat files have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff444-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff444-134">See Also</span></span>  
 <span data-ttu-id="ff444-135">[Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="ff444-135">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 <span data-ttu-id="ff444-136">[Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ff444-136">[How to Create Schemas for Flat File Messages](../core/how-to-create-schemas-for-flat-file-messages.md) </span></span>  
 [<span data-ttu-id="ff444-137">Migración de registros de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="ff444-137">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)
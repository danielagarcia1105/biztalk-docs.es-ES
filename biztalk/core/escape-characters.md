---
title: Caracteres de escape | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6f1ff202c1ffa96bc696415ab7ec1024ae57e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970653"
---
# <a name="escape-characters"></a><span data-ttu-id="0767f-102">Caracteres de escape</span><span class="sxs-lookup"><span data-stu-id="0767f-102">Escape Characters</span></span>

## <a name="overview"></a><span data-ttu-id="0767f-103">Información general</span><span class="sxs-lookup"><span data-stu-id="0767f-103">Overview</span></span>
<span data-ttu-id="0767f-104">Un carácter de escape es un carácter individual que suprime cualquier significado especial que tenga el carácter que le sigue.</span><span class="sxs-lookup"><span data-stu-id="0767f-104">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="0767f-105">Por ejemplo, si define un registro de archivo sin formato con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0767f-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="0767f-106">Nombre = Record1</span><span class="sxs-lookup"><span data-stu-id="0767f-106">Name = Record1</span></span>  
  
- <span data-ttu-id="0767f-107">Delimitado</span><span class="sxs-lookup"><span data-stu-id="0767f-107">Delimited</span></span>  
  
- <span data-ttu-id="0767f-108">Delimitador secundario = coma (,)</span><span class="sxs-lookup"><span data-stu-id="0767f-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="0767f-109">Orden secundario = prefijo</span><span class="sxs-lookup"><span data-stu-id="0767f-109">Child order = prefix</span></span>  
  
- <span data-ttu-id="0767f-110">Carácter de escape = barra diagonal inversa (\\)</span><span class="sxs-lookup"><span data-stu-id="0767f-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="0767f-111">Etiqueta = RECORD1</span><span class="sxs-lookup"><span data-stu-id="0767f-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="0767f-112">Dos campos denominados Field1 y Field2</span><span class="sxs-lookup"><span data-stu-id="0767f-112">Two fields named Field1 and Field2</span></span>  
  
  <span data-ttu-id="0767f-113">Serán aplicables al registro los datos de archivo sin formato siguientes:</span><span class="sxs-lookup"><span data-stu-id="0767f-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 <span data-ttu-id="0767f-114">Los datos se desensamblarán en el siguiente fragmento de XML.</span><span class="sxs-lookup"><span data-stu-id="0767f-114">The data will be disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 <span data-ttu-id="0767f-115">Tenga en cuenta que el escape de la secuencia de caracteres `\,` indicado en la línea siguiente del registro de archivo sin formato, se ha convertido en un carácter de coma sin el carácter de escape en los datos de Field1 del registro XML equivalente.</span><span class="sxs-lookup"><span data-stu-id="0767f-115">Note that the escape character sequence `\,` indicated on the line following the flat file record, has been converted to a single comma character without the escape character in the data for Field1 in the equivalent XML record.</span></span> <span data-ttu-id="0767f-116">Además, el carácter de coma no se ha interpretado como un delimitador de campo como las otras dos comas.</span><span class="sxs-lookup"><span data-stu-id="0767f-116">Furthermore, that comma character was not interpreted as a field delimiter like the other two commas are.</span></span>  
  
 <span data-ttu-id="0767f-117">Cuando el ensamblador de archivos sin formato realice la operación inversa (conversión de la versión XML del registro en el registro de archivo sin formato equivalente), el carácter de escape se insertará antes de la coma, a mitad de los datos de Field1, para indicar que se debe interpretar como datos en lugar de como un delimitador de campo.</span><span class="sxs-lookup"><span data-stu-id="0767f-117">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the escape character will be inserted before the comma in the middle of Field1, thereby indicating that it should be interpreted as data rather than as a field delimiter.</span></span>  
  
 <span data-ttu-id="0767f-118">Al crear un esquema de archivo sin formato mediante el Editor de BizTalk, puede definir un carácter de escape predeterminado para el esquema completo mediante la **carácter de Escape predeterminado** y **tipo de carácter de Escape predeterminado** propiedades de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="0767f-118">When creating a flat file schema using BizTalk Editor, you can define a default escape character for the entire schema using the **Default Escape Character** and **Default Escape Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="0767f-119">A continuación, puede configurar cada registro individual en el esquema para usar este carácter de escape predeterminado o un carácter de escape personalizado y específico del registro mediante el **carácter de Escape]** y **tipo de carácter de Escape**propiedades de la **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="0767f-119">Then, you can configure each individual record in the schema to either use this default escape character or a custom, record-specific escape character using the **Escape Character]** and **Escape Character Type** properties of the **Record** node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0767f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0767f-120">See Also</span></span>  
- [<span data-ttu-id="0767f-121">Formas de interpretar los caracteres especiales de un valor de campo</span><span class="sxs-lookup"><span data-stu-id="0767f-121">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="0767f-122">Propiedades de carácter de escape [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="0767f-122">Escape character properties  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="0767f-123">Carácter de Escape predeterminado (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="0767f-123">Default Escape Character (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="0767f-124">Tipo de carácter de Escape predeterminado (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="0767f-124">Default Escape Character Type (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="0767f-125">Carácter de escape (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="0767f-125">Escape Character (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="0767f-126">Tipo de carácter (propiedad de nodo de esquemas de archivo sin formato) de escape</span><span class="sxs-lookup"><span data-stu-id="0767f-126">Escape Character Type (Node Property of Flat File Schemas)</span></span>
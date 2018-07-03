---
title: Ajustar caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7d88c412c94505600443d351a150b6ca8a6876a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996597"
---
# <a name="wrap-characters"></a><span data-ttu-id="6d99e-102">Incluir caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="6d99e-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="6d99e-103">Información general</span><span class="sxs-lookup"><span data-stu-id="6d99e-103">Overview</span></span>
<span data-ttu-id="6d99e-104">Un carácter de ajuste es un carácter simple que sirve para ajustar los caracteres de datos en un campo con el fin de suprimir el significado especial que, en caso contrario, tendría cualquiera de estos caracteres de datos.</span><span class="sxs-lookup"><span data-stu-id="6d99e-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="6d99e-105">Por ejemplo, si define un registro de archivo sin formato con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6d99e-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="6d99e-106">Nombre = Record1</span><span class="sxs-lookup"><span data-stu-id="6d99e-106">Name = Record1</span></span>  
  
- <span data-ttu-id="6d99e-107">Delimitado</span><span class="sxs-lookup"><span data-stu-id="6d99e-107">Delimited</span></span>  
  
- <span data-ttu-id="6d99e-108">Delimitador secundario = coma (,)</span><span class="sxs-lookup"><span data-stu-id="6d99e-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="6d99e-109">Orden secundario = infijo</span><span class="sxs-lookup"><span data-stu-id="6d99e-109">Child order = infix</span></span>  
  
- <span data-ttu-id="6d99e-110">Carácter de escape = barra diagonal inversa (\\)</span><span class="sxs-lookup"><span data-stu-id="6d99e-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="6d99e-111">Etiqueta = RECORD1</span><span class="sxs-lookup"><span data-stu-id="6d99e-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="6d99e-112">Tres campos denominados Field1, Field2 y Field3, cada uno de ellos definido para que use el carácter de signo de número (#) como carácter de ajuste.</span><span class="sxs-lookup"><span data-stu-id="6d99e-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
  <span data-ttu-id="6d99e-113">Serán aplicables al registro los datos de archivo sin formato siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d99e-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="6d99e-114">Los datos se desensamblan en el siguiente fragmento de XML.</span><span class="sxs-lookup"><span data-stu-id="6d99e-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="6d99e-115">Tenga en cuenta que se han quitado los caracteres de ajuste (#) que rodean a los caracteres de datos en negrita fieldl1, field2 y field3.</span><span class="sxs-lookup"><span data-stu-id="6d99e-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="6d99e-116">Cuando el ensamblador de archivo sin formato realiza la operación inversa, convertir la versión XML del registro a registro de archivo sin formato equivalente, se insertan los caracteres de ajuste antes y después de cada uno de los campos para producir la secuencia original de los caracteres de datos caracteres de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="6d99e-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="6d99e-117">El carácter de escape definido y el carácter de ajuste definido se pueden usar de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="6d99e-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="6d99e-118">Por ejemplo, supongamos que se cambia el valor de Field1 como se muestra a continuación (en negrita):</span><span class="sxs-lookup"><span data-stu-id="6d99e-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="6d99e-119">Cuando se ensamble el fragmento XML, mediante las definiciones de registro y campo proporcionadas, se generará la siguiente secuencia de caracteres de archivo sin formado (la secuencia de caracteres de signo de número con escape se muestra en negrita).</span><span class="sxs-lookup"><span data-stu-id="6d99e-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="6d99e-120">Al crear un esquema de archivo sin formato mediante el Editor de BizTalk, puede definir un carácter de ajuste predeterminado para el esquema completo mediante la **carácter de ajuste predeterminado** y **tipo de carácter de ajuste predeterminado** propiedades de la **Esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="6d99e-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="6d99e-121">A continuación, puede configurar cada campo en el esquema para usar este carácter de ajuste predeterminado o un carácter de ajuste personalizado, específica de campo mediante el **carácter de ajuste** y **tipo de carácter de ajuste** propiedades de la **elemento de campo** o **atributo de campo** nodos en esquemas de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="6d99e-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d99e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d99e-122">See Also</span></span>  
- [<span data-ttu-id="6d99e-123">Formas de interpretar los caracteres especiales de un valor de campo</span><span class="sxs-lookup"><span data-stu-id="6d99e-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="6d99e-124">Propiedades de carácter de ajuste [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="6d99e-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="6d99e-125">Carácter de ajuste predeterminado (propiedad de nodo de esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="6d99e-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="6d99e-126">Tipo de carácter de ajuste predeterminado (propiedad de nodo de esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="6d99e-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="6d99e-127">(Propiedad de nodo de esquemas de archivo sin formato de carácter de ajuste</span><span class="sxs-lookup"><span data-stu-id="6d99e-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="6d99e-128">Tipo de carácter (propiedad de nodo de esquemas de archivo sin formato de ajuste</span><span class="sxs-lookup"><span data-stu-id="6d99e-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>
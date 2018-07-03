---
title: Control de etiqueta en los registros delimitados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50a3daad9bb77ba4a9cbc264f018e29601edfff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972469"
---
# <a name="tag-handling-in-delimited-records"></a><span data-ttu-id="8ac74-102">Etiqueta de control en los registros delimitados</span><span class="sxs-lookup"><span data-stu-id="8ac74-102">Tag Handling in Delimited Records</span></span>

## <a name="overview"></a><span data-ttu-id="8ac74-103">Información general</span><span class="sxs-lookup"><span data-stu-id="8ac74-103">Overview</span></span>
<span data-ttu-id="8ac74-104">Los registros delimitados pueden incluir una secuencia conocida de caracteres, denominada etiqueta, que puede usarse para eliminar la ambigüedad existente entre un tipo de registro y otro.</span><span class="sxs-lookup"><span data-stu-id="8ac74-104">Delimited records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="8ac74-105">Esto permitirá que el Desensamblador de archivos sin formato identificar correctamente el adecuado **registro** nodo en el esquema que contiene la información necesaria para analizar correctamente el registro de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="8ac74-105">This will allow the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  

 <span data-ttu-id="8ac74-106">Puede usar el **identificador de etiquetas** propiedad para especificar la etiqueta dentro de un registro delimitado.</span><span class="sxs-lookup"><span data-stu-id="8ac74-106">You can use the **Tag Identifier** property to specify the tag within a delimited record.</span></span> <span data-ttu-id="8ac74-107">A diferencia de las etiquetas de los registros posicionales, las etiquetas de los registros delimitados deben aparecer al principio del registro delimitado y nunca se incluyen automáticamente en los datos cuando el registro se traduce al formato XML equivalente.</span><span class="sxs-lookup"><span data-stu-id="8ac74-107">Unlike tags in positional records, tags in delimited records must occur at the beginning of the delimited record and are automatically never included in the data when the record is translated to its equivalent XML format.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8ac74-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ac74-108">See Also</span></span>  
- [<span data-ttu-id="8ac74-109">Consideraciones acerca de los registros delimitados</span><span class="sxs-lookup"><span data-stu-id="8ac74-109">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="8ac74-110">**Identificador de etiquetas (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac74-110">**Tag Identifier (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

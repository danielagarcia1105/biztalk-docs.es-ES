---
title: Que se codifican los caracteres de nombre de nodo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a581d2-48fa-4c36-b5c2-fe87c328a7f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b72c7bb1eb05e8bb8ce8c0596cbacc88cb3d2f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022074"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="79d03-102">Caracteres de los nombres de nodo que se codifican</span><span class="sxs-lookup"><span data-stu-id="79d03-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="79d03-103">XML aplica algunas restricciones a los caracteres que se pueden usar en los nombres XML (como los nombres de elemento), incluidas algunas restricciones especiales para el primer carácter de un nombre XML.</span><span class="sxs-lookup"><span data-stu-id="79d03-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="79d03-104">Los objetivos conceptuales para determinar qué caracteres se permiten y qué caracteres se deben excluir de los nombres XML permitidos son:</span><span class="sxs-lookup"><span data-stu-id="79d03-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
- <span data-ttu-id="79d03-105">En los casos en los que proceda, adopte un enfoque de inclusión más que de exclusión para que se puedan incluir los nuevos sistemas de escritura cuando se codifiquen en Unicode.</span><span class="sxs-lookup"><span data-stu-id="79d03-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
- <span data-ttu-id="79d03-106">Excluya los caracteres que se puedan utilizar o se usen como delimitadores para que los nombres XML puedan aparecer más fácilmente en un contexto delimitado no basado en XML.</span><span class="sxs-lookup"><span data-stu-id="79d03-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
  <span data-ttu-id="79d03-107">La siguiente tabla muestra los caracteres que se pueden usar en un nombre XML, ya sea en cualquier posición dentro del nombre o en cualquier posición excepto en la primera.</span><span class="sxs-lookup"><span data-stu-id="79d03-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="79d03-108">Para el primer carácter del nombre, se excluyen algunos caracteres de los permitidos.</span><span class="sxs-lookup"><span data-stu-id="79d03-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="79d03-109">Los caracteres literales aparecen entre comillas, y los intervalos se muestran entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="79d03-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="79d03-110">Posición en el nombre</span><span class="sxs-lookup"><span data-stu-id="79d03-110">Position in name</span></span>|<span data-ttu-id="79d03-111">Caracteres permitidos</span><span class="sxs-lookup"><span data-stu-id="79d03-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="79d03-112">Cualquier posición</span><span class="sxs-lookup"><span data-stu-id="79d03-112">Any position</span></span>|<span data-ttu-id="79d03-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="79d03-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="79d03-114">Cualquier posición excepto la primera</span><span class="sxs-lookup"><span data-stu-id="79d03-114">Any position except first</span></span>|<span data-ttu-id="79d03-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="79d03-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="79d03-116">Las recomendaciones para un nombre de elemento o atributo (un nombre de nodo en la vista de árbol de esquema) en inglés son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="79d03-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="79d03-117">Utilice caracteres alfanuméricos; excepción: no empiece un nombre con un número.</span><span class="sxs-lookup"><span data-stu-id="79d03-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="79d03-118">Use el carácter de subrayado (_), guión (-), punto (.) y el punto medio (en inglés).</span><span class="sxs-lookup"><span data-stu-id="79d03-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="79d03-119">No utilice espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="79d03-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="79d03-120">Emplee palabras o combinaciones de palabras en los lenguajes naturales que sean significativas.</span><span class="sxs-lookup"><span data-stu-id="79d03-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d03-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="79d03-121">See Also</span></span>  
 <span data-ttu-id="79d03-122">[Propiedad Node Name](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="79d03-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="79d03-123">Cómo se codifican los caracteres de los nombres de nodo</span><span class="sxs-lookup"><span data-stu-id="79d03-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)
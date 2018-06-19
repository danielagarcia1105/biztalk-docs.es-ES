---
title: Que se codifican los caracteres del nombre de nodo | Documentos de Microsoft
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
ms.openlocfilehash: 3895fd74ac63380d5502a05eed7c145e13bfd681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289188"
---
# <a name="which-node-name-characters-get-encoded"></a><span data-ttu-id="33026-102">Caracteres de los nombres de nodo que se codifican</span><span class="sxs-lookup"><span data-stu-id="33026-102">Which Node Name Characters Get Encoded</span></span>
<span data-ttu-id="33026-103">XML aplica algunas restricciones a los caracteres que se pueden usar en los nombres XML (como los nombres de elemento), incluidas algunas restricciones especiales para el primer carácter de un nombre XML.</span><span class="sxs-lookup"><span data-stu-id="33026-103">XML places some restrictions on the characters that can be used in XML names, such as element names, including some special restrictions on the first character of an XML name.</span></span> <span data-ttu-id="33026-104">Los objetivos conceptuales para determinar qué caracteres se permiten y qué caracteres se deben excluir de los nombres XML permitidos son:</span><span class="sxs-lookup"><span data-stu-id="33026-104">The conceptual goals in determining which characters to allow and which characters to exclude from legal XML names are:</span></span>  
  
-   <span data-ttu-id="33026-105">En los casos en los que proceda, adopte un enfoque de inclusión más que de exclusión para que se puedan incluir los nuevos sistemas de escritura cuando se codifiquen en Unicode.</span><span class="sxs-lookup"><span data-stu-id="33026-105">Wherever applicable, be inclusive rather than exclusive, so that new writing systems can be accommodated as they are encoded in Unicode.</span></span>  
  
-   <span data-ttu-id="33026-106">Excluya los caracteres que se puedan utilizar o se usen como delimitadores para que los nombres XML puedan aparecer más fácilmente en un contexto delimitado no basado en XML.</span><span class="sxs-lookup"><span data-stu-id="33026-106">Exclude characters that may be or are used as delimiters, so that XML names can more easily appear in a non-XML, delimited context.</span></span>  
  
 <span data-ttu-id="33026-107">La siguiente tabla muestra los caracteres que se pueden usar en un nombre XML, ya sea en cualquier posición dentro del nombre o en cualquier posición excepto en la primera.</span><span class="sxs-lookup"><span data-stu-id="33026-107">The following table shows which characters can be used in an XML name, either in any position within the name, or in any position other than the first.</span></span> <span data-ttu-id="33026-108">Para el primer carácter del nombre, se excluyen algunos caracteres de los permitidos.</span><span class="sxs-lookup"><span data-stu-id="33026-108">Some allowable characters are excluded from being the first character in the name.</span></span> <span data-ttu-id="33026-109">Los caracteres literales aparecen entre comillas, y los intervalos se muestran entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="33026-109">Literal characters are quoted, and ranges are shown within square brackets.</span></span>  
  
|<span data-ttu-id="33026-110">Posición en el nombre</span><span class="sxs-lookup"><span data-stu-id="33026-110">Position in name</span></span>|<span data-ttu-id="33026-111">Caracteres permitidos</span><span class="sxs-lookup"><span data-stu-id="33026-111">Allowed characters</span></span>|  
|----------------------|------------------------|  
|<span data-ttu-id="33026-112">Cualquier posición</span><span class="sxs-lookup"><span data-stu-id="33026-112">Any position</span></span>|<span data-ttu-id="33026-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span><span class="sxs-lookup"><span data-stu-id="33026-113">["A"-"Z"], ["a"-"z"], "_", [0x00C0-0x02FF], [0x0370-0x037D], [0x037F-0x1FFF], [0x200C-0x200D], [0x2070-0x218F], [0x2C00-0x2FEF], [0x3001-0xD7FF], [0xF900-0xEFFF]</span></span>|  
|<span data-ttu-id="33026-114">Cualquier posición excepto la primera</span><span class="sxs-lookup"><span data-stu-id="33026-114">Any position except first</span></span>|<span data-ttu-id="33026-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span><span class="sxs-lookup"><span data-stu-id="33026-115">"-", ".", ["0"-"9"], 0x00B7, [0x0300-0x036F], [0x203F-0x2040]</span></span>|  
  
 <span data-ttu-id="33026-116">Las recomendaciones para un nombre de elemento o atributo (un nombre de nodo en la vista de árbol de esquema) en inglés son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="33026-116">Best practice in English for an element or attribute name (a node name in the schema tree view) can be summarized as:</span></span>  
  
-   <span data-ttu-id="33026-117">Utilice caracteres alfanuméricos; excepción: no empiece un nombre con un número.</span><span class="sxs-lookup"><span data-stu-id="33026-117">Use alphanumeric characters, except do not begin a name with a numeral.</span></span>  
  
-   <span data-ttu-id="33026-118">Utilice el carácter de subrayado (_), guión (-), punto (.) y punto intermedio (·).</span><span class="sxs-lookup"><span data-stu-id="33026-118">Use the underscore (_),hyphen (-), period (.), and middle dot (·).</span></span>  
  
-   <span data-ttu-id="33026-119">No utilice espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="33026-119">Do not use white space.</span></span>  
  
-   <span data-ttu-id="33026-120">Emplee palabras o combinaciones de palabras en los lenguajes naturales que sean significativas.</span><span class="sxs-lookup"><span data-stu-id="33026-120">Use meaningful words or combinations of words in natural languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33026-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="33026-121">See Also</span></span>  
 <span data-ttu-id="33026-122">[Propiedad Node Name](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="33026-122">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="33026-123">¿Cómo se codifican los caracteres del nombre de nodo</span><span class="sxs-lookup"><span data-stu-id="33026-123">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)
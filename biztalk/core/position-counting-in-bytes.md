---
title: Contar posiciones en Bytes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264036"
---
# <a name="position-counting-in-bytes"></a><span data-ttu-id="e08c7-102">Contar posiciones en Bytes</span><span class="sxs-lookup"><span data-stu-id="e08c7-102">Position Counting in Bytes</span></span>

## <a name="overview"></a><span data-ttu-id="e08c7-103">Información general</span><span class="sxs-lookup"><span data-stu-id="e08c7-103">Overview</span></span>

<span data-ttu-id="e08c7-104">Puede usar el **contar posiciones en Bytes** propiedad de la **esquema** nodo:</span><span class="sxs-lookup"><span data-stu-id="e08c7-104">You can use the **Count Positions In Bytes** property of the **Schema** node to:</span></span> 

* <span data-ttu-id="e08c7-105">Especificar cómo los valores especifique para la **longitud posicional** y **desplazamiento posicional** se interpretan las propiedades de los campos de los registros posicionales</span><span class="sxs-lookup"><span data-stu-id="e08c7-105">Specify how the values you enter for the **Positional Length** and **Positional Offset** properties of the various fields within positional records are interpreted</span></span>
* <span data-ttu-id="e08c7-106">Especificar cómo los valores especifique para la **desplazamiento de etiquetas** se interpreta la propiedad de los propios registros posicionales</span><span class="sxs-lookup"><span data-stu-id="e08c7-106">Specify how the values you enter for the **Tag Offset** property of the positional records themselves are interpreted</span></span>

<span data-ttu-id="e08c7-107">De forma predeterminada, estos valores se interpretan como un número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e08c7-107">By default, these values are interpreted as a number of characters.</span></span> <span data-ttu-id="e08c7-108">Pero cuando el **contar posiciones en Bytes** propiedad está establecida en **True**, estos valores se interpretan como un número de bytes.</span><span class="sxs-lookup"><span data-stu-id="e08c7-108">But when the **Count Positions In Bytes** property is set to **True**, these values are interpreted as a number of bytes.</span></span>  
  
 <span data-ttu-id="e08c7-109">Establecer el **contar posiciones en Bytes** propiedad **True** se podría es necesario cuando se trabaja con juegos de caracteres multibyte establecer datos (MNCS o DBCS), o cuando los mensajes de archivo sin formato se originan en SAP, grandes sistemas, o otros sistemas que puedan contar posiciones en bytes.</span><span class="sxs-lookup"><span data-stu-id="e08c7-109">Setting the **Count Positions In Bytes** property to **True** might be necessary when dealing with multibyte character set (MBCS or DBCS) data, or when your flat file messages originate in SAP, mainframes, or other systems that may count positions in bytes.</span></span>  
  
 <span data-ttu-id="e08c7-110">El proceso de contar las longitudes de los campos en bytes puede ser complejo si el número de bytes utilizados para codificar los caracteres es variable y puede originar algunos problemas con respecto a la determinación de los límites de campo.</span><span class="sxs-lookup"><span data-stu-id="e08c7-110">Counting field lengths in bytes can be complicated when the number of bytes used to encode characters is variable, and can result in some issues with respect to determining field boundaries.</span></span> <span data-ttu-id="e08c7-111">Cuando el desensamblador de archivos sin formato analiza un archivo sin formato en estas situaciones, intenta tomar las decisiones de análisis adecuadas según el conocimiento que tiene de la codificación de caracteres en uso.</span><span class="sxs-lookup"><span data-stu-id="e08c7-111">When the flat file disassembler parses a flat file in such situations, it attempts to make appropriate parsing decisions based on its knowledge of the character encoding in use.</span></span>  
  
 <span data-ttu-id="e08c7-112">Un ejemplo de problema de este tipo de decisión de análisis está relacionado con el tratamiento de los bytes iniciales en las codificaciones de caracteres MBCS.</span><span class="sxs-lookup"><span data-stu-id="e08c7-112">An example of this type of parsing decision concerns lead bytes in MBCS character encodings.</span></span> <span data-ttu-id="e08c7-113">Los bytes iniciales son valores de byte muy conocidos que se utilizan para iniciar las codificaciones de caracteres multibyte y nunca deben aparecer de forma aislada.</span><span class="sxs-lookup"><span data-stu-id="e08c7-113">Lead bytes are well-known byte values that are used to begin multibyte character encodings, and which should never occur on their own.</span></span> <span data-ttu-id="e08c7-114">Al especificar la longitud de los campos mediante bytes en lugar de caracteres, pueden surgir situaciones en las que el último byte de un campo se considere un byte inicial, que no puede constituir un carácter por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="e08c7-114">When specifying the length of the fields using bytes rather than character, situations may arise in which the last byte in a field is found to be a lead byte, which cannot constitute an entire character on its own.</span></span> <span data-ttu-id="e08c7-115">En tales casos, el desensamblador de archivos sin formato tratará el carácter que aparece justo antes del byte inicial como el último carácter del campo anterior y empezará a analizar el siguiente campo a partir del byte inicial.</span><span class="sxs-lookup"><span data-stu-id="e08c7-115">In such cases, the flat file disassembler will treat the character occurring just prior to the lead byte as the last character in the previous field, and begin parsing the next field starting with the lead byte.</span></span>  

<span data-ttu-id="e08c7-116">Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="e08c7-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e08c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e08c7-117">See Also</span></span>  
 [<span data-ttu-id="e08c7-118">Consideraciones del registro posicional</span><span class="sxs-lookup"><span data-stu-id="e08c7-118">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   

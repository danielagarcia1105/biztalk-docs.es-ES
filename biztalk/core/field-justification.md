---
title: "Campo de justificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9209040e64380b3a7a167dd013a15232543a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="field-justification"></a><span data-ttu-id="b4396-102">Justificación de los campos</span><span class="sxs-lookup"><span data-stu-id="b4396-102">Field Justification</span></span>

## <a name="overview"></a><span data-ttu-id="b4396-103">Información general</span><span class="sxs-lookup"><span data-stu-id="b4396-103">Overview</span></span>
<span data-ttu-id="b4396-104">Por justificación de campo se entiende si los caracteres de datos de un campo aparecen antes (alineados a la izquierda) o después (alineados a la derecha) de cualquier carácter controlador que les acompañe.</span><span class="sxs-lookup"><span data-stu-id="b4396-104">Field justification concerns whether the data characters in a field occur before (left-aligned) or after (right-aligned) any accompanying pad characters.</span></span>  
  
 <span data-ttu-id="b4396-105">En ocasiones, los caracteres de datos incluidos en un campo no necesitan todo el espacio dedicado a ese campo.</span><span class="sxs-lookup"><span data-stu-id="b4396-105">Sometimes the data characters contained within a field do not require all of the space dedicated to that field.</span></span> <span data-ttu-id="b4396-106">Esto es cierto con mayor frecuencia en los registros posicionales, donde el número de bytes o caracteres dedicados a un campo es fijo, según lo determinado por la **longitud posicional** y **desplazamiento posicional** propiedades.</span><span class="sxs-lookup"><span data-stu-id="b4396-106">This is true most frequently in positional records, where the number of bytes or characters dedicated to a field is fixed, as determined by the **Positional Length** and **Positional Offset** properties.</span></span> <span data-ttu-id="b4396-107">Esto es habitual en situaciones en las que el elemento de datos es más pequeño que la longitud de campo, con la parte sin utilizar del campo rellenada con caracteres controladores.</span><span class="sxs-lookup"><span data-stu-id="b4396-107">It is common in such scenarios that the item of data is smaller than the field length, with the unused portion of the field being filled with pad characters.</span></span>  
  
 <span data-ttu-id="b4396-108">Tal relleno también puede producirse en los registros delimitados cuando el valor de la **longitud mínima con carácter controlador** propiedad supera el espacio necesario para almacenar el elemento de datos relevante.</span><span class="sxs-lookup"><span data-stu-id="b4396-108">Such padding can also occur in delimited records when the value of the **Minimum Length with Pad Character** property exceeds the space required to store the relevant item of data.</span></span>  
  
 <span data-ttu-id="b4396-109">En ambos casos, el valor de la **justificación** propiedad (**izquierda** o **derecha**) de la correspondiente **elemento de campo** o **Atributo de campo** nodo determina si los caracteres controladores seguirá los caracteres de datos (alineados a la izquierda) o si los caracteres controladores estará precedido por los caracteres de datos (alineados a la derecha).</span><span class="sxs-lookup"><span data-stu-id="b4396-109">In both such cases, the value of the **Justification** property (**Left** or **Right**) of the relevant **Field Element** or **Field Attribute** node determines whether the pad characters will follow the data characters (left-aligned) or whether the pad characters will precede the data characters (right-aligned).</span></span>  
  
 <span data-ttu-id="b4396-110">Cuando el Desensamblador de archivos sin formato convierte un mensaje de instancia de archivo sin formato en el mensaje de instancia XML equivalente, el **justificación** propiedad se utiliza al analizar el campo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b4396-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the **Justification** property is used when parsing the corresponding field.</span></span> <span data-ttu-id="b4396-111">Cuando el ensamblador de archivo sin formato convierte un mensaje de instancia XML en un mensaje de instancia de archivo sin formato equivalente, el **justificación** propiedad se utiliza para determinar si los caracteres controladores asociados con un campo concreto, si los hay, se debe agregar al flujo de datos: ya sea antes o después de los caracteres de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b4396-111">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the **Justification** property is used to determine when the pad characters associated with a particular field, if any, should be added to the data stream: either before or after the corresponding data characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4396-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4396-112">See Also</span></span>  
- [<span data-ttu-id="b4396-113">Consideraciones de campo</span><span class="sxs-lookup"><span data-stu-id="b4396-113">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="b4396-114">Obtener más información sobre las propiedades siguientes [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="b4396-114">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="b4396-115">Justificación (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="b4396-115">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="b4396-116">Desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="b4396-116">Positional Offset (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="b4396-117">Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)</span><span class="sxs-lookup"><span data-stu-id="b4396-117">Positional Length (Node Property of Flat File Schemas)</span></span>
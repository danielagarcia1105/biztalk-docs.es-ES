---
title: Longitudes de los campos dentro de los registros delimitados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 992ffbc6a2e0568bc000413bf90b3c92012d4d59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983317"
---
# <a name="minimum-field-lengths-within-delimited-records"></a><span data-ttu-id="c486b-102">Longitudes de los campos dentro de los registros delimitados</span><span class="sxs-lookup"><span data-stu-id="c486b-102">Minimum Field Lengths Within Delimited Records</span></span>
<span data-ttu-id="c486b-103">Por definición, los campos de los registros posicionales están definidos para tener longitudes exactas específicas.</span><span class="sxs-lookup"><span data-stu-id="c486b-103">By definition, the fields in positional records are all defined to have specific exact lengths.</span></span> <span data-ttu-id="c486b-104">Los campos de los registros delimitados también pueden estar definidos para tener una longitud mínima.</span><span class="sxs-lookup"><span data-stu-id="c486b-104">Fields in delimited records can also be defined to have a minimum length.</span></span> <span data-ttu-id="c486b-105">Esta característica se define por la **[longitud mínima con carácter controlador** propiedad de **elemento de campo** y **atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="c486b-105">This characteristic is defined by the **[Minimum Length with Pad Character** property of **Field Element** and **Field Attribute** nodes.</span></span>  

 <span data-ttu-id="c486b-106">Cuando se proporciona un valor distinto de cero para el **longitud mínima con carácter controlador** propiedad, el ensamblador de archivo sin formato determinará si el número de caracteres de datos asociado con el campo es menor que la configuración de la **Longitud mínima con carácter controlador** propiedad, se usará el carácter controlador relevante para compensar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="c486b-106">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file assembler will determine whether the number of data characters associated with the field is smaller than the setting of the **Minimum Length with Pad Character** property, the relevant pad character will be used to make up the difference.</span></span>  

 <span data-ttu-id="c486b-107">Los caracteres controladores se agregarán antes o después de los caracteres de datos según la configuración de la **justificación** propiedad para el campo.</span><span class="sxs-lookup"><span data-stu-id="c486b-107">The pad characters will be added before or after the data characters based on the setting of the **Justification** property for the field.</span></span> <span data-ttu-id="c486b-108">Cuando el **justificación** propiedad está establecida en **izquierda**, se agregarán los caracteres controladores necesarios para cubrir la longitud mínima después de los caracteres de datos.</span><span class="sxs-lookup"><span data-stu-id="c486b-108">When the **Justification** property is set to **Left**, any pad characters required to meet the minimum length will be added after the data characters.</span></span> <span data-ttu-id="c486b-109">Cuando el **justificación** propiedad está establecida en **derecha**, se agregarán los caracteres controladores necesarios para cubrir la longitud mínima antes de los caracteres de datos.</span><span class="sxs-lookup"><span data-stu-id="c486b-109">When the **Justification** property is set to **Right**, any pad characters required to meet the minimum length will be added before the data characters.</span></span>  

 <span data-ttu-id="c486b-110">Cuando se proporciona un valor distinto de cero para el **longitud mínima con carácter controlador** propiedad, el Desensamblador de archivos sin formato examinará el principio o al final (según la configuración de la **justificación** propiedad) de el valor del campo para la presencia del carácter controlador relevante y, si está presente, los caracteres controladores se descartarán y no aparecen en el mensaje XML equivalente que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="c486b-110">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file disassembler will examine the beginning or end (based on the setting of the **Justification** property) of the field value for the presence of the relevant pad character, and if present, the pad characters will be discarded and not appear in the equivalent XML message being constructed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c486b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c486b-111">See Also</span></span>  
- [<span data-ttu-id="c486b-112">Consideraciones sobre campos</span><span class="sxs-lookup"><span data-stu-id="c486b-112">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="c486b-113">**Justificación (propiedad de nodo de esquemas de archivo sin formato)** y **longitud mínima con carácter controlador (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c486b-113">**Justification (Node Property of Flat File Schemas)** and **Minimum Length with Pad Character (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

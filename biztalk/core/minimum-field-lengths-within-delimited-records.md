---
title: "Longitudes mínimas de los campos de los registros delimitados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d803eb311bda7c27db5a05830f7a84f9b9857e8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="minimum-field-lengths-within-delimited-records"></a><span data-ttu-id="1fb54-102">Longitudes mínimas de los campos de los registros delimitados</span><span class="sxs-lookup"><span data-stu-id="1fb54-102">Minimum Field Lengths Within Delimited Records</span></span>
<span data-ttu-id="1fb54-103">Por definición, los campos de los registros posicionales están definidos para tener longitudes exactas específicas.</span><span class="sxs-lookup"><span data-stu-id="1fb54-103">By definition, the fields in positional records are all defined to have specific exact lengths.</span></span> <span data-ttu-id="1fb54-104">Los campos de los registros delimitados también pueden estar definidos para tener una longitud mínima.</span><span class="sxs-lookup"><span data-stu-id="1fb54-104">Fields in delimited records can also be defined to have a minimum length.</span></span> <span data-ttu-id="1fb54-105">Esta característica se define por la **[longitud mínima con carácter controlador** propiedad de **elemento de campo** y **atributo de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="1fb54-105">This characteristic is defined by the **[Minimum Length with Pad Character** property of **Field Element** and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="1fb54-106">Cuando se proporciona un valor distinto de cero para la **longitud mínima con carácter controlador** propiedad, el ensamblador de archivo sin formato determinará si el número de caracteres de datos asociados al campo es menor que la configuración de la **Longitud mínima con carácter controlador** propiedad, se usará el carácter controlador relevante para compensar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="1fb54-106">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file assembler will determine whether the number of data characters associated with the field is smaller than the setting of the **Minimum Length with Pad Character** property, the relevant pad character will be used to make up the difference.</span></span>  
  
 <span data-ttu-id="1fb54-107">Los caracteres controladores se agregarán antes o después de los caracteres de datos en función del valor de la **justificación** propiedad para el campo.</span><span class="sxs-lookup"><span data-stu-id="1fb54-107">The pad characters will be added before or after the data characters based on the setting of the **Justification** property for the field.</span></span> <span data-ttu-id="1fb54-108">Cuando el **justificación** propiedad está establecida en **izquierda**, se agregarán los caracteres controladores necesarios para satisfacer la longitud mínima después de los caracteres de datos.</span><span class="sxs-lookup"><span data-stu-id="1fb54-108">When the **Justification** property is set to **Left**, any pad characters required to meet the minimum length will be added after the data characters.</span></span> <span data-ttu-id="1fb54-109">Cuando el **justificación** propiedad está establecida en **derecha**, se agregarán los caracteres controladores necesarios para satisfacer la longitud mínima antes de los caracteres de datos.</span><span class="sxs-lookup"><span data-stu-id="1fb54-109">When the **Justification** property is set to **Right**, any pad characters required to meet the minimum length will be added before the data characters.</span></span>  
  
 <span data-ttu-id="1fb54-110">Cuando se proporciona un valor distinto de cero para la **longitud mínima con carácter controlador** propiedad, el Desensamblador de archivos sin formato examinará el principio o el final (según la configuración de la **justificación** propiedad) de el valor del campo para la presencia del carácter controlador relevante y, si está presente, los caracteres controladores se descartarán y no aparecen en el mensaje XML equivalente que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="1fb54-110">When you provide a nonzero value for the **Minimum Length with Pad Character** property, the flat file disassembler will examine the beginning or end (based on the setting of the **Justification** property) of the field value for the presence of the relevant pad character, and if present, the pad characters will be discarded and not appear in the equivalent XML message being constructed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb54-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fb54-111">See Also</span></span>  
-  [<span data-ttu-id="1fb54-112">Consideraciones de campo</span><span class="sxs-lookup"><span data-stu-id="1fb54-112">Field Considerations</span></span>](../core/field-considerations.md)   
-  <span data-ttu-id="1fb54-113">**Justificación (propiedad de nodo de esquemas de archivo sin formato)** y **longitud mínima con carácter controlador (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb54-113">**Justification (Node Property of Flat File Schemas)** and **Minimum Length with Pad Character (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
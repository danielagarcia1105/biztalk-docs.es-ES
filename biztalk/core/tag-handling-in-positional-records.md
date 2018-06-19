---
title: Control de etiqueta en los registros posicionales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804647b3cf43b9b6747b2e5f50e05e38313b03d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278572"
---
# <a name="tag-handling-in-positional-records"></a><span data-ttu-id="5825d-102">Tratamiento de los registros posicionales de las etiquetas</span><span class="sxs-lookup"><span data-stu-id="5825d-102">Tag Handling in Positional Records</span></span>

## <a name="overview"></a><span data-ttu-id="5825d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="5825d-103">Overview</span></span>
<span data-ttu-id="5825d-104">Los registros posicionales pueden incluir una secuencia conocida de caracteres denominada etiqueta que puede usarse para eliminar la ambigüedad existente entre un tipo de registro y otro.</span><span class="sxs-lookup"><span data-stu-id="5825d-104">Positional records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="5825d-105">Esto permite que el Desensamblador de archivos sin formato identificar correctamente la correspondiente **registro** nodo en el esquema que contiene la información necesaria para analizar correctamente el registro de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="5825d-105">This allows the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  
  
 <span data-ttu-id="5825d-106">Puede usar el **[identificador de etiquetas** y **desplazamiento de etiquetas** propiedades entre sí para especificar la etiqueta y su posición dentro de un registro posicional.</span><span class="sxs-lookup"><span data-stu-id="5825d-106">You can use the **[Tag Identifier** and **Tag Offset** properties together to specify the tag and its position within a positional record.</span></span> <span data-ttu-id="5825d-107">Tenga en cuenta que esto permite que la etiqueta aparezca en cualquier lugar dentro del registro posicional y que, según la configuración para la **longitud posicional** y **desplazamiento posicional** propiedades de los distintos campos el registro, la etiqueta se puede interpretar como parte de los datos asociados a uno o varios de estos campos.</span><span class="sxs-lookup"><span data-stu-id="5825d-107">Note that this allows the tag to occur anywhere within the positional record and that depending on your settings for the **Positional Length** and **Positional Offset** properties of the various fields within the record, the tag can be interpreted as part of data associated with one or more of these fields.</span></span>  
  
 <span data-ttu-id="5825d-108">El **desplazamiento posicional** propiedad también permite tratar la etiqueta por separado de los datos en el registro.</span><span class="sxs-lookup"><span data-stu-id="5825d-108">The **Positional Offset** property also allows you to treat the tag separately from the data in the record.</span></span> <span data-ttu-id="5825d-109">Por ejemplo, si la etiqueta se produce al principio del registro y es de cuatro caracteres de longitud, podría establecer el valor de la **desplazamiento posicional** propiedad del primer campo en el registro en cuatro, con lo que se omitirá de forma eficaz el etiqueta del registro posicional cuando se convierte el valor del primer campo en el formato XML equivalente del registro.</span><span class="sxs-lookup"><span data-stu-id="5825d-109">For example, if the tag occurs at the beginning of the record and is four characters in length, you could set the value of the **Positional Offset** property of the first field in the record to four, thereby effectively skipping over the positional record tag when the value of the first field is translated in the equivalent XML format of the record.</span></span>  

<span data-ttu-id="5825d-110">Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="5825d-110">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5825d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5825d-111">See Also</span></span>  
 [<span data-ttu-id="5825d-112">Consideraciones del registro posicional</span><span class="sxs-lookup"><span data-stu-id="5825d-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   

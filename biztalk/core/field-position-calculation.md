---
title: "Cálculo de la posición de campo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c58f532ea64300518667d677d2248f5c1c2b6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="field-position-calculation"></a><span data-ttu-id="9d246-102">Cálculo de la posición de campo</span><span class="sxs-lookup"><span data-stu-id="9d246-102">Field Position Calculation</span></span>

## <a name="overview"></a><span data-ttu-id="9d246-103">Información general</span><span class="sxs-lookup"><span data-stu-id="9d246-103">Overview</span></span>
<span data-ttu-id="9d246-104">Cuando se usa el **longitud posicional** y **desplazamiento posicional** propiedades de la **elemento de campo** y **atributo de campo** nodos en el esquema para definir el diseño de los registros posicionales en el mensaje de archivo sin formato, el **posición iniciar** y **longitud** columnas de la **archivos planos** pestaña Editor de BizTalk muestra las posiciones iniciales calculadas y longitudes, respectivamente, de los campos correspondientes y los registros.</span><span class="sxs-lookup"><span data-stu-id="9d246-104">When you use the **Positional Length** and **Positional Offset** properties of the **Field Element** and **Field Attribute** nodes in your schema to define the layout of the positional records in your flat file message, the **Start Position** and **Length** columns of the **Flat File** tab in BizTalk Editor show the calculated starting positions and lengths, respectively, of the relevant fields and records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d246-105">El **archivos planos** ficha aparece como una vista con pestañas alternativa con la vista XSD en el Editor de BizTalk cuando se ha configurado la extensión de archivo sin formato mediante la **extensiones de Editor de esquemas** propiedad de la **Esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="9d246-105">The **Flat File** tab appear as an alternate tabbed view with the XSD view in BizTalk Editor when you have configured the flat file extension using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="9d246-106">Para obtener más información acerca de esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="9d246-106">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="9d246-107">En general, la posición inicial de un campo determinado *N* es la posición inicial del campo anterior más la longitud del campo anterior, más el desplazamiento (posicional) especificado para el campo *N*.</span><span class="sxs-lookup"><span data-stu-id="9d246-107">In general, the starting position of a particular field *N* is the starting position of the previous field, plus the length of the previous field, plus the (positional) offset you have specified for field *N*.</span></span>  
  
 <span data-ttu-id="9d246-108">Todo el cálculo posición de campo en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es realiza automáticamente, sobre la marcha, sin necesidad de ejecutar un comando (como ocurría en versiones anteriores de BizTalk Server).</span><span class="sxs-lookup"><span data-stu-id="9d246-108">All field position calculation in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is performed automatically, on-the-fly, without any need to execute a command (as was required in previous versions of BizTalk Server).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d246-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d246-109">See Also</span></span>  
-  [<span data-ttu-id="9d246-110">Consideraciones del registro posicional</span><span class="sxs-lookup"><span data-stu-id="9d246-110">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
-  <span data-ttu-id="9d246-111">**Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)** y **desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9d246-111">**Positional Length (Node Property of Flat File Schemas)** and **Positional Offset (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
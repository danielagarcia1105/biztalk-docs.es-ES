---
title: Cálculo de la posición de campo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb167c0bf704aee869e81798116377608fde0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983029"
---
# <a name="field-position-calculation"></a><span data-ttu-id="c73da-102">Cálculo de la posición de campo</span><span class="sxs-lookup"><span data-stu-id="c73da-102">Field Position Calculation</span></span>

## <a name="overview"></a><span data-ttu-id="c73da-103">Información general</span><span class="sxs-lookup"><span data-stu-id="c73da-103">Overview</span></span>
<span data-ttu-id="c73da-104">Cuando se usa el **longitud posicional** y **desplazamiento posicional** propiedades de la **elemento de campo** y **atributo de campo** nodos en el esquema para definir el diseño de los registros posicionales en un mensaje de archivo sin formato, el **posición iniciar** y **longitud** columnas de la **archivos sin formato** pestaña El Editor de BizTalk muestran las posiciones de iniciales calculadas y longitudes, respectivamente, de los campos correspondientes y los registros.</span><span class="sxs-lookup"><span data-stu-id="c73da-104">When you use the **Positional Length** and **Positional Offset** properties of the **Field Element** and **Field Attribute** nodes in your schema to define the layout of the positional records in your flat file message, the **Start Position** and **Length** columns of the **Flat File** tab in BizTalk Editor show the calculated starting positions and lengths, respectively, of the relevant fields and records.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c73da-105">El **archivos planos** pestaña aparece como una vista con pestañas alternativa con la vista XSD en el Editor de BizTalk cuando se ha configurado la extensión de archivo sin formato mediante el **extensiones de Editor de esquemas** propiedad de la **Esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="c73da-105">The **Flat File** tab appear as an alternate tabbed view with the XSD view in BizTalk Editor when you have configured the flat file extension using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="c73da-106">Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="c73da-106">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

 <span data-ttu-id="c73da-107">En general, la posición inicial de un campo determinado *N* es la posición inicial del campo anterior, así como la longitud del campo anterior, más el desplazamiento (posicional) especificado para el campo *N*.</span><span class="sxs-lookup"><span data-stu-id="c73da-107">In general, the starting position of a particular field *N* is the starting position of the previous field, plus the length of the previous field, plus the (positional) offset you have specified for field *N*.</span></span>  

 <span data-ttu-id="c73da-108">Cálculo de la posición de campo todos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es realiza automáticamente, en la marcha, sin necesidad de ejecutar un comando (como era necesario en versiones anteriores de BizTalk Server).</span><span class="sxs-lookup"><span data-stu-id="c73da-108">All field position calculation in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is performed automatically, on-the-fly, without any need to execute a command (as was required in previous versions of BizTalk Server).</span></span>  

## <a name="see-also"></a><span data-ttu-id="c73da-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c73da-109">See Also</span></span>  
- [<span data-ttu-id="c73da-110">Consideraciones acerca de los registros posicionales</span><span class="sxs-lookup"><span data-stu-id="c73da-110">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
- <span data-ttu-id="c73da-111">**Longitud posicional (propiedad de nodo de esquemas de archivo sin formato)** y **desplazamiento posicional (propiedad de nodo de esquemas de archivo sin formato)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c73da-111">**Positional Length (Node Property of Flat File Schemas)** and **Positional Offset (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

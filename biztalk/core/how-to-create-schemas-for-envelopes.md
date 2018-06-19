---
title: Cómo crear esquemas para sobres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae1c991c-447f-497e-803c-1cb8cad2846b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7308a093f9f95ce2342f268554deb67193aea053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249596"
---
# <a name="create-schemas-for-envelopes"></a><span data-ttu-id="df1bb-102">Crear esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="df1bb-102">Create Schemas for Envelopes</span></span>

## <a name="overview"></a><span data-ttu-id="df1bb-103">Información general</span><span class="sxs-lookup"><span data-stu-id="df1bb-103">Overview</span></span>
<span data-ttu-id="df1bb-104">Después de crear un esquema de mensaje XML como se describe en [crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md), establezca el **sobres** propiedad de la **esquema** nodo **Sí**.</span><span class="sxs-lookup"><span data-stu-id="df1bb-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), set the **Envelope** property of the **Schema** node to **Yes**.</span></span> <span data-ttu-id="df1bb-105">En función de determinadas características del esquema de sobre, como si hay varios nodos raíz, deberá establecer otras propiedades específicas del sobre.</span><span class="sxs-lookup"><span data-stu-id="df1bb-105">Depending on certain characteristics of your envelope schema, such as whether there are multiple root nodes, you will need to set several other envelope-specific properties.</span></span> <span data-ttu-id="df1bb-106">Para obtener más información, consulte [esquemas de sobres](../core/envelope-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="df1bb-106">For more information, see [Envelope Schemas](../core/envelope-schemas.md).</span></span>  
  
 <span data-ttu-id="df1bb-107">La propiedad XPath de cuerpo del sobre hace referencia al elemento que contiene los elementos de documento.</span><span class="sxs-lookup"><span data-stu-id="df1bb-107">The body XPath property of the envelope points to the element that contains the document elements.</span></span> <span data-ttu-id="df1bb-108">El elemento real al que hace referencia el XPath no pertenece al documento.</span><span class="sxs-lookup"><span data-stu-id="df1bb-108">The actual element where the XPath points to does not belong to the document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1bb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="df1bb-109">See Also</span></span>  
-  [<span data-ttu-id="df1bb-110">Administrar esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="df1bb-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
-  <span data-ttu-id="df1bb-111">**Envoltura** propiedad[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="df1bb-111">**Envelope** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
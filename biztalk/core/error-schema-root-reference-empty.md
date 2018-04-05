---
title: 'Error: referencia raíz de esquema vacía | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7217f6f9ea328aff4864cfdf3bee9ea71de3741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-root-reference-empty"></a><span data-ttu-id="97e04-102">Error: referencia raíz de esquema vacía</span><span class="sxs-lookup"><span data-stu-id="97e04-102">Error - Schema Root Reference Empty</span></span>
<span data-ttu-id="97e04-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="97e04-103">**Error Code**</span></span>  
  
 <span data-ttu-id="97e04-104">BEC2005</span><span class="sxs-lookup"><span data-stu-id="97e04-104">BEC2005</span></span>  
  
 <span data-ttu-id="97e04-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="97e04-105">**Explanation**</span></span>  
  
 <span data-ttu-id="97e04-106">El **referencia raíz** propiedad de la **esquema** nodo no está establecido.</span><span class="sxs-lookup"><span data-stu-id="97e04-106">The **Root Reference** property of the **Schema** node is not set.</span></span> <span data-ttu-id="97e04-107">Cuando el **estándar** propiedad de la **esquema** nodo se establece en un valor distinto de **XML**, debe establecer el **referencia raíz** propiedad indicar qué nodo secundario de la **esquema** nodo está pensado para usarse como la raíz del mensaje definido por este esquema.</span><span class="sxs-lookup"><span data-stu-id="97e04-107">When the **Standard** property of the **Schema** node is set to a value other than **XML**, you must set the **Root Reference** property to indicate which child node of the **Schema** node is meant to be used as the root of the message defined by this schema.</span></span>  
  
 <span data-ttu-id="97e04-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="97e04-108">**User Action**</span></span>  
  
 <span data-ttu-id="97e04-109">Según corresponda para el esquema, establezca el **estándar** propiedad de la **esquema** nodo **XML**, o establecer la **referencia raíz** propiedad de la **esquema** nodo para el nodo secundario correspondiente de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="97e04-109">As appropriate for your schema, either set the **Standard** property of the **Schema** node to **XML**, or set the **Root Reference** property of the **Schema** node to the appropriate child node of the **Schema** node.</span></span> <span data-ttu-id="97e04-110">Los siguientes nodos secundarios están disponibles en la **referencia raíz** lista de propiedades de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="97e04-110">These child nodes are the available in the **Root Reference** property drop-down list.</span></span>
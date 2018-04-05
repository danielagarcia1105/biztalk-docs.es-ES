---
title: 'Advertencia: esquema de sobres necesita nodo raíz registro | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.envelopeSchemaNeedsRoot
ms.assetid: 3fbc1571-1270-4c5e-adcf-00633bf46efe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccc0f472e15a31c9bef6e1090e8c153f730acbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---envelope-schema-needs-root-record-node"></a><span data-ttu-id="5307c-102">Advertencia: esquema de sobres necesita nodo de registro raíz</span><span class="sxs-lookup"><span data-stu-id="5307c-102">Warning - Envelope Schema Needs Root Record Node</span></span>
<span data-ttu-id="5307c-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="5307c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5307c-104">BEC1010</span><span class="sxs-lookup"><span data-stu-id="5307c-104">BEC1010</span></span>  
  
 <span data-ttu-id="5307c-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="5307c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5307c-106">Esquemas de sobres deben tener al menos una raíz **registro** nodo como un elemento secundario de su **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="5307c-106">Envelope schemas are required to have at least one root **Record** node as a child of its **Schema** node.</span></span>  
  
 <span data-ttu-id="5307c-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="5307c-107">**User Action**</span></span>  
  
 <span data-ttu-id="5307c-108">Haga clic en el **esquema** nodo, haga clic en **Insertar registro secundario** en el menú contextual y, a continuación, escriba un nombre descriptivo para las filas insertadas **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="5307c-108">Right-click the **Schema** node, click **Insert Child Record** on the shortcut menu, and then type a descriptive name for the inserted **Record** node.</span></span> <span data-ttu-id="5307c-109">En general, los esquemas de sobres también tendrán nodos adicionales insertados dentro de la raíz **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="5307c-109">In general, envelope schemas will also have additional nodes inserted within the root **Record** node.</span></span>
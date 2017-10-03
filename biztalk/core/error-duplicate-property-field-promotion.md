---
title: "Error - promoción de campos de propiedades duplicados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87d9f6ee346f5aae98ea69c2ce4e00c4fa1d6dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---duplicate-property-field-promotion"></a><span data-ttu-id="03a81-102">Error - promoción de campos de propiedades duplicados</span><span class="sxs-lookup"><span data-stu-id="03a81-102">Error - Duplicate Property Field Promotion</span></span>
<span data-ttu-id="03a81-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="03a81-103">**Error Code**</span></span>  
  
 <span data-ttu-id="03a81-104">BEC2016</span><span class="sxs-lookup"><span data-stu-id="03a81-104">BEC2016</span></span>  
  
 <span data-ttu-id="03a81-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="03a81-105">**Explanation**</span></span>  
  
 <span data-ttu-id="03a81-106">Varios nodos de este esquema se están promocionando como campos de propiedades al mismo **elemento de campo** nodo en el mismo esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="03a81-106">Multiple nodes in this schema are being promoted as Property Fields to the same **Field Element** node in the same property schema.</span></span>  
  
 <span data-ttu-id="03a81-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="03a81-107">**User Action**</span></span>  
  
 <span data-ttu-id="03a81-108">Use el **campos de propiedades** pestaña de la **promocionar propiedades** cuadro de diálogo, tiene acceso a través de la **promocionar propiedades** propiedad de la **esquema**nodo, para eliminar todo excepto una de las promociones de campo de propiedad que están asociadas con el mismo **elemento de campo** nodo en el esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="03a81-108">Use the **Property Fields** tab of the **Promote Properties** dialog box, accessed through the **Promote Properties** property of the **Schema** node, to delete all but one of the Property Field promotions that are associated with the same **Field Element** node in the property schema.</span></span> <span data-ttu-id="03a81-109">Puede que desee agregar nuevos **elemento de campo** nodos en el esquema de propiedad para que las promociones eliminadas se puedan volver a promovido a su propia **elemento de campo** nodos.</span><span class="sxs-lookup"><span data-stu-id="03a81-109">You may want to add new **Field Element** nodes to the property schema so that the deleted promotions can be re-promoted to their own **Field Element** nodes.</span></span>
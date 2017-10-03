---
title: 'Advertencia: XPath de cuerpo no es un descendiente | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.bodyXPathNotDescendant
ms.assetid: bfeff370-9b84-4fd9-81e9-1e54b166f561
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b5d228e1119bc7c569b45cc6795f3f5b8454ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---body-xpath-not-a-descendent"></a><span data-ttu-id="0b07f-102">Advertencia: XPath de cuerpo no es un descendiente</span><span class="sxs-lookup"><span data-stu-id="0b07f-102">Warning - Body XPath Not A Descendent</span></span>
<span data-ttu-id="0b07f-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="0b07f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0b07f-104">BEC1004</span><span class="sxs-lookup"><span data-stu-id="0b07f-104">BEC1004</span></span>  
  
 <span data-ttu-id="0b07f-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="0b07f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0b07f-106">El **XPath de cuerpo** propiedad del nodo raíz indicado en este esquema de sobre hace referencia a un nodo que no es un descendiente del nodo raíz, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0b07f-106">The **Body XPath** property of the indicated root node in this envelope schema references a node that is not a descendent of that root node, as required.</span></span> <span data-ttu-id="0b07f-107">Este error no debería producirse a menos que la **XPath de cuerpo** propiedad se modificó fuera del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0b07f-107">This error should not occur unless the **Body XPath** property is modified outside of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="0b07f-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="0b07f-108">**User Action**</span></span>  
  
 <span data-ttu-id="0b07f-109">Seleccione el nodo raíz indicado y el valor para el **XPath de cuerpo** propiedad que identifique correctamente el nodo de nivel superior del cuerpo del mensaje asociado.</span><span class="sxs-lookup"><span data-stu-id="0b07f-109">Select the indicated root node and select the value for the **Body XPath** property that correctly identifies the top-level node of the associated message body.</span></span>
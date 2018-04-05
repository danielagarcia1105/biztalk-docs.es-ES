---
title: 'Error: falta el campo de propiedad | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d77311e4c8585cfb7f6108364e6a5085619595a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-field-missing"></a><span data-ttu-id="1b202-102">Error: falta el campo de propiedad</span><span class="sxs-lookup"><span data-stu-id="1b202-102">Error - Property Field Missing</span></span>
<span data-ttu-id="1b202-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="1b202-103">**Error Code**</span></span>  
  
 <span data-ttu-id="1b202-104">BEC2008</span><span class="sxs-lookup"><span data-stu-id="1b202-104">BEC2008</span></span>  
  
 <span data-ttu-id="1b202-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="1b202-105">**Explanation**</span></span>  
  
 <span data-ttu-id="1b202-106">El nodo indicado en este esquema se está promocionando a un **elemento de campo** nodo en el esquema de propiedad correspondiente que no existe.</span><span class="sxs-lookup"><span data-stu-id="1b202-106">The indicated node in this schema is being promoted to a **Field Element** node in the corresponding property schema that does not exist.</span></span> <span data-ttu-id="1b202-107">Esta condición puede producirse cuando un **elemento de campo** nodo se quitó o cambió de nombre en un esquema de propiedad una vez que se haya utilizado como destino de una promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1b202-107">This condition can occur when a **Field Element** node is removed from, or renamed in, a property schema after it has been used as the target of a property promotion.</span></span>  
  
 <span data-ttu-id="1b202-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="1b202-108">**User Action**</span></span>  
  
 <span data-ttu-id="1b202-109">Modifique el esquema de propiedades para que contenga el carácter que falta **elemento de campo** nodo, o utilizar el **promocionar propiedades** cuadro de diálogo para eliminar o modificar la promoción de propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1b202-109">Either modify the property schema so that it contains the missing **Field Element** node, or use the **Promote Properties** dialog box to delete or otherwise modify the relevant property promotion.</span></span>
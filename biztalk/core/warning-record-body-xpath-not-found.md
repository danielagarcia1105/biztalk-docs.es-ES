---
title: 'Advertencia: XPath de cuerpo de registro no encontrado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.recordBodyXPathNotFound
ms.assetid: d46e0732-08ce-4292-84d8-56dc020063e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd6640aa469fe9383b615d70235ab488c8798f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288108"
---
# <a name="warning---record-body-xpath-not-found"></a><span data-ttu-id="8e29a-102">Advertencia: XPath de cuerpo de registro no encontrado</span><span class="sxs-lookup"><span data-stu-id="8e29a-102">Warning - Record Body XPath Not Found</span></span>
<span data-ttu-id="8e29a-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="8e29a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8e29a-104">BEC1008</span><span class="sxs-lookup"><span data-stu-id="8e29a-104">BEC1008</span></span>  
  
 <span data-ttu-id="8e29a-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="8e29a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8e29a-106">El **XPath de cuerpo** se encontró la propiedad del nodo raíz indicado en este esquema de sobre para que esté vacía o hacer referencia a un nodo no existente.</span><span class="sxs-lookup"><span data-stu-id="8e29a-106">The **Body XPath** property of the indicated root node in this envelope schema was found to be empty or referencing a nonexistent node.</span></span> <span data-ttu-id="8e29a-107">Esquemas de sobres, tal y como especifica la **sobres** propiedad de la **esquema** nodo, es necesario que tengan un valor válido el **XPath de cuerpo** propiedad de la raíz especificada nodo de referencia en el esquema.</span><span class="sxs-lookup"><span data-stu-id="8e29a-107">Envelope schemas, as specified by the **Envelope** property of the **Schema** node, are required to have a valid value in the **Body XPath** property of the specified root reference node in the schema.</span></span>  
  
 <span data-ttu-id="8e29a-108">Si no se especifica ningún nodo raíz por el **referencia raíz** propiedad de la **esquema** nodo, el primer nodo raíz en el esquema, el nodo de referencia raíz de forma predeterminada, es necesario tener un valor válido en su  **XPath de cuerpo** propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e29a-108">If no root reference node is specified by the **Root Reference** property of the **Schema** node, the first root node in the schema, the default root reference node, is required to have a valid value in its **Body XPath** property.</span></span> <span data-ttu-id="8e29a-109">**XPath de cuerpo** valores de propiedad se utilizan para identificar el esquema de cada uno de los mensajes contenidos en el sobre.</span><span class="sxs-lookup"><span data-stu-id="8e29a-109">**Body XPath** property values are used to identify the schema for the each of the messages contained within the envelope.</span></span>  
  
 <span data-ttu-id="8e29a-110">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="8e29a-110">**User Action**</span></span>  
  
 <span data-ttu-id="8e29a-111">Seleccione el nodo raíz indicado y, a continuación, seleccione el valor de la **XPath de cuerpo** propiedad que identifique correctamente el esquema del cuerpo del mensaje asociado.</span><span class="sxs-lookup"><span data-stu-id="8e29a-111">Select the indicated root node and then select the value for the **Body XPath** property that correctly identifies the schema of the associated message body.</span></span>
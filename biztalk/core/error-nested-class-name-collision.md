---
title: 'Error: colisión de nombre de clase anidada | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856841093c37848924dc6e9b6d160186e03ad304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003333"
---
# <a name="error---nested-class-name-collision"></a><span data-ttu-id="92bbd-102">Error: colisión de nombre de clase anidada</span><span class="sxs-lookup"><span data-stu-id="92bbd-102">Error - Nested Class Name Collision</span></span>
<span data-ttu-id="92bbd-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="92bbd-103">**Error Code**</span></span>  

 <span data-ttu-id="92bbd-104">BEC2017</span><span class="sxs-lookup"><span data-stu-id="92bbd-104">BEC2017</span></span>  

 <span data-ttu-id="92bbd-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="92bbd-105">**Explanation**</span></span>  

 <span data-ttu-id="92bbd-106">El **nombre de tipo** se encontró la propiedad de este esquema para ser el mismo que el **RootNode TypeName** propiedad de uno de los nodos raíz en el esquema.</span><span class="sxs-lookup"><span data-stu-id="92bbd-106">The **Type Name** property of this schema was found to be the same as the **RootNode TypeName** property of one of the root nodes in the schema.</span></span> <span data-ttu-id="92bbd-107">C# no permite clases anidadas con el mismo nombre; por tanto, esta condición produce un error.</span><span class="sxs-lookup"><span data-stu-id="92bbd-107">C# disallows nested classes with the same names; therefore this condition causes an error.</span></span>  

 <span data-ttu-id="92bbd-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="92bbd-108">**User Action**</span></span>  

 <span data-ttu-id="92bbd-109">Debe cambiar uno o ambos valores de la propiedad correspondiente para evitar la colisión de nombres.</span><span class="sxs-lookup"><span data-stu-id="92bbd-109">You must change one or both of the relevant property values so that you avoid the name collision.</span></span> <span data-ttu-id="92bbd-110">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="92bbd-110">Either:</span></span>  

- <span data-ttu-id="92bbd-111">Seleccione el archivo de esquema correspondiente en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] , el Explorador de soluciones y, a continuación, en la ventana Propiedades, cambie la **nombre de tipo** propiedad a un valor válido único.</span><span class="sxs-lookup"><span data-stu-id="92bbd-111">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a unique valid value.</span></span>  

   <span data-ttu-id="92bbd-112">\- O bien</span><span class="sxs-lookup"><span data-stu-id="92bbd-112">\- or -</span></span>  

- <span data-ttu-id="92bbd-113">Seleccione el nodo raíz indicado y, a continuación, en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, cambie la **RootNode TypeName** propiedad a un valor válido único.</span><span class="sxs-lookup"><span data-stu-id="92bbd-113">Select the indicated root node, and then in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a unique valid value.</span></span>

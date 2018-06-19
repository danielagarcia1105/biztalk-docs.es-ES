---
title: No se puede continuar debido a un conflicto entre nombres de tipo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ced6de4-0950-498e-a548-5c85419726d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1d4962db915a462990962e933c1413a408eee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231212"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="6f36d-102">No se puede continuar por un conflicto entre nombres</span><span class="sxs-lookup"><span data-stu-id="6f36d-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="6f36d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6f36d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f36d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6f36d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6f36d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6f36d-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="6f36d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6f36d-106">Event ID</span></span>|<span data-ttu-id="6f36d-107">0</span><span class="sxs-lookup"><span data-stu-id="6f36d-107">0</span></span>|  
|<span data-ttu-id="6f36d-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6f36d-108">Event Source</span></span>|<span data-ttu-id="6f36d-109">0</span><span class="sxs-lookup"><span data-stu-id="6f36d-109">0</span></span>|  
|<span data-ttu-id="6f36d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6f36d-110">Component</span></span>|<span data-ttu-id="6f36d-111">0</span><span class="sxs-lookup"><span data-stu-id="6f36d-111">0</span></span>|  
|<span data-ttu-id="6f36d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6f36d-112">Symbolic Name</span></span>|<span data-ttu-id="6f36d-113">0</span><span class="sxs-lookup"><span data-stu-id="6f36d-113">0</span></span>|  
|<span data-ttu-id="6f36d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6f36d-114">Message Text</span></span>|<span data-ttu-id="6f36d-115">No se puede continuar por un conflicto entre nombres.</span><span class="sxs-lookup"><span data-stu-id="6f36d-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="6f36d-116">"{0}" ya existe en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f36d-116">The name "{0}" already exists in the namespace</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6f36d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6f36d-117">Explanation</span></span>  
 <span data-ttu-id="6f36d-118">Este error indica que varios artefactos del mismo espacio de nombres definido tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="6f36d-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6f36d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6f36d-119">User Action</span></span>  
 <span data-ttu-id="6f36d-120">Cambie el nombre de los artefactos del mismo espacio de nombres o colóquelos en un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="6f36d-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>
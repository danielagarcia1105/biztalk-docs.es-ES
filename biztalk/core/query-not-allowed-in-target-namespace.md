---
title: Consulta no se permite en el espacio de nombres de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d0475fe-2a44-415e-9995-dcb77e0d945d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce61d036912dc6caf2fd0062abb238de4ac6f491
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978863"
---
# <a name="query-not-allowed-in-target-namespace"></a><span data-ttu-id="f5a7a-102">No se admite la consulta en espacio de nombres de destino</span><span class="sxs-lookup"><span data-stu-id="f5a7a-102">Query not allowed in target namespace</span></span>
## <a name="details"></a><span data-ttu-id="f5a7a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5a7a-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f5a7a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f5a7a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f5a7a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f5a7a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f5a7a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f5a7a-106">Event ID</span></span>     |                                         <span data-ttu-id="f5a7a-107">0</span><span class="sxs-lookup"><span data-stu-id="f5a7a-107">0</span></span>                                          |
|  <span data-ttu-id="f5a7a-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f5a7a-108">Event Source</span></span>   |                                         <span data-ttu-id="f5a7a-109">0</span><span class="sxs-lookup"><span data-stu-id="f5a7a-109">0</span></span>                                          |
|    <span data-ttu-id="f5a7a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f5a7a-110">Component</span></span>    |                                         <span data-ttu-id="f5a7a-111">0</span><span class="sxs-lookup"><span data-stu-id="f5a7a-111">0</span></span>                                          |
|  <span data-ttu-id="f5a7a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f5a7a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f5a7a-113">0</span><span class="sxs-lookup"><span data-stu-id="f5a7a-113">0</span></span>                                          |
|  <span data-ttu-id="f5a7a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f5a7a-114">Message Text</span></span>   |                     <span data-ttu-id="f5a7a-115">No se admite la consulta '?' en espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="f5a7a-115">Query '?' not allowed in target namespace.</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="f5a7a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f5a7a-116">Explanation</span></span>  
 <span data-ttu-id="f5a7a-117">Este error indica que el espacio de nombres de destino especificado no puede contener consultas.</span><span class="sxs-lookup"><span data-stu-id="f5a7a-117">This error indicates the target namespace specified cannot contain queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5a7a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f5a7a-118">User Action</span></span>  
 <span data-ttu-id="f5a7a-119">Especifique un espacio de nombres de destino diferente sin la consulta.</span><span class="sxs-lookup"><span data-stu-id="f5a7a-119">Specify a different target namespace without the query.</span></span>
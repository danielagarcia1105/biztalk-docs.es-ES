---
title: 'De sesión único: Evento 10821 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2200011e-3e4f-4fe4-b01f-f3b86cdc96db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1b9d5499ac11f29034f0110e0ff0fe6850f66a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988085"
---
# <a name="single-sign-on-event-10821"></a><span data-ttu-id="e22d4-102">De sesión único: Evento 10821</span><span class="sxs-lookup"><span data-stu-id="e22d4-102">Single Sign-On: Event 10821</span></span>
## <a name="details"></a><span data-ttu-id="e22d4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e22d4-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e22d4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e22d4-104">Product Name</span></span>   |                             <span data-ttu-id="e22d4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e22d4-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="e22d4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e22d4-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="e22d4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e22d4-107">Event ID</span></span>     |                                       <span data-ttu-id="e22d4-108">10821</span><span class="sxs-lookup"><span data-stu-id="e22d4-108">10821</span></span>                                        |
|  <span data-ttu-id="e22d4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e22d4-109">Event Source</span></span>   |                                       <span data-ttu-id="e22d4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e22d4-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="e22d4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e22d4-111">Component</span></span>    |                                        <span data-ttu-id="e22d4-112">N/D</span><span class="sxs-lookup"><span data-stu-id="e22d4-112">N/A</span></span>                                         |
|  <span data-ttu-id="e22d4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e22d4-113">Symbolic Name</span></span>  |                     <span data-ttu-id="e22d4-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="e22d4-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span></span>                     |
|  <span data-ttu-id="e22d4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e22d4-115">Message Text</span></span>   | <span data-ttu-id="e22d4-116">No se puede eliminar el adaptador porque actualmente está asignado a un adaptador de grupo.</span><span class="sxs-lookup"><span data-stu-id="e22d4-116">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e22d4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e22d4-117">Explanation</span></span>  
 <span data-ttu-id="e22d4-118">No se puede eliminar el adaptador porque actualmente está asignado a un adaptador de grupo.</span><span class="sxs-lookup"><span data-stu-id="e22d4-118">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e22d4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e22d4-119">User Action</span></span>  
 <span data-ttu-id="e22d4-120">Quite la asignación del adaptador y, a continuación, elimínelo.</span><span class="sxs-lookup"><span data-stu-id="e22d4-120">Unassign the adapter and then delete it.</span></span>
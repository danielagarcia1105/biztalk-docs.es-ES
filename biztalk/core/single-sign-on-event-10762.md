---
title: 'De sesión único: Evento 10762 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905c59062f8f4af397872f3f7d4434a67b19842e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996013"
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="3b7d8-102">De sesión único: Evento 10762</span><span class="sxs-lookup"><span data-stu-id="3b7d8-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="3b7d8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b7d8-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3b7d8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3b7d8-104">Product Name</span></span>   |                                                   <span data-ttu-id="3b7d8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3b7d8-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="3b7d8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3b7d8-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="3b7d8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3b7d8-107">Event ID</span></span>     |                                                             <span data-ttu-id="3b7d8-108">10762</span><span class="sxs-lookup"><span data-stu-id="3b7d8-108">10762</span></span>                                                              |
|  <span data-ttu-id="3b7d8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3b7d8-109">Event Source</span></span>   |                                                             <span data-ttu-id="3b7d8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3b7d8-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="3b7d8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3b7d8-111">Component</span></span>    |                                                              <span data-ttu-id="3b7d8-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3b7d8-112">N/A</span></span>                                                               |
|  <span data-ttu-id="3b7d8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b7d8-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="3b7d8-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="3b7d8-114">ENTSSO_E_WRONG_THREAD</span></span>                                                      |
|  <span data-ttu-id="3b7d8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b7d8-115">Message Text</span></span>   | <span data-ttu-id="3b7d8-116">Se llamó al componente de cliente de SSO en el subproceso incorrecto.</span><span class="sxs-lookup"><span data-stu-id="3b7d8-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="3b7d8-117">Actualmente, se encuentra bloqueado en un subproceso porque tiene una transacción.</span><span class="sxs-lookup"><span data-stu-id="3b7d8-117">It is currently locked to a thread because it has a transaction.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3b7d8-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b7d8-118">Explanation</span></span>  
 <span data-ttu-id="3b7d8-119">Los componentes sólo pueden ser multiproceso cuando no tienen una transacción.</span><span class="sxs-lookup"><span data-stu-id="3b7d8-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="3b7d8-120">Este componente tiene una transacción y, por lo tanto, está bloqueado en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b7d8-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b7d8-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b7d8-121">User Action</span></span>  
 <span data-ttu-id="3b7d8-122">Configure la aplicación para que no llame a componentes de cliente de SSO en varios subprocesos cuando usa transacciones.</span><span class="sxs-lookup"><span data-stu-id="3b7d8-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>
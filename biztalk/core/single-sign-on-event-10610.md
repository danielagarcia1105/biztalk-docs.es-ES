---
title: 'De sesión único: Evento 10610 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c90855c1f136dc8204afe718ea4456c834ab667
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024410"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="82b7b-102">De sesión único: Evento 10610</span><span class="sxs-lookup"><span data-stu-id="82b7b-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="82b7b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="82b7b-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="82b7b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="82b7b-104">Product Name</span></span>   |                                                       <span data-ttu-id="82b7b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="82b7b-105">Enterprise Single Sign-On</span></span>                                                       |
| <span data-ttu-id="82b7b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="82b7b-106">Product Version</span></span> |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="82b7b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="82b7b-107">Event ID</span></span>     |                                                                 <span data-ttu-id="82b7b-108">10610</span><span class="sxs-lookup"><span data-stu-id="82b7b-108">10610</span></span>                                                                 |
|  <span data-ttu-id="82b7b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="82b7b-109">Event Source</span></span>   |                                                                <span data-ttu-id="82b7b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="82b7b-110">ENTSSO</span></span>                                                                 |
|    <span data-ttu-id="82b7b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="82b7b-111">Component</span></span>    |                                                                  <span data-ttu-id="82b7b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="82b7b-112">N/A</span></span>                                                                  |
|  <span data-ttu-id="82b7b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="82b7b-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="82b7b-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="82b7b-114">SSO_WARN_CRED_CACHE_FAILED</span></span>                                                       |
|  <span data-ttu-id="82b7b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="82b7b-115">Message Text</span></span>   | <span data-ttu-id="82b7b-116">La memoria caché de credenciales detectó un error inesperado y se cerró.</span><span class="sxs-lookup"><span data-stu-id="82b7b-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="82b7b-117">Esto puede afectar el rendimiento.%r</span><span class="sxs-lookup"><span data-stu-id="82b7b-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="82b7b-118">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="82b7b-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="82b7b-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="82b7b-119">Explanation</span></span>  
 <span data-ttu-id="82b7b-120">La memoria caché de credenciales detectó un error inesperado y se cerró.</span><span class="sxs-lookup"><span data-stu-id="82b7b-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="82b7b-121">Si bien este error puede afectar el rendimiento, no afectará la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="82b7b-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82b7b-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="82b7b-122">User Action</span></span>  
 <span data-ttu-id="82b7b-123">Reinicie el servicio SSO cuando lo considere conveniente.</span><span class="sxs-lookup"><span data-stu-id="82b7b-123">Restart the SSO service when convenient.</span></span>
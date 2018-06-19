---
title: 'Inicio de sesión único: Evento 10610 | Documentos de Microsoft'
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
ms.openlocfilehash: d3e4edc579c18147ad34234fbf268ec8d867c60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271340"
---
# <a name="single-sign-on-event-10610"></a><span data-ttu-id="70610-102">Inicio de sesión único: Evento 10610</span><span class="sxs-lookup"><span data-stu-id="70610-102">Single Sign-On: Event 10610</span></span>
## <a name="details"></a><span data-ttu-id="70610-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="70610-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70610-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="70610-104">Product Name</span></span>|<span data-ttu-id="70610-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="70610-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="70610-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="70610-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="70610-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="70610-107">Event ID</span></span>|<span data-ttu-id="70610-108">10610</span><span class="sxs-lookup"><span data-stu-id="70610-108">10610</span></span>|  
|<span data-ttu-id="70610-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="70610-109">Event Source</span></span>|<span data-ttu-id="70610-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="70610-110">ENTSSO</span></span>|  
|<span data-ttu-id="70610-111">Componente</span><span class="sxs-lookup"><span data-stu-id="70610-111">Component</span></span>|<span data-ttu-id="70610-112">N/D</span><span class="sxs-lookup"><span data-stu-id="70610-112">N/A</span></span>|  
|<span data-ttu-id="70610-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="70610-113">Symbolic Name</span></span>|<span data-ttu-id="70610-114">SSO_WARN_CRED_CACHE_FAILED</span><span class="sxs-lookup"><span data-stu-id="70610-114">SSO_WARN_CRED_CACHE_FAILED</span></span>|  
|<span data-ttu-id="70610-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="70610-115">Message Text</span></span>|<span data-ttu-id="70610-116">La memoria caché de credenciales detectó un error inesperado y se cerró.</span><span class="sxs-lookup"><span data-stu-id="70610-116">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="70610-117">Esto puede afectar el rendimiento.%r</span><span class="sxs-lookup"><span data-stu-id="70610-117">This may affect performance.%r</span></span><br /><br /> <span data-ttu-id="70610-118">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="70610-118">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70610-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="70610-119">Explanation</span></span>  
 <span data-ttu-id="70610-120">La memoria caché de credenciales detectó un error inesperado y se cerró.</span><span class="sxs-lookup"><span data-stu-id="70610-120">The credential cache has encountered an unexpected error and has shut down.</span></span> <span data-ttu-id="70610-121">Si bien este error puede afectar el rendimiento, no afectará la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="70610-121">While this may affect performance, it will not affect functionality.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70610-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="70610-122">User Action</span></span>  
 <span data-ttu-id="70610-123">Reinicie el servicio SSO cuando lo considere conveniente.</span><span class="sxs-lookup"><span data-stu-id="70610-123">Restart the SSO service when convenient.</span></span>
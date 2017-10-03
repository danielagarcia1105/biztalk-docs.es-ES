---
title: "Inicio de sesión único: Evento 11042 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da20346fbf2f73ac2ab64db3c9137394aa5bd366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="85024-102">Inicio de sesión único: Evento 11042</span><span class="sxs-lookup"><span data-stu-id="85024-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="85024-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="85024-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85024-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="85024-104">Product Name</span></span>|<span data-ttu-id="85024-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="85024-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="85024-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="85024-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="85024-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="85024-107">Event ID</span></span>|<span data-ttu-id="85024-108">11042</span><span class="sxs-lookup"><span data-stu-id="85024-108">11042</span></span>|  
|<span data-ttu-id="85024-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="85024-109">Event Source</span></span>|<span data-ttu-id="85024-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="85024-110">ENTSSO</span></span>|  
|<span data-ttu-id="85024-111">Componente</span><span class="sxs-lookup"><span data-stu-id="85024-111">Component</span></span>|<span data-ttu-id="85024-112">N/D</span><span class="sxs-lookup"><span data-stu-id="85024-112">N/A</span></span>|  
|<span data-ttu-id="85024-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="85024-113">Symbolic Name</span></span>|<span data-ttu-id="85024-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="85024-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>|  
|<span data-ttu-id="85024-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="85024-115">Message Text</span></span>|<span data-ttu-id="85024-116">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="85024-116">Access denied.</span></span><br /><br /> <span data-ttu-id="85024-117">El usuario del cliente debe ser miembro de una de las siguientes cuentas para realizar esta función.%r</span><span class="sxs-lookup"><span data-stu-id="85024-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="85024-118">Administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="85024-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="85024-119">Administradores afiliados de SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="85024-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="85024-120">Administradores de aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="85024-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="85024-121">Usuarios de aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="85024-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="85024-122">Datos adicionales: %5</span><span class="sxs-lookup"><span data-stu-id="85024-122">Additional Data: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="85024-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="85024-123">Explanation</span></span>  
 <span data-ttu-id="85024-124">Para realizar esta función, el usuario del cliente debe ser miembro de una de las cuentas enumeradas en la advertencia.</span><span class="sxs-lookup"><span data-stu-id="85024-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85024-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="85024-125">User Action</span></span>  
 <span data-ttu-id="85024-126">Debe unirse a una de las cuentas para realizar esta función.</span><span class="sxs-lookup"><span data-stu-id="85024-126">You must join one of the accounts to perform this function.</span></span>
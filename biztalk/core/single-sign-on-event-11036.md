---
title: "Inicio de sesión único: Evento 11036 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63b11005248471c222f63c88439a0e60571b341e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11036"></a><span data-ttu-id="2a555-102">Inicio de sesión único: Evento 11036</span><span class="sxs-lookup"><span data-stu-id="2a555-102">Single Sign-On: Event 11036</span></span>
## <a name="details"></a><span data-ttu-id="2a555-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2a555-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a555-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2a555-104">Product Name</span></span>|<span data-ttu-id="2a555-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="2a555-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2a555-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2a555-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2a555-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2a555-107">Event ID</span></span>|<span data-ttu-id="2a555-108">11036</span><span class="sxs-lookup"><span data-stu-id="2a555-108">11036</span></span>|  
|<span data-ttu-id="2a555-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2a555-109">Event Source</span></span>|<span data-ttu-id="2a555-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2a555-110">ENTSSO</span></span>|  
|<span data-ttu-id="2a555-111">Componente</span><span class="sxs-lookup"><span data-stu-id="2a555-111">Component</span></span>|<span data-ttu-id="2a555-112">N/D</span><span class="sxs-lookup"><span data-stu-id="2a555-112">N/A</span></span>|  
|<span data-ttu-id="2a555-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2a555-113">Symbolic Name</span></span>|<span data-ttu-id="2a555-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span><span class="sxs-lookup"><span data-stu-id="2a555-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span></span>|  
|<span data-ttu-id="2a555-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2a555-115">Message Text</span></span>|<span data-ttu-id="2a555-116">Cambio de contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="2a555-116">Windows password change.</span></span> <span data-ttu-id="2a555-117">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque el adaptador configurado para esta aplicación no admite sincronización de contraseñas para sistemas externos.%r</span><span class="sxs-lookup"><span data-stu-id="2a555-117">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.%r</span></span><br /><br /> <span data-ttu-id="2a555-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2a555-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="2a555-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2a555-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="2a555-120">Aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2a555-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="2a555-121">Adaptador: %4 %r</span><span class="sxs-lookup"><span data-stu-id="2a555-121">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="2a555-122">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="2a555-122">Client User: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a555-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="2a555-123">Explanation</span></span>  
 <span data-ttu-id="2a555-124">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque el adaptador configurado para esta aplicación no admite sincronización de contraseñas para sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="2a555-124">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a555-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2a555-125">User Action</span></span>  
 <span data-ttu-id="2a555-126">Compruebe la configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="2a555-126">Check your adapter configuration.</span></span>  
  
 <span data-ttu-id="2a555-127">Para obtener información sobre la sincronización de contraseñas, consulte [Password Synchronization](../core/password-synchronization2.md).</span><span class="sxs-lookup"><span data-stu-id="2a555-127">For information on Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>
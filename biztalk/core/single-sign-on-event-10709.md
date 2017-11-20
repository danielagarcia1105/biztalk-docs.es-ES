---
title: "Inicio de sesión único: Evento 10709 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a28807d9307ba1217e5b48e24facfe36711536f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10709"></a><span data-ttu-id="ed494-102">Inicio de sesión único: Evento 10709</span><span class="sxs-lookup"><span data-stu-id="ed494-102">Single Sign-On: Event 10709</span></span>
## <a name="details"></a><span data-ttu-id="ed494-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ed494-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed494-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ed494-104">Product Name</span></span>|<span data-ttu-id="ed494-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ed494-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ed494-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ed494-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ed494-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ed494-107">Event ID</span></span>|<span data-ttu-id="ed494-108">10709</span><span class="sxs-lookup"><span data-stu-id="ed494-108">10709</span></span>|  
|<span data-ttu-id="ed494-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ed494-109">Event Source</span></span>|<span data-ttu-id="ed494-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ed494-110">ENTSSO</span></span>|  
|<span data-ttu-id="ed494-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ed494-111">Component</span></span>|<span data-ttu-id="ed494-112">N\D</span><span class="sxs-lookup"><span data-stu-id="ed494-112">N\A</span></span>|  
|<span data-ttu-id="ed494-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ed494-113">Symbolic Name</span></span>|<span data-ttu-id="ed494-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="ed494-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="ed494-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ed494-115">Message Text</span></span>|<span data-ttu-id="ed494-116">Los cambios de contraseña de Windows desde PCNS sólo se aceptarán si provienen de controladores de dominio del dominio de acceso.%r</span><span class="sxs-lookup"><span data-stu-id="ed494-116">Windows password changes from PCNS will only be accepted from Domain Controllers in the access domain.%r</span></span><br /><br /> <span data-ttu-id="ed494-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ed494-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ed494-118">El usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ed494-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="ed494-119">Dominio de acceso: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ed494-119">Access Domain: %3%r</span></span><br /><br /> <span data-ttu-id="ed494-120">Sid de acceso: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ed494-120">Access Sid: %4%r</span></span><br /><br /> <span data-ttu-id="ed494-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="ed494-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ed494-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="ed494-122">Explanation</span></span>  
 <span data-ttu-id="ed494-123">Este evento de advertencia indica que se recibió un cambio de contraseña de Windows proveniente del servicio de notificación de cambio de contraseña (PCNS) en un servidor fuera del dominio del servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="ed494-123">This Warning event indicates that a Windows password change was received from Password Change Notification Services (PCNS) on a server outside the ENTSSO server's domain.</span></span> <span data-ttu-id="ed494-124">Los cambios de contraseña de Windows sólo se aceptarán si provienen de controladores de dominio en el mismo dominio como el servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="ed494-124">Windows password changes will only be accepted from domain controllers in the same domain as the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed494-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ed494-125">User Action</span></span>  
 <span data-ttu-id="ed494-126">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed494-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="ed494-127">Configure un servidor de ENTSSO en el mismo dominio que PCNS.</span><span class="sxs-lookup"><span data-stu-id="ed494-127">Configure an ENTSSO server in the same domain as PCNS.</span></span>  
  
 <span data-ttu-id="ed494-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed494-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="ed494-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="ed494-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
---
title: "Inicio de sesión único: Evento 10585 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b4781628121edad8904130e546038698de03161
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10585"></a><span data-ttu-id="2baea-102">Inicio de sesión único: Evento 10585</span><span class="sxs-lookup"><span data-stu-id="2baea-102">Single Sign-On: Event 10585</span></span>
## <a name="details"></a><span data-ttu-id="2baea-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2baea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2baea-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2baea-104">Product Name</span></span>|<span data-ttu-id="2baea-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="2baea-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2baea-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2baea-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2baea-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2baea-107">Event ID</span></span>|<span data-ttu-id="2baea-108">10585</span><span class="sxs-lookup"><span data-stu-id="2baea-108">10585</span></span>|  
|<span data-ttu-id="2baea-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2baea-109">Event Source</span></span>|<span data-ttu-id="2baea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2baea-110">ENTSSO</span></span>|  
|<span data-ttu-id="2baea-111">Componente</span><span class="sxs-lookup"><span data-stu-id="2baea-111">Component</span></span>|<span data-ttu-id="2baea-112">N/D</span><span class="sxs-lookup"><span data-stu-id="2baea-112">N/A</span></span>|  
|<span data-ttu-id="2baea-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2baea-113">Symbolic Name</span></span>|<span data-ttu-id="2baea-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span><span class="sxs-lookup"><span data-stu-id="2baea-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span></span>|  
|<span data-ttu-id="2baea-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2baea-115">Message Text</span></span>|<span data-ttu-id="2baea-116">Se está canjeando un vale después de que caducó el período de tiempo de espera de vale.</span><span class="sxs-lookup"><span data-stu-id="2baea-116">A ticket is being redeemed after the ticket time-out period has expired.</span></span> <span data-ttu-id="2baea-117">Esto se permite porque el período de tiempo de espera de vale está deshabilitado para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="2baea-117">This is allowed because the ticket time-out is disabled for this application.%r</span></span><br /><br /> <span data-ttu-id="2baea-118">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="2baea-118">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2baea-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="2baea-119">Explanation</span></span>  
 <span data-ttu-id="2baea-120">El tiempo de espera de vale se puede habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="2baea-120">Ticket time-out can be enabled or disabled.</span></span> <span data-ttu-id="2baea-121">En este caso, se canjea un vale aunque su período de tiempo de espera ha caducado porque el tiempo de espera está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2baea-121">In this case a ticket is being redeemed even though its time-out period has expired, because the time-out is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2baea-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2baea-122">User Action</span></span>  
 <span data-ttu-id="2baea-123">Si el tiempo de espera debía estar deshabilitado, no es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="2baea-123">If the time-out was supposed to be disabled, no user action is required.</span></span> <span data-ttu-id="2baea-124">No obstante, si no tenía conocimiento de que el tiempo de espera de esta aplicación específica estaba deshabilitado, compruebe la aplicación de inmediato para asegurarse de que desea permitirlo.</span><span class="sxs-lookup"><span data-stu-id="2baea-124">However, if you were not aware that this particular application had its time-out disabled, check the application immediately to be sure you want to allow it.</span></span>
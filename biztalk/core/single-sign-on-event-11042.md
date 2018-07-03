---
title: 'De sesión único: Evento 11042 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109678e68c3624cec11c4c9f235063288f342f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985693"
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="7c100-102">De sesión único: Evento 11042</span><span class="sxs-lookup"><span data-stu-id="7c100-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="7c100-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7c100-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c100-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7c100-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="7c100-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7c100-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="7c100-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7c100-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="7c100-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7c100-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="7c100-108">11042</span><span class="sxs-lookup"><span data-stu-id="7c100-108">11042</span></span>                                                                                                                                                             |
|  <span data-ttu-id="7c100-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7c100-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="7c100-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7c100-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="7c100-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7c100-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="7c100-112">N/D</span><span class="sxs-lookup"><span data-stu-id="7c100-112">N/A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="7c100-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7c100-113">Symbolic Name</span></span>  |                                                                                                                                                <span data-ttu-id="7c100-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="7c100-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>                                                                                                                                                |
|  <span data-ttu-id="7c100-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7c100-115">Message Text</span></span>   | <span data-ttu-id="7c100-116">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="7c100-116">Access denied.</span></span><br /><br /> <span data-ttu-id="7c100-117">El usuario del cliente debe ser miembro de una de las siguientes cuentas para realizar esta función.%r</span><span class="sxs-lookup"><span data-stu-id="7c100-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="7c100-118">Administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7c100-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="7c100-119">Administradores afiliados de SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7c100-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="7c100-120">Administradores de aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7c100-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="7c100-121">Usuarios de aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="7c100-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="7c100-122">Datos adicionales: %5</span><span class="sxs-lookup"><span data-stu-id="7c100-122">Additional Data: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7c100-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="7c100-123">Explanation</span></span>  
 <span data-ttu-id="7c100-124">Para realizar esta función, el usuario del cliente debe ser miembro de una de las cuentas enumeradas en la advertencia.</span><span class="sxs-lookup"><span data-stu-id="7c100-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c100-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7c100-125">User Action</span></span>  
 <span data-ttu-id="7c100-126">Debe unirse a una de las cuentas para realizar esta función.</span><span class="sxs-lookup"><span data-stu-id="7c100-126">You must join one of the accounts to perform this function.</span></span>
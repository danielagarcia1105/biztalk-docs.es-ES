---
title: 'Inicio de sesión único: Evento 11016 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f84bfef5dcef8e28bb3616ce30f1addc77f240c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276532"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="8fd2f-102">Inicio de sesión único: Evento 11016</span><span class="sxs-lookup"><span data-stu-id="8fd2f-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="8fd2f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8fd2f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fd2f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8fd2f-104">Product Name</span></span>|<span data-ttu-id="8fd2f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8fd2f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8fd2f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8fd2f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8fd2f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8fd2f-107">Event ID</span></span>|<span data-ttu-id="8fd2f-108">11016</span><span class="sxs-lookup"><span data-stu-id="8fd2f-108">11016</span></span>|  
|<span data-ttu-id="8fd2f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8fd2f-109">Event Source</span></span>|<span data-ttu-id="8fd2f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8fd2f-110">ENTSSO</span></span>|  
|<span data-ttu-id="8fd2f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8fd2f-111">Component</span></span>|<span data-ttu-id="8fd2f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8fd2f-112">N/A</span></span>|  
|<span data-ttu-id="8fd2f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8fd2f-113">Symbolic Name</span></span>|<span data-ttu-id="8fd2f-114">INFORMACIÓN AMPLIADA DE ERRORES DE RPC%r</span><span class="sxs-lookup"><span data-stu-id="8fd2f-114">RPC EXTENDED ERROR INFORMATION%r</span></span>|  
|<span data-ttu-id="8fd2f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8fd2f-115">Message Text</span></span>|<span data-ttu-id="8fd2f-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="8fd2f-116">%1%r</span></span><br /><br /> <span data-ttu-id="8fd2f-117">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="8fd2f-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="8fd2f-118">Error en la función AuthzInitializeContextFromSid con ERROR_ACCESS_DENIED.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="8fd2f-119">Esto significa que la cuenta de servicio en la que se ejecuta el servidor de SSO no tiene permisos suficientes para comprobar la pertenencia a grupos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="8fd2f-120">Consulte la documentación para obtener información detallada sobre el procedimiento para solucionar este problema.%r</span><span class="sxs-lookup"><span data-stu-id="8fd2f-120">Please check your documentation for details on how to fix this problem.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8fd2f-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="8fd2f-121">Explanation</span></span>  
 <span data-ttu-id="8fd2f-122">La cuenta de servicio en la que se ejecuta el servidor de SSO no tiene permisos suficientes para comprobar la pertenencia a grupos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fd2f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8fd2f-123">User Action</span></span>  
 <span data-ttu-id="8fd2f-124">Vea [servidor de SSO](../core/sso-server.md) en la documentación de SSO.</span><span class="sxs-lookup"><span data-stu-id="8fd2f-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>
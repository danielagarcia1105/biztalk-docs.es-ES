---
title: "Inicio de sesión único: Evento 11009 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99308e7a9e709cff5c0e1e15963eeb4769c00f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="8543f-102">Inicio de sesión único: Evento 11009</span><span class="sxs-lookup"><span data-stu-id="8543f-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="8543f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8543f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8543f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8543f-104">Product Name</span></span>|<span data-ttu-id="8543f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8543f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8543f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8543f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8543f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8543f-107">Event ID</span></span>|<span data-ttu-id="8543f-108">11009</span><span class="sxs-lookup"><span data-stu-id="8543f-108">11009</span></span>|  
|<span data-ttu-id="8543f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8543f-109">Event Source</span></span>|<span data-ttu-id="8543f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8543f-110">ENTSSO</span></span>|  
|<span data-ttu-id="8543f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8543f-111">Component</span></span>|<span data-ttu-id="8543f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8543f-112">N/A</span></span>|  
|<span data-ttu-id="8543f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8543f-113">Symbolic Name</span></span>|<span data-ttu-id="8543f-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="8543f-114">SSO_WARN_NOT_SSO_ADMIN</span></span>|  
|<span data-ttu-id="8543f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8543f-115">Message Text</span></span>|<span data-ttu-id="8543f-116">El usuario del cliente no es miembro de la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="8543f-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="8543f-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8543f-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8543f-118">El usuario cliente: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="8543f-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="8543f-119">Los administradores SSO: %4</span><span class="sxs-lookup"><span data-stu-id="8543f-119">SSO Administrators: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8543f-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="8543f-120">Explanation</span></span>  
 <span data-ttu-id="8543f-121">El usuario del cliente no es miembro de la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="8543f-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="8543f-122">Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.</span><span class="sxs-lookup"><span data-stu-id="8543f-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8543f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8543f-123">User Action</span></span>  
 <span data-ttu-id="8543f-124">Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="8543f-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="8543f-125">Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8543f-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>
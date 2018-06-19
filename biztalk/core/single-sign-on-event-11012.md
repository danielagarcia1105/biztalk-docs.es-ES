---
title: 'Inicio de sesión único: Evento 11012 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 252bedc8-8dc3-4962-b078-465f9b064ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c559f7416e0f882b4487629033e5b059802d20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277884"
---
# <a name="single-sign-on-event-11012"></a><span data-ttu-id="a5153-102">Inicio de sesión único: Evento 11012</span><span class="sxs-lookup"><span data-stu-id="a5153-102">Single Sign-On: Event 11012</span></span>
## <a name="details"></a><span data-ttu-id="a5153-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a5153-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5153-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a5153-104">Product Name</span></span>|<span data-ttu-id="a5153-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a5153-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a5153-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a5153-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a5153-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a5153-107">Event ID</span></span>|<span data-ttu-id="a5153-108">11012</span><span class="sxs-lookup"><span data-stu-id="a5153-108">11012</span></span>|  
|<span data-ttu-id="a5153-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a5153-109">Event Source</span></span>|<span data-ttu-id="a5153-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a5153-110">ENTSSO</span></span>|  
|<span data-ttu-id="a5153-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a5153-111">Component</span></span>|<span data-ttu-id="a5153-112">N/D</span><span class="sxs-lookup"><span data-stu-id="a5153-112">N/A</span></span>|  
|<span data-ttu-id="a5153-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a5153-113">Symbolic Name</span></span>|<span data-ttu-id="a5153-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span><span class="sxs-lookup"><span data-stu-id="a5153-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span></span>|  
|<span data-ttu-id="a5153-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a5153-115">Message Text</span></span>|<span data-ttu-id="a5153-116">El usuario del cliente no es miembro de la cuenta de administradores de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="a5153-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="a5153-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a5153-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a5153-118">El usuario cliente: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="a5153-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="a5153-119">Nombre de la aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="a5153-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="a5153-120">Los administradores de aplicaciones: %5</span><span class="sxs-lookup"><span data-stu-id="a5153-120">Application Administrators: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5153-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="a5153-121">Explanation</span></span>  
 <span data-ttu-id="a5153-122">El usuario del cliente no es miembro de la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5153-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="a5153-123">Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.</span><span class="sxs-lookup"><span data-stu-id="a5153-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5153-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a5153-124">User Action</span></span>  
 <span data-ttu-id="a5153-125">Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5153-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="a5153-126">Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a5153-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>
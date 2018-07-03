---
title: 'De sesión único: Evento 11011 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ef430a-fb3b-4bf7-936f-a866262a6c3a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ba98bf7fb3f57fdf9ce082028f2fff9ea7f618
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972973"
---
# <a name="single-sign-on-event-11011"></a><span data-ttu-id="f54a0-102">De sesión único: Evento 11011</span><span class="sxs-lookup"><span data-stu-id="f54a0-102">Single Sign-On: Event 11011</span></span>
## <a name="details"></a><span data-ttu-id="f54a0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f54a0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f54a0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f54a0-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="f54a0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f54a0-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="f54a0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f54a0-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="f54a0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f54a0-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="f54a0-108">11011</span><span class="sxs-lookup"><span data-stu-id="f54a0-108">11011</span></span>                                                                                                          |
|  <span data-ttu-id="f54a0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f54a0-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="f54a0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f54a0-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="f54a0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f54a0-111">Component</span></span>    |                                                                                                          <span data-ttu-id="f54a0-112">N/D</span><span class="sxs-lookup"><span data-stu-id="f54a0-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="f54a0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f54a0-113">Symbolic Name</span></span>  |                                                                                                 <span data-ttu-id="f54a0-114">SSO_WARN_NOT_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="f54a0-114">SSO_WARN_NOT_APP_ADMIN</span></span>                                                                                                 |
|  <span data-ttu-id="f54a0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f54a0-115">Message Text</span></span>   | <span data-ttu-id="f54a0-116">El usuario del cliente no es miembro de la cuenta de administradores de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="f54a0-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="f54a0-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f54a0-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f54a0-118">Usuario del cliente: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="f54a0-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="f54a0-119">Nombre de la aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f54a0-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="f54a0-120">Los administradores de aplicaciones: %5</span><span class="sxs-lookup"><span data-stu-id="f54a0-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f54a0-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="f54a0-121">Explanation</span></span>  
 <span data-ttu-id="f54a0-122">El usuario del cliente no es miembro de la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54a0-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="f54a0-123">Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.</span><span class="sxs-lookup"><span data-stu-id="f54a0-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f54a0-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f54a0-124">User Action</span></span>  
 <span data-ttu-id="f54a0-125">Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54a0-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="f54a0-126">Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f54a0-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>
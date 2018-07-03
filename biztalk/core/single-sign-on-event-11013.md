---
title: 'De sesión único: Evento 11013 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 450836dc-ddeb-4423-9966-69ad173f2c87
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f251dcbe15fc53c45f0b253cd4437e9e123d54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000317"
---
# <a name="single-sign-on-event-11013"></a><span data-ttu-id="91354-102">De sesión único: Evento 11013</span><span class="sxs-lookup"><span data-stu-id="91354-102">Single Sign-On: Event 11013</span></span>
## <a name="details"></a><span data-ttu-id="91354-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="91354-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="91354-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="91354-104">Product Name</span></span>   |                                                                                      <span data-ttu-id="91354-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="91354-105">Enterprise Single Sign-On</span></span>                                                                                       |
| <span data-ttu-id="91354-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="91354-106">Product Version</span></span> |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    <span data-ttu-id="91354-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="91354-107">Event ID</span></span>     |                                                                                                <span data-ttu-id="91354-108">11013</span><span class="sxs-lookup"><span data-stu-id="91354-108">11013</span></span>                                                                                                 |
|  <span data-ttu-id="91354-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="91354-109">Event Source</span></span>   |                                                                                                <span data-ttu-id="91354-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="91354-110">ENTSSO</span></span>                                                                                                |
|    <span data-ttu-id="91354-111">Componente</span><span class="sxs-lookup"><span data-stu-id="91354-111">Component</span></span>    |                                                                                                 <span data-ttu-id="91354-112">N/D</span><span class="sxs-lookup"><span data-stu-id="91354-112">N/A</span></span>                                                                                                  |
|  <span data-ttu-id="91354-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="91354-113">Symbolic Name</span></span>  |                                                                                        <span data-ttu-id="91354-114">SSO_WARN_NOT_APP_USER</span><span class="sxs-lookup"><span data-stu-id="91354-114">SSO_WARN_NOT_APP_USER</span></span>                                                                                         |
|  <span data-ttu-id="91354-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="91354-115">Message Text</span></span>   | <span data-ttu-id="91354-116">El usuario del cliente no es miembro de la cuenta de usuarios de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="91354-116">Client user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="91354-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="91354-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="91354-118">Usuario del cliente: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="91354-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="91354-119">Nombre de la aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="91354-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="91354-120">Los usuarios de aplicación: %5</span><span class="sxs-lookup"><span data-stu-id="91354-120">Application Users: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="91354-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="91354-121">Explanation</span></span>  
 <span data-ttu-id="91354-122">El usuario del cliente no es miembro de la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="91354-122">The client user is not a member of the Application Users account.</span></span> <span data-ttu-id="91354-123">Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.</span><span class="sxs-lookup"><span data-stu-id="91354-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91354-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="91354-124">User Action</span></span>  
 <span data-ttu-id="91354-125">Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="91354-125">To remedy the situation, you must make the client user a member of the Application Users account.</span></span> <span data-ttu-id="91354-126">Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="91354-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>
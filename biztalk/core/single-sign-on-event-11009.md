---
title: 'De sesión único: Evento 11009 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dc58b9f4a0e3fbed894323e2d281b1e9884961
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972125"
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="0cc72-102">De sesión único: Evento 11009</span><span class="sxs-lookup"><span data-stu-id="0cc72-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="0cc72-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0cc72-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0cc72-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0cc72-104">Product Name</span></span>   |                                                                      <span data-ttu-id="0cc72-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0cc72-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="0cc72-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0cc72-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="0cc72-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0cc72-107">Event ID</span></span>     |                                                                                <span data-ttu-id="0cc72-108">11009</span><span class="sxs-lookup"><span data-stu-id="0cc72-108">11009</span></span>                                                                                |
|  <span data-ttu-id="0cc72-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0cc72-109">Event Source</span></span>   |                                                                               <span data-ttu-id="0cc72-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0cc72-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="0cc72-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0cc72-111">Component</span></span>    |                                                                                 <span data-ttu-id="0cc72-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0cc72-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="0cc72-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0cc72-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="0cc72-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="0cc72-114">SSO_WARN_NOT_SSO_ADMIN</span></span>                                                                        |
|  <span data-ttu-id="0cc72-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0cc72-115">Message Text</span></span>   | <span data-ttu-id="0cc72-116">El usuario del cliente no es miembro de la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="0cc72-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="0cc72-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0cc72-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0cc72-118">Usuario del cliente: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="0cc72-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="0cc72-119">Los administradores SSO: %4</span><span class="sxs-lookup"><span data-stu-id="0cc72-119">SSO Administrators: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0cc72-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="0cc72-120">Explanation</span></span>  
 <span data-ttu-id="0cc72-121">El usuario del cliente no es miembro de la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="0cc72-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="0cc72-122">Esta advertencia sólo se muestra cuando los niveles de auditoría se establecen en Alto.</span><span class="sxs-lookup"><span data-stu-id="0cc72-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0cc72-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0cc72-123">User Action</span></span>  
 <span data-ttu-id="0cc72-124">Para solucionar el problema, debe incluir al usuario del cliente como miembro de la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="0cc72-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="0cc72-125">Para que esta advertencia no vuelva a aparecer en el futuro, puede reducir los niveles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0cc72-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>
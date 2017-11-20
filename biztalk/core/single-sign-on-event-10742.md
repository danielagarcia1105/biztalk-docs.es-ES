---
title: "Inicio de sesión único: Evento 10742 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb3acb03e60d1d7a7e705ac8b36aa5157616f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10742"></a><span data-ttu-id="2601f-102">Inicio de sesión único: Evento 10742</span><span class="sxs-lookup"><span data-stu-id="2601f-102">Single Sign-On: Event 10742</span></span>
## <a name="details"></a><span data-ttu-id="2601f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2601f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2601f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2601f-104">Product Name</span></span>|<span data-ttu-id="2601f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="2601f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2601f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2601f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2601f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2601f-107">Event ID</span></span>|<span data-ttu-id="2601f-108">10742</span><span class="sxs-lookup"><span data-stu-id="2601f-108">10742</span></span>|  
|<span data-ttu-id="2601f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2601f-109">Event Source</span></span>|<span data-ttu-id="2601f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2601f-110">ENTSSO</span></span>|  
|<span data-ttu-id="2601f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="2601f-111">Component</span></span>|<span data-ttu-id="2601f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="2601f-112">N\A</span></span>|  
|<span data-ttu-id="2601f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2601f-113">Symbolic Name</span></span>|<span data-ttu-id="2601f-114">SSO_WARN_NO_UPDATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="2601f-114">SSO_WARN_NO_UPDATE_ADAPTER</span></span>|  
|<span data-ttu-id="2601f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2601f-115">Message Text</span></span>|<span data-ttu-id="2601f-116">Para actualizar el adaptador, el usuario del cliente debe ser miembro de la cuenta de administradores de SSO o de la cuenta de administradores de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="2601f-116">The client user must be a member of the SSO Administrators account or the Application Administrators account to update the adapter.%r</span></span><br /><br /> <span data-ttu-id="2601f-117">El usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2601f-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="2601f-118">Administradores de SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2601f-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="2601f-119">Administradores de aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2601f-119">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="2601f-120">Adaptador: %4 %r</span><span class="sxs-lookup"><span data-stu-id="2601f-120">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="2601f-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="2601f-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2601f-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="2601f-122">Explanation</span></span>  
 <span data-ttu-id="2601f-123">Este evento de advertencia indica que se intentó actualizar el adaptador especificado, pero que no pudo completarse la actualización porque la cuenta de usuario que se usó no es miembro de la cuenta de administradores de SSO o de la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2601f-123">This Warning event indicates that an attempt to update the specified adapter was made, but could not be completed because the user account used is not a member of the SSO Administrators account or the Application Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2601f-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2601f-124">User Action</span></span>  
 <span data-ttu-id="2601f-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2601f-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="2601f-126">Agregue la cuenta de usuario a la cuenta de administradores de SSO o a la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2601f-126">Add user account to the SSO Administrators account or the Application Administrators account.</span></span>  
  
-   <span data-ttu-id="2601f-127">Vuelva a intentar la actualización.</span><span class="sxs-lookup"><span data-stu-id="2601f-127">Retry update.</span></span>  
  
 <span data-ttu-id="2601f-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2601f-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="2601f-129">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="2601f-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
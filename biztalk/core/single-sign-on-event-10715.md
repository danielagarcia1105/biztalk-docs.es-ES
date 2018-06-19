---
title: 'Inicio de sesión único: Evento 10715 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24bf65f00d9ef915d585c91aa06900b96d4b44d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270852"
---
# <a name="single-sign-on-event-10715"></a><span data-ttu-id="42bf9-102">Inicio de sesión único: Evento 10715</span><span class="sxs-lookup"><span data-stu-id="42bf9-102">Single Sign-On: Event 10715</span></span>
## <a name="details"></a><span data-ttu-id="42bf9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="42bf9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42bf9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="42bf9-104">Product Name</span></span>|<span data-ttu-id="42bf9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="42bf9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="42bf9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="42bf9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="42bf9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="42bf9-107">Event ID</span></span>|<span data-ttu-id="42bf9-108">10715</span><span class="sxs-lookup"><span data-stu-id="42bf9-108">10715</span></span>|  
|<span data-ttu-id="42bf9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="42bf9-109">Event Source</span></span>|<span data-ttu-id="42bf9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="42bf9-110">ENTSSO</span></span>|  
|<span data-ttu-id="42bf9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="42bf9-111">Component</span></span>|<span data-ttu-id="42bf9-112">N\D</span><span class="sxs-lookup"><span data-stu-id="42bf9-112">N\A</span></span>|  
|<span data-ttu-id="42bf9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="42bf9-113">Symbolic Name</span></span>|<span data-ttu-id="42bf9-114">SSO_WARN_NO_CREATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="42bf9-114">SSO_WARN_NO_CREATE_ADAPTER</span></span>|  
|<span data-ttu-id="42bf9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="42bf9-115">Message Text</span></span>|<span data-ttu-id="42bf9-116">Para crear adaptadores, el usuario del cliente debe ser miembro de la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="42bf9-116">The client user must be a member of the SSO Administrators account to create adapters.%r</span></span><br /><br /> <span data-ttu-id="42bf9-117">El usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="42bf9-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="42bf9-118">Administradores de SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="42bf9-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="42bf9-119">Adaptador: %3 %r</span><span class="sxs-lookup"><span data-stu-id="42bf9-119">Adapter: %3%r</span></span><br /><br /> <span data-ttu-id="42bf9-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="42bf9-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42bf9-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="42bf9-121">Explanation</span></span>  
 <span data-ttu-id="42bf9-122">Este evento de advertencia indica que el usuario del cliente debe ser miembro de la cuenta de administradores de SSO para crear cuentas.</span><span class="sxs-lookup"><span data-stu-id="42bf9-122">This Warning event indicates that the client user must be a member of the SSO Administrators account to create adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42bf9-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="42bf9-123">User Action</span></span>  
 <span data-ttu-id="42bf9-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42bf9-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="42bf9-125">Inicie sesión con una cuenta que pertenezca al grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="42bf9-125">Logon with an account that belongs to the SSO Administrators group.</span></span>  
  
 <span data-ttu-id="42bf9-126">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="42bf9-126">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="42bf9-127">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="42bf9-127">SSO User Groups</span></span>](../core/sso-user-groups.md)
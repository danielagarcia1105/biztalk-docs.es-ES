---
title: 'Inicio de sesión único: Evento 10517 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2716eb7d331ec5c15070555a028c00310188856c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271244"
---
# <a name="single-sign-on-event-10517"></a><span data-ttu-id="4cdd8-102">Inicio de sesión único: Evento 10517</span><span class="sxs-lookup"><span data-stu-id="4cdd8-102">Single Sign-On: Event 10517</span></span>
## <a name="details"></a><span data-ttu-id="4cdd8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4cdd8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cdd8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4cdd8-104">Product Name</span></span>|<span data-ttu-id="4cdd8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4cdd8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4cdd8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4cdd8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4cdd8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4cdd8-107">Event ID</span></span>|<span data-ttu-id="4cdd8-108">10517</span><span class="sxs-lookup"><span data-stu-id="4cdd8-108">10517</span></span>|  
|<span data-ttu-id="4cdd8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4cdd8-109">Event Source</span></span>|<span data-ttu-id="4cdd8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4cdd8-110">ENTSSO</span></span>|  
|<span data-ttu-id="4cdd8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4cdd8-111">Component</span></span>|<span data-ttu-id="4cdd8-112">N\D</span><span class="sxs-lookup"><span data-stu-id="4cdd8-112">N\A</span></span>|  
|<span data-ttu-id="4cdd8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4cdd8-113">Symbolic Name</span></span>|<span data-ttu-id="4cdd8-114">SSO_ERROR_BAD_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="4cdd8-114">SSO_ERROR_BAD_SSO_ADMIN</span></span>|  
|<span data-ttu-id="4cdd8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4cdd8-115">Message Text</span></span>|<span data-ttu-id="4cdd8-116">Cuenta de administradores de SSO no válida.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-116">The SSO Administrators account is not valid.</span></span> <span data-ttu-id="4cdd8-117">Si se trata de una cuenta local, compruebe si existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="4cdd8-118">Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="4cdd8-119">Cuando la cuenta sea válida, habilite SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4cdd8-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="4cdd8-120">Administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4cdd8-120">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="4cdd8-121">Cuentas no válidas: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4cdd8-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="4cdd8-122">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="4cdd8-122">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4cdd8-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="4cdd8-123">Explanation</span></span>  
 <span data-ttu-id="4cdd8-124">Este evento de error indica que la cuenta de administradores de SSO especificada para el inicio de sesión único empresarial no es una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-124">This Error event indicates that the SSO Administrators account specified for Enterprise Single Sign-On is not a valid Windows account.</span></span> <span data-ttu-id="4cdd8-125">La cuenta de servicio que ejecute el inicio de sesión único (SSO) empresarial deberá ser miembro de esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-125">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="4cdd8-126">La cuenta de administradores de SSO puede ser una cuenta de grupo de Windows o una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-126">The SSO Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="4cdd8-127">La cuenta de administradores de SSO también puede ser una cuenta de grupo local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-127">The SSO Administrators account can also be either a domain or local group account.</span></span> <span data-ttu-id="4cdd8-128">Si se utiliza una cuenta individual, no se podrá cambiar esta cuenta por otra cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-128">When using an individual account, you cannot change this account to another individual account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4cdd8-129">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4cdd8-129">User Action</span></span>  
 <span data-ttu-id="4cdd8-130">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4cdd8-130">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="4cdd8-131">Compruebe si existe la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="4cdd8-131">Verify the SSO Administrators account exists.</span></span>  
  
 <span data-ttu-id="4cdd8-132">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4cdd8-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4cdd8-133">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="4cdd8-133">SSO User Groups</span></span>](../core/sso-user-groups.md)
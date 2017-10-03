---
title: "Inicio de sesión único: Evento 10516 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b74ca4a47bc62d28b25564bd5843729c56362
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10516"></a><span data-ttu-id="26087-102">Inicio de sesión único: Evento 10516</span><span class="sxs-lookup"><span data-stu-id="26087-102">Single Sign-On: Event 10516</span></span>
## <a name="details"></a><span data-ttu-id="26087-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="26087-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26087-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="26087-104">Product Name</span></span>|<span data-ttu-id="26087-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="26087-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="26087-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="26087-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="26087-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="26087-107">Event ID</span></span>|<span data-ttu-id="26087-108">10516</span><span class="sxs-lookup"><span data-stu-id="26087-108">10516</span></span>|  
|<span data-ttu-id="26087-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="26087-109">Event Source</span></span>|<span data-ttu-id="26087-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="26087-110">ENTSSO</span></span>|  
|<span data-ttu-id="26087-111">Componente</span><span class="sxs-lookup"><span data-stu-id="26087-111">Component</span></span>|<span data-ttu-id="26087-112">N\D</span><span class="sxs-lookup"><span data-stu-id="26087-112">N\A</span></span>|  
|<span data-ttu-id="26087-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="26087-113">Symbolic Name</span></span>|<span data-ttu-id="26087-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="26087-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span></span>|  
|<span data-ttu-id="26087-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="26087-115">Message Text</span></span>|<span data-ttu-id="26087-116">Cuenta de administradores afiliados de SSO no válida.</span><span class="sxs-lookup"><span data-stu-id="26087-116">The SSO Affiliate Administrators account is not valid.</span></span> <span data-ttu-id="26087-117">Si se trata de una cuenta local, compruebe si existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="26087-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="26087-118">Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="26087-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="26087-119">Cuando la cuenta sea válida, habilite SSO.%r</span><span class="sxs-lookup"><span data-stu-id="26087-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="26087-120">Administradores afiliados de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="26087-120">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="26087-121">Cuentas no válidas: %2 %r</span><span class="sxs-lookup"><span data-stu-id="26087-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="26087-122">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="26087-122">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26087-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="26087-123">Explanation</span></span>  
 <span data-ttu-id="26087-124">Este evento de error indica que el grupo o la cuenta de administradores afiliados de SSO creada por el inicio de sesión único empresarial no es una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="26087-124">This Error event indicates that the SSO Affiliate Administrator account or group created by Enterprise Sing Sign-on is not a valid Windows account.</span></span> <span data-ttu-id="26087-125">La cuenta de administradores afiliados de SSO puede ser una cuenta de grupo de Windows o una cuenta individual.</span><span class="sxs-lookup"><span data-stu-id="26087-125">The SSO Affiliate Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="26087-126">La cuenta de administradores afiliados de SSO también puede ser una cuenta de grupo local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="26087-126">The SSO Affiliate Administrator account can also be either a domain or local group account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26087-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="26087-127">User Action</span></span>  
 <span data-ttu-id="26087-128">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26087-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="26087-129">Compruebe si existe la cuenta de administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="26087-129">Verify the SSO Affiliate Administrator account exists.</span></span>  
  
 <span data-ttu-id="26087-130">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="26087-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="26087-131">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="26087-131">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="26087-132">Cómo actualizar la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="26087-132">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)
---
title: "Inicio de sesión único: Evento 10519 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e709957e-a690-4a44-a863-07b2a55dae7b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928892ff1d0ee461a26095ddc7a72fd3accecf10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10519"></a><span data-ttu-id="fe701-102">Inicio de sesión único: Evento 10519</span><span class="sxs-lookup"><span data-stu-id="fe701-102">Single Sign-On: Event 10519</span></span>
## <a name="details"></a><span data-ttu-id="fe701-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fe701-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe701-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fe701-104">Product Name</span></span>|<span data-ttu-id="fe701-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fe701-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fe701-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fe701-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fe701-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fe701-107">Event ID</span></span>|<span data-ttu-id="fe701-108">10519</span><span class="sxs-lookup"><span data-stu-id="fe701-108">10519</span></span>|  
|<span data-ttu-id="fe701-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fe701-109">Event Source</span></span>|<span data-ttu-id="fe701-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fe701-110">ENTSSO</span></span>|  
|<span data-ttu-id="fe701-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fe701-111">Component</span></span>|<span data-ttu-id="fe701-112">N\D</span><span class="sxs-lookup"><span data-stu-id="fe701-112">N\A</span></span>|  
|<span data-ttu-id="fe701-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fe701-113">Symbolic Name</span></span>|<span data-ttu-id="fe701-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="fe701-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="fe701-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fe701-115">Message Text</span></span>|<span data-ttu-id="fe701-116">Cuenta de administradores de aplicación no válida para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe701-116">The Application Administrators account for this application is not valid.</span></span> <span data-ttu-id="fe701-117">Si se trata de una cuenta local, compruebe si existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fe701-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="fe701-118">Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="fe701-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="fe701-119">Habilite la aplicación cuando la cuenta sea válida.</span><span class="sxs-lookup"><span data-stu-id="fe701-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="fe701-120">Puede ignorar este mensaje si no usará esta aplicación en este equipo.%r</span><span class="sxs-lookup"><span data-stu-id="fe701-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="fe701-121">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fe701-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="fe701-122">Administradores de aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fe701-122">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="fe701-123">Cuentas no válidas: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fe701-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="fe701-124">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="fe701-124">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fe701-125">Explicación</span><span class="sxs-lookup"><span data-stu-id="fe701-125">Explanation</span></span>  
 <span data-ttu-id="fe701-126">Este evento de advertencia indica que una cuenta de grupo de administradores de aplicación no es una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="fe701-126">This Warning event indicates that an Application Administrators group account is not a valid Windows account.</span></span> <span data-ttu-id="fe701-127">Hay una cuenta de grupo de administradores de aplicación por cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="fe701-127">There is one Application Administraotrs account group for each affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fe701-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fe701-128">User Action</span></span>  
 <span data-ttu-id="fe701-129">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe701-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="fe701-130">Compruebe si existe la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe701-130">Verify the specified Application Administrators account exists.</span></span>  
  
-   <span data-ttu-id="fe701-131">Use la utilidad de administración de SSO para comprobar si la aplicación afiliada especificada está configurada para usar la cuenta de administradores de aplicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="fe701-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application administrators account.</span></span>  
  
 <span data-ttu-id="fe701-132">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fe701-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="fe701-133">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="fe701-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="fe701-134">Aplicaciones afiliadas de SSO</span><span class="sxs-lookup"><span data-stu-id="fe701-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="fe701-135">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="fe701-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
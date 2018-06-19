---
title: 'Inicio de sesión único: Evento 10518 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27b82d7f0a6bbaf02400679add53851867d728c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271316"
---
# <a name="single-sign-on-event-10518"></a><span data-ttu-id="1fe4f-102">Inicio de sesión único: Evento 10518</span><span class="sxs-lookup"><span data-stu-id="1fe4f-102">Single Sign-On: Event 10518</span></span>
## <a name="details"></a><span data-ttu-id="1fe4f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1fe4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fe4f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1fe4f-104">Product Name</span></span>|<span data-ttu-id="1fe4f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1fe4f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1fe4f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1fe4f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1fe4f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1fe4f-107">Event ID</span></span>|<span data-ttu-id="1fe4f-108">10518</span><span class="sxs-lookup"><span data-stu-id="1fe4f-108">10518</span></span>|  
|<span data-ttu-id="1fe4f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1fe4f-109">Event Source</span></span>|<span data-ttu-id="1fe4f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1fe4f-110">ENTSSO</span></span>|  
|<span data-ttu-id="1fe4f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1fe4f-111">Component</span></span>|<span data-ttu-id="1fe4f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="1fe4f-112">N\A</span></span>|  
|<span data-ttu-id="1fe4f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1fe4f-113">Symbolic Name</span></span>|<span data-ttu-id="1fe4f-114">SSO_WARN_BAD_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="1fe4f-114">SSO_WARN_BAD_USER_GROUP</span></span>|  
|<span data-ttu-id="1fe4f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1fe4f-115">Message Text</span></span>|<span data-ttu-id="1fe4f-116">Cuenta de usuarios de aplicación no válida para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-116">The Application Users account for this application is not valid.</span></span> <span data-ttu-id="1fe4f-117">Si se trata de una cuenta local, compruebe si existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="1fe4f-118">Si se trata de una cuenta de dominio, póngase en contacto con el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="1fe4f-119">Habilite la aplicación cuando la cuenta sea válida.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="1fe4f-120">Puede ignorar este mensaje si no usará esta aplicación en este equipo.%r</span><span class="sxs-lookup"><span data-stu-id="1fe4f-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="1fe4f-121">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1fe4f-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="1fe4f-122">Usuarios de aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1fe4f-122">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="1fe4f-123">Cuentas no válidas: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1fe4f-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="1fe4f-124">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="1fe4f-124">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1fe4f-125">Explicación</span><span class="sxs-lookup"><span data-stu-id="1fe4f-125">Explanation</span></span>  
 <span data-ttu-id="1fe4f-126">Este evento de advertencia indica que una cuenta de grupo de usuarios de aplicación no es una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-126">This Warning event indicates that an Application Users group account is not a valid Windows account.</span></span> <span data-ttu-id="1fe4f-127">Hay un grupo de cuentas de usuarios de la aplicación para cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-127">There is one Application Users account group for each affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1fe4f-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1fe4f-128">User Action</span></span>  
 <span data-ttu-id="1fe4f-129">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1fe4f-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="1fe4f-130">Compruebe si existe la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-130">Verify the specified Application Users account exists.</span></span>  
  
-   <span data-ttu-id="1fe4f-131">Use la utilidad de administración de SSO para comprobar si la aplicación afiliada especificada está configurada para usar la cuenta de usuarios de aplicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="1fe4f-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application users account.</span></span>  
  
 <span data-ttu-id="1fe4f-132">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1fe4f-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1fe4f-133">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="1fe4f-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="1fe4f-134">Aplicaciones afiliadas de SSO</span><span class="sxs-lookup"><span data-stu-id="1fe4f-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="1fe4f-135">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="1fe4f-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
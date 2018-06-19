---
title: 'Inicio de sesión único: Evento 10731 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10960489638aa565a11ecc32c70fc3a8fc6d477b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270692"
---
# <a name="single-sign-on-event-10731"></a><span data-ttu-id="70e27-102">Inicio de sesión único: Evento 10731</span><span class="sxs-lookup"><span data-stu-id="70e27-102">Single Sign-On: Event 10731</span></span>
## <a name="details"></a><span data-ttu-id="70e27-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="70e27-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70e27-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="70e27-104">Product Name</span></span>|<span data-ttu-id="70e27-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="70e27-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="70e27-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="70e27-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="70e27-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="70e27-107">Event ID</span></span>|<span data-ttu-id="70e27-108">10731</span><span class="sxs-lookup"><span data-stu-id="70e27-108">10731</span></span>|  
|<span data-ttu-id="70e27-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="70e27-109">Event Source</span></span>|<span data-ttu-id="70e27-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="70e27-110">ENTSSO</span></span>|  
|<span data-ttu-id="70e27-111">Componente</span><span class="sxs-lookup"><span data-stu-id="70e27-111">Component</span></span>|<span data-ttu-id="70e27-112">N\D</span><span class="sxs-lookup"><span data-stu-id="70e27-112">N\A</span></span>|  
|<span data-ttu-id="70e27-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="70e27-113">Symbolic Name</span></span>|<span data-ttu-id="70e27-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="70e27-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span></span>|  
|<span data-ttu-id="70e27-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="70e27-115">Message Text</span></span>|<span data-ttu-id="70e27-116">No se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="70e27-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="70e27-117">Nombre de dominio: %1 %r</span><span class="sxs-lookup"><span data-stu-id="70e27-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="70e27-118">Nombre de usuario: %2 %r</span><span class="sxs-lookup"><span data-stu-id="70e27-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="70e27-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="70e27-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="70e27-120">Usuarios de aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="70e27-120">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="70e27-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="70e27-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="70e27-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="70e27-122">Explanation</span></span>  
 <span data-ttu-id="70e27-123">Este evento de advertencia indica que no se pudo crear la asignación porque el usuario especificado no es miembro de la cuenta de usuarios de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="70e27-123">This Warning event indicates that a mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
 <span data-ttu-id="70e27-124">Existe una cuenta de grupo de usuarios de aplicación para cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="70e27-124">An application user's group account exists for each affiliate application.</span></span> <span data-ttu-id="70e27-125">Los miembros de esta cuenta pueden comprobar sus credenciales en la aplicación afiliada y, también, pueden administrar sus asignaciones de credenciales en ella.</span><span class="sxs-lookup"><span data-stu-id="70e27-125">Members of this account can verify their credentials in the affiliate application and can manage their credential mappings in the affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70e27-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="70e27-126">User Action</span></span>  
 <span data-ttu-id="70e27-127">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70e27-127">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="70e27-128">Agregue el usuario especificado al grupo de usuarios de aplicación para la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="70e27-128">Add the specified user to the application user's group for the specified affiliate application.</span></span>  
  
 <span data-ttu-id="70e27-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="70e27-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="70e27-130">Grupos de usuarios SSO</span><span class="sxs-lookup"><span data-stu-id="70e27-130">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="70e27-131">Aplicaciones afiliadas de SSO</span><span class="sxs-lookup"><span data-stu-id="70e27-131">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)
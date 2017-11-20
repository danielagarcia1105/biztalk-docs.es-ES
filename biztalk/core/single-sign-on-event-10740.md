---
title: "Inicio de sesión único: Evento 10740 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928760bebef1119207ee6a3021cd39c22ceacad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="12cbe-102">Inicio de sesión único: Evento 10740</span><span class="sxs-lookup"><span data-stu-id="12cbe-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="12cbe-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="12cbe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12cbe-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="12cbe-104">Product Name</span></span>|<span data-ttu-id="12cbe-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="12cbe-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="12cbe-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="12cbe-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="12cbe-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="12cbe-107">Event ID</span></span>|<span data-ttu-id="12cbe-108">10740</span><span class="sxs-lookup"><span data-stu-id="12cbe-108">10740</span></span>|  
|<span data-ttu-id="12cbe-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="12cbe-109">Event Source</span></span>|<span data-ttu-id="12cbe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="12cbe-110">ENTSSO</span></span>|  
|<span data-ttu-id="12cbe-111">Componente</span><span class="sxs-lookup"><span data-stu-id="12cbe-111">Component</span></span>|<span data-ttu-id="12cbe-112">N\D</span><span class="sxs-lookup"><span data-stu-id="12cbe-112">N\A</span></span>|  
|<span data-ttu-id="12cbe-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="12cbe-113">Symbolic Name</span></span>|<span data-ttu-id="12cbe-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="12cbe-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>|  
|<span data-ttu-id="12cbe-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="12cbe-115">Message Text</span></span>|<span data-ttu-id="12cbe-116">Cuenta de Windows no válida para actualización de la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="12cbe-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="12cbe-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="12cbe-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="12cbe-118">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="12cbe-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="12cbe-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="12cbe-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="12cbe-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="12cbe-120">Explanation</span></span>  
 <span data-ttu-id="12cbe-121">Este evento de advertencia indica que la cuenta de Windows (especificada en el mensaje de evento) no es válida para la actualización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12cbe-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="12cbe-122">Esto puede ocurrir cuando se cambia la cuenta de Windows de una aplicación de grupo host.</span><span class="sxs-lookup"><span data-stu-id="12cbe-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="12cbe-123">Las aplicaciones de grupo host se usan para inicio de sesión único desde sistemas externos en sistemas de Windows.</span><span class="sxs-lookup"><span data-stu-id="12cbe-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="12cbe-124">Estas aplicaciones pueden asignar un conjunto de usuarios externos a una única cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="12cbe-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="12cbe-125">La cuenta de Windows a la que se asignan se define en el campo de usuarios de aplicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12cbe-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12cbe-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="12cbe-126">User Action</span></span>  
 <span data-ttu-id="12cbe-127">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="12cbe-127">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="12cbe-128">Compruebe si la cuenta de Windows que se usa es válida.</span><span class="sxs-lookup"><span data-stu-id="12cbe-128">Check that the Windows account your are using is valid.</span></span>  
  
-   <span data-ttu-id="12cbe-129">Vuelva a crear la cuenta de Windows con las propiedades correctas de cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="12cbe-129">Recreate the Windows account with the correct Windows account properties.</span></span>  
  
 <span data-ttu-id="12cbe-130">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="12cbe-130">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="12cbe-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="12cbe-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
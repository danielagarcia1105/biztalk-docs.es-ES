---
title: "Inicio de sesión único: Evento 10669 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334180225d47cb9a86577cab75490ea0b6f2225a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="5380a-102">Inicio de sesión único: Evento 10669</span><span class="sxs-lookup"><span data-stu-id="5380a-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="5380a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5380a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5380a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5380a-104">Product Name</span></span>|<span data-ttu-id="5380a-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5380a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5380a-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5380a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5380a-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5380a-107">Event ID</span></span>|<span data-ttu-id="5380a-108">10669</span><span class="sxs-lookup"><span data-stu-id="5380a-108">10669</span></span>|  
|<span data-ttu-id="5380a-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5380a-109">Event Source</span></span>|<span data-ttu-id="5380a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5380a-110">ENTSSO</span></span>|  
|<span data-ttu-id="5380a-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5380a-111">Component</span></span>|<span data-ttu-id="5380a-112">N\D</span><span class="sxs-lookup"><span data-stu-id="5380a-112">N\A</span></span>|  
|<span data-ttu-id="5380a-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5380a-113">Symbolic Name</span></span>|<span data-ttu-id="5380a-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="5380a-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>|  
|<span data-ttu-id="5380a-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5380a-115">Message Text</span></span>|<span data-ttu-id="5380a-116">No se pudo cambiar la contraseña de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="5380a-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="5380a-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5380a-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="5380a-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5380a-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="5380a-119">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5380a-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="5380a-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="5380a-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5380a-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="5380a-121">Explanation</span></span>  
 <span data-ttu-id="5380a-122">Este evento de advertencia indica que SSO no pudo cambiar la contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="5380a-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="5380a-123">SSO llama a la función NetUserChangePassword de Win32 para que cambie la contraseña de Windows asociada con la asignación.</span><span class="sxs-lookup"><span data-stu-id="5380a-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="5380a-124">Si la función genera error, se emite este mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="5380a-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="5380a-125">El código de error será el que devuelva la función NetUserChangePassword.</span><span class="sxs-lookup"><span data-stu-id="5380a-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="5380a-126">Para obtener información detallada, consulte la documentación de esta función en MSDN.</span><span class="sxs-lookup"><span data-stu-id="5380a-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="5380a-127">Las causas más probables del error son que la contraseña anterior era incorrecta o que la contraseña nueva no respeta la directiva de contraseñas de Windows.</span><span class="sxs-lookup"><span data-stu-id="5380a-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5380a-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5380a-128">User Action</span></span>  
 <span data-ttu-id="5380a-129">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5380a-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="5380a-130">Compruebe la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="5380a-130">Verify the old password.</span></span> <span data-ttu-id="5380a-131">Si esta contraseña es incorrecta, se puede establecer manualmente en la base de datos de SSO a través de las herramientas de línea de comandos o MMC de administración.</span><span class="sxs-lookup"><span data-stu-id="5380a-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  
  
-   <span data-ttu-id="5380a-132">Compruebe si la contraseña nueva respeta la directiva de contraseñas de Windows requerida.</span><span class="sxs-lookup"><span data-stu-id="5380a-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="5380a-133">Si no es así, considere la posibilidad de usar filtros de contraseña.</span><span class="sxs-lookup"><span data-stu-id="5380a-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  
  
 <span data-ttu-id="5380a-134">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5380a-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="5380a-135">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="5380a-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
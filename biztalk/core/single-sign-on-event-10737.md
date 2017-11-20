---
title: "Inicio de sesión único: Evento 10737 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b89397206529cffb6048cc0f5578b3bac5cb1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10737"></a><span data-ttu-id="32012-102">Inicio de sesión único: Evento 10737</span><span class="sxs-lookup"><span data-stu-id="32012-102">Single Sign-On: Event 10737</span></span>
## <a name="details"></a><span data-ttu-id="32012-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="32012-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32012-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="32012-104">Product Name</span></span>|<span data-ttu-id="32012-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="32012-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="32012-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="32012-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="32012-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="32012-107">Event ID</span></span>|<span data-ttu-id="32012-108">10737</span><span class="sxs-lookup"><span data-stu-id="32012-108">10737</span></span>|  
|<span data-ttu-id="32012-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="32012-109">Event Source</span></span>|<span data-ttu-id="32012-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32012-110">ENTSSO</span></span>|  
|<span data-ttu-id="32012-111">Componente</span><span class="sxs-lookup"><span data-stu-id="32012-111">Component</span></span>|<span data-ttu-id="32012-112">N\D</span><span class="sxs-lookup"><span data-stu-id="32012-112">N\A</span></span>|  
|<span data-ttu-id="32012-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="32012-113">Symbolic Name</span></span>|<span data-ttu-id="32012-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="32012-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span></span>|  
|<span data-ttu-id="32012-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="32012-115">Message Text</span></span>|<span data-ttu-id="32012-116">No se pudo actualizar la contraseña externa en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="32012-116">Failed to update the external password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="32012-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="32012-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="32012-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="32012-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="32012-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="32012-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="32012-120">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="32012-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="32012-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="32012-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="32012-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="32012-122">Explanation</span></span>  
 <span data-ttu-id="32012-123">Este evento de advertencia indica que SSO no pudo actualizar la contraseña externa en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="32012-123">This Warning event indicates that SSO failed to update the external password in the SSO database.</span></span> <span data-ttu-id="32012-124">El mensaje de advertencia indica que existen varias causas posibles para el error. En algunos casos, esta advertencia podría indicar un problema de configuración; en otros casos, es posible que se haya eliminado la asignación mientras el cambio de contraseña estaba en curso.</span><span class="sxs-lookup"><span data-stu-id="32012-124">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32012-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="32012-125">User Action</span></span>  
 <span data-ttu-id="32012-126">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="32012-126">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="32012-127">Intente cambiar la contraseña nuevamente.</span><span class="sxs-lookup"><span data-stu-id="32012-127">Retry the password change.</span></span>  
  
-   <span data-ttu-id="32012-128">Si los intentos adicionales generan error, cambie la contraseña manualmente mediante las herramientas de línea de comandos o de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="32012-128">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  
  
 <span data-ttu-id="32012-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="32012-129">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="32012-130">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="32012-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
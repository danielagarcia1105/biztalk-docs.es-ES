---
title: 'Inicio de sesión único: Evento 10739 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a3dc964d830155a63a5ada8817e8b44aaa4c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271356"
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="3305f-102">Inicio de sesión único: Evento 10739</span><span class="sxs-lookup"><span data-stu-id="3305f-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="3305f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3305f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3305f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3305f-104">Product Name</span></span>|<span data-ttu-id="3305f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3305f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3305f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3305f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3305f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3305f-107">Event ID</span></span>|<span data-ttu-id="3305f-108">10739</span><span class="sxs-lookup"><span data-stu-id="3305f-108">10739</span></span>|  
|<span data-ttu-id="3305f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3305f-109">Event Source</span></span>|<span data-ttu-id="3305f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3305f-110">ENTSSO</span></span>|  
|<span data-ttu-id="3305f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3305f-111">Component</span></span>|<span data-ttu-id="3305f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="3305f-112">N\A</span></span>|  
|<span data-ttu-id="3305f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3305f-113">Symbolic Name</span></span>|<span data-ttu-id="3305f-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="3305f-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>|  
|<span data-ttu-id="3305f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3305f-115">Message Text</span></span>|<span data-ttu-id="3305f-116">No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="3305f-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="3305f-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3305f-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3305f-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3305f-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3305f-119">Cuenta de Windows: %3\\%4 %r</span><span class="sxs-lookup"><span data-stu-id="3305f-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="3305f-120">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="3305f-120">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3305f-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="3305f-121">Explanation</span></span>  
 <span data-ttu-id="3305f-122">Este evento de advertencia indica que SSO no pudo actualizar la contraseña de Windows en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="3305f-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="3305f-123">El mensaje de advertencia indica que existen varias causas posibles para el error. En algunos casos, esta advertencia podría indicar un problema de configuración; en otros casos, es posible que se haya eliminado la asignación mientras el cambio de contraseña estaba en curso.</span><span class="sxs-lookup"><span data-stu-id="3305f-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3305f-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3305f-124">User Action</span></span>  
 <span data-ttu-id="3305f-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3305f-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="3305f-126">Intente cambiar la contraseña nuevamente.</span><span class="sxs-lookup"><span data-stu-id="3305f-126">Retry the password change.</span></span>  
  
-   <span data-ttu-id="3305f-127">Si los intentos adicionales generan error, cambie la contraseña manualmente mediante las herramientas de línea de comandos o de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3305f-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  
  
 <span data-ttu-id="3305f-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3305f-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="3305f-129">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="3305f-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
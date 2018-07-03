---
title: 'De sesión único: Evento 10737 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd21b244e86c14aaf0f3af7418f1ca2ed8fbf067
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987685"
---
# <a name="single-sign-on-event-10737"></a><span data-ttu-id="637f2-102">De sesión único: Evento 10737</span><span class="sxs-lookup"><span data-stu-id="637f2-102">Single Sign-On: Event 10737</span></span>
## <a name="details"></a><span data-ttu-id="637f2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="637f2-103">Details</span></span>  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="637f2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="637f2-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="637f2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="637f2-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="637f2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="637f2-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="637f2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="637f2-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="637f2-108">10737</span><span class="sxs-lookup"><span data-stu-id="637f2-108">10737</span></span>                                                                                                          |
|  <span data-ttu-id="637f2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="637f2-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="637f2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="637f2-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="637f2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="637f2-111">Component</span></span>    |                                                                                                          <span data-ttu-id="637f2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="637f2-112">N\A</span></span>                                                                                                           |
|  <span data-ttu-id="637f2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="637f2-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="637f2-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="637f2-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span></span>                                                                                            |
|  <span data-ttu-id="637f2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="637f2-115">Message Text</span></span>   | <span data-ttu-id="637f2-116">No se pudo actualizar la contraseña externa en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="637f2-116">Failed to update the external password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="637f2-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="637f2-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="637f2-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="637f2-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="637f2-119">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="637f2-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="637f2-120">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="637f2-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="637f2-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="637f2-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="637f2-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="637f2-122">Explanation</span></span>  
 <span data-ttu-id="637f2-123">Este evento de advertencia indica que SSO no pudo actualizar la contraseña externa en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="637f2-123">This Warning event indicates that SSO failed to update the external password in the SSO database.</span></span> <span data-ttu-id="637f2-124">El mensaje de advertencia indica que existen varias causas posibles para el error. En algunos casos, esta advertencia podría indicar un problema de configuración; en otros casos, es posible que se haya eliminado la asignación mientras el cambio de contraseña estaba en curso.</span><span class="sxs-lookup"><span data-stu-id="637f2-124">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="637f2-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="637f2-125">User Action</span></span>  
 <span data-ttu-id="637f2-126">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="637f2-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="637f2-127">Intente cambiar la contraseña nuevamente.</span><span class="sxs-lookup"><span data-stu-id="637f2-127">Retry the password change.</span></span>  

- <span data-ttu-id="637f2-128">Si los intentos adicionales generan error, cambie la contraseña manualmente mediante las herramientas de línea de comandos o de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="637f2-128">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="637f2-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="637f2-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="637f2-130">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="637f2-130">Password Synchronization</span></span>](../core/password-synchronization2.md)

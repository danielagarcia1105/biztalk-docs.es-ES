---
title: 'De sesión único: Evento 10739 | Microsoft Docs'
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
ms.openlocfilehash: a08c0b5194b3c6cb2a75966a33d7215fd0b7b499
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969453"
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="cedf1-102">De sesión único: Evento 10739</span><span class="sxs-lookup"><span data-stu-id="cedf1-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="cedf1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cedf1-103">Details</span></span>  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cedf1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cedf1-104">Product Name</span></span>   |                                                                               <span data-ttu-id="cedf1-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="cedf1-105">Enterprise Single Sign-On</span></span>                                                                               |
| <span data-ttu-id="cedf1-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cedf1-106">Product Version</span></span> |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    <span data-ttu-id="cedf1-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cedf1-107">Event ID</span></span>     |                                                                                         <span data-ttu-id="cedf1-108">10739</span><span class="sxs-lookup"><span data-stu-id="cedf1-108">10739</span></span>                                                                                         |
|  <span data-ttu-id="cedf1-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cedf1-109">Event Source</span></span>   |                                                                                        <span data-ttu-id="cedf1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cedf1-110">ENTSSO</span></span>                                                                                         |
|    <span data-ttu-id="cedf1-111">Componente</span><span class="sxs-lookup"><span data-stu-id="cedf1-111">Component</span></span>    |                                                                                          <span data-ttu-id="cedf1-112">N\D</span><span class="sxs-lookup"><span data-stu-id="cedf1-112">N\A</span></span>                                                                                          |
|  <span data-ttu-id="cedf1-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cedf1-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="cedf1-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="cedf1-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>                                                                        |
|  <span data-ttu-id="cedf1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cedf1-115">Message Text</span></span>   | <span data-ttu-id="cedf1-116">No se pudo actualizar la contraseña de Windows en la base de datos de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="cedf1-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="cedf1-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cedf1-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cedf1-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cedf1-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="cedf1-119">Cuenta de Windows: %3\\%4 %r</span><span class="sxs-lookup"><span data-stu-id="cedf1-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="cedf1-120">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="cedf1-120">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="cedf1-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="cedf1-121">Explanation</span></span>  
 <span data-ttu-id="cedf1-122">Este evento de advertencia indica que SSO no pudo actualizar la contraseña de Windows en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cedf1-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="cedf1-123">El mensaje de advertencia indica que existen varias causas posibles para el error. En algunos casos, esta advertencia podría indicar un problema de configuración; en otros casos, es posible que se haya eliminado la asignación mientras el cambio de contraseña estaba en curso.</span><span class="sxs-lookup"><span data-stu-id="cedf1-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cedf1-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cedf1-124">User Action</span></span>  
 <span data-ttu-id="cedf1-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cedf1-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="cedf1-126">Intente cambiar la contraseña nuevamente.</span><span class="sxs-lookup"><span data-stu-id="cedf1-126">Retry the password change.</span></span>  

- <span data-ttu-id="cedf1-127">Si los intentos adicionales generan error, cambie la contraseña manualmente mediante las herramientas de línea de comandos o de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="cedf1-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="cedf1-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cedf1-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="cedf1-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="cedf1-129">Password Synchronization</span></span>](../core/password-synchronization2.md)

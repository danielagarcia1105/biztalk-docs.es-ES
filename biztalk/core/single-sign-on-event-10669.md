---
title: 'De sesión único: Evento 10669 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3006b8c861ac56effa504480f2645f22f9deae8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019272"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="65d45-102">De sesión único: Evento 10669</span><span class="sxs-lookup"><span data-stu-id="65d45-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="65d45-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="65d45-103">Details</span></span>  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="65d45-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="65d45-104">Product Name</span></span>   |                                                                   <span data-ttu-id="65d45-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="65d45-105">Enterprise Single Sign-On</span></span>                                                                   |
| <span data-ttu-id="65d45-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="65d45-106">Product Version</span></span> |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="65d45-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="65d45-107">Event ID</span></span>     |                                                                             <span data-ttu-id="65d45-108">10669</span><span class="sxs-lookup"><span data-stu-id="65d45-108">10669</span></span>                                                                             |
|  <span data-ttu-id="65d45-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="65d45-109">Event Source</span></span>   |                                                                            <span data-ttu-id="65d45-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="65d45-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="65d45-111">Componente</span><span class="sxs-lookup"><span data-stu-id="65d45-111">Component</span></span>    |                                                                              <span data-ttu-id="65d45-112">N\D</span><span class="sxs-lookup"><span data-stu-id="65d45-112">N\A</span></span>                                                                              |
|  <span data-ttu-id="65d45-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="65d45-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="65d45-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="65d45-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>                                                            |
|  <span data-ttu-id="65d45-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="65d45-115">Message Text</span></span>   | <span data-ttu-id="65d45-116">No se pudo cambiar la contraseña de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="65d45-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="65d45-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="65d45-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="65d45-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="65d45-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="65d45-119">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="65d45-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="65d45-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="65d45-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="65d45-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="65d45-121">Explanation</span></span>  
 <span data-ttu-id="65d45-122">Este evento de advertencia indica que SSO no pudo cambiar la contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="65d45-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="65d45-123">SSO llama a la función NetUserChangePassword de Win32 para que cambie la contraseña de Windows asociada con la asignación.</span><span class="sxs-lookup"><span data-stu-id="65d45-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="65d45-124">Si la función genera error, se emite este mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="65d45-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="65d45-125">El código de error será el que devuelva la función NetUserChangePassword.</span><span class="sxs-lookup"><span data-stu-id="65d45-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="65d45-126">Para obtener información detallada, consulte la documentación de esta función en MSDN.</span><span class="sxs-lookup"><span data-stu-id="65d45-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="65d45-127">Las causas más probables del error son que la contraseña anterior era incorrecta o que la contraseña nueva no respeta la directiva de contraseñas de Windows.</span><span class="sxs-lookup"><span data-stu-id="65d45-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  

## <a name="user-action"></a><span data-ttu-id="65d45-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="65d45-128">User Action</span></span>  
 <span data-ttu-id="65d45-129">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="65d45-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="65d45-130">Compruebe la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="65d45-130">Verify the old password.</span></span> <span data-ttu-id="65d45-131">Si esta contraseña es incorrecta, se puede establecer manualmente en la base de datos de SSO a través de las herramientas de línea de comandos o MMC de administración.</span><span class="sxs-lookup"><span data-stu-id="65d45-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  

- <span data-ttu-id="65d45-132">Compruebe si la contraseña nueva respeta la directiva de contraseñas de Windows requerida.</span><span class="sxs-lookup"><span data-stu-id="65d45-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="65d45-133">Si no es así, considere la posibilidad de usar filtros de contraseña.</span><span class="sxs-lookup"><span data-stu-id="65d45-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  

  <span data-ttu-id="65d45-134">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="65d45-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="65d45-135">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="65d45-135">Password Synchronization</span></span>](../core/password-synchronization2.md)

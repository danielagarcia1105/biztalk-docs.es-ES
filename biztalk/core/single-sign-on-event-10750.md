---
title: 'De sesión único: Evento 10750 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28526c6695cbf8f9c29e99621d6cb2f852fa7021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984373"
---
# <a name="single-sign-on-event-10750"></a><span data-ttu-id="7074e-102">De sesión único: Evento 10750</span><span class="sxs-lookup"><span data-stu-id="7074e-102">Single Sign-On: Event 10750</span></span>
## <a name="details"></a><span data-ttu-id="7074e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7074e-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7074e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7074e-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="7074e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7074e-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="7074e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7074e-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="7074e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7074e-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="7074e-108">10750</span><span class="sxs-lookup"><span data-stu-id="7074e-108">10750</span></span>                                                                                                                               |
|  <span data-ttu-id="7074e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7074e-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="7074e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7074e-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="7074e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7074e-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="7074e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="7074e-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="7074e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7074e-113">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="7074e-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span><span class="sxs-lookup"><span data-stu-id="7074e-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span></span>                                                                                                                 |
|  <span data-ttu-id="7074e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7074e-115">Message Text</span></span>   | <span data-ttu-id="7074e-116">PasswordChangeNotify: Tipo de nombre de usuario incorrecto.</span><span class="sxs-lookup"><span data-stu-id="7074e-116">PasswordChangeNotify: Incorrect User Name Type.</span></span> <span data-ttu-id="7074e-117">El único valor aceptado es USER_NAME_TYPE_NT4.</span><span class="sxs-lookup"><span data-stu-id="7074e-117">The only accepted value is USER_NAME_TYPE_NT4.</span></span><br /><br /> <span data-ttu-id="7074e-118">La configuración del destino es incorrecta en Active Directory.%r</span><span class="sxs-lookup"><span data-stu-id="7074e-118">The target is incorrectly configured in Active Directory.%r</span></span><br /><br /> <span data-ttu-id="7074e-119">Tipo de nombre de usuario: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7074e-119">User Name Type: %1%r</span></span><br /><br /> <span data-ttu-id="7074e-120">Usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7074e-120">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="7074e-121">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="7074e-121">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="7074e-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="7074e-122">Explanation</span></span>  
 <span data-ttu-id="7074e-123">Este evento de error indica que la sincronización de contraseñas recibió un cambio de contraseña proveniente del servicio de notificación de cambio de contraseña (PCNS), pero que dicha contraseña tenía un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="7074e-123">This Error event indicates that Password Sync received a password change from the Password Change Notification Service (PCNS), but the password change was in the wrong format.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7074e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7074e-124">User Action</span></span>  
 <span data-ttu-id="7074e-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7074e-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="7074e-126">Compruebe la configuración de PCNS.</span><span class="sxs-lookup"><span data-stu-id="7074e-126">Check the PCNS configuration.</span></span> <span data-ttu-id="7074e-127">PCNS sólo puede ejecutarse en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="7074e-127">PCNS can run only on a domain controller.</span></span>  

- <span data-ttu-id="7074e-128">Configure el tipo de nombre de usuario en USER_NAME_TYPE_NT4 en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7074e-128">Configure User Name Type to USER_NAME_TYPE_NT4 in Active Directory.</span></span>  

  <span data-ttu-id="7074e-129">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7074e-129">For more information, see the following resources:</span></span>  

- <span data-ttu-id="7074e-130">Para obtener más información sobre el procedimiento para especificar el tipo de nombre de usuario, consulte la documentación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7074e-130">Refer to Active Directory documentation for information on how to specify User Name Type.</span></span>  

- [<span data-ttu-id="7074e-131">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7074e-131">Password Synchronization</span></span>](../core/password-synchronization2.md)

---
title: 'De sesión único: Evento 10711 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9966cd2f588d34c3be60282bc7acfa54cd1f42b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982581"
---
# <a name="single-sign-on-event-10711"></a><span data-ttu-id="0617b-102">De sesión único: Evento 10711</span><span class="sxs-lookup"><span data-stu-id="0617b-102">Single Sign-On: Event 10711</span></span>
## <a name="details"></a><span data-ttu-id="0617b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0617b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0617b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0617b-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="0617b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0617b-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="0617b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0617b-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="0617b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0617b-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="0617b-108">10711</span><span class="sxs-lookup"><span data-stu-id="0617b-108">10711</span></span>                                                                                                                       |
|  <span data-ttu-id="0617b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0617b-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="0617b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0617b-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="0617b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0617b-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="0617b-112">N\D</span><span class="sxs-lookup"><span data-stu-id="0617b-112">N\A</span></span>                                                                                                                        |
|  <span data-ttu-id="0617b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0617b-113">Symbolic Name</span></span>  |                                                                                                         <span data-ttu-id="0617b-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="0617b-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="0617b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0617b-115">Message Text</span></span>   | <span data-ttu-id="0617b-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="0617b-116">External password change.</span></span> <span data-ttu-id="0617b-117">Algunos campos de credenciales externas faltantes de esta asignación se han establecido en los valores predeterminados.%r</span><span class="sxs-lookup"><span data-stu-id="0617b-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="0617b-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0617b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0617b-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0617b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="0617b-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0617b-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="0617b-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="0617b-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="0617b-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="0617b-122">Explanation</span></span>  
 <span data-ttu-id="0617b-123">Este evento de advertencia indica que se recibió un cambio de contraseña externa con credenciales faltantes.</span><span class="sxs-lookup"><span data-stu-id="0617b-123">This Warning event indicates that an external password change was received with missing credentials.</span></span> <span data-ttu-id="0617b-124">En esos campos se usaron los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0617b-124">Default values were used in those fields.</span></span>  

## <a name="user-action"></a><span data-ttu-id="0617b-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0617b-125">User Action</span></span>  
 <span data-ttu-id="0617b-126">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0617b-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="0617b-127">Si es necesario, establezca las credenciales para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="0617b-127">If necessary, set the credentials to match.</span></span>  

  <span data-ttu-id="0617b-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0617b-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="0617b-129">Aplicaciones afiliadas de SSO</span><span class="sxs-lookup"><span data-stu-id="0617b-129">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  

- [<span data-ttu-id="0617b-130">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0617b-130">Password Synchronization</span></span>](../core/password-synchronization2.md)

---
title: 'De sesión único: Evento 10677 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1fc5bfbb6df26f1b1125a0d5d8b06a75e441f15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022002"
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="2f757-102">De sesión único: Evento 10677</span><span class="sxs-lookup"><span data-stu-id="2f757-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="2f757-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f757-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2f757-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2f757-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="2f757-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="2f757-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="2f757-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2f757-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="2f757-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2f757-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="2f757-108">10677</span><span class="sxs-lookup"><span data-stu-id="2f757-108">10677</span></span>                                                                                                                               |
|  <span data-ttu-id="2f757-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2f757-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="2f757-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2f757-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="2f757-111">Componente</span><span class="sxs-lookup"><span data-stu-id="2f757-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="2f757-112">N\D</span><span class="sxs-lookup"><span data-stu-id="2f757-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="2f757-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2f757-113">Symbolic Name</span></span>  |                                                                                                                  <span data-ttu-id="2f757-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="2f757-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>                                                                                                                   |
|  <span data-ttu-id="2f757-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2f757-115">Message Text</span></span>   | <span data-ttu-id="2f757-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="2f757-116">External password change.</span></span> <span data-ttu-id="2f757-117">No se puede comprobar la contraseña anterior porque no existen credenciales para la cuenta externa.%r</span><span class="sxs-lookup"><span data-stu-id="2f757-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="2f757-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2f757-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="2f757-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2f757-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="2f757-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2f757-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="2f757-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="2f757-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="2f757-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="2f757-122">Explanation</span></span>  
 <span data-ttu-id="2f757-123">Este evento de advertencia indica que no se puede realizar el cambio de contraseña externa porque la contraseña anterior no tiene credenciales existentes.</span><span class="sxs-lookup"><span data-stu-id="2f757-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2f757-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2f757-124">User Action</span></span>  
 <span data-ttu-id="2f757-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f757-125">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="2f757-126">Determine qué aplicaciones se asignaron a este adaptador (nombre en el mensaje de registro de eventos) y, a continuación, use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta externa.</span><span class="sxs-lookup"><span data-stu-id="2f757-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="2f757-127">Debe establecer la contraseña externa (para la cuenta especificada) en todas esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2f757-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="2f757-128">Más información</span><span class="sxs-lookup"><span data-stu-id="2f757-128">More info</span></span>

- [<span data-ttu-id="2f757-129">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2f757-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="2f757-130">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2f757-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

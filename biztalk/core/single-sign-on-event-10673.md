---
title: 'De sesión único: Evento 10673 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fb923d1e137a00eed4ba87e65df71b226287aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975141"
---
# <a name="single-sign-on-event-10673"></a><span data-ttu-id="1a2b7-102">De sesión único: Evento 10673</span><span class="sxs-lookup"><span data-stu-id="1a2b7-102">Single Sign-On: Event 10673</span></span>
## <a name="details"></a><span data-ttu-id="1a2b7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1a2b7-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1a2b7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1a2b7-104">Product Name</span></span>   |                                                                                                                                                                        <span data-ttu-id="1a2b7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="1a2b7-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                         |
| <span data-ttu-id="1a2b7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1a2b7-106">Product Version</span></span> |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    <span data-ttu-id="1a2b7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1a2b7-107">Event ID</span></span>     |                                                                                                                                                                                  <span data-ttu-id="1a2b7-108">10673</span><span class="sxs-lookup"><span data-stu-id="1a2b7-108">10673</span></span>                                                                                                                                                                                   |
|  <span data-ttu-id="1a2b7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1a2b7-109">Event Source</span></span>   |                                                                                                                                                                                  <span data-ttu-id="1a2b7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1a2b7-110">ENTSSO</span></span>                                                                                                                                                                                  |
|    <span data-ttu-id="1a2b7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="1a2b7-111">Component</span></span>    |                                                                                                                                                                                   <span data-ttu-id="1a2b7-112">N\D</span><span class="sxs-lookup"><span data-stu-id="1a2b7-112">N\A</span></span>                                                                                                                                                                                    |
|  <span data-ttu-id="1a2b7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1a2b7-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="1a2b7-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="1a2b7-114">SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                 |
|  <span data-ttu-id="1a2b7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1a2b7-115">Message Text</span></span>   | <span data-ttu-id="1a2b7-116">El cambio de contraseña externa provocará cambios en varias cuentas de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-116">An external password change will cause changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="1a2b7-117">Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="1a2b7-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="1a2b7-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="1a2b7-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="1a2b7-121">Cuenta de Windows 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="1a2b7-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="1a2b7-122">Cuenta de Windows 2: %5</span><span class="sxs-lookup"><span data-stu-id="1a2b7-122">Windows Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="1a2b7-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="1a2b7-123">Explanation</span></span>  
 <span data-ttu-id="1a2b7-124">Este evento de información indica que el cambio de contraseña externa provocará cambios en varias cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-124">This Information event indicates that an external password change will cause changes to more than one Windows account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1a2b7-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1a2b7-125">User Action</span></span>  

-   <span data-ttu-id="1a2b7-126">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="1a2b7-127">Más información</span><span class="sxs-lookup"><span data-stu-id="1a2b7-127">More info</span></span>

- [<span data-ttu-id="1a2b7-128">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="1a2b7-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="1a2b7-129">**Propiedades del adaptador de sincronización de contraseñas: opciones** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1a2b7-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="1a2b7-130">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1a2b7-130">Password Synchronization</span></span>](../core/password-synchronization2.md)

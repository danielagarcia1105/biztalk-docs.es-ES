---
title: 'Inicio de sesión único: Evento 10674 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d239353276657e85c7fbdcfa634c3c1268723724
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270932"
---
# <a name="single-sign-on-event-10674"></a><span data-ttu-id="7a424-102">Inicio de sesión único: Evento 10674</span><span class="sxs-lookup"><span data-stu-id="7a424-102">Single Sign-On: Event 10674</span></span>
## <a name="details"></a><span data-ttu-id="7a424-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a424-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a424-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7a424-104">Product Name</span></span>|<span data-ttu-id="7a424-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7a424-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="7a424-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7a424-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="7a424-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7a424-107">Event ID</span></span>|<span data-ttu-id="7a424-108">10674</span><span class="sxs-lookup"><span data-stu-id="7a424-108">10674</span></span>|  
|<span data-ttu-id="7a424-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7a424-109">Event Source</span></span>|<span data-ttu-id="7a424-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a424-110">ENTSSO</span></span>|  
|<span data-ttu-id="7a424-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7a424-111">Component</span></span>|<span data-ttu-id="7a424-112">N\D</span><span class="sxs-lookup"><span data-stu-id="7a424-112">N\A</span></span>|  
|<span data-ttu-id="7a424-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7a424-113">Symbolic Name</span></span>|<span data-ttu-id="7a424-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="7a424-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="7a424-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7a424-115">Message Text</span></span>|<span data-ttu-id="7a424-116">El cambio de contraseña externa habría provocado cambios en varias cuentas de Windows.%r</span><span class="sxs-lookup"><span data-stu-id="7a424-116">An external password change would have caused changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="7a424-117">El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="7a424-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="7a424-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7a424-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7a424-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7a424-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="7a424-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7a424-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="7a424-121">Cuenta de Windows 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="7a424-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="7a424-122">Cuenta de Windows 2: %5</span><span class="sxs-lookup"><span data-stu-id="7a424-122">Windows Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a424-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="7a424-123">Explanation</span></span>  
 <span data-ttu-id="7a424-124">Este evento de advertencia indica que el cambio de contraseña externa habría provocado cambios en varias cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a424-124">This Warning event indicates that an external password change would have caused changes to more than one Windows account.</span></span> <span data-ttu-id="7a424-125">El cambio se impidió porque la configuración del adaptador no lo permitiría.</span><span class="sxs-lookup"><span data-stu-id="7a424-125">This change was prevented because the adapter configuration would not allow it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a424-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7a424-126">User Action</span></span>  
 <span data-ttu-id="7a424-127">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a424-127">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="7a424-128">Si se espera conflictos de asignación y se permiten, use las herramientas de administración de SSO para configurar el **Permitir conflictos de asignación** propiedad para el adaptador de sincronización de contraseña.</span><span class="sxs-lookup"><span data-stu-id="7a424-128">If mapping conflicts are expected and allowed, use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="7a424-129">Más información</span><span class="sxs-lookup"><span data-stu-id="7a424-129">More info</span></span>
  
-   <span data-ttu-id="7a424-130">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7a424-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="7a424-131">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="7a424-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
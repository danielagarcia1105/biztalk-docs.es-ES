---
title: 'Inicio de sesión único: Evento 10679 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f612f3cf6540340124a3f11ed99fe736df65296b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271748"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="deaaf-102">Inicio de sesión único: Evento 10679</span><span class="sxs-lookup"><span data-stu-id="deaaf-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="deaaf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="deaaf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deaaf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="deaaf-104">Product Name</span></span>|<span data-ttu-id="deaaf-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="deaaf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="deaaf-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="deaaf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="deaaf-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="deaaf-107">Event ID</span></span>|<span data-ttu-id="deaaf-108">10679</span><span class="sxs-lookup"><span data-stu-id="deaaf-108">10679</span></span>|  
|<span data-ttu-id="deaaf-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="deaaf-109">Event Source</span></span>|<span data-ttu-id="deaaf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="deaaf-110">ENTSSO</span></span>|  
|<span data-ttu-id="deaaf-111">Componente</span><span class="sxs-lookup"><span data-stu-id="deaaf-111">Component</span></span>|<span data-ttu-id="deaaf-112">N\D</span><span class="sxs-lookup"><span data-stu-id="deaaf-112">N\A</span></span>|  
|<span data-ttu-id="deaaf-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="deaaf-113">Symbolic Name</span></span>|<span data-ttu-id="deaaf-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="deaaf-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>|  
|<span data-ttu-id="deaaf-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="deaaf-115">Message Text</span></span>|<span data-ttu-id="deaaf-116">Cambio de contraseña externa.</span><span class="sxs-lookup"><span data-stu-id="deaaf-116">External password change.</span></span> <span data-ttu-id="deaaf-117">No se pudo cambiar la contraseña de la cuenta externa porque la asignación está deshabilitada.%r</span><span class="sxs-lookup"><span data-stu-id="deaaf-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="deaaf-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="deaaf-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="deaaf-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="deaaf-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="deaaf-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="deaaf-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="deaaf-121">Cuenta externa: %4</span><span class="sxs-lookup"><span data-stu-id="deaaf-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="deaaf-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="deaaf-122">Explanation</span></span>  
 <span data-ttu-id="deaaf-123">Este evento de advertencia indica que no se cambió la contraseña de la cuenta externa porque la asignación está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="deaaf-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="deaaf-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="deaaf-124">User Action</span></span>  
 <span data-ttu-id="deaaf-125">Para solucionar la advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="deaaf-125">To resolve this warning do the following:</span></span>  
  
-   <span data-ttu-id="deaaf-126">Use las herramientas de administración de SSO para habilitar la asignación para este adaptador.</span><span class="sxs-lookup"><span data-stu-id="deaaf-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="deaaf-127">Más información</span><span class="sxs-lookup"><span data-stu-id="deaaf-127">More info</span></span>
  
-   [<span data-ttu-id="deaaf-128">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="deaaf-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="deaaf-129">**Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="deaaf-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
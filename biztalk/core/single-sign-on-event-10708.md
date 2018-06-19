---
title: 'Inicio de sesión único: Evento 10708 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d600c39b2e79e619e5adfbda2ffc152169ccd5d4
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271700"
---
# <a name="single-sign-on-event-10708"></a><span data-ttu-id="00ab8-102">Inicio de sesión único: Evento 10708</span><span class="sxs-lookup"><span data-stu-id="00ab8-102">Single Sign-On: Event 10708</span></span>
## <a name="details"></a><span data-ttu-id="00ab8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="00ab8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00ab8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="00ab8-104">Product Name</span></span>|<span data-ttu-id="00ab8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="00ab8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="00ab8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="00ab8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="00ab8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="00ab8-107">Event ID</span></span>|<span data-ttu-id="00ab8-108">10708</span><span class="sxs-lookup"><span data-stu-id="00ab8-108">10708</span></span>|  
|<span data-ttu-id="00ab8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="00ab8-109">Event Source</span></span>|<span data-ttu-id="00ab8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="00ab8-110">ENTSSO</span></span>|  
|<span data-ttu-id="00ab8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="00ab8-111">Component</span></span>|<span data-ttu-id="00ab8-112">N\D</span><span class="sxs-lookup"><span data-stu-id="00ab8-112">N\A</span></span>|  
|<span data-ttu-id="00ab8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="00ab8-113">Symbolic Name</span></span>|<span data-ttu-id="00ab8-114">SSO_WARN_PS_NO_WIN_SYNC</span><span class="sxs-lookup"><span data-stu-id="00ab8-114">SSO_WARN_PS_NO_WIN_SYNC</span></span>|  
|<span data-ttu-id="00ab8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="00ab8-115">Message Text</span></span>|<span data-ttu-id="00ab8-116">No se permite la sincronización de contraseñas desde Windows.</span><span class="sxs-lookup"><span data-stu-id="00ab8-116">Password sync from Windows is not allowed.</span></span> <span data-ttu-id="00ab8-117">Compruebe los marcadores globales.%r</span><span class="sxs-lookup"><span data-stu-id="00ab8-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="00ab8-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="00ab8-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="00ab8-119">Usuario cliente: %2</span><span class="sxs-lookup"><span data-stu-id="00ab8-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00ab8-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="00ab8-120">Explanation</span></span>  
 <span data-ttu-id="00ab8-121">Este evento de advertencia indica que Windows solicita la sincronización de contraseñas pero no se establecieron los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="00ab8-121">This Warning event indicates that password sync is requested by Windows and neither of the global flags is set.</span></span> <span data-ttu-id="00ab8-122">Existen dos marcadores, que permite el envío de contraseñas a sistemas externos: (sso_flag_full_sync_from_windows_to_external) y otra que permite la recepción de contraseñas de sistemas externos (sso_flag_partial_sync_from_external_to_db).</span><span class="sxs-lookup"><span data-stu-id="00ab8-122">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00ab8-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="00ab8-123">User Action</span></span>  
 <span data-ttu-id="00ab8-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00ab8-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="00ab8-125">Usar el SSO administrador complemento MMC, (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="00ab8-125">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="00ab8-126">Más información</span><span class="sxs-lookup"><span data-stu-id="00ab8-126">More info</span></span>
  
-   <span data-ttu-id="00ab8-127">**Marcas de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="00ab8-127">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="00ab8-128">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="00ab8-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
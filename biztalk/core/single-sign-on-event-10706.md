---
title: 'Inicio de sesión único: Evento 10706 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5703c81d87376349561f644da558b8594cd51b79
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271564"
---
# <a name="single-sign-on-event-10706"></a><span data-ttu-id="c2126-102">Inicio de sesión único: Evento 10706</span><span class="sxs-lookup"><span data-stu-id="c2126-102">Single Sign-On: Event 10706</span></span>
## <a name="details"></a><span data-ttu-id="c2126-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c2126-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2126-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c2126-104">Product Name</span></span>|<span data-ttu-id="c2126-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c2126-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c2126-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c2126-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c2126-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c2126-107">Event ID</span></span>|<span data-ttu-id="c2126-108">10706</span><span class="sxs-lookup"><span data-stu-id="c2126-108">10706</span></span>|  
|<span data-ttu-id="c2126-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c2126-109">Event Source</span></span>|<span data-ttu-id="c2126-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2126-110">ENTSSO</span></span>|  
|<span data-ttu-id="c2126-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c2126-111">Component</span></span>|<span data-ttu-id="c2126-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c2126-112">N\A</span></span>|  
|<span data-ttu-id="c2126-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c2126-113">Symbolic Name</span></span>|<span data-ttu-id="c2126-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span><span class="sxs-lookup"><span data-stu-id="c2126-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span></span>|  
|<span data-ttu-id="c2126-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2126-115">Message Text</span></span>|<span data-ttu-id="c2126-116">Los adaptadores de grupo requieren que los marcadores globales permitan la sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="c2126-116">Group adapters require password sync to be allowed by the global flags.</span></span> <span data-ttu-id="c2126-117">Compruebe los marcadores globales.%r</span><span class="sxs-lookup"><span data-stu-id="c2126-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="c2126-118">Adaptador: %1</span><span class="sxs-lookup"><span data-stu-id="c2126-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c2126-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="c2126-119">Explanation</span></span>  
 <span data-ttu-id="c2126-120">Este evento de advertencia indica que un adaptador de sincronización de contraseñas externas solicita la sincronización de contraseñas pero ninguno de los marcadores globales está establecido.</span><span class="sxs-lookup"><span data-stu-id="c2126-120">This Warning event indicates that password sync is requested by an external password sync adapter and neither of the global flags is set.</span></span> <span data-ttu-id="c2126-121">Existen dos marcadores, que permite el envío de contraseñas a sistemas externos: (sso_flag_full_sync_from_windows_to_external) y otra que permite la recepción de contraseñas de sistemas externos (sso_flag_partial_sync_from_external_to_db).</span><span class="sxs-lookup"><span data-stu-id="c2126-121">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2126-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c2126-122">User Action</span></span>  
 <span data-ttu-id="c2126-123">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2126-123">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="c2126-124">Usar el SSO administrador complemento MMC, (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="c2126-124">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="c2126-125">Más información</span><span class="sxs-lookup"><span data-stu-id="c2126-125">More info</span></span>
  
-   <span data-ttu-id="c2126-126">**Marcas de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c2126-126">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="c2126-127">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="c2126-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
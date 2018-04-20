---
title: 'Inicio de sesión único: Evento 10707 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10707"></a><span data-ttu-id="55b5e-102">Inicio de sesión único: Evento 10707</span><span class="sxs-lookup"><span data-stu-id="55b5e-102">Single Sign-On: Event 10707</span></span>
## <a name="details"></a><span data-ttu-id="55b5e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="55b5e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55b5e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="55b5e-104">Product Name</span></span>|<span data-ttu-id="55b5e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="55b5e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="55b5e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="55b5e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="55b5e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="55b5e-107">Event ID</span></span>|<span data-ttu-id="55b5e-108">10707</span><span class="sxs-lookup"><span data-stu-id="55b5e-108">10707</span></span>|  
|<span data-ttu-id="55b5e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="55b5e-109">Event Source</span></span>|<span data-ttu-id="55b5e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="55b5e-110">ENTSSO</span></span>|  
|<span data-ttu-id="55b5e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="55b5e-111">Component</span></span>|<span data-ttu-id="55b5e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="55b5e-112">N\A</span></span>|  
|<span data-ttu-id="55b5e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="55b5e-113">Symbolic Name</span></span>|<span data-ttu-id="55b5e-114">SSO_WARN_PS_NO_APP_SYNC</span><span class="sxs-lookup"><span data-stu-id="55b5e-114">SSO_WARN_PS_NO_APP_SYNC</span></span>|  
|<span data-ttu-id="55b5e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="55b5e-115">Message Text</span></span>|<span data-ttu-id="55b5e-116">Los marcadores de sincronización de contraseñas de este adaptador deben permitir la sincronización de contraseñas y deben coincidir con los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="55b5e-116">Password sync flags for this adapter must allow password sync and must match the global flags.</span></span> <span data-ttu-id="55b5e-117">Compruebe los marcadores de adaptador y los marcadores globales.%r</span><span class="sxs-lookup"><span data-stu-id="55b5e-117">Check the adapter flags and the global flags.%r</span></span><br /><br /> <span data-ttu-id="55b5e-118">Adaptador: %1</span><span class="sxs-lookup"><span data-stu-id="55b5e-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55b5e-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="55b5e-119">Explanation</span></span>  
 <span data-ttu-id="55b5e-120">Este evento de advertencia indica que los marcadores de sincronización de contraseñas de este adaptador deben permitir la sincronización de contraseñas y deben coincidir con los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="55b5e-120">This Warning event indicates that password sync flags for this adapter must allow password sync and must match the global flags.</span></span>  
  
 <span data-ttu-id="55b5e-121">La sincronización de contraseñas para un adaptador de sincronización de contraseñas se controla mediante dos marcadores, uno permite el envío de contraseñas a sistemas externos (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) y el otro permite la recepción de contraseñas de sistemas externos (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span><span class="sxs-lookup"><span data-stu-id="55b5e-121">Password sync for a password sync adapter is controlled by two flags, one allows sending of password to external systems (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) and another which allows receiving of passwords from external systems (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span></span> <span data-ttu-id="55b5e-122">Para lograr una sincronización de contraseñas correcta, estos marcadores deben establecerse tanto para los "marcadores globales" como para los marcadores del adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="55b5e-122">For successfull password sync these must be set for both the “global flags” and also for the specific adapter flags.</span></span> <span data-ttu-id="55b5e-123">Este evento de advertencia se emite cuando un adaptador de sincronización de contraseñas necesita sincronización de contraseñas pero ninguno de estos marcadores está establecido para los "marcadores globales" y los marcadores del adaptador.</span><span class="sxs-lookup"><span data-stu-id="55b5e-123">This warning event is issued when password sync is requested by an external password sync adapter and neither of these flags is set for both the “global flags” and the adapter flags.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55b5e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="55b5e-124">User Action</span></span>  
 <span data-ttu-id="55b5e-125">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55b5e-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="55b5e-126">Use el complemento MMC del Administrador de SSO (sistema &#124; propiedades &#124; opciones) o la herramienta de línea de comandos `ssomanage –enable winsync/extsync` para habilitar los marcadores globales.</span><span class="sxs-lookup"><span data-stu-id="55b5e-126">Use the SSO Admin MMC Snap-In (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="55b5e-127">Más información</span><span class="sxs-lookup"><span data-stu-id="55b5e-127">More info</span></span>
  
-   <span data-ttu-id="55b5e-128">**Marcas de inicio de sesión único de Enterprise** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="55b5e-128">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="55b5e-129">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="55b5e-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
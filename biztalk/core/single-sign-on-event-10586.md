---
title: 'Inicio de sesión único: Evento 10586 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 124ed0a722d0da0f21722f3b337c8bb938068b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270716"
---
# <a name="single-sign-on-event-10586"></a><span data-ttu-id="428cb-102">Inicio de sesión único: Evento 10586</span><span class="sxs-lookup"><span data-stu-id="428cb-102">Single Sign-On: Event 10586</span></span>
## <a name="details"></a><span data-ttu-id="428cb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="428cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="428cb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="428cb-104">Product Name</span></span>|<span data-ttu-id="428cb-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="428cb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="428cb-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="428cb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="428cb-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="428cb-107">Event ID</span></span>|<span data-ttu-id="428cb-108">10586</span><span class="sxs-lookup"><span data-stu-id="428cb-108">10586</span></span>|  
|<span data-ttu-id="428cb-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="428cb-109">Event Source</span></span>|<span data-ttu-id="428cb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="428cb-110">ENTSSO</span></span>|  
|<span data-ttu-id="428cb-111">Componente</span><span class="sxs-lookup"><span data-stu-id="428cb-111">Component</span></span>|<span data-ttu-id="428cb-112">N/D</span><span class="sxs-lookup"><span data-stu-id="428cb-112">N/A</span></span>|  
|<span data-ttu-id="428cb-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="428cb-113">Symbolic Name</span></span>|<span data-ttu-id="428cb-114">SSO_WARN_CRED_CACHE_OFF</span><span class="sxs-lookup"><span data-stu-id="428cb-114">SSO_WARN_CRED_CACHE_OFF</span></span>|  
|<span data-ttu-id="428cb-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="428cb-115">Message Text</span></span>|<span data-ttu-id="428cb-116">La memoria caché de credenciales se deshabilitó para este servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="428cb-116">The credential cache has been disabled for this SSO server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="428cb-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="428cb-117">Explanation</span></span>  
 <span data-ttu-id="428cb-118">Se deshabilitó la memoria caché de credenciales que, por lo general, está habilitada.</span><span class="sxs-lookup"><span data-stu-id="428cb-118">The credential cache, which is generally enabled, has been disabled.</span></span> <span data-ttu-id="428cb-119">Sólo el administrador del sistema puede habilitar o deshabilitar la memoria caché de credenciales.</span><span class="sxs-lookup"><span data-stu-id="428cb-119">Only a system administrator can enable or disable the credential cache.</span></span> <span data-ttu-id="428cb-120">En ciertos casos, si se deshabilita esta memoria, hay más credenciales actuales del sistema ENTSSO, aunque esto podría disminuir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="428cb-120">Disabling the credential cache will sometimes result in more current credentials from the ENTSSO system, although it could slow down peformance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="428cb-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="428cb-121">User Action</span></span>  
 <span data-ttu-id="428cb-122">Para volver a habilitar la caché de credenciales, vea la tabla de propiedades de aplicaciones afiliadas de [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="428cb-122">To re-enable the credential cache, see the Afflilate Application Properties table in [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>
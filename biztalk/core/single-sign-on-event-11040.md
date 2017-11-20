---
title: "Inicio de sesión único: Evento 11040 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9eafbbe1c0cbcb0db96c94d072ed511e69b2d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="75227-102">Inicio de sesión único: Evento 11040</span><span class="sxs-lookup"><span data-stu-id="75227-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="75227-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="75227-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75227-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="75227-104">Product Name</span></span>|<span data-ttu-id="75227-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="75227-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="75227-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="75227-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="75227-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="75227-107">Event ID</span></span>|<span data-ttu-id="75227-108">11040</span><span class="sxs-lookup"><span data-stu-id="75227-108">11040</span></span>|  
|<span data-ttu-id="75227-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="75227-109">Event Source</span></span>|<span data-ttu-id="75227-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="75227-110">ENTSSO</span></span>|  
|<span data-ttu-id="75227-111">Componente</span><span class="sxs-lookup"><span data-stu-id="75227-111">Component</span></span>|<span data-ttu-id="75227-112">N/D</span><span class="sxs-lookup"><span data-stu-id="75227-112">N/A</span></span>|  
|<span data-ttu-id="75227-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="75227-113">Symbolic Name</span></span>|<span data-ttu-id="75227-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="75227-114">SSO_WARN_NETWORK_SERVICE</span></span>|  
|<span data-ttu-id="75227-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="75227-115">Message Text</span></span>|<span data-ttu-id="75227-116">El servicio SSO se está ejecutando en una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="75227-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="75227-117">Existen algunas consideraciones especiales para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="75227-117">There are some special considerations for this account.</span></span> <span data-ttu-id="75227-118">Para obtener información detallada, consulte la documentación.%r</span><span class="sxs-lookup"><span data-stu-id="75227-118">See your documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75227-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="75227-119">Explanation</span></span>  
 <span data-ttu-id="75227-120">El servicio SSO se está ejecutando en una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="75227-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="75227-121">Existen algunas consideraciones especiales para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="75227-121">There are some special considerations for this account.</span></span> <span data-ttu-id="75227-122">Por ejemplo, se debe reiniciar el equipo después de agregar una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="75227-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="75227-123">Además, la ejecución en una cuenta de servicio de red restringe la ejecución a escenarios muy limitados.</span><span class="sxs-lookup"><span data-stu-id="75227-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75227-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="75227-124">User Action</span></span>  
 <span data-ttu-id="75227-125">Para obtener más información, consulte [recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="75227-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>
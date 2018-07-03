---
title: 'De sesión único: Evento 11040 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eefc6c65e07b430851606ce7779aad3771776a83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019074"
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="65240-102">De sesión único: Evento 11040</span><span class="sxs-lookup"><span data-stu-id="65240-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="65240-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="65240-103">Details</span></span>  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="65240-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="65240-104">Product Name</span></span>   |                                                                  <span data-ttu-id="65240-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="65240-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="65240-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="65240-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="65240-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="65240-107">Event ID</span></span>     |                                                                            <span data-ttu-id="65240-108">11040</span><span class="sxs-lookup"><span data-stu-id="65240-108">11040</span></span>                                                                            |
|  <span data-ttu-id="65240-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="65240-109">Event Source</span></span>   |                                                                           <span data-ttu-id="65240-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="65240-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="65240-111">Componente</span><span class="sxs-lookup"><span data-stu-id="65240-111">Component</span></span>    |                                                                             <span data-ttu-id="65240-112">N/D</span><span class="sxs-lookup"><span data-stu-id="65240-112">N/A</span></span>                                                                             |
|  <span data-ttu-id="65240-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="65240-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="65240-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="65240-114">SSO_WARN_NETWORK_SERVICE</span></span>                                                                   |
|  <span data-ttu-id="65240-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="65240-115">Message Text</span></span>   | <span data-ttu-id="65240-116">El servicio SSO se está ejecutando en una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="65240-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="65240-117">Existen algunas consideraciones especiales para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="65240-117">There are some special considerations for this account.</span></span> <span data-ttu-id="65240-118">Para obtener información detallada, consulte la documentación.%r</span><span class="sxs-lookup"><span data-stu-id="65240-118">See your documentation for details.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="65240-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="65240-119">Explanation</span></span>  
 <span data-ttu-id="65240-120">El servicio SSO se está ejecutando en una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="65240-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="65240-121">Existen algunas consideraciones especiales para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="65240-121">There are some special considerations for this account.</span></span> <span data-ttu-id="65240-122">Por ejemplo, se debe reiniciar el equipo después de agregar una cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="65240-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="65240-123">Además, la ejecución en una cuenta de servicio de red restringe la ejecución a escenarios muy limitados.</span><span class="sxs-lookup"><span data-stu-id="65240-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65240-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="65240-124">User Action</span></span>  
 <span data-ttu-id="65240-125">Para obtener más información, consulte [recomendaciones de seguridad de inicio de sesión único](../core/sso-security-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="65240-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>
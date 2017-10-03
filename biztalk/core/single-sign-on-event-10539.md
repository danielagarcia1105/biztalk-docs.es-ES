---
title: "Inicio de sesión único: Evento 10539 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ca34f40359b518e1a52b3326dae9917ca4910e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="28ec9-102">Inicio de sesión único: Evento 10539</span><span class="sxs-lookup"><span data-stu-id="28ec9-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="28ec9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="28ec9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28ec9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="28ec9-104">Product Name</span></span>|<span data-ttu-id="28ec9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="28ec9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="28ec9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="28ec9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="28ec9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="28ec9-107">Event ID</span></span>|<span data-ttu-id="28ec9-108">10539</span><span class="sxs-lookup"><span data-stu-id="28ec9-108">10539</span></span>|  
|<span data-ttu-id="28ec9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="28ec9-109">Event Source</span></span>|<span data-ttu-id="28ec9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="28ec9-110">ENTSSO</span></span>|  
|<span data-ttu-id="28ec9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="28ec9-111">Component</span></span>|<span data-ttu-id="28ec9-112">CO</span><span class="sxs-lookup"><span data-stu-id="28ec9-112">CO</span></span>|  
|<span data-ttu-id="28ec9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="28ec9-113">Symbolic Name</span></span>|<span data-ttu-id="28ec9-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="28ec9-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="28ec9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="28ec9-115">Message Text</span></span>|<span data-ttu-id="28ec9-116">No se habilitaron vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="28ec9-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28ec9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="28ec9-117">Explanation</span></span>  
 <span data-ttu-id="28ec9-118">Este evento de advertencia indica que no está habilitado el uso de vales de SSO.</span><span class="sxs-lookup"><span data-stu-id="28ec9-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="28ec9-119">La posibilidad de permitir el uso de vales de SSO es una característica opcional del sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="28ec9-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="28ec9-120">Esta característica no se habilitó en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="28ec9-120">This feature has not been enabled on your SSO system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28ec9-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="28ec9-121">User Action</span></span>  
 <span data-ttu-id="28ec9-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28ec9-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="28ec9-123">Póngase en contacto con el administrador de SSO para habilitar vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="28ec9-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="28ec9-124">Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="28ec9-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="28ec9-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="28ec9-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="28ec9-126">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="28ec9-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="28ec9-127">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="28ec9-127">Using SSO</span></span>](../core/using-sso.md)
---
title: "Inicio de sesión único: Evento 10545 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="ca841-102">Inicio de sesión único: Evento 10545</span><span class="sxs-lookup"><span data-stu-id="ca841-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="ca841-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ca841-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca841-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ca841-104">Product Name</span></span>|<span data-ttu-id="ca841-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ca841-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ca841-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ca841-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ca841-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ca841-107">Event ID</span></span>|<span data-ttu-id="ca841-108">10545</span><span class="sxs-lookup"><span data-stu-id="ca841-108">10545</span></span>|  
|<span data-ttu-id="ca841-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ca841-109">Event Source</span></span>|<span data-ttu-id="ca841-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ca841-110">ENTSSO</span></span>|  
|<span data-ttu-id="ca841-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ca841-111">Component</span></span>|<span data-ttu-id="ca841-112">CO</span><span class="sxs-lookup"><span data-stu-id="ca841-112">CO</span></span>|  
|<span data-ttu-id="ca841-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ca841-113">Symbolic Name</span></span>|<span data-ttu-id="ca841-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="ca841-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="ca841-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ca841-115">Message Text</span></span>|<span data-ttu-id="ca841-116">No se habilitaron vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="ca841-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca841-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ca841-117">Explanation</span></span>  
 <span data-ttu-id="ca841-118">Este evento de advertencia indica que no se habilitaron vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="ca841-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="ca841-119">Si se deshabilita la concesión de vales en el nivel del sistema, tampoco se podrá usar en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ca841-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="ca841-120">Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ca841-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca841-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ca841-121">User Action</span></span>  
 <span data-ttu-id="ca841-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca841-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="ca841-123">Habilite los vales en el nivel de sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="ca841-123">Enable tickets at the SSO System level.</span></span>  
  
 <span data-ttu-id="ca841-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca841-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ca841-125">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="ca841-125">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="ca841-126">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="ca841-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
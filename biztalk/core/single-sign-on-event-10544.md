---
title: "Inicio de sesión único: Evento 10544 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a01cda4272e2851f929c35fd2b767c321a9dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="5acb8-102">Inicio de sesión único: Evento 10544</span><span class="sxs-lookup"><span data-stu-id="5acb8-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="5acb8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5acb8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5acb8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5acb8-104">Product Name</span></span>|<span data-ttu-id="5acb8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5acb8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5acb8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5acb8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5acb8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5acb8-107">Event ID</span></span>|<span data-ttu-id="5acb8-108">10544</span><span class="sxs-lookup"><span data-stu-id="5acb8-108">10544</span></span>|  
|<span data-ttu-id="5acb8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5acb8-109">Event Source</span></span>|<span data-ttu-id="5acb8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5acb8-110">ENTSSO</span></span>|  
|<span data-ttu-id="5acb8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5acb8-111">Component</span></span>|<span data-ttu-id="5acb8-112">CO</span><span class="sxs-lookup"><span data-stu-id="5acb8-112">CO</span></span>|  
|<span data-ttu-id="5acb8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5acb8-113">Symbolic Name</span></span>|<span data-ttu-id="5acb8-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="5acb8-114">SSO_WARN_TICKET_EXPIRED</span></span>|  
|<span data-ttu-id="5acb8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5acb8-115">Message Text</span></span>|<span data-ttu-id="5acb8-116">Vale caducado.%r</span><span class="sxs-lookup"><span data-stu-id="5acb8-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="5acb8-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="5acb8-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5acb8-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="5acb8-118">Explanation</span></span>  
 <span data-ttu-id="5acb8-119">Este evento de advertencia indica que el tiempo de espera de vale de aplicación ha caducado.</span><span class="sxs-lookup"><span data-stu-id="5acb8-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="5acb8-120">El tiempo de espera de vale se puede especificar tanto en el nivel de sistema como en el de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5acb8-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="5acb8-121">Si se especifica el tiempo de espera de ambos niveles, se usa el tiempo de espera del nivel de aplicación para determinar el tiempo de caducidad.</span><span class="sxs-lookup"><span data-stu-id="5acb8-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5acb8-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5acb8-122">User Action</span></span>  
 <span data-ttu-id="5acb8-123">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5acb8-123">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="5acb8-124">Determine por qué caducó el vale antes de su validación.</span><span class="sxs-lookup"><span data-stu-id="5acb8-124">Determine why the ticket expired before being validated.</span></span>  
  
-   <span data-ttu-id="5acb8-125">Asegúrese de que el valor de tiempo de espera de vale es lo suficientemente largo para que finalice entre la hora de emisión del vale y la hora de su canje.</span><span class="sxs-lookup"><span data-stu-id="5acb8-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  
  
 <span data-ttu-id="5acb8-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5acb8-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="5acb8-127">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="5acb8-127">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="5acb8-128">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="5acb8-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
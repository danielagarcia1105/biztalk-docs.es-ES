---
title: 'De sesión único: Evento 10544 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f476e664d50d05a57f42006ec08aa03d901e9f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983933"
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="a2ad2-102">De sesión único: Evento 10544</span><span class="sxs-lookup"><span data-stu-id="a2ad2-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="a2ad2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2ad2-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="a2ad2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a2ad2-104">Product Name</span></span>   |                 <span data-ttu-id="a2ad2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a2ad2-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="a2ad2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a2ad2-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="a2ad2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a2ad2-107">Event ID</span></span>     |                           <span data-ttu-id="a2ad2-108">10544</span><span class="sxs-lookup"><span data-stu-id="a2ad2-108">10544</span></span>                            |
|  <span data-ttu-id="a2ad2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a2ad2-109">Event Source</span></span>   |                           <span data-ttu-id="a2ad2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a2ad2-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="a2ad2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a2ad2-111">Component</span></span>    |                             <span data-ttu-id="a2ad2-112">CO</span><span class="sxs-lookup"><span data-stu-id="a2ad2-112">CO</span></span>                             |
|  <span data-ttu-id="a2ad2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a2ad2-113">Symbolic Name</span></span>  |                  <span data-ttu-id="a2ad2-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="a2ad2-114">SSO_WARN_TICKET_EXPIRED</span></span>                   |
|  <span data-ttu-id="a2ad2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a2ad2-115">Message Text</span></span>   | <span data-ttu-id="a2ad2-116">Vale caducado.%r</span><span class="sxs-lookup"><span data-stu-id="a2ad2-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="a2ad2-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="a2ad2-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="a2ad2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="a2ad2-118">Explanation</span></span>  
 <span data-ttu-id="a2ad2-119">Este evento de advertencia indica que el tiempo de espera de vale de aplicación ha caducado.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="a2ad2-120">El tiempo de espera de vale se puede especificar tanto en el nivel de sistema como en el de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="a2ad2-121">Si se especifica el tiempo de espera de ambos niveles, se usa el tiempo de espera del nivel de aplicación para determinar el tiempo de caducidad.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a2ad2-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a2ad2-122">User Action</span></span>  
 <span data-ttu-id="a2ad2-123">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2ad2-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a2ad2-124">Determine por qué caducó el vale antes de su validación.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-124">Determine why the ticket expired before being validated.</span></span>  

- <span data-ttu-id="a2ad2-125">Asegúrese de que el valor de tiempo de espera de vale es lo suficientemente largo para que finalice entre la hora de emisión del vale y la hora de su canje.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  

  <span data-ttu-id="a2ad2-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2ad2-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a2ad2-127">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="a2ad2-127">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="a2ad2-128">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="a2ad2-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)

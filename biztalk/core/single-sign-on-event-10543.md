---
title: 'Inicio de sesión único: Evento 10543 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9bf30640bf61f9c88de3fedbb5727be7a715aa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270004"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="f7b6d-102">Inicio de sesión único: Evento 10543</span><span class="sxs-lookup"><span data-stu-id="f7b6d-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="f7b6d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f7b6d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7b6d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f7b6d-104">Product Name</span></span>|<span data-ttu-id="f7b6d-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f7b6d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f7b6d-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f7b6d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f7b6d-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f7b6d-107">Event ID</span></span>|<span data-ttu-id="f7b6d-108">10543</span><span class="sxs-lookup"><span data-stu-id="f7b6d-108">10543</span></span>|  
|<span data-ttu-id="f7b6d-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f7b6d-109">Event Source</span></span>|<span data-ttu-id="f7b6d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7b6d-110">ENTSSO</span></span>|  
|<span data-ttu-id="f7b6d-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f7b6d-111">Component</span></span>|<span data-ttu-id="f7b6d-112">CO</span><span class="sxs-lookup"><span data-stu-id="f7b6d-112">CO</span></span>|  
|<span data-ttu-id="f7b6d-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f7b6d-113">Symbolic Name</span></span>|<span data-ttu-id="f7b6d-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="f7b6d-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>|  
|<span data-ttu-id="f7b6d-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f7b6d-115">Message Text</span></span>|<span data-ttu-id="f7b6d-116">El vale se emitió con validación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="f7b6d-117">Si no se valida, no puede canjearse para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="f7b6d-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="f7b6d-118">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="f7b6d-118">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f7b6d-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="f7b6d-119">Explanation</span></span>  
 <span data-ttu-id="f7b6d-120">Este evento de advertencia indica que se emitió un vale de aplicación con validación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="f7b6d-121">Los vales no se pueden canjear si no se validan.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="f7b6d-122">La validación de vales se realiza según la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-122">Validation of the ticket is on a per affiliate application basis.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7b6d-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f7b6d-123">User Action</span></span>  
 <span data-ttu-id="f7b6d-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7b6d-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="f7b6d-125">Si usa el inicio de sesión único empresarial, asegúrese de que los mensajes se envíen solamente a través de hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="f7b6d-126">De este modo, disminuirá el riesgo de alteración de datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
-   <span data-ttu-id="f7b6d-127">Si el escenario lo permite, desactive la validación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="f7b6d-128">La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  
  
 <span data-ttu-id="f7b6d-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f7b6d-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f7b6d-130">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="f7b6d-130">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="f7b6d-131">Cómo mostrar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="f7b6d-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="f7b6d-132">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="f7b6d-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
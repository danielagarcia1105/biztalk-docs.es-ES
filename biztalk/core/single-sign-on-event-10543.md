---
title: 'De sesión único: Evento 10543 | Microsoft Docs'
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
ms.openlocfilehash: cf5c026384bf463f6ee0a33045dd1e7b1fca4188
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998453"
---
# <a name="single-sign-on-event-10543"></a><span data-ttu-id="bec8b-102">De sesión único: Evento 10543</span><span class="sxs-lookup"><span data-stu-id="bec8b-102">Single Sign-On: Event 10543</span></span>
## <a name="details"></a><span data-ttu-id="bec8b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bec8b-103">Details</span></span>  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bec8b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="bec8b-104">Product Name</span></span>   |                                                               <span data-ttu-id="bec8b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="bec8b-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="bec8b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="bec8b-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="bec8b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="bec8b-107">Event ID</span></span>     |                                                                         <span data-ttu-id="bec8b-108">10543</span><span class="sxs-lookup"><span data-stu-id="bec8b-108">10543</span></span>                                                                          |
|  <span data-ttu-id="bec8b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="bec8b-109">Event Source</span></span>   |                                                                         <span data-ttu-id="bec8b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bec8b-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="bec8b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="bec8b-111">Component</span></span>    |                                                                           <span data-ttu-id="bec8b-112">CO</span><span class="sxs-lookup"><span data-stu-id="bec8b-112">CO</span></span>                                                                           |
|  <span data-ttu-id="bec8b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bec8b-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="bec8b-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="bec8b-114">SSO_WARN_ORIGINAL_TICKET_VALIDATED</span></span>                                                           |
|  <span data-ttu-id="bec8b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bec8b-115">Message Text</span></span>   | <span data-ttu-id="bec8b-116">El vale se emitió con validación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="bec8b-116">The ticket was issued with validation required.</span></span> <span data-ttu-id="bec8b-117">Si no se valida, no puede canjearse para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="bec8b-117">It cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="bec8b-118">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="bec8b-118">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="bec8b-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="bec8b-119">Explanation</span></span>  
 <span data-ttu-id="bec8b-120">Este evento de advertencia indica que se emitió un vale de aplicación con validación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="bec8b-120">This Warning event indicates that an application ticket was issued with validation required.</span></span> <span data-ttu-id="bec8b-121">Los vales no se pueden canjear si no se validan.</span><span class="sxs-lookup"><span data-stu-id="bec8b-121">Tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="bec8b-122">La validación de vales se realiza según la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="bec8b-122">Validation of the ticket is on a per affiliate application basis.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bec8b-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bec8b-123">User Action</span></span>  
 <span data-ttu-id="bec8b-124">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bec8b-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="bec8b-125">Si usa el inicio de sesión único empresarial, asegúrese de que los mensajes se envíen solamente a través de hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="bec8b-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="bec8b-126">De este modo, disminuirá el riesgo de alteración de datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bec8b-126">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="bec8b-127">Si el escenario lo permite, desactive la validación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="bec8b-127">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="bec8b-128">La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.</span><span class="sxs-lookup"><span data-stu-id="bec8b-128">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="bec8b-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bec8b-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bec8b-130">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="bec8b-130">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="bec8b-131">Cómo enumerar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="bec8b-131">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="bec8b-132">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="bec8b-132">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)

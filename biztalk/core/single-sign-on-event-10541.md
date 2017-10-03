---
title: "Inicio de sesión único: Evento 10541 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e206158-5652-453c-91ac-9a75ab02809a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201a43682898f312687f3d5d453f3b050bc75d48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10541"></a><span data-ttu-id="ccca9-102">Inicio de sesión único: Evento 10541</span><span class="sxs-lookup"><span data-stu-id="ccca9-102">Single Sign-On: Event 10541</span></span>
## <a name="details"></a><span data-ttu-id="ccca9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccca9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccca9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ccca9-104">Product Name</span></span>|<span data-ttu-id="ccca9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ccca9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ccca9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ccca9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ccca9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ccca9-107">Event ID</span></span>|<span data-ttu-id="ccca9-108">10541</span><span class="sxs-lookup"><span data-stu-id="ccca9-108">10541</span></span>|  
|<span data-ttu-id="ccca9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ccca9-109">Event Source</span></span>|<span data-ttu-id="ccca9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ccca9-110">ENTSSO</span></span>|  
|<span data-ttu-id="ccca9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ccca9-111">Component</span></span>|<span data-ttu-id="ccca9-112">CO</span><span class="sxs-lookup"><span data-stu-id="ccca9-112">CO</span></span>|  
|<span data-ttu-id="ccca9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ccca9-113">Symbolic Name</span></span>|<span data-ttu-id="ccca9-114">SSO_WARN_SSO_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="ccca9-114">SSO_WARN_SSO_TICKETS_VALIDATED</span></span>|  
|<span data-ttu-id="ccca9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ccca9-115">Message Text</span></span>|<span data-ttu-id="ccca9-116">Los vales no se pueden canjear si no se validan.</span><span class="sxs-lookup"><span data-stu-id="ccca9-116">Tickets cannot be redeemed without being validated.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ccca9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ccca9-117">Explanation</span></span>  
 <span data-ttu-id="ccca9-118">Este evento de advertencia indica que los vales de SSO no pueden canjearse si no se validan.</span><span class="sxs-lookup"><span data-stu-id="ccca9-118">This Warning event indicates that SSO tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="ccca9-119">Cuando se canjean vales de SSO, pueden o no validarse.</span><span class="sxs-lookup"><span data-stu-id="ccca9-119">When SSO tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="ccca9-120">La validación mejora la seguridad al comparar el nombre del usuario que emitió el vale con el nombre del usuario que figura en el mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ccca9-120">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="ccca9-121">Si los nombres no coinciden, se produce un error de validación.</span><span class="sxs-lookup"><span data-stu-id="ccca9-121">If the names are not the same then validation fails.</span></span> <span data-ttu-id="ccca9-122">Cuando el mensaje de BizTalk se transmite a través de un host que no es de confianza, el nombre del usuario de este mensaje cambia al nombre del host que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="ccca9-122">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="ccca9-123">La validación garantiza que el mensaje de BizTalk sólo se transmita a través de hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="ccca9-123">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="ccca9-124">Este mensaje indica específicamente que es necesaria la validación en el nivel de sistema SSO (debido a la configuración de opciones del sistema SSO), pero que el usuario que llama no proporcionó la información de validación.</span><span class="sxs-lookup"><span data-stu-id="ccca9-124">This message means specifically that validation is required at the SSO system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ccca9-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ccca9-125">User Action</span></span>  
 <span data-ttu-id="ccca9-126">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ccca9-126">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ccca9-127">Si usa BizTalk Server, asegúrese de que los mensajes se envíen solamente a través de hosts de BizTalk de confianza.</span><span class="sxs-lookup"><span data-stu-id="ccca9-127">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="ccca9-128">De este modo, disminuirá el riesgo de alteración de datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ccca9-128">This will reduce the risk of tampering with the data in the message.</span></span>  
  
-   <span data-ttu-id="ccca9-129">Si el escenario lo permite, desactive la validación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccca9-129">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="ccca9-130">La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.</span><span class="sxs-lookup"><span data-stu-id="ccca9-130">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  
  
 <span data-ttu-id="ccca9-131">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ccca9-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ccca9-132">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="ccca9-132">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="ccca9-133">Cómo mostrar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="ccca9-133">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="ccca9-134">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="ccca9-134">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)
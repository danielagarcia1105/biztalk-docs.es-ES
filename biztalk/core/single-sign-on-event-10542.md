---
title: 'De sesión único: Evento 10542 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be63569d76bf7c0cfb14cb10bda27b6da52a3efc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979381"
---
# <a name="single-sign-on-event-10542"></a><span data-ttu-id="12017-102">De sesión único: Evento 10542</span><span class="sxs-lookup"><span data-stu-id="12017-102">Single Sign-On: Event 10542</span></span>
## <a name="details"></a><span data-ttu-id="12017-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="12017-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="12017-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="12017-104">Product Name</span></span>   |                                          <span data-ttu-id="12017-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="12017-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="12017-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="12017-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="12017-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="12017-107">Event ID</span></span>     |                                                    <span data-ttu-id="12017-108">10542</span><span class="sxs-lookup"><span data-stu-id="12017-108">10542</span></span>                                                    |
|  <span data-ttu-id="12017-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="12017-109">Event Source</span></span>   |                                                   <span data-ttu-id="12017-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="12017-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="12017-111">Componente</span><span class="sxs-lookup"><span data-stu-id="12017-111">Component</span></span>    |                                                     <span data-ttu-id="12017-112">CO</span><span class="sxs-lookup"><span data-stu-id="12017-112">CO</span></span>                                                      |
|  <span data-ttu-id="12017-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="12017-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="12017-114">SSO_WARN_APP_TICKETS_VALIDATED</span><span class="sxs-lookup"><span data-stu-id="12017-114">SSO_WARN_APP_TICKETS_VALIDATED</span></span>                                        |
|  <span data-ttu-id="12017-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="12017-115">Message Text</span></span>   | <span data-ttu-id="12017-116">Si no se validan, los vales no pueden canjearse para esta aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="12017-116">Tickets cannot be redeemed for this application without being validated.%r</span></span><br /><br /> <span data-ttu-id="12017-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="12017-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="12017-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="12017-118">Explanation</span></span>  
 <span data-ttu-id="12017-119">Este evento de advertencia indica que los vales de aplicación no pueden canjearse si no se validan.</span><span class="sxs-lookup"><span data-stu-id="12017-119">This Warning event indicates that application tickets cannot be redeemed without being validated.</span></span> <span data-ttu-id="12017-120">Cuando se canjean vales de aplicación, pueden o no validarse.</span><span class="sxs-lookup"><span data-stu-id="12017-120">When application tickets are redeemed they can be validated or not validated.</span></span> <span data-ttu-id="12017-121">La validación mejora la seguridad al comparar el nombre del usuario que emitió el vale con el nombre del usuario que figura en el mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="12017-121">Validation improves security by comparing the name of the user who issued the ticket with the name of the user in the BizTalk message.</span></span> <span data-ttu-id="12017-122">Si los nombres no coinciden, se produce un error de validación.</span><span class="sxs-lookup"><span data-stu-id="12017-122">If the names are not the same then validation fails.</span></span> <span data-ttu-id="12017-123">Cuando el mensaje de BizTalk se transmite a través de un host que no es de confianza, el nombre del usuario de este mensaje cambia al nombre del host que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="12017-123">When a BizTalk message flows through an un-trusted host, the name of the user in the BizTalk message is changed to that of the un-trusted host.</span></span> <span data-ttu-id="12017-124">La validación garantiza que el mensaje de BizTalk sólo se transmita a través de hosts de confianza.</span><span class="sxs-lookup"><span data-stu-id="12017-124">Validation ensures that the BizTalk message has only flowed through trusted hosts.</span></span> <span data-ttu-id="12017-125">Este mensaje indica específicamente que es necesaria la validación en el nivel de sistema de aplicaciones (debido a la configuración de opciones del sistema SSO), pero que el usuario que llama no proporcionó la información de validación.</span><span class="sxs-lookup"><span data-stu-id="12017-125">This message means specifically that validation is required at the application system level (due to an SSO system option setting), but no validation information was provided by the caller.</span></span>  

## <a name="user-action"></a><span data-ttu-id="12017-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="12017-126">User Action</span></span>  
 <span data-ttu-id="12017-127">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="12017-127">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="12017-128">Si usa BizTalk Server, asegúrese de que los mensajes se envíen solamente a través de hosts de BizTalk de confianza.</span><span class="sxs-lookup"><span data-stu-id="12017-128">If you are using BizTalk Server, ensure that your message is flowing only through trusted hosts.</span></span> <span data-ttu-id="12017-129">De este modo, disminuirá el riesgo de alteración de datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="12017-129">This will reduce the risk of tampering with the data in the message.</span></span>  

- <span data-ttu-id="12017-130">Si el escenario lo permite, desactive la validación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="12017-130">If your scenario allows it, turn off validation for this application.</span></span> <span data-ttu-id="12017-131">La validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.</span><span class="sxs-lookup"><span data-stu-id="12017-131">Validation is an administration option which can be turned off for the system or just for this particular application.</span></span>  

  <span data-ttu-id="12017-132">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="12017-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="12017-133">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="12017-133">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="12017-134">Cómo enumerar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="12017-134">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [<span data-ttu-id="12017-135">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="12017-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)

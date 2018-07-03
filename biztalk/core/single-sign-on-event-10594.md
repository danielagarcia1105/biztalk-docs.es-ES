---
title: 'De sesión único: Evento 10594 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba733d9a919b2af09824242a48a2fa85af8ab481
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004764"
---
# <a name="single-sign-on-event-10594"></a><span data-ttu-id="0c613-102">De sesión único: Evento 10594</span><span class="sxs-lookup"><span data-stu-id="0c613-102">Single Sign-On: Event 10594</span></span>
## <a name="details"></a><span data-ttu-id="0c613-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c613-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0c613-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0c613-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="0c613-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0c613-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="0c613-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0c613-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="0c613-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0c613-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="0c613-108">10594</span><span class="sxs-lookup"><span data-stu-id="0c613-108">10594</span></span>                                                                                            |
|  <span data-ttu-id="0c613-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0c613-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="0c613-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0c613-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="0c613-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0c613-111">Component</span></span>    |                                                                                            <span data-ttu-id="0c613-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0c613-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="0c613-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0c613-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="0c613-114">SSO_WARN_TICKET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="0c613-114">SSO_WARN_TICKET_VALIDATE_FAILED</span></span>                                                                               |
|  <span data-ttu-id="0c613-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0c613-115">Message Text</span></span>   | <span data-ttu-id="0c613-116">Error al validar el vale.</span><span class="sxs-lookup"><span data-stu-id="0c613-116">Validation of the ticket failed.</span></span> <span data-ttu-id="0c613-117">El nombre del remitente debe coincidir con el emisor del vale.%r</span><span class="sxs-lookup"><span data-stu-id="0c613-117">The sender name must match that of the ticket issuer.%r</span></span><br /><br /> <span data-ttu-id="0c613-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0c613-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="0c613-119">Vale emitido por: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0c613-119">Ticket Issued By: %2%r</span></span><br /><br /> <span data-ttu-id="0c613-120">Nombre del remitente: %3</span><span class="sxs-lookup"><span data-stu-id="0c613-120">Sender Name: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0c613-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="0c613-121">Explanation</span></span>  
 <span data-ttu-id="0c613-122">Para que se valide un vale, deben coincidir los campos Vale emitido por y Nombre del remitente (en el mensaje de advertencia).</span><span class="sxs-lookup"><span data-stu-id="0c613-122">In order for a ticket to be validated, the Ticket Issued By and Sender Name fields (in the warning message) must match.</span></span> <span data-ttu-id="0c613-123">Sin embargo, si el mensaje se envía a través de un host de BizTalk que no es de confianza, el nombre del remitente cambia al nombre de este host y no se valida el vale.</span><span class="sxs-lookup"><span data-stu-id="0c613-123">If, however, the message is sent through a BizTalk untrusted host, the Sender Name gets changed to the name of the BizTalk untrusted host, and the ticket will not validate.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c613-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0c613-124">User Action</span></span>  
 <span data-ttu-id="0c613-125">Si usa el inicio de sesión único empresarial, asegúrese de que los mensajes se envíen solamente a través de hosts de BizTalk de confianza.</span><span class="sxs-lookup"><span data-stu-id="0c613-125">If you are using Enterprise Single Sign-On, ensure that your message is flowing only through BizTalk trusted hosts.</span></span> <span data-ttu-id="0c613-126">De este modo, disminuirá el riesgo de alteración de datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c613-126">This will reduce the risk of tampering with the data in the message.</span></span>  
  
 <span data-ttu-id="0c613-127">Si comprende plenamente las implicaciones de seguridad del escenario, puede desactivar la validación para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c613-127">If you fully understand the security implications for your scenario, you can turn off validation for this application.</span></span> <span data-ttu-id="0c613-128">Tenga en cuenta que la validación es una opción administrativa que se puede desactivar tanto para el sistema como para esta aplicación específica solamente.</span><span class="sxs-lookup"><span data-stu-id="0c613-128">Note that validation is an administration option which can be turned off for the system or just for this particular application.</span></span>
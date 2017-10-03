---
title: "Inicio de sesión único: Evento 10655 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 185a8315cc49de3bfc807636ce78755e8421d802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10655"></a><span data-ttu-id="2ab03-102">Inicio de sesión único: Evento 10655</span><span class="sxs-lookup"><span data-stu-id="2ab03-102">Single Sign-On: Event 10655</span></span>
## <a name="details"></a><span data-ttu-id="2ab03-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2ab03-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ab03-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2ab03-104">Product Name</span></span>|<span data-ttu-id="2ab03-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="2ab03-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2ab03-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2ab03-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2ab03-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2ab03-107">Event ID</span></span>|<span data-ttu-id="2ab03-108">10655</span><span class="sxs-lookup"><span data-stu-id="2ab03-108">10655</span></span>|  
|<span data-ttu-id="2ab03-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2ab03-109">Event Source</span></span>|<span data-ttu-id="2ab03-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2ab03-110">ENTSSO</span></span>|  
|<span data-ttu-id="2ab03-111">Componente</span><span class="sxs-lookup"><span data-stu-id="2ab03-111">Component</span></span>|<span data-ttu-id="2ab03-112">N\D</span><span class="sxs-lookup"><span data-stu-id="2ab03-112">N\A</span></span>|  
|<span data-ttu-id="2ab03-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2ab03-113">Symbolic Name</span></span>|<span data-ttu-id="2ab03-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="2ab03-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="2ab03-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2ab03-115">Message Text</span></span>|<span data-ttu-id="2ab03-116">Acceso denegado al servidor de sincronización de contraseñas (para ping).%r</span><span class="sxs-lookup"><span data-stu-id="2ab03-116">Password sync server (for ping) access denied.%r</span></span><br /><br /> <span data-ttu-id="2ab03-117">Usuario cliente: %1</span><span class="sxs-lookup"><span data-stu-id="2ab03-117">Client User: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ab03-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="2ab03-118">Explanation</span></span>  
 <span data-ttu-id="2ab03-119">Este evento de error indica que se envió un mensaje al servidor [nombre] pero se bloqueó la respuesta.</span><span class="sxs-lookup"><span data-stu-id="2ab03-119">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="2ab03-120">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2ab03-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ab03-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2ab03-121">User Action</span></span>  
 <span data-ttu-id="2ab03-122">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ab03-122">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="2ab03-123">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con los servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ab03-123">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  
  
 <span data-ttu-id="2ab03-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2ab03-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="2ab03-125">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="2ab03-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
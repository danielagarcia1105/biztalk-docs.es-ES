---
title: 'Inicio de sesión único: Evento 10654 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d7de49ec1606c7c0a33f802af11af4e8ad2848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270868"
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="b92af-102">Inicio de sesión único: Evento 10654</span><span class="sxs-lookup"><span data-stu-id="b92af-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="b92af-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b92af-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b92af-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b92af-104">Product Name</span></span>|<span data-ttu-id="b92af-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b92af-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b92af-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b92af-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b92af-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b92af-107">Event ID</span></span>|<span data-ttu-id="b92af-108">10654</span><span class="sxs-lookup"><span data-stu-id="b92af-108">10654</span></span>|  
|<span data-ttu-id="b92af-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b92af-109">Event Source</span></span>|<span data-ttu-id="b92af-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b92af-110">ENTSSO</span></span>|  
|<span data-ttu-id="b92af-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b92af-111">Component</span></span>|<span data-ttu-id="b92af-112">N\D</span><span class="sxs-lookup"><span data-stu-id="b92af-112">N\A</span></span>|  
|<span data-ttu-id="b92af-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b92af-113">Symbolic Name</span></span>|<span data-ttu-id="b92af-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="b92af-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="b92af-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b92af-115">Message Text</span></span>|<span data-ttu-id="b92af-116">Acceso denegado al servidor de sincronización de contraseñas (para Windows).%r</span><span class="sxs-lookup"><span data-stu-id="b92af-116">Password sync server (for Windows) access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b92af-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b92af-117">Explanation</span></span>  
 <span data-ttu-id="b92af-118">Este evento de error indica que se envió un mensaje al servidor [nombre] pero se bloqueó la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b92af-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="b92af-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b92af-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b92af-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b92af-120">User Action</span></span>  
 <span data-ttu-id="b92af-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b92af-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="b92af-122">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con los servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b92af-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  
  
 <span data-ttu-id="b92af-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b92af-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b92af-124">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="b92af-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
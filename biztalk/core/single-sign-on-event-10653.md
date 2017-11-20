---
title: "Inicio de sesión único: Evento 10653 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91ec21a7883c3c1d3e97519f9239050ea18035fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10653"></a><span data-ttu-id="ce0d6-102">Inicio de sesión único: Evento 10653</span><span class="sxs-lookup"><span data-stu-id="ce0d6-102">Single Sign-On: Event 10653</span></span>
## <a name="details"></a><span data-ttu-id="ce0d6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ce0d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce0d6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ce0d6-104">Product Name</span></span>|<span data-ttu-id="ce0d6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ce0d6-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ce0d6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ce0d6-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ce0d6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ce0d6-107">Event ID</span></span>|<span data-ttu-id="ce0d6-108">10653</span><span class="sxs-lookup"><span data-stu-id="ce0d6-108">10653</span></span>|  
|<span data-ttu-id="ce0d6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ce0d6-109">Event Source</span></span>|<span data-ttu-id="ce0d6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ce0d6-110">ENTSSO</span></span>|  
|<span data-ttu-id="ce0d6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ce0d6-111">Component</span></span>|<span data-ttu-id="ce0d6-112">N\D</span><span class="sxs-lookup"><span data-stu-id="ce0d6-112">N\A</span></span>|  
|<span data-ttu-id="ce0d6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ce0d6-113">Symbolic Name</span></span>|<span data-ttu-id="ce0d6-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="ce0d6-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="ce0d6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ce0d6-115">Message Text</span></span>|<span data-ttu-id="ce0d6-116">Acceso denegado al servidor de sincronización de contraseñas (para adaptadores).%r</span><span class="sxs-lookup"><span data-stu-id="ce0d6-116">Password sync server (for adapters) access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ce0d6-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ce0d6-117">Explanation</span></span>  
 <span data-ttu-id="ce0d6-118">Este evento de error indica que un cliente intentó comunicarse con el servidor pero se rechazó la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce0d6-118">This Error event indicates that a client attempted to contact the server but the call was refused.</span></span> <span data-ttu-id="ce0d6-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes.</span><span class="sxs-lookup"><span data-stu-id="ce0d6-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce0d6-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ce0d6-120">User Action</span></span>  
 <span data-ttu-id="ce0d6-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce0d6-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="ce0d6-122">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con los servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce0d6-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  
  
 <span data-ttu-id="ce0d6-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ce0d6-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ce0d6-124">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="ce0d6-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
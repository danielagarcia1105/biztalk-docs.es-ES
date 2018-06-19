---
title: Tipos de mensajes sin partes no se admiten | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e3e6cc0f5d4a2ae18ff6bcb5fa0dc8ef605d730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263108"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="7065d-102">No se admiten los tipos de mensajes sin partes</span><span class="sxs-lookup"><span data-stu-id="7065d-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="7065d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7065d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7065d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7065d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7065d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7065d-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7065d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7065d-106">Event ID</span></span>|<span data-ttu-id="7065d-107">0</span><span class="sxs-lookup"><span data-stu-id="7065d-107">0</span></span>|  
|<span data-ttu-id="7065d-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7065d-108">Event Source</span></span>|<span data-ttu-id="7065d-109">0</span><span class="sxs-lookup"><span data-stu-id="7065d-109">0</span></span>|  
|<span data-ttu-id="7065d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7065d-110">Component</span></span>|<span data-ttu-id="7065d-111">0</span><span class="sxs-lookup"><span data-stu-id="7065d-111">0</span></span>|  
|<span data-ttu-id="7065d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7065d-112">Symbolic Name</span></span>|<span data-ttu-id="7065d-113">0</span><span class="sxs-lookup"><span data-stu-id="7065d-113">0</span></span>|  
|<span data-ttu-id="7065d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7065d-114">Message Text</span></span>|<span data-ttu-id="7065d-115">No se admiten los tipos de mensajes sin partes.</span><span class="sxs-lookup"><span data-stu-id="7065d-115">Message types without parts are not supported.</span></span> <span data-ttu-id="7065d-116">Corrija el tipo de mensaje de descripción "{0}" servicio "{{1}" y vuelva a ejecutar al asistente.</span><span class="sxs-lookup"><span data-stu-id="7065d-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7065d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="7065d-117">Explanation</span></span>  
 <span data-ttu-id="7065d-118">Este error indica que el servicio que se intenta consumir no tiene un tipo de mensaje definido.</span><span class="sxs-lookup"><span data-stu-id="7065d-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7065d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7065d-119">User Action</span></span>  
 <span data-ttu-id="7065d-120">Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="7065d-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="7065d-121">De lo contrario, póngase en contacto con el proveedor de servicio.</span><span class="sxs-lookup"><span data-stu-id="7065d-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="7065d-122">Para obtener información adicional sobre los mensajes, vea el siguiente recurso en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ayuda:</span><span class="sxs-lookup"><span data-stu-id="7065d-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="7065d-123">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="7065d-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)
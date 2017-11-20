---
title: Elemento que falta parte de mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd5a423a34d8b6ddf8f4689351b0f6dbcef53c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-part-missing-element"></a><span data-ttu-id="01586-102">Falta un elemento de parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="01586-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="01586-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="01586-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01586-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="01586-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="01586-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="01586-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="01586-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="01586-106">Event ID</span></span>|<span data-ttu-id="01586-107">0</span><span class="sxs-lookup"><span data-stu-id="01586-107">0</span></span>|  
|<span data-ttu-id="01586-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="01586-108">Event Source</span></span>|<span data-ttu-id="01586-109">0</span><span class="sxs-lookup"><span data-stu-id="01586-109">0</span></span>|  
|<span data-ttu-id="01586-110">Componente</span><span class="sxs-lookup"><span data-stu-id="01586-110">Component</span></span>|<span data-ttu-id="01586-111">0</span><span class="sxs-lookup"><span data-stu-id="01586-111">0</span></span>|  
|<span data-ttu-id="01586-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="01586-112">Symbolic Name</span></span>|<span data-ttu-id="01586-113">0</span><span class="sxs-lookup"><span data-stu-id="01586-113">0</span></span>|  
|<span data-ttu-id="01586-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="01586-114">Message Text</span></span>|<span data-ttu-id="01586-115">Falta un elemento de parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="01586-115">Message part missing element.</span></span> <span data-ttu-id="01586-116">Corrija la parte "{{1}" "{{2}" del tipo de mensaje de descripción "{0}" servicio y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="01586-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01586-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="01586-117">Explanation</span></span>  
 <span data-ttu-id="01586-118">Este error indica que el servicio que se intenta consumir no tiene la etiqueta de elemento que identifica el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="01586-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01586-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="01586-119">User Action</span></span>  
 <span data-ttu-id="01586-120">Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="01586-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="01586-121">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="01586-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="01586-122">Para obtener más información sobre mensajes, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="01586-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="01586-123">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="01586-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)
---
title: Falta un elemento de parte de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412b25d2f7ea027de53818b032b50562faab9865
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009445"
---
# <a name="message-part-missing-element"></a><span data-ttu-id="24a00-102">Falta un elemento de parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="24a00-102">Message part missing element</span></span>
## <a name="details"></a><span data-ttu-id="24a00-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="24a00-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="24a00-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="24a00-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="24a00-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="24a00-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="24a00-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="24a00-106">Event ID</span></span>     |                                                         <span data-ttu-id="24a00-107">0</span><span class="sxs-lookup"><span data-stu-id="24a00-107">0</span></span>                                                          |
|  <span data-ttu-id="24a00-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="24a00-108">Event Source</span></span>   |                                                         <span data-ttu-id="24a00-109">0</span><span class="sxs-lookup"><span data-stu-id="24a00-109">0</span></span>                                                          |
|    <span data-ttu-id="24a00-110">Componente</span><span class="sxs-lookup"><span data-stu-id="24a00-110">Component</span></span>    |                                                         <span data-ttu-id="24a00-111">0</span><span class="sxs-lookup"><span data-stu-id="24a00-111">0</span></span>                                                          |
|  <span data-ttu-id="24a00-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="24a00-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="24a00-113">0</span><span class="sxs-lookup"><span data-stu-id="24a00-113">0</span></span>                                                          |
|  <span data-ttu-id="24a00-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="24a00-114">Message Text</span></span>   | <span data-ttu-id="24a00-115">Falta un elemento de parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="24a00-115">Message part missing element.</span></span> <span data-ttu-id="24a00-116">Corrija la descripción del servicio "{0}"tipo de mensaje"{1}"elemento"{2}" y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="24a00-116">Correct service description "{0}" message type "{1}" part "{2}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="24a00-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="24a00-117">Explanation</span></span>  
 <span data-ttu-id="24a00-118">Este error indica que el servicio que se intenta consumir no tiene la etiqueta de elemento que identifica el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="24a00-118">This error indicates the service that is trying to be consumed does not have the element tag identifying the type of message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24a00-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="24a00-119">User Action</span></span>  
 <span data-ttu-id="24a00-120">Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="24a00-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="24a00-121">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="24a00-121">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="24a00-122">Para obtener más información sobre mensajes, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="24a00-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="24a00-123">Construcción de mensajes web</span><span class="sxs-lookup"><span data-stu-id="24a00-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)
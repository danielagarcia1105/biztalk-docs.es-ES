---
title: Tipos de mensajes sin partes no se admiten | Microsoft Docs
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
ms.openlocfilehash: 60bb78e2bbf06ff80315bd9bbc2b33346ed18d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024170"
---
# <a name="message-types-without-parts-are-not-supported"></a><span data-ttu-id="44b0f-102">No se admiten los tipos de mensajes sin partes</span><span class="sxs-lookup"><span data-stu-id="44b0f-102">Message types without parts are not supported</span></span>
## <a name="details"></a><span data-ttu-id="44b0f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="44b0f-103">Details</span></span>  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="44b0f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="44b0f-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="44b0f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="44b0f-105">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="44b0f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="44b0f-106">Event ID</span></span>     |                                                             <span data-ttu-id="44b0f-107">0</span><span class="sxs-lookup"><span data-stu-id="44b0f-107">0</span></span>                                                             |
|  <span data-ttu-id="44b0f-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="44b0f-108">Event Source</span></span>   |                                                             <span data-ttu-id="44b0f-109">0</span><span class="sxs-lookup"><span data-stu-id="44b0f-109">0</span></span>                                                             |
|    <span data-ttu-id="44b0f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="44b0f-110">Component</span></span>    |                                                             <span data-ttu-id="44b0f-111">0</span><span class="sxs-lookup"><span data-stu-id="44b0f-111">0</span></span>                                                             |
|  <span data-ttu-id="44b0f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="44b0f-112">Symbolic Name</span></span>  |                                                             <span data-ttu-id="44b0f-113">0</span><span class="sxs-lookup"><span data-stu-id="44b0f-113">0</span></span>                                                             |
|  <span data-ttu-id="44b0f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="44b0f-114">Message Text</span></span>   | <span data-ttu-id="44b0f-115">No se admiten los tipos de mensajes sin partes.</span><span class="sxs-lookup"><span data-stu-id="44b0f-115">Message types without parts are not supported.</span></span> <span data-ttu-id="44b0f-116">Corrija la descripción del servicio "{0}"tipo de mensaje"{1}" y vuelva a ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="44b0f-116">Correct service description "{0}" message type "{1}" and rerun the wizard.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="44b0f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="44b0f-117">Explanation</span></span>  
 <span data-ttu-id="44b0f-118">Este error indica que el servicio que se intenta consumir no tiene un tipo de mensaje definido.</span><span class="sxs-lookup"><span data-stu-id="44b0f-118">This error indicates the service that is trying to be consumed does not have a message type defined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44b0f-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="44b0f-119">User Action</span></span>  
 <span data-ttu-id="44b0f-120">Corrija el servicio con el tipo de mensaje adecuado e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="44b0f-120">Correct the service with the appropriate message type and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="44b0f-121">De lo contrario, póngase en contacto con el proveedor de servicio.</span><span class="sxs-lookup"><span data-stu-id="44b0f-121">Otherwise, contact the serviced provider.</span></span>  <span data-ttu-id="44b0f-122">Para obtener más información sobre los mensajes, vea el siguiente recurso en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ayuda:</span><span class="sxs-lookup"><span data-stu-id="44b0f-122">For additional information on messages, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Help:</span></span>  
  
-   [<span data-ttu-id="44b0f-123">Construcción de mensajes web</span><span class="sxs-lookup"><span data-stu-id="44b0f-123">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)
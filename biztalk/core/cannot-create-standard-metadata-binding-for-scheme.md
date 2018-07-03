---
title: No se puede crear el enlace de metadatos estándar para el esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fd4a91535c7872bb5be7328755808eb91758db6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989317"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a><span data-ttu-id="c740d-102">No se puede crear el enlace de metadatos estándar para el esquema</span><span class="sxs-lookup"><span data-stu-id="c740d-102">Cannot create standard metadata binding for scheme</span></span>
## <a name="details"></a><span data-ttu-id="c740d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c740d-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c740d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c740d-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="c740d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c740d-105">Product Version</span></span> |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    <span data-ttu-id="c740d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c740d-106">Event ID</span></span>     |                                                         <span data-ttu-id="c740d-107">0</span><span class="sxs-lookup"><span data-stu-id="c740d-107">0</span></span>                                                          |
|  <span data-ttu-id="c740d-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c740d-108">Event Source</span></span>   |                                                         <span data-ttu-id="c740d-109">0</span><span class="sxs-lookup"><span data-stu-id="c740d-109">0</span></span>                                                          |
|    <span data-ttu-id="c740d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c740d-110">Component</span></span>    |                                                         <span data-ttu-id="c740d-111">0</span><span class="sxs-lookup"><span data-stu-id="c740d-111">0</span></span>                                                          |
|  <span data-ttu-id="c740d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c740d-112">Symbolic Name</span></span>  |                                                         <span data-ttu-id="c740d-113">0</span><span class="sxs-lookup"><span data-stu-id="c740d-113">0</span></span>                                                          |
|  <span data-ttu-id="c740d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c740d-114">Message Text</span></span>   | <span data-ttu-id="c740d-115">No se puede crear el enlace de metadatos estándar para el esquema "{0}".</span><span class="sxs-lookup"><span data-stu-id="c740d-115">Cannot create standard metadata binding for scheme "{0}".</span></span> <span data-ttu-id="c740d-116">Los esquemas admitidos son http, https, net.pipe y net.tcp</span><span class="sxs-lookup"><span data-stu-id="c740d-116">Supported schemes are http, https, net.pipe, and net.tcp</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c740d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="c740d-117">Explanation</span></span>  
 <span data-ttu-id="c740d-118">Este error indica que el servicio del que se intenta consumir los metadatos no es un esquema admitido.</span><span class="sxs-lookup"><span data-stu-id="c740d-118">This error indicates the service from which the metadata is trying to be consumed is not a supported scheme.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c740d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c740d-119">User Action</span></span>  
 <span data-ttu-id="c740d-120">Publique los metadatos con un esquema válido y ejecute de nuevo el asistente, en la nueva ubicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c740d-120">Publish the metadata with a valid scheme and then run the wizard again, against the new metadata location.</span></span>  
  
 <span data-ttu-id="c740d-121">Para obtener más información sobre adaptadores y enlaces, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c740d-121">For additional information on adapters and binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="c740d-122">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="c740d-122">WCF Adapters</span></span>](../core/wcf-adapters.md)
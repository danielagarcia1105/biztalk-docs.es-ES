---
title: Errores en los metadatos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262948"
---
# <a name="metadata-errors"></a><span data-ttu-id="183d9-102">Errores de metadatos</span><span class="sxs-lookup"><span data-stu-id="183d9-102">Metadata Errors</span></span>
<span data-ttu-id="183d9-103">Información para diagnosticar y resolver errores en los metadatos de WCF.</span><span class="sxs-lookup"><span data-stu-id="183d9-103">Information for diagnosing and resolving WCF Metadata errors.</span></span>  
  
## <a name="error-consuming-wcf-service-metadata"></a><span data-ttu-id="183d9-104">Error al consumir los metadatos del Servicio WCF</span><span class="sxs-lookup"><span data-stu-id="183d9-104">Error consuming WCF service metadata</span></span>

||<span data-ttu-id="183d9-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="183d9-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="183d9-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="183d9-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="183d9-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="183d9-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="183d9-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="183d9-108">Event ID</span></span>|<span data-ttu-id="183d9-109">0</span><span class="sxs-lookup"><span data-stu-id="183d9-109">0</span></span>|  
|<span data-ttu-id="183d9-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="183d9-110">Event Source</span></span>|<span data-ttu-id="183d9-111">0</span><span class="sxs-lookup"><span data-stu-id="183d9-111">0</span></span>|  
|<span data-ttu-id="183d9-112">Componente</span><span class="sxs-lookup"><span data-stu-id="183d9-112">Component</span></span>|<span data-ttu-id="183d9-113">0</span><span class="sxs-lookup"><span data-stu-id="183d9-113">0</span></span>|  
|<span data-ttu-id="183d9-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="183d9-114">Symbolic Name</span></span>|<span data-ttu-id="183d9-115">0</span><span class="sxs-lookup"><span data-stu-id="183d9-115">0</span></span>|  
|<span data-ttu-id="183d9-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="183d9-116">Message Text</span></span>|<span data-ttu-id="183d9-117">Error al consumir los metadatos del Servicio WCF</span><span class="sxs-lookup"><span data-stu-id="183d9-117">Error consuming WCF service metadata</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="183d9-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="183d9-118">Explanation</span></span>  
 <span data-ttu-id="183d9-119">Este error indica que los metadatos para el servicio no están disponibles o que no son válidos.</span><span class="sxs-lookup"><span data-stu-id="183d9-119">This error indicates the metadata for the service is either not available or is not valid.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="183d9-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="183d9-120">User Action</span></span>  
 <span data-ttu-id="183d9-121">Corrija los metadatos del servicio e intente consumirlo (si es propietario del Servicio WCF que está intentando consumir).</span><span class="sxs-lookup"><span data-stu-id="183d9-121">Correct the service metadata and try to consume (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="183d9-122">Vaya al Editor de configuración de servicio (**svcConfigEditor.exe**) y realizar cambios en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="183d9-122">Go to the Service Configuration Editor (**svcConfigEditor.exe**) and make changes to the configuration file.</span></span>  <span data-ttu-id="183d9-123">En caso contrario, póngase en contacto con el proveedor de servicios</span><span class="sxs-lookup"><span data-stu-id="183d9-123">Otherwise, contact the service provider</span></span>

## <a name="failed-to-get-metadata"></a><span data-ttu-id="183d9-124">Error al obtener metadatos</span><span class="sxs-lookup"><span data-stu-id="183d9-124">Failed to get metadata</span></span>

||<span data-ttu-id="183d9-125">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="183d9-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="183d9-126">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="183d9-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="183d9-127">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="183d9-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="183d9-128">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="183d9-128">Event ID</span></span>|<span data-ttu-id="183d9-129">0</span><span class="sxs-lookup"><span data-stu-id="183d9-129">0</span></span>|  
|<span data-ttu-id="183d9-130">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="183d9-130">Event Source</span></span>|<span data-ttu-id="183d9-131">0</span><span class="sxs-lookup"><span data-stu-id="183d9-131">0</span></span>|  
|<span data-ttu-id="183d9-132">Componente</span><span class="sxs-lookup"><span data-stu-id="183d9-132">Component</span></span>|<span data-ttu-id="183d9-133">0</span><span class="sxs-lookup"><span data-stu-id="183d9-133">0</span></span>|  
|<span data-ttu-id="183d9-134">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="183d9-134">Symbolic Name</span></span>|<span data-ttu-id="183d9-135">0</span><span class="sxs-lookup"><span data-stu-id="183d9-135">0</span></span>|  
|<span data-ttu-id="183d9-136">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="183d9-136">Message Text</span></span>|<span data-ttu-id="183d9-137">Error al obtener metadatos de "{0}.</span><span class="sxs-lookup"><span data-stu-id="183d9-137">Failed to get metadata from "{0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="183d9-138">Explicación</span><span class="sxs-lookup"><span data-stu-id="183d9-138">Explanation</span></span>  
 <span data-ttu-id="183d9-139">Este error indica que los metadatos no están disponibles para el servicio.</span><span class="sxs-lookup"><span data-stu-id="183d9-139">This error indicates the metadata is not available for that service.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="183d9-140">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="183d9-140">User Action</span></span>  
 <span data-ttu-id="183d9-141">Habilite los metadatos para el servicio y vuelva a ejecutar el Asistente para consumición (si es propietario del Servicio WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="183d9-141">Enable metadata for the service and run the consuming wizard again (if you own the WCF service you are trying to consume).</span></span> <span data-ttu-id="183d9-142">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="183d9-142">Otherwise, contact the service provider.</span></span>
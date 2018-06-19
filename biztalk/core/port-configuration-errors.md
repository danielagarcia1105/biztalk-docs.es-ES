---
title: Errores de configuración de puerto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f0e51c06fab9dadb60fc43a003108e50bbb0fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264196"
---
# <a name="port-configuration-errors"></a><span data-ttu-id="5c880-102">Errores de configuración de puerto</span><span class="sxs-lookup"><span data-stu-id="5c880-102">Port Configuration Errors</span></span>
<span data-ttu-id="5c880-103">Información para diagnosticar y resolver errores de configuración de puerto de WCF.</span><span class="sxs-lookup"><span data-stu-id="5c880-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="5c880-104">No se puede combinar la operación debido a un conflicto de patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="5c880-104">Cannot merge operation due to communication pattern conflict</span></span>
  
||<span data-ttu-id="5c880-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="5c880-105">Details</span></span>|  
|-|-|  
|<span data-ttu-id="5c880-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5c880-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5c880-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5c880-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5c880-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5c880-108">Event ID</span></span>|<span data-ttu-id="5c880-109">0</span><span class="sxs-lookup"><span data-stu-id="5c880-109">0</span></span>|  
|<span data-ttu-id="5c880-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5c880-110">Event Source</span></span>|<span data-ttu-id="5c880-111">0</span><span class="sxs-lookup"><span data-stu-id="5c880-111">0</span></span>|  
|<span data-ttu-id="5c880-112">Componente</span><span class="sxs-lookup"><span data-stu-id="5c880-112">Component</span></span>|<span data-ttu-id="5c880-113">0</span><span class="sxs-lookup"><span data-stu-id="5c880-113">0</span></span>|  
|<span data-ttu-id="5c880-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5c880-114">Symbolic Name</span></span>|<span data-ttu-id="5c880-115">0</span><span class="sxs-lookup"><span data-stu-id="5c880-115">0</span></span>|  
|<span data-ttu-id="5c880-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5c880-116">Message Text</span></span>|<span data-ttu-id="5c880-117">No se puede combinar la operación "{0}". Conflicto de patrón de comunicación.</span><span class="sxs-lookup"><span data-stu-id="5c880-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="5c880-118">Todas las operaciones deben ser unidireccionales o de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c880-118">All operations must be one-way or request-response</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="5c880-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="5c880-119">Explanation</span></span>  
 <span data-ttu-id="5c880-120">Este error indica que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta combinar puertos con tipos de puertos que tienen patrones de comunicación diferentes.</span><span class="sxs-lookup"><span data-stu-id="5c880-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="5c880-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5c880-121">User Action</span></span>  
 <span data-ttu-id="5c880-122">Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen la misma dirección de comunicación, unidireccional o de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c880-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="5c880-123">Para obtener más información sobre la configuración del puerto, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c880-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="5c880-124">No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="5c880-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
||<span data-ttu-id="5c880-125">Detalles</span><span class="sxs-lookup"><span data-stu-id="5c880-125">Details</span></span>|  
|-|-|  
|<span data-ttu-id="5c880-126">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5c880-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5c880-127">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5c880-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5c880-128">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5c880-128">Event ID</span></span>|<span data-ttu-id="5c880-129">0</span><span class="sxs-lookup"><span data-stu-id="5c880-129">0</span></span>|  
|<span data-ttu-id="5c880-130">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5c880-130">Event Source</span></span>|<span data-ttu-id="5c880-131">0</span><span class="sxs-lookup"><span data-stu-id="5c880-131">0</span></span>|  
|<span data-ttu-id="5c880-132">Componente</span><span class="sxs-lookup"><span data-stu-id="5c880-132">Component</span></span>|<span data-ttu-id="5c880-133">0</span><span class="sxs-lookup"><span data-stu-id="5c880-133">0</span></span>|  
|<span data-ttu-id="5c880-134">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5c880-134">Symbolic Name</span></span>|<span data-ttu-id="5c880-135">0</span><span class="sxs-lookup"><span data-stu-id="5c880-135">0</span></span>|  
|<span data-ttu-id="5c880-136">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5c880-136">Message Text</span></span>|<span data-ttu-id="5c880-137">No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="5c880-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="5c880-138">Corrija el tipo de puerto de servicio descripción "{0}" "{{1}" y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="5c880-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="5c880-139">Explicación</span><span class="sxs-lookup"><span data-stu-id="5c880-139">Explanation</span></span>  
 <span data-ttu-id="5c880-140">Este error indica que el servicio que se intenta consumir tiene operaciones que son unidireccionales y bidireccionales (solicitud-respuesta).</span><span class="sxs-lookup"><span data-stu-id="5c880-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="5c880-141">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5c880-141">User Action</span></span>  
 <span data-ttu-id="5c880-142">Corrija el servicio con las operaciones adecuadas (unidireccionales o de solicitud-respuesta, pero no ambas) e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="5c880-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="5c880-143">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="5c880-143">Otherwise, contact the service provider.</span></span>

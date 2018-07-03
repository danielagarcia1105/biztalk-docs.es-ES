---
title: Errores de configuración de puerto | Microsoft Docs
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
ms.openlocfilehash: c8cc3c8763115e93387bed5195f234bf4a070b9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986909"
---
# <a name="port-configuration-errors"></a><span data-ttu-id="de9c1-102">Errores de configuración de puerto</span><span class="sxs-lookup"><span data-stu-id="de9c1-102">Port Configuration Errors</span></span>
<span data-ttu-id="de9c1-103">Información para diagnosticar y resolver errores de configuración de puerto de WCF.</span><span class="sxs-lookup"><span data-stu-id="de9c1-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="de9c1-104">No se puede combinar la operación debido a un conflicto de patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="de9c1-104">Cannot merge operation due to communication pattern conflict</span></span>
  
|                 |                                                         <span data-ttu-id="de9c1-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="de9c1-105">Details</span></span>                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="de9c1-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="de9c1-106">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="de9c1-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="de9c1-107">Product Version</span></span> |                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                |
|    <span data-ttu-id="de9c1-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="de9c1-108">Event ID</span></span>     |                                                            <span data-ttu-id="de9c1-109">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-109">0</span></span>                                                            |
|  <span data-ttu-id="de9c1-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="de9c1-110">Event Source</span></span>   |                                                            <span data-ttu-id="de9c1-111">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-111">0</span></span>                                                            |
|    <span data-ttu-id="de9c1-112">Componente</span><span class="sxs-lookup"><span data-stu-id="de9c1-112">Component</span></span>    |                                                            <span data-ttu-id="de9c1-113">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-113">0</span></span>                                                            |
|  <span data-ttu-id="de9c1-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="de9c1-114">Symbolic Name</span></span>  |                                                            <span data-ttu-id="de9c1-115">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-115">0</span></span>                                                            |
|  <span data-ttu-id="de9c1-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="de9c1-116">Message Text</span></span>   | <span data-ttu-id="de9c1-117">No se puede combinar la operación "{0}" debido a un conflicto de patrón de comunicación.</span><span class="sxs-lookup"><span data-stu-id="de9c1-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="de9c1-118">Todas las operaciones deben ser unidireccionales o de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="de9c1-118">All operations must be one-way or request-response</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="de9c1-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="de9c1-119">Explanation</span></span>  
 <span data-ttu-id="de9c1-120">Este error indica que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta combinar puertos con tipos de puertos que tienen patrones de comunicación diferentes.</span><span class="sxs-lookup"><span data-stu-id="de9c1-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="de9c1-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="de9c1-121">User Action</span></span>  
 <span data-ttu-id="de9c1-122">Con el Asistente para configuración de puertos, asegúrese de que todos los puertos que se combinan tienen la misma dirección de comunicación, unidireccional o de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="de9c1-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="de9c1-123">Para obtener más información sobre la configuración de puerto, consulte [cómo ejecutar el Asistente para configuración de puerto](../core/how-to-run-the-port-configuration-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="de9c1-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="de9c1-124">No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="de9c1-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
|                 |                                                                                <span data-ttu-id="de9c1-125">Detalles</span><span class="sxs-lookup"><span data-stu-id="de9c1-125">Details</span></span>                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="de9c1-126">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="de9c1-126">Product Name</span></span>   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="de9c1-127">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="de9c1-127">Product Version</span></span> |                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                       |
|    <span data-ttu-id="de9c1-128">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="de9c1-128">Event ID</span></span>     |                                                                                   <span data-ttu-id="de9c1-129">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-129">0</span></span>                                                                                   |
|  <span data-ttu-id="de9c1-130">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="de9c1-130">Event Source</span></span>   |                                                                                   <span data-ttu-id="de9c1-131">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-131">0</span></span>                                                                                   |
|    <span data-ttu-id="de9c1-132">Componente</span><span class="sxs-lookup"><span data-stu-id="de9c1-132">Component</span></span>    |                                                                                   <span data-ttu-id="de9c1-133">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-133">0</span></span>                                                                                   |
|  <span data-ttu-id="de9c1-134">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="de9c1-134">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="de9c1-135">0</span><span class="sxs-lookup"><span data-stu-id="de9c1-135">0</span></span>                                                                                   |
|  <span data-ttu-id="de9c1-136">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="de9c1-136">Message Text</span></span>   | <span data-ttu-id="de9c1-137">No se permiten los tipos de puertos que tengan una combinación de operaciones unidireccionales y de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="de9c1-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="de9c1-138">Corrija la descripción del servicio "{0}"tipo de puerto"{1}" y vuelva a ejecutar el Asistente</span><span class="sxs-lookup"><span data-stu-id="de9c1-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="de9c1-139">Explicación</span><span class="sxs-lookup"><span data-stu-id="de9c1-139">Explanation</span></span>  
 <span data-ttu-id="de9c1-140">Este error indica que el servicio que se intenta consumir tiene operaciones que son unidireccionales y bidireccionales (solicitud-respuesta).</span><span class="sxs-lookup"><span data-stu-id="de9c1-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="de9c1-141">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="de9c1-141">User Action</span></span>  
 <span data-ttu-id="de9c1-142">Corrija el servicio con las operaciones adecuadas (unidireccionales o de solicitud-respuesta, pero no ambas) e intente consumirlo (si es propietario de los Servicios WCF que intenta consumir).</span><span class="sxs-lookup"><span data-stu-id="de9c1-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="de9c1-143">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="de9c1-143">Otherwise, contact the service provider.</span></span>

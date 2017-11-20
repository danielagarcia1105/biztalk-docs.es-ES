---
title: Enviar errores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67741af0520d990be9a552685c8319aa6a5ae881
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-errors"></a><span data-ttu-id="3b810-102">Enviar errores</span><span class="sxs-lookup"><span data-stu-id="3b810-102">Send Errors</span></span>
<span data-ttu-id="3b810-103">Información para diagnosticar y resolver errores de envío de WCF.</span><span class="sxs-lookup"><span data-stu-id="3b810-103">Information for diagnosing and resolving WCF Send errors.</span></span>  
  
## <a name="failed-to-generate-odx-file"></a><span data-ttu-id="3b810-104">No se pudo generar el archivo ODX.</span><span class="sxs-lookup"><span data-stu-id="3b810-104">Failed to generate ODX file</span></span>

||<span data-ttu-id="3b810-105">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="3b810-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="3b810-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3b810-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3b810-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3b810-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="3b810-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3b810-108">Event ID</span></span>|<span data-ttu-id="3b810-109">0</span><span class="sxs-lookup"><span data-stu-id="3b810-109">0</span></span>|  
|<span data-ttu-id="3b810-110">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3b810-110">Event Source</span></span>|<span data-ttu-id="3b810-111">0</span><span class="sxs-lookup"><span data-stu-id="3b810-111">0</span></span>|  
|<span data-ttu-id="3b810-112">Componente</span><span class="sxs-lookup"><span data-stu-id="3b810-112">Component</span></span>|<span data-ttu-id="3b810-113">0</span><span class="sxs-lookup"><span data-stu-id="3b810-113">0</span></span>|  
|<span data-ttu-id="3b810-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b810-114">Symbolic Name</span></span>|<span data-ttu-id="3b810-115">0</span><span class="sxs-lookup"><span data-stu-id="3b810-115">0</span></span>|  
|<span data-ttu-id="3b810-116">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b810-116">Message Text</span></span>|<span data-ttu-id="3b810-117">No se pudo generar el archivo ODX.</span><span class="sxs-lookup"><span data-stu-id="3b810-117">Failed to generate ODX file</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="3b810-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b810-118">Explanation</span></span>  
 <span data-ttu-id="3b810-119">Este error indica que hay un error al consumir el servicio.</span><span class="sxs-lookup"><span data-stu-id="3b810-119">This error indicates there was an error in consuming the service.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="3b810-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b810-120">User Action</span></span>  
 <span data-ttu-id="3b810-121">Compruebe que el servicio tenga un método web válido y que estén hospedados los metadatos (si es propietario de los Servicios WCF).</span><span class="sxs-lookup"><span data-stu-id="3b810-121">Check that the service has valid Web Method and that metadata is hosted (if you own the WCF services).</span></span> <span data-ttu-id="3b810-122">En caso contrario, póngase en contacto con el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="3b810-122">Otherwise, contact the service provider.</span></span>  
  
 <span data-ttu-id="3b810-123">Para obtener información adicional sobre el consumo de servicios WCF, vea [consideraciones al consumir servicios WCF con los adaptadores de envío de WCF](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="3b810-123">For additional information on consuming WCF services, see [Considerations When Consuming WCF Services with the WCF Send Adapters](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md).</span></span>
 
## <a name="response-message-body-was-not-read"></a><span data-ttu-id="3b810-124">No se puede leer el cuerpo del mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="3b810-124">Response message body was not read</span></span>
  
||<span data-ttu-id="3b810-125">Detalles del error</span><span class="sxs-lookup"><span data-stu-id="3b810-125">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="3b810-126">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3b810-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3b810-127">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3b810-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="3b810-128">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3b810-128">Event ID</span></span>|<span data-ttu-id="3b810-129">0</span><span class="sxs-lookup"><span data-stu-id="3b810-129">0</span></span>|  
|<span data-ttu-id="3b810-130">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3b810-130">Event Source</span></span>|<span data-ttu-id="3b810-131">0</span><span class="sxs-lookup"><span data-stu-id="3b810-131">0</span></span>|  
|<span data-ttu-id="3b810-132">Componente</span><span class="sxs-lookup"><span data-stu-id="3b810-132">Component</span></span>|<span data-ttu-id="3b810-133">0</span><span class="sxs-lookup"><span data-stu-id="3b810-133">0</span></span>|  
|<span data-ttu-id="3b810-134">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b810-134">Symbolic Name</span></span>|<span data-ttu-id="3b810-135">0</span><span class="sxs-lookup"><span data-stu-id="3b810-135">0</span></span>|  
|<span data-ttu-id="3b810-136">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b810-136">Message Text</span></span>|<span data-ttu-id="3b810-137">No se pudo leer el cuerpo del mensaje de respuesta. (Esto puede indicar el cierre de la conexión.)</span><span class="sxs-lookup"><span data-stu-id="3b810-137">The response message body was not read  (This may indicate the connection has been closed.)</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="3b810-138">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b810-138">Explanation</span></span>  
 <span data-ttu-id="3b810-139">Es posible que el cliente se haya desconectado antes de que se haya devuelto el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3b810-139">The client may be disconnected before the response message is sent back.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="3b810-140">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b810-140">User Action</span></span>  
 <span data-ttu-id="3b810-141">Compurebe la conectividad del cliente.</span><span class="sxs-lookup"><span data-stu-id="3b810-141">Check the client connectivity.</span></span> <span data-ttu-id="3b810-142">Los pasos tomados y la extensión de la acción dependerán del tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="3b810-142">The steps taken, and the extent of the action, will depend on the port type.</span></span>   
<span data-ttu-id="3b810-143">Para obtener más información, consulte [herramientas y utilidades que se usan para la solución de problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="3b810-143">For further information, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>
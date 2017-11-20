---
title: "Ubicaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9866edd5dfa6f953c4e847f191891bd7e6bc25ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-locations"></a><span data-ttu-id="cf3b1-102">Ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="cf3b1-102">Receive Locations</span></span>
<span data-ttu-id="cf3b1-103">La creación de una ubicación de recepción conlleva especificar la dirección a la que llegan los mensajes de entrada, además de la canalización de mensajería que procesa los mensajes recibidos en dicha dirección.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-103">Creating a receive location involves specifying an address at which inbound messages arrive and the messaging pipeline that processes the message received at that address.</span></span> <span data-ttu-id="cf3b1-104">Solo los administradores pueden crear y habilitar las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-104">Only administrators can create and enable receive locations.</span></span>  
  
 <span data-ttu-id="cf3b1-105">Un administrador usa la consola de administración de BizTalk para crear ubicaciones de recepción, enlazar ubicaciones de recepción con orquestaciones, habilitar ubicaciones de recepción, deshabilitar ubicaciones de recepción y establecer propiedades globales para las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-105">An administrator uses the BizTalk Administration Console to create receive locations, bind receive locations to orchestrations, enable receive locations, disable receive locations, and set global properties for receive locations.</span></span>  
  
 <span data-ttu-id="cf3b1-106">Un administrador (que usa la consola de administración de BizTalk) sigue estos pasos para crear una ubicación de recepción:</span><span class="sxs-lookup"><span data-stu-id="cf3b1-106">An administrator (using the BizTalk Administration Console) follows these steps to create a receive location:</span></span>  
  
1.  <span data-ttu-id="cf3b1-107">Crea una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-107">Creates a receive location.</span></span>  
  
2.  <span data-ttu-id="cf3b1-108">Asocia la ubicación de recepción con un host.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-108">Associates the receive location with a host.</span></span>  
  
3.  <span data-ttu-id="cf3b1-109">Enlaza la ubicación de recepción con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-109">Binds the receive location to an orchestration.</span></span>  
  
4.  <span data-ttu-id="cf3b1-110">Habilita la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-110">Enables the receive location.</span></span>  
  
5.  <span data-ttu-id="cf3b1-111">La ubicación de recepción recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-111">The receive location receives messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf3b1-112">Los cambios en las ubicaciones de recepción realizadas con el Instrumental de administración de Windows (WMI) afectan a cómo aparecen las ubicaciones de recepción en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-112">Changes to receive locations made by using Windows Management Instrumentation (WMI) affect how receive locations appear in the BizTalk Administration Console.</span></span> <span data-ttu-id="cf3b1-113">Por ejemplo, si un administrador usa WMI para crear una nueva ubicación de recepción, esa ubicación de recepción aparece en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-113">For example, if an administrator uses WMI to create a new receive location, that receive location appears in the BizTalk Administration Console.</span></span> <span data-ttu-id="cf3b1-114">De forma similar, si un administrador elimina una ubicación de recepción, la ubicación de recepción desaparece de la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-114">Similarly, if an administrator deletes a receive location, the receive location disappears from the BizTalk Administration Console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf3b1-115">Cada ubicación de recepción debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-115">Each receive location must have a unique name.</span></span> <span data-ttu-id="cf3b1-116">Dos ubicaciones de recepción no puede tener el mismo nombre en la misma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]implementación.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-116">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf3b1-117">Se recomienda establecer listas de control de acceso (ACL) seguras en la ubicación de destino de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-117">We recommend that you set strong access control lists (ACL) in the drop location for the receive locations.</span></span> <span data-ttu-id="cf3b1-118">Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-118">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="receive-location-types"></a><span data-ttu-id="cf3b1-119">Tipos de ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="cf3b1-119">Receive Location Types</span></span>  
 <span data-ttu-id="cf3b1-120">Hay dos tipos de ubicaciones de recepción:</span><span class="sxs-lookup"><span data-stu-id="cf3b1-120">There are two types of receive locations</span></span>  
  
-   <span data-ttu-id="cf3b1-121">Unidireccional:</span><span class="sxs-lookup"><span data-stu-id="cf3b1-121">One-way.</span></span> <span data-ttu-id="cf3b1-122">se utiliza para las aplicaciones que entregan un mensaje sin esperar una respuesta sincrónica.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-122">Used for applications that drop off a message and do not wait for a synchronous reply.</span></span>  
  
-   <span data-ttu-id="cf3b1-123">Solicitud-respuesta:</span><span class="sxs-lookup"><span data-stu-id="cf3b1-123">Request-response.</span></span> <span data-ttu-id="cf3b1-124">se utiliza con las aplicaciones que requieren una respuesta a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-124">Used with applications that require a response to a message.</span></span>  
  
## <a name="receive-location-properties"></a><span data-ttu-id="cf3b1-125">Propiedades de la ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="cf3b1-125">Receive Location Properties</span></span>  
 <span data-ttu-id="cf3b1-126">Las ubicaciones de recepción tienen propiedades globales y propiedades específicas del adaptador.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-126">Receive locations have global and adapter-specific properties.</span></span> <span data-ttu-id="cf3b1-127">Los administradores, mediante la consola de administración de BizTalk, establecer propiedades globales para todas las ubicaciones de recepción asociadas a un adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-127">Administrators, using the BizTalk Administration Console, set global properties for all of the receive locations associated with a specific adapter.</span></span>  
  
 <span data-ttu-id="cf3b1-128">Los cambios en las propiedades de una ubicación de recepción se producen de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-128">Changes to receive location properties happen sequentially.</span></span> <span data-ttu-id="cf3b1-129">Si un programador de soluciones modifica un valor de propiedad para una determinada ubicación de recepción, las invalidaciones de valor de propiedad nuevo el valor de propiedad global para esa ubicación de recepción que el administrador haya establecido en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cf3b1-129">If a solutions developer modifies a property value for a specific receive location, the new property value overrides the global property value for that receive location that the administrator set in the BizTalk Administration Console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3b1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf3b1-130">See Also</span></span>  
 <span data-ttu-id="cf3b1-131">[Administrar ubicaciones de recepción](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="cf3b1-131">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="cf3b1-132">Artefactos</span><span class="sxs-lookup"><span data-stu-id="cf3b1-132">Artifacts</span></span>](../core/artifacts.md)
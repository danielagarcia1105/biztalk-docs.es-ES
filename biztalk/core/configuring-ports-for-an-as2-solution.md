---
title: "Configurar puertos para una solución AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-ports-for-an-as2-solution"></a><span data-ttu-id="5dcbd-102">Configurar puertos para una solución AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-102">Configuring Ports for an AS2 Solution</span></span>
<span data-ttu-id="5dcbd-103">Puede usar los siguientes puertos de recepción y envío para transmitir mensajes EDI y no pertenecientes a EDI a través de AS2:</span><span class="sxs-lookup"><span data-stu-id="5dcbd-103">You can use the following receive and send ports to transmit EDI and non-EDI messages over AS2:</span></span>  
  
 <span data-ttu-id="5dcbd-104">**Puertos de recepción**</span><span class="sxs-lookup"><span data-stu-id="5dcbd-104">**Receive Ports**</span></span>  
  
|<span data-ttu-id="5dcbd-105">Para recibir</span><span class="sxs-lookup"><span data-stu-id="5dcbd-105">To Receive</span></span>|<span data-ttu-id="5dcbd-106">Para enviar</span><span class="sxs-lookup"><span data-stu-id="5dcbd-106">To Send</span></span>|<span data-ttu-id="5dcbd-107">Tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="5dcbd-107">Type of Port</span></span>|  
|----------------|-------------|------------------|  
|<span data-ttu-id="5dcbd-108">Un mensaje o confirmación EDI o no perteneciente a EDI</span><span class="sxs-lookup"><span data-stu-id="5dcbd-108">An EDI or non-EDI message or acknowledgment</span></span>|<span data-ttu-id="5dcbd-109">Una respuesta MDN (si se encuentra en modo sincrónico) o una respuesta HTTP (si se encuentra en modo asíncrono)</span><span class="sxs-lookup"><span data-stu-id="5dcbd-109">An MDN response (if in synchronous mode) or an HTTP response (if in asynchronous mode)</span></span>|<span data-ttu-id="5dcbd-110">Puerto de recepción HTTP de solicitud-respuesta bidireccional</span><span class="sxs-lookup"><span data-stu-id="5dcbd-110">Two-way request-response HTTP receive port</span></span>|  
|<span data-ttu-id="5dcbd-111">Una respuesta MDN</span><span class="sxs-lookup"><span data-stu-id="5dcbd-111">An MDN response</span></span>|-|<span data-ttu-id="5dcbd-112">Puerto de recepción HTTP unidireccional</span><span class="sxs-lookup"><span data-stu-id="5dcbd-112">One-way HTTP receive port</span></span>|  
  
 <span data-ttu-id="5dcbd-113">**Puertos de envío**</span><span class="sxs-lookup"><span data-stu-id="5dcbd-113">**Send Ports**</span></span>  
  
|<span data-ttu-id="5dcbd-114">Para enviar</span><span class="sxs-lookup"><span data-stu-id="5dcbd-114">To Send</span></span>|<span data-ttu-id="5dcbd-115">Para recibir</span><span class="sxs-lookup"><span data-stu-id="5dcbd-115">To Receive</span></span>|<span data-ttu-id="5dcbd-116">Tipo de puerto</span><span class="sxs-lookup"><span data-stu-id="5dcbd-116">Type of Port</span></span>|  
|-------------|----------------|------------------|  
|<span data-ttu-id="5dcbd-117">Un mensaje o confirmación EDI o no perteneciente a EDI</span><span class="sxs-lookup"><span data-stu-id="5dcbd-117">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="5dcbd-118">(enrutamiento basado en acuerdo)</span><span class="sxs-lookup"><span data-stu-id="5dcbd-118">(agreement-based routing)</span></span>|-|<span data-ttu-id="5dcbd-119">Puerto de envío HTTP unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="5dcbd-119">Static one-way HTTP send port</span></span>|  
|<span data-ttu-id="5dcbd-120">Un mensaje o confirmación EDI o no perteneciente a EDI</span><span class="sxs-lookup"><span data-stu-id="5dcbd-120">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="5dcbd-121">(enrutamiento por contenidos)</span><span class="sxs-lookup"><span data-stu-id="5dcbd-121">(content-based routing)</span></span>|<span data-ttu-id="5dcbd-122">Una respuesta MDN</span><span class="sxs-lookup"><span data-stu-id="5dcbd-122">An MDN response</span></span>|<span data-ttu-id="5dcbd-123">Puerto de envío HTTP de petición-respuesta bidireccional dinámico</span><span class="sxs-lookup"><span data-stu-id="5dcbd-123">Dynamic two-way solicit-response HTTP send port</span></span>|  
|<span data-ttu-id="5dcbd-124">Un mensaje o confirmación EDI o no perteneciente a EDI</span><span class="sxs-lookup"><span data-stu-id="5dcbd-124">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="5dcbd-125">(enrutamiento por contenidos)</span><span class="sxs-lookup"><span data-stu-id="5dcbd-125">(content-based routing)</span></span>|-|<span data-ttu-id="5dcbd-126">Puerto de envío HTTP unidireccional dinámico</span><span class="sxs-lookup"><span data-stu-id="5dcbd-126">Dynamic one-way HTTP send port</span></span>|  
|<span data-ttu-id="5dcbd-127">Una respuesta MDN asíncrona</span><span class="sxs-lookup"><span data-stu-id="5dcbd-127">An asynchronous MDN response</span></span><br /><br /> <span data-ttu-id="5dcbd-128">(enrutamiento por contenidos)</span><span class="sxs-lookup"><span data-stu-id="5dcbd-128">(content-based routing)</span></span>|-|<span data-ttu-id="5dcbd-129">Puerto de envío unidireccional dinámico</span><span class="sxs-lookup"><span data-stu-id="5dcbd-129">Dynamic one-way send port</span></span>|  
|<span data-ttu-id="5dcbd-130">Una respuesta MDN asíncrona</span><span class="sxs-lookup"><span data-stu-id="5dcbd-130">An asynchronous MDN response</span></span>|-|<span data-ttu-id="5dcbd-131">Puerto de envío unidireccional estático</span><span class="sxs-lookup"><span data-stu-id="5dcbd-131">Static one-way send port</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="5dcbd-132">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5dcbd-132">In This Section</span></span>  
  
-   [<span data-ttu-id="5dcbd-133">Configurar un puerto de recepción de mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-133">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="5dcbd-134">Configurar un puerto de recepción para MDN entrantes</span><span class="sxs-lookup"><span data-stu-id="5dcbd-134">Configuring a Receive Port for Incoming MDNs</span></span>](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [<span data-ttu-id="5dcbd-135">Configurar un puerto de envío estático para mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-135">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="5dcbd-136">Configurar un puerto de envío dinámico para mensajes a través de AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-136">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="5dcbd-137">Configurar un puerto de envío estático para MDN asíncronos a través de AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-137">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [<span data-ttu-id="5dcbd-138">Configurar un puerto de envío dinámico para MDN asíncronos a través de AS2</span><span class="sxs-lookup"><span data-stu-id="5dcbd-138">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="5dcbd-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dcbd-139">See Also</span></span>  
 [<span data-ttu-id="5dcbd-140">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5dcbd-140">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
---
title: Optimizar el rendimiento del adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5624eb6cf88f45d1ecad0b68fee3f5f7b8a8ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007341"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a><span data-ttu-id="23994-102">Optimizar el rendimiento del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="23994-102">Optimizing Performance of the MSMQ Adapter</span></span>
<span data-ttu-id="23994-103">La optimización del adaptador de MSMQ no es la misma para envío y para recepción.</span><span class="sxs-lookup"><span data-stu-id="23994-103">Optimization of the MSMQ adapter differs between the send and receive sides.</span></span> <span data-ttu-id="23994-104">Para la recepción, la optimización se controla definiendo una propiedad en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="23994-104">You control optimization on the receive side by setting a property on the receive location.</span></span> <span data-ttu-id="23994-105">Para el envío, la optimización puede controlarse mediante una orquestación.</span><span class="sxs-lookup"><span data-stu-id="23994-105">On the send side, you can control optimization by using an orchestration.</span></span>  
  
## <a name="receive-optimization"></a><span data-ttu-id="23994-106">Optimización de recepción</span><span class="sxs-lookup"><span data-stu-id="23994-106">Receive Optimization</span></span>  
 <span data-ttu-id="23994-107">En el caso de la recepción, el adaptador puede utilizar un único subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="23994-107">On the receive side, you can have the adapter use a single execution thread.</span></span> <span data-ttu-id="23994-108">Si el adaptador utiliza un único subproceso o varios subprocesos depende del valor de la **procesamiento ordenado** propiedad en la ubicación de recepción, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="23994-108">Whether the adapter uses a single thread or multiple threads depends on the setting of the **Ordered Processing** property on the receive location, as follows:</span></span>  
  
-   <span data-ttu-id="23994-109">Cuando la propiedad es **True**, el adaptador funciona en un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="23994-109">When the property is **True**, the adapter operates on a single thread.</span></span> <span data-ttu-id="23994-110">Esto limita el adaptador a un solo mensaje a la vez y permite ahorrar memoria.</span><span class="sxs-lookup"><span data-stu-id="23994-110">This limits the adapter to one message at a time and conserves memory.</span></span> <span data-ttu-id="23994-111">Tenga en cuenta que este procedimiento define **tamaño de lote** a uno (1), independientemente del valor asignado a él en la hoja de propiedades.</span><span class="sxs-lookup"><span data-stu-id="23994-111">Notice that this effectively sets **Batch Size** to one (1), regardless of the value assigned to it in the property sheet.</span></span>  
  
-   <span data-ttu-id="23994-112">Cuando **procesamiento ordenado** es **False**, el adaptador ejecuta varios subprocesos y puede procesar varios mensajes a la vez, incrementando así el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="23994-112">When **Ordered Processing** is **False**, the adapter runs multiple threads and can process multiple messages at a time, therefore increasing performance.</span></span>  
  
 <span data-ttu-id="23994-113">Debe establecer **procesamiento ordenado** a **True** si desea limitar sobre la administración de recursos del servidor, o si el número o el tamaño de los mensajes pudiese agotar la memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="23994-113">You must set **Ordered Processing** to **True** if you put a premium on managing server resources, or if the number or size of messages might exhaust available memory.</span></span>  
  
 <span data-ttu-id="23994-114">También puede controlar el uso de memoria si reduce el valor de **tamaño de lote** en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="23994-114">You can also control memory use by reducing the value of **Batch Size** on the receive location.</span></span> <span data-ttu-id="23994-115">Cuanto más pequeño sea el tamaño del lote, menor número de mensajes se guardará en memoria, lo que implica un menor consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="23994-115">A smaller batch size keeps fewer messages in memory and therefore uses less memory.</span></span>  
  
 <span data-ttu-id="23994-116">La colocación de los puertos de envío y de las ubicaciones de recepción en equipos distintos también permite reducir el consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="23994-116">Placing send ports and receive locations on separate computers can also reduce memory use.</span></span>  
  
## <a name="send-optimization"></a><span data-ttu-id="23994-117">Optimización de envío</span><span class="sxs-lookup"><span data-stu-id="23994-117">Send Optimization</span></span>  
 <span data-ttu-id="23994-118">En el caso de los envíos, el procesamiento de un solo mensaje se consigue utilizando la orquestación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="23994-118">On the send side, you can achieve the equivalent single-message processing by using the sample orchestration.</span></span> <span data-ttu-id="23994-119">La orquestación de ejemplo envía un solo mensaje y espera a recibir la confirmación para enviar el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="23994-119">The sample sends a single message and then waits to send the next message until it receives an acknowledgment.</span></span> <span data-ttu-id="23994-120">Para obtener más información, consulte [cómo crear ubicaciones de recepción de MSMQ y puertos de envío desde el código](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span><span class="sxs-lookup"><span data-stu-id="23994-120">For more information, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="remote-transactional-read-operations"></a><span data-ttu-id="23994-121">Operaciones de lectura transaccionales remotas</span><span class="sxs-lookup"><span data-stu-id="23994-121">Remote Transactional Read Operations</span></span>  
 <span data-ttu-id="23994-122">Con BizTalk Server el MSMQ para el adaptador es capaz de realizar operaciones de lectura remotas desde colas MSMQ transaccionales.</span><span class="sxs-lookup"><span data-stu-id="23994-122">With BizTalk Server the MSMQ adapter is capable of making remote read operations from transactional MSMQ queues.</span></span>  <span data-ttu-id="23994-123">Esto se debe a que MSMQ 4.0 y las versiones posteriores admiten operaciones de lectura remotas transaccionales.</span><span class="sxs-lookup"><span data-stu-id="23994-123">This is because MSMQ 4.0 and later versions support remote transactional read operations.</span></span>  <span data-ttu-id="23994-124">Sin embargo, las operaciones de lectura transaccionales suelen ser operaciones lentas.</span><span class="sxs-lookup"><span data-stu-id="23994-124">However, transactional read operations are typically slow operations.</span></span> <span data-ttu-id="23994-125">Para optimizar el rendimiento, se deben usar únicamente cuando no hay ninguna otra opción.</span><span class="sxs-lookup"><span data-stu-id="23994-125">To optimize performance they should be used only when there is no other option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23994-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="23994-126">See Also</span></span>  
 <span data-ttu-id="23994-127">[Cómo configurar ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="23994-127">[How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) </span></span>  
 <span data-ttu-id="23994-128">[Cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="23994-128">[How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) </span></span>  
 [<span data-ttu-id="23994-129">Configuración del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="23994-129">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)
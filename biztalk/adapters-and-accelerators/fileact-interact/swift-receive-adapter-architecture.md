---
title: "Arquitectura del adaptador de recepción de SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-architecture"></a><span data-ttu-id="45d14-102">Arquitectura del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-102">SWIFT Receive Adapter Architecture</span></span>
<span data-ttu-id="45d14-103">En BizTalk Server, el adaptador de recepción se hospeda dentro de su propio espacio de memoria, lo que significa que se crea un proceso independiente para ejecutar el host.</span><span class="sxs-lookup"><span data-stu-id="45d14-103">In BizTalk Server, the receive adapter is hosted within its own memory space, which means a separate process is created to run the host.</span></span> <span data-ttu-id="45d14-104">Este host se genera mediante la definición de un subsistema en la configuración de vínculo SWIFTNet (SNL).</span><span class="sxs-lookup"><span data-stu-id="45d14-104">This host is spawned by defining a subsystem in the SWIFTNet Link (SNL) configuration.</span></span>  
  
 <span data-ttu-id="45d14-105">El ejecutable del servidor se configura como un subsistema en la configuración de SNL (paramfile) y se genera al ejecutar el comando de inicio de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="45d14-105">The server executable is configured as a subsystem in the SNL configuration (paramfile) and is spawned by executing the SWIFTNet Start command.</span></span> <span data-ttu-id="45d14-106">Finaliza la aplicación de SNL server ejecutando el comando de detención de SWIFTNet.</span><span class="sxs-lookup"><span data-stu-id="45d14-106">The SNL server application is terminated by executing the SWIFTNet Stop command.</span></span> <span data-ttu-id="45d14-107">SNL administra la duración del ejecutable del servidor.</span><span class="sxs-lookup"><span data-stu-id="45d14-107">SNL manages the lifetime of the server executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45d14-108">El escenario de oficina de servicio requiere que el adaptador para varios miembros SWIFT que se ejecuta en su propio contexto de seguridad del servicio.</span><span class="sxs-lookup"><span data-stu-id="45d14-108">The service bureau scenario requires the adapter to service multiple SWIFT members running under their own security contexts.</span></span> <span data-ttu-id="45d14-109">Esto puede admitirse mediante la configuración de un individuo ubicación por cada miembro y la creación de varias instancias del ejecutable del servidor de recepción, cada una de ellas dedicada a una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="45d14-109">This can be supported by configuring an individual receive location per member and spawning multiple instances of the server executable — each one dedicated to one receive location.</span></span>  
  
 <span data-ttu-id="45d14-110">En BizTalk Server, el adaptador de recepción admite los siguientes patrones de comunicación para interactuar con el motor de mensajería de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="45d14-110">In BizTalk Server, the receive adapter supports the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="45d14-111">Unidireccional: este modo es necesario cuando el adaptador de recepción (servidor) está funcionando en modo diferido.</span><span class="sxs-lookup"><span data-stu-id="45d14-111">One way — this mode is required when the receive adapter (server) is operating in deferred mode.</span></span> <span data-ttu-id="45d14-112">En el modo diferido, el adaptador envía una confirmación de forma predeterminada para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="45d14-112">In deferred mode, the adapter sends a default acknowledgment for incoming messages.</span></span> <span data-ttu-id="45d14-113">Los valores predeterminados para la confirmación pueden configurarse en las propiedades del adaptador.</span><span class="sxs-lookup"><span data-stu-id="45d14-113">The default values for the acknowledgment can be configured in the adapter properties.</span></span> <span data-ttu-id="45d14-114">Respuesta de nivel de negocio puede enviarse más tarde por la aplicación de LOB a través del adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="45d14-114">Business level response can be sent later by the LOB application through the send adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45d14-115">En el caso de modo diferido, todos los valores deben llenar en la configuración del adaptador, ya que el adaptador es la construcción de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="45d14-115">In case of deferred mode, all values must be filled up in the adapter configuration, since the adapter is constructing the response.</span></span>  
  
-   <span data-ttu-id="45d14-116">Solicitud-respuesta: en este modo, el adaptador envía la solicitud de SWIFT de BizTalk y espera respuesta.</span><span class="sxs-lookup"><span data-stu-id="45d14-116">Request response — in this mode the adapter submits the request from SWIFT to BizTalk and waits for response.</span></span> <span data-ttu-id="45d14-117">El adaptador de contar con tiempo de espera si no hay ninguna respuesta de la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="45d14-117">The adapter would timeout if there is no response from the LOB application.</span></span> <span data-ttu-id="45d14-118">El valor de tiempo de espera es configurable en configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="45d14-118">The time out value is configurable in adapter configuration.</span></span> <span data-ttu-id="45d14-119">El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="45d14-119">The default value is 60 seconds.</span></span>  
  
     <span data-ttu-id="45d14-120">El adaptador de recepción puede recibir la devolución de llamada de SNL solo en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="45d14-120">The receive adapter can receive the callback from SNL only on one thread.</span></span> <span data-ttu-id="45d14-121">Esto significa que el adaptador de recepción puede recibir más mensajes de SNL solo después de enviar el primer mensaje.</span><span class="sxs-lookup"><span data-stu-id="45d14-121">This means that the receive adapter can receive further messages from SNL only after submitting the first message.</span></span> <span data-ttu-id="45d14-122">Por lo tanto, el tamaño del lote de forma predeterminada se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="45d14-122">Therefore, the default batch size is set to 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45d14-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="45d14-123">In This Section</span></span>  
  
-   [<span data-ttu-id="45d14-124">URI del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-124">SWIFT Receive Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [<span data-ttu-id="45d14-125">La inicialización del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-125">SWIFT Receive Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [<span data-ttu-id="45d14-126">Contexto de seguridad del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-126">SWIFT Receive Adapter Security Context</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [<span data-ttu-id="45d14-127">Modos sincrónico y diferido del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-127">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [<span data-ttu-id="45d14-128">Adaptador de almacenamiento y reenvío de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="45d14-128">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)
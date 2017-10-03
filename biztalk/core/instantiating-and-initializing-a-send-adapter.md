---
title: "Crear instancias e inicializar un adaptador de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f10e6507-3351-4173-95f5-48546ca5f5c4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ed590b73d31a03a4b3316a4d84edfc1e39eb0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-and-initializing-a-send-adapter"></a><span data-ttu-id="ac927-102">Crear instancias e inicializar un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="ac927-102">Instantiating and Initializing a Send Adapter</span></span>
<span data-ttu-id="ac927-103">De forma predeterminada, no se crea ninguna instancia de los adaptadores de envío hasta que se les entrega el primer mensaje. A este proceso se le denomina "creación diferida".</span><span class="sxs-lookup"><span data-stu-id="ac927-103">By default, send adapters are not instantiated until the first message is delivered to them, a process known as "lazy creation."</span></span> <span data-ttu-id="ac927-104">El método predeterminado de creación diferida es útil para conservar los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ac927-104">The default lazy creation approach helps to conserve system resources.</span></span> <span data-ttu-id="ac927-105">El adaptador de envío, una vez creado, se almacena en caché y está activo hasta que se detiene el servicio de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ac927-105">After the send adapter is created, it is cached and lives until the BizTalk Server service is stopped.</span></span>  
  
 <span data-ttu-id="ac927-106">El **InitTransmitterOnServiceStart** miembro de la **capacidades** enumeración indica al motor de mensajería para crear el adaptador de envío en el inicio del servicio, en lugar de utilizar la creación diferida predeterminada, Si se desea esto.</span><span class="sxs-lookup"><span data-stu-id="ac927-106">The **InitTransmitterOnServiceStart** member of the **Capabilities** enumeration directs the Messaging Engine to create the send adapter on service startup, rather than using the default lazy creation, if this is desired.</span></span>  
  
 <span data-ttu-id="ac927-107">El modelo de enviar un mensaje es diferente del de recibir un mensaje en cuanto al procesamiento por lotes de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ac927-107">Sending a message is a different model than receiving a message with respect to batching of messages.</span></span> <span data-ttu-id="ac927-108">En el caso de la recepción, el adaptador tiene mensajes entrantes que insertar en un lote obtenido del motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="ac927-108">In the receive case the adapter has incoming messages to insert into a batch obtained from the Messaging Engine.</span></span> <span data-ttu-id="ac927-109">En el caso del envío, el motor de mensajería obtiene un lote del adaptador y envía mensajes al adaptador para que se transmitan.</span><span class="sxs-lookup"><span data-stu-id="ac927-109">In the send case the Messaging Engine obtains a batch from the adapter and sends messages to the adapter to be transmitted.</span></span> <span data-ttu-id="ac927-110">En ambos casos, se usa el proxy de transporte para obtener los objetos de lote de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ac927-110">Both use the transport proxy to obtain the message batch objects.</span></span>  
  
## <a name="how-a-send-adapter-is-initialized"></a><span data-ttu-id="ac927-111">Cómo se inicializa un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="ac927-111">How a Send Adapter Is Initialized</span></span>  
 <span data-ttu-id="ac927-112">Para habilitar la configuración y el enlace al proxy de transporte, los adaptadores deben implementar las interfaces de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac927-112">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
-   <span data-ttu-id="ac927-113">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="ac927-113">**IBTTransport**</span></span>  
  
-   <span data-ttu-id="ac927-114">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="ac927-114">**IBaseComponent**</span></span>  
  
-   <span data-ttu-id="ac927-115">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="ac927-115">**IBTTransportControl**</span></span>  
  
-   <span data-ttu-id="ac927-116">**IPersistPropertyBag**</span><span class="sxs-lookup"><span data-stu-id="ac927-116">**IPersistPropertyBag**</span></span>  
  
 <span data-ttu-id="ac927-117">Los pasos siguientes describen la secuencia de eventos que conlleva la inicialización de un adaptador de envío:</span><span class="sxs-lookup"><span data-stu-id="ac927-117">The following steps describe the sequence of events involved in initializing a send adapter:</span></span>  
  
1.  <span data-ttu-id="ac927-118">Cuando el motor de mensajería Inicializa un adaptador de envío, en primer lugar realiza un **QueryInterface** para **IPersistPropertyBag**, que es una interfaz opcional.</span><span class="sxs-lookup"><span data-stu-id="ac927-118">When the Messaging Engine initializes a send adapter, it first performs a **QueryInterface** for **IPersistPropertyBag**, which is an optional interface.</span></span> <span data-ttu-id="ac927-119">Si el adaptador implementa la interfaz, la configuración del controlador se pasa al adaptador en la **carga** llamada al método.</span><span class="sxs-lookup"><span data-stu-id="ac927-119">If the adapter implements the interface, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="ac927-120">El adaptador usa esta información para asegurarse de que está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac927-120">The adapter uses this information to ensure it is configured correctly.</span></span>  
  
2.  <span data-ttu-id="ac927-121">El motor de mensajería realiza una **QueryInterface** para **IBTTransportControl**, que es una interfaz obligatoria.</span><span class="sxs-lookup"><span data-stu-id="ac927-121">The Messaging Engine performs a **QueryInterface** for **IBTTransportControl**, which is a mandatory interface.</span></span>  
  
3.  <span data-ttu-id="ac927-122">El motor llama **IBTTransportControl.Initialize**, pasando el proxy de transporte para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac927-122">The engine calls **IBTTransportControl.Initialize**, passing in the transport proxy for the adapter.</span></span>  
  
4.  <span data-ttu-id="ac927-123">El motor de mensajería realiza una **QueryInterface** para **IBTTransmitter**.</span><span class="sxs-lookup"><span data-stu-id="ac927-123">The Messaging Engine performs a **QueryInterface** for **IBTTransmitter**.</span></span>  
  
     <span data-ttu-id="ac927-124">Si el motor de mensajería detecta esta interfaz, el adaptador se considera como un transmisor no compatible con lotes.</span><span class="sxs-lookup"><span data-stu-id="ac927-124">If the Messaging Engine discovers this interface, the adapter is treated as a batch-unaware transmitter.</span></span>  
  
     <span data-ttu-id="ac927-125">Si el motor de mensajería no detecta esta interfaz, el motor de mensajería realiza una **QueryInterface** para **IBTBatchTransmitter**, detección de los cuales indica que el adaptador es un compatibles con lotes mando a distancia.</span><span class="sxs-lookup"><span data-stu-id="ac927-125">If the Messaging Engine does not discover this interface, the Messaging Engine performs a **QueryInterface** for **IBTBatchTransmitter**, discovery of which indicates that the adapter is a batch-aware transmitter.</span></span>  
  
     <span data-ttu-id="ac927-126">Si el motor de mensajería no detecta ninguna de estas interfaces, se produce un error de inicialización.</span><span class="sxs-lookup"><span data-stu-id="ac927-126">If the Messaging Engine discovers neither of these interfaces, an error condition results, causing the initialization to fail.</span></span> <span data-ttu-id="ac927-127">Este error ocurre cuando no se detecta alguna de las interfaces obligatorias.</span><span class="sxs-lookup"><span data-stu-id="ac927-127">The initialization fails if any mandatory interfaces are not discovered.</span></span>  
  
 <span data-ttu-id="ac927-128">En el diagrama siguiente se muestra esta secuencia de llamadas a la API; las interfaces de color azul son las que implementa el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac927-128">The following diagram illustrates this sequence of API calls; the interfaces in blue are implemented by the adapter.</span></span>  
  
 ![](../core/media/transmit-adapter-init.gif "Transmit_adapter_init")  
  
 <span data-ttu-id="ac927-129">El adaptador puede enviar mensajes justo después de inicializarse y configurarse.</span><span class="sxs-lookup"><span data-stu-id="ac927-129">The adapter can send messages as soon as it is initialized and configured.</span></span>  
  
 <span data-ttu-id="ac927-130">La ilustración siguiente muestra las interacciones de objetos que conlleva la inicialización de un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="ac927-130">The following figure shows the object interactions involved in initializing a send adapter.</span></span>  
  
 ![](../core/media/ebiz-sdk-devadapter10.gif "ebiz_sdk_devadapter10")  
<span data-ttu-id="ac927-131">Flujo de trabajo correspondiente a la inicialización de un adaptador de envío</span><span class="sxs-lookup"><span data-stu-id="ac927-131">Workflow for initializing a send adapter</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac927-132">Adaptadores no deberían bloquear el motor de mensajería en las llamadas como **IBTTransportControl.Initialize** y **IPersistPropertyBag.Load**.</span><span class="sxs-lookup"><span data-stu-id="ac927-132">Adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize** and **IPersistPropertyBag.Load**.</span></span> <span data-ttu-id="ac927-133">Un procesamiento excesivo en estas llamadas afecta al tiempo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac927-133">Performing excessive processing in these calls affects service startup time.</span></span>
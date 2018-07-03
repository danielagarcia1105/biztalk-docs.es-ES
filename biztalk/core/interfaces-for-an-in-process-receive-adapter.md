---
title: Interfaces para un proceso en el adaptador de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d608f9e511b1a3cb0ba94f30fbe3cd1eb7c9e87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965869"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a><span data-ttu-id="a8727-102">Interfaces de un adaptador de recepción de tipo En curso</span><span class="sxs-lookup"><span data-stu-id="a8727-102">Interfaces for an In-Process Receive Adapter</span></span>
<span data-ttu-id="a8727-103">El motor de mensajería crea instancias y configura los adaptadores de tipo En curso, pasando el proxy de transporte para permitir que el adaptador tenga acceso a su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a8727-103">The Messaging Engine instantiates and configures in-process adapters, passing in the transport proxy to allow the adapter to access its functionality.</span></span> <span data-ttu-id="a8727-104">Para habilitar la configuración y el enlace al proxy de transporte, los adaptadores deben implementar las interfaces de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8727-104">To enable configuration and binding to the transport proxy, adapters must implement the following configuration interfaces:</span></span>  
  
- <span data-ttu-id="a8727-105">**IBTTransport**</span><span class="sxs-lookup"><span data-stu-id="a8727-105">**IBTTransport**</span></span>  
  
- <span data-ttu-id="a8727-106">**IBTTransportControl**</span><span class="sxs-lookup"><span data-stu-id="a8727-106">**IBTTransportControl**</span></span>  
  
- <span data-ttu-id="a8727-107">**IBTTransportConfig**</span><span class="sxs-lookup"><span data-stu-id="a8727-107">**IBTTransportConfig**</span></span>  
  
- <span data-ttu-id="a8727-108">**IBaseComponent**</span><span class="sxs-lookup"><span data-stu-id="a8727-108">**IBaseComponent**</span></span>  
  
  <span data-ttu-id="a8727-109">Opcionalmente, si el adaptador desea recibir información del controlador durante la inicialización, tiene que implementar **IPersistPropertyBag**.</span><span class="sxs-lookup"><span data-stu-id="a8727-109">Optionally if the adapter wants to receive handler information during initialization it needs to implement **IPersistPropertyBag**.</span></span>  
  
  <span data-ttu-id="a8727-110">El motor de mensajería crea una instancia de un adaptador, lo inicializa y establece la configuración de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="a8727-110">The Messaging Engine creates an instance of an adapter, initializes it, and sets the configuration of receive locations.</span></span> <span data-ttu-id="a8727-111">El motor de mensajería se pasa una bolsa de propiedades a un adaptador en el **AddReceiveEndpoint** llamada al método.</span><span class="sxs-lookup"><span data-stu-id="a8727-111">The Messaging Engine passes a property bag to an adapter on the **AddReceiveEndpoint** method call.</span></span> <span data-ttu-id="a8727-112">La bolsa de propiedades contiene la configuración de la ubicación de recepción y del controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="a8727-112">The property bag contains the configuration for the receive location and receive handler.</span></span> <span data-ttu-id="a8727-113">La configuración se almacena en la base de datos en forma de bolsa de propiedades de estilo XML.</span><span class="sxs-lookup"><span data-stu-id="a8727-113">The configuration is stored in the database in the form of an XML-styled property bag.</span></span> <span data-ttu-id="a8727-114">El motor de mensajería lee el XML y rehidrata una bolsa de propiedades desde el XML.</span><span class="sxs-lookup"><span data-stu-id="a8727-114">The Messaging Engine reads the XML and rehydrates a property bag from the XML.</span></span> <span data-ttu-id="a8727-115">Después de que se agregue un extremo (ubicación de recepción) como mínimo, el adaptador puede comenzar a enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a8727-115">After at least one endpoint (receive location) is added, the adapter can start submitting messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8727-116">Los adaptadores deben no bloque motor de mensajería llama como **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, y **IBTTransportConfig.AddReceiveEndpoint**.</span><span class="sxs-lookup"><span data-stu-id="a8727-116">Adapters should not block Messaging Engine calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="a8727-117">La realización de un procesamiento excesivo en estas llamadas afectará al tiempo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="a8727-117">Performing excessive processing in these calls will affect service startup time.</span></span>  
  
 <span data-ttu-id="a8727-118">La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción de tipo En curso.</span><span class="sxs-lookup"><span data-stu-id="a8727-118">The following figure shows the object interactions involved in creating an in-process receive adapter.</span></span>  
  
 <span data-ttu-id="a8727-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span><span class="sxs-lookup"><span data-stu-id="a8727-119">![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")</span></span>  
<span data-ttu-id="a8727-120">Flujo de trabajo correspondiente a un adaptador de recepción de tipo En curso</span><span class="sxs-lookup"><span data-stu-id="a8727-120">Workflow for an in-process receive adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8727-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8727-121">See Also</span></span>  
 <span data-ttu-id="a8727-122">[Variables de adaptador](../core/adapter-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-122">[Adapter Variables](../core/adapter-variables.md) </span></span>  
 <span data-ttu-id="a8727-123">[Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-123">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="a8727-124">[Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-124">[Instantiating and Initializing a Receive Adapter](../core/instantiating-and-initializing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="a8727-125">[Adaptador de recepción de las interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-125">[Interfaces for an Isolated Receive Adapter](../core/interfaces-for-an-isolated-receive-adapter.md) </span></span>  
 <span data-ttu-id="a8727-126">[Interfaces para admite lote del adaptador de recepción](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-126">[Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md) </span></span>  
 <span data-ttu-id="a8727-127">[Interfaces para un transaccional compatible con lotes del adaptador de recepción](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a8727-127">[Interfaces for a Transactional Batch-Supported Receive Adapter](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md) </span></span>  
 [<span data-ttu-id="a8727-128">Interfaces para un adaptador de recepción sincrónico de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="a8727-128">Interfaces for a Synchronous Request-Response Receive Adapter</span></span>](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)
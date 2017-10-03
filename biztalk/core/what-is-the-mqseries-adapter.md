---
title: "¿Qué es el adaptador de MQSeries? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f72d0012050fc8022b53120377aeb648641d21f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-mqseries-adapter"></a><span data-ttu-id="2e9be-103">¿Qué es el adaptador de MQSeries?</span><span class="sxs-lookup"><span data-stu-id="2e9be-103">What Is the MQSeries Adapter?</span></span>
<span data-ttu-id="2e9be-104">El adaptador de MQSeries permite enviar y recibir mensajes a sistemas de MQSeries mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e9be-104">With the MQSeries adapter you can send and receive messages to MQSeries systems using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2e9be-105">El adaptador funciona con MQSeries Server para Windows.</span><span class="sxs-lookup"><span data-stu-id="2e9be-105">The adapter relies on MQSeries Server for Windows.</span></span> <span data-ttu-id="2e9be-106">Este diseño garantiza un servicio de mensajería confiable, pues MQSeries Server para Windows es compatible con el Coordinador de transacciones distribuidas de Microsoft (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="2e9be-106">This design guarantees reliable messaging because MQSeries Server for Windows supports Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
 <span data-ttu-id="2e9be-107">El adaptador admite servidores MQSeries y administradores de cola de MQSeries agrupados, así como servidores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e9be-107">The adapter supports clustered MQSeries Servers and clustered MQSeries Queue Managers, and also clustered BizTalk servers.</span></span>  
  
 <span data-ttu-id="2e9be-108">El adaptador de MQSeries permite hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e9be-108">You can do the following with the MQSeries adapter:</span></span>  
  
-   <span data-ttu-id="2e9be-109">Enviar mensajes a colas de definición remota, colas locales, colas de transmisión y colas de alias de MQSeries desde BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e9be-109">Send messages to MQSeries remote definition queues, local queues, transmission queues, and alias queues from BizTalk Server.</span></span>  
  
-   <span data-ttu-id="2e9be-110">Recibir mensajes procedentes de colas de transmisión, colas locales y colas de alias de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="2e9be-110">Receive messages from MQSeries transmission queues, local queues, and alias queues.</span></span>  
  
-   <span data-ttu-id="2e9be-111">Enviar y recibir mensajes desde MQSeries Server para Windows (MQSeries Server puede ejecutarse en el mismo equipo que BizTalk Server, o bien en una instalación remota).</span><span class="sxs-lookup"><span data-stu-id="2e9be-111">Send and receive messages from MQSeries Server for Windows (MQSeries Server can run on the same computer as BizTalk Server or on a remote installation).</span></span> <span data-ttu-id="2e9be-112">Sólo tendrá que implementar una copia de MQSAgent (el componente COM+ del adaptador) como base para todas las instalaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e9be-112">You only have to deploy one copy of MQSAgent (the COM+ component of the adapter) to support all your BizTalk Server installations.</span></span>  
  
-   <span data-ttu-id="2e9be-113">Realizar sondeos de MQSeries Server con un intervalo de espera.</span><span class="sxs-lookup"><span data-stu-id="2e9be-113">Poll MQSeries Server with a wait interval.</span></span>  
  
-   <span data-ttu-id="2e9be-114">Utilizar puertos de envío dinámicos para controlar el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2e9be-114">Use dynamic send ports to control the adapter.</span></span>  
  
-   <span data-ttu-id="2e9be-115">Crear colas de forma dinámica en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2e9be-115">Dynamically create queues at run time.</span></span>  
  
-   <span data-ttu-id="2e9be-116">Recibir dinámicamente los mensajes procedentes de colas basadas en MQSeries MatchOptions.</span><span class="sxs-lookup"><span data-stu-id="2e9be-116">Dynamically receive messages from queues based upon MQSeries MatchOptions.</span></span>  
  
-   <span data-ttu-id="2e9be-117">Asignar propiedades de contexto a propiedades de encabezado para la transmisión y recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2e9be-117">Map context properties to header properties for both transmitting and receiving messages.</span></span> <span data-ttu-id="2e9be-118">Se pueden obtener y definir propiedades de encabezado de MQSeries (incluidas MQMD, MQXQH, MQCIH y MQIIH) mediante propiedades de contexto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e9be-118">You can get and set MQSeries header properties (including MQMD, MQXQH, MQCIH, and MQIIH) through BizTalk Server context properties.</span></span>  
  
-   <span data-ttu-id="2e9be-119">Habilitar la correlación con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o MQSeries Server mediante la creación del identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="2e9be-119">Enable correlation with either [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or MQSeries Server creating the correlation identifier.</span></span>  
  
-   <span data-ttu-id="2e9be-120">Solicitar la entrega transaccional y no transaccional de mensajes para envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="2e9be-120">Request transactional and nontransactional delivery of messages for send and receive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e9be-121">Cuando se usan características como MQSeries que hacen llamadas del Modelo de objetos componentes distribuido (DCOM) al servidor, asegúrese de que no tiene un servidor de seguridad con NAT (Traducción de direcciones de red) habilitado.</span><span class="sxs-lookup"><span data-stu-id="2e9be-121">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="2e9be-122">El cliente debe poder obtener acceso al servidor mediante su dirección IP real y los servidores de seguridad con NAT traducen esta dirección en algo que el cliente no reconoce.</span><span class="sxs-lookup"><span data-stu-id="2e9be-122">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e9be-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2e9be-123">In This Section</span></span>  
  
-   [<span data-ttu-id="2e9be-124">Componentes del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="2e9be-124">Components of the MQSeries Adapter</span></span>](../core/components-of-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="2e9be-125">Arquitectura del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="2e9be-125">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)  
  
-   [<span data-ttu-id="2e9be-126">Uso del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="2e9be-126">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="2e9be-127">Seguridad del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="2e9be-127">MQSeries Adapter Security</span></span>](../core/mqseries-adapter-security.md)
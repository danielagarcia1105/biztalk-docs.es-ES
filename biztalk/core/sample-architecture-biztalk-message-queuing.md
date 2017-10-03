---
title: 'Arquitectura de ejemplo: Message Queue Server de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f38d373680fd1b47722fc1ac52c56b113ef59cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-biztalk-message-queuing"></a><span data-ttu-id="e1904-102">Arquitectura de ejemplo: Message Queue Server de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e1904-102">Sample Architecture: BizTalk Message Queuing</span></span>
<span data-ttu-id="e1904-103">En esta tema se describe la arquitectura de ejemplo cuando se usa el adaptador de BizTalk para Message Queue Server para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="e1904-103">This topic describes the sample architecture when you use the BizTalk Message Queuing adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="e1904-104">La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de Message Queue Server de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1904-104">The following figure shows the components of the BizTalk Server sample architecture when you use the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="e1904-105">**Figura 1: arquitectura de ejemplo que muestra el adaptador de Message Queue Server de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="e1904-105">**Figure 1 Sample architecture that shows BizTalk Message Queuing adapter**</span></span>  
  
 <span data-ttu-id="e1904-106">![Ejemplo de arquitectura para Message Queue Server de BizTalk](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span><span class="sxs-lookup"><span data-stu-id="e1904-106">![Sample architecture for BizTalk Message Queuing](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span></span>  
  
 <span data-ttu-id="e1904-107">Esta arquitectura de ejemplo contiene los componentes que se analizan en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e1904-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="e1904-108">Red perimetral-Internet</span><span class="sxs-lookup"><span data-stu-id="e1904-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="e1904-109">No se recomienda utilizar el protocolo binario de Message Queue Server en Internet.</span><span class="sxs-lookup"><span data-stu-id="e1904-109">We do not recommend using the Message Queuing binary protocol over the Internet.</span></span> <span data-ttu-id="e1904-110">No debe permitir que cualquier tráfico de Message Queue Server a través del Firewall 1.</span><span class="sxs-lookup"><span data-stu-id="e1904-110">You should not let any Message Queuing traffic through Firewall 1.</span></span> <span data-ttu-id="e1904-111">Si desea utilizar el adaptador de BizTalk para Message Queue para recibir mensajes a través de Internet, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1904-111">If you want to use the BizTalk Message Queuing adapter to receive messages over the Internet, do the following:</span></span>  
  
-   <span data-ttu-id="e1904-112">Utilice un servidor de Message Queue Server en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="e1904-112">Use a Message Queuing server in the perimeter network.</span></span>  
  
-   <span data-ttu-id="e1904-113">Utilice el protocolo HTTP de Message Queue Server en Internet.</span><span class="sxs-lookup"><span data-stu-id="e1904-113">Use the Message Queuing HTTP protocol over the Internet.</span></span>  
  
-   <span data-ttu-id="e1904-114">Coloque una aplicación de reenvío en la red perimetral para que obtenga los mensajes del servidor de Message Queue Server y los reenvíe al adaptador de Message Queue Server de BizTalk mediante un protocolo binario.</span><span class="sxs-lookup"><span data-stu-id="e1904-114">Have a forwarding application in the perimeter network that picks up the messages from the Message Queuing server and forwards them to the BizTalk Message Queuing adapter by using a binary protocol.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e1904-115">Mantenga cerrados los puertos del servidor de seguridad 1 que usa Message Queue Server de BizTalk aunque lo utilice para recibir mensajes de Internet.</span><span class="sxs-lookup"><span data-stu-id="e1904-115">Even if you use BizTalk Message Queuing to receive messages from the Internet, the ports that BizTalk Message Queuing uses should remain closed in Firewall 1.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="e1904-116">Red perimetral: intranet</span><span class="sxs-lookup"><span data-stu-id="e1904-116">Perimeter network―intranet</span></span>  
 <span data-ttu-id="e1904-117">Si se utiliza el adaptador de BizTalk para Message Queue Server para recibir mensajes de la intranet, un servidor de Message Queue Server de Windows reenviará el tráfico de Message Queue Server al servidor de BizTalk Server que ejecuta una instancia de host del adaptador de Message Queue Server de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1904-117">When you use the BizTalk Message Queuing adapter to receive messages from the intranet, there is a Windows Message Queuing server that forwards the Message Queuing traffic to the BizTalk Server that runs a host instance of the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="e1904-118">Si los dominios de intranet y de negocio electrónico comparten un Active Directory común, los mensajes atraviesan una serie de enrutadores de Message Queue Server hasta alcanzar su destino (el servidor BizTalk Server que ejecuta una instancia de host del adaptador de recepción de Message Queue Server de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="e1904-118">If the intranet and the E-Business domain share a common Active Directory, a message goes through a series of Message Queuing routers until it reaches the right destination (the BizTalk Server that runs a host instance of the BizTalk Message Queuing receive adapter).</span></span> <span data-ttu-id="e1904-119">Esta opción no aparece representada en el diagrama porque es menos segura que la primera.</span><span class="sxs-lookup"><span data-stu-id="e1904-119">This option is not represented in the diagram because it is less secure than the first one.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="e1904-120">Dominio de negocio electrónico</span><span class="sxs-lookup"><span data-stu-id="e1904-120">E-Business domain</span></span>  
 <span data-ttu-id="e1904-121">Los servidores de este domino son:</span><span class="sxs-lookup"><span data-stu-id="e1904-121">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="e1904-122">**BizTalk Server (procesamiento, adaptador de Message Queue Server de BizTalk y hosts de seguimiento).**</span><span class="sxs-lookup"><span data-stu-id="e1904-122">**BizTalk Server (processing, BizTalk Message Queuing adapter, and Tracking hosts).**</span></span> <span data-ttu-id="e1904-123">Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e1904-123">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="e1904-124">Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="e1904-124">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="e1904-125">Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio.</span><span class="sxs-lookup"><span data-stu-id="e1904-125">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="e1904-126">Asimismo, este host contiene instancias del host que ejecutan los adaptadores de recepción y envío de Message Queue Server de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1904-126">Additionally, this host contains instances of the host that runs the BizTalk Message Queuing send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1904-127">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e1904-127">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="e1904-128">**Servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="e1904-128">**Master secret server.**</span></span> <span data-ttu-id="e1904-129">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1904-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e1904-130">**Servidor SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e1904-130">**SQL Server.**</span></span> <span data-ttu-id="e1904-131">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1904-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e1904-132">**Controlador de dominio.**</span><span class="sxs-lookup"><span data-stu-id="e1904-132">**Domain controller.**</span></span> <span data-ttu-id="e1904-133">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1904-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e1904-134">**Herramientas de administración.**</span><span class="sxs-lookup"><span data-stu-id="e1904-134">**Administration tools.**</span></span> <span data-ttu-id="e1904-135">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1904-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1904-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1904-136">See Also</span></span>  
 <span data-ttu-id="e1904-137">[Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="e1904-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="e1904-138">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="e1904-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)
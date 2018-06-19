---
title: Administrar instancias de Host y Hosts de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262588"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a><span data-ttu-id="25567-102">Administrar hosts de BizTalk e instancias de host</span><span class="sxs-lookup"><span data-stu-id="25567-102">Managing BizTalk Hosts and Host Instances</span></span>
<span data-ttu-id="25567-103">Un host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es un conjunto lógico de cero o más procesos de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se implementan elementos como controladores de adaptador, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="25567-103">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host is a logical set of zero or more [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time processes in which you deploy items such as adapter handlers, receive locations (including pipelines), and orchestrations.</span></span> <span data-ttu-id="25567-104">Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).</span><span class="sxs-lookup"><span data-stu-id="25567-104">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="25567-105">Una instancia de host es el proceso en el que tiene lugar el procesamiento, la recepción y la transmisión de mensajes.</span><span class="sxs-lookup"><span data-stu-id="25567-105">A host instance is the process where the message processing, receiving, and transmitting occurs.</span></span> <span data-ttu-id="25567-106">Instalar una instancia de host en cada servidor que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que tiene uno o varios hosts asignados a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="25567-106">You install a host instance on each server running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that has one or more hosts mapped to that server.</span></span> <span data-ttu-id="25567-107">Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="25567-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="25567-108">Los hosts tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="25567-108">Hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="25567-109">Los hosts son contenedores lógicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25567-109">Hosts are the logical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="25567-110">Solo puede existir una instancia de un host específico en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="25567-110">Only one instance of a specific host can exist on each server.</span></span>  
  
-   <span data-ttu-id="25567-111">Puede asignar un host a varios servidores.</span><span class="sxs-lookup"><span data-stu-id="25567-111">You can map one host to multiple servers.</span></span>  
  
 <span data-ttu-id="25567-112">Las instancias de host tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="25567-112">Host instances have the following characteristics:</span></span>  
  
-   <span data-ttu-id="25567-113">Las instancias de host son contenedores físicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25567-113">Host instances are the physical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="25567-114">Se crea una instancia de host cuando se asigna un servidor a un host.</span><span class="sxs-lookup"><span data-stu-id="25567-114">You create a host instance when you map a server to a host.</span></span>  
  
-   <span data-ttu-id="25567-115">Pueden existir varias instancias de host (o hosts diferentes) en un servidor cuando se efectúa el equilibrio de carga o para la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="25567-115">Multiple host instances (of different hosts) can exist on a server when load balancing or for failover.</span></span>  
  
 <span data-ttu-id="25567-116">La siguiente ilustración muestra la relación entre servidores, hosts e instancias de host.</span><span class="sxs-lookup"><span data-stu-id="25567-116">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
 <span data-ttu-id="25567-117">![Hosts, instancias de host y las relaciones de servidor](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="25567-117">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
<span data-ttu-id="25567-118">Relación entre hosts, instancias de host y servidores</span><span class="sxs-lookup"><span data-stu-id="25567-118">Relationship between hosts, host instances, and servers</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25567-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="25567-119">In This Section</span></span>  
  
-   [<span data-ttu-id="25567-120">Cómo crear un entorno de host de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="25567-120">How to Create a BizTalk Server Hosting Environment</span></span>](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [<span data-ttu-id="25567-121">Cómo crear un nuevo Host</span><span class="sxs-lookup"><span data-stu-id="25567-121">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)  
  
-   [<span data-ttu-id="25567-122">Cómo modificar las propiedades de Host</span><span class="sxs-lookup"><span data-stu-id="25567-122">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)  
  
-   [<span data-ttu-id="25567-123">Cómo eliminar un Host</span><span class="sxs-lookup"><span data-stu-id="25567-123">How to Delete a Host</span></span>](../core/how-to-delete-a-host.md)  
  
-   [<span data-ttu-id="25567-124">Cómo agregar una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="25567-124">How to Add a Host Instance</span></span>](../core/how-to-add-a-host-instance.md)  
  
-   [<span data-ttu-id="25567-125">Cómo iniciar una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="25567-125">How to Start a Host Instance</span></span>](../core/how-to-start-a-host-instance.md)  
  
-   [<span data-ttu-id="25567-126">Cómo detener una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="25567-126">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)  
  
-   [<span data-ttu-id="25567-127">Cómo eliminar una instancia de Host</span><span class="sxs-lookup"><span data-stu-id="25567-127">How to Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)  
  
-   [<span data-ttu-id="25567-128">Cómo modificar las propiedades de la instancia de Host</span><span class="sxs-lookup"><span data-stu-id="25567-128">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)
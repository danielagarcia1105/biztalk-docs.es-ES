---
title: 'Arquitectura de ejemplo: Adaptador de archivo de | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269612"
---
# <a name="sample-architecture-file-adapter"></a><span data-ttu-id="dc3e1-102">Arquitectura de ejemplo: Adaptador de archivo de</span><span class="sxs-lookup"><span data-stu-id="dc3e1-102">Sample Architecture: File Adapter</span></span>
<span data-ttu-id="dc3e1-103">En este tema se describe la arquitectura de ejemplo cuando se usa el adaptador de archivo para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-103">This topic describes the sample architecture when you use the File adapter to send and receive messages.</span></span>  
  
## <a name="file-adapter-components"></a><span data-ttu-id="dc3e1-104">Componentes del adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="dc3e1-104">File Adapter Components</span></span>  
 <span data-ttu-id="dc3e1-105">En la siguiente ilustración se muestran los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-105">The following figure shows the components of the BizTalk Server sample architecture when you use the File adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc3e1-106">Esta arquitectura de ejemplo se aplica también cuando se utiliza el adaptador de EDI.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-106">This sample architecture is also applicable when you use the EDI adapter.</span></span>  
  
 <span data-ttu-id="dc3e1-107">**Figura 1: arquitectura de ejemplo que muestra el adaptador de archivo**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-107">**Figure 1 Sample architecture that shows File adapter**</span></span>  
  
 <span data-ttu-id="dc3e1-108">![Ejemplo de arquitectura de adaptador de archivo](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span><span class="sxs-lookup"><span data-stu-id="dc3e1-108">![Sample architecture for File adapter](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span></span>  
  
 <span data-ttu-id="dc3e1-109">Esta arquitectura de ejemplo contiene los componentes descritos en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-109">This sample architecture contains the components discussed in the following sections.</span></span>  
  
## <a name="perimeter-network-internet"></a><span data-ttu-id="dc3e1-110">Red perimetral-Internet</span><span class="sxs-lookup"><span data-stu-id="dc3e1-110">Perimeter network-Internet</span></span>  
 <span data-ttu-id="dc3e1-111">Normalmente las compañías utilizan el protocolo de archivo para las comunicaciones basadas en intranet y, por tanto, no es necesario que ningún servidor de la red perimetral de Internet admita este escenario.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-111">Companies commonly use the File protocol for intranet-based communications, and therefore you do not need any servers in the Internet perimeter network to support this scenario.</span></span>  
  
## <a name="perimeter-network-intranet"></a><span data-ttu-id="dc3e1-112">Red perimetral-intranet</span><span class="sxs-lookup"><span data-stu-id="dc3e1-112">Perimeter network-intranet</span></span>  
 <span data-ttu-id="dc3e1-113">Cuando se utiliza el adaptador de archivo, hay un servidor de archivos en la red perimetral de la intranet.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-113">When you use the File adapter, there is a File server in the intranet perimeter network.</span></span> <span data-ttu-id="dc3e1-114">Este es el servidor en el que los socios descargan mensajes, y en el que el adaptador de recepción de archivos de BizTalk los recoge.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-114">This is the server where your partners drop their messages, and the BizTalk File receive adapter picks up messages from this server.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="dc3e1-115">Dominio de negocio electrónico</span><span class="sxs-lookup"><span data-stu-id="dc3e1-115">E-Business domain</span></span>  
 <span data-ttu-id="dc3e1-116">Los servidores de este domino son:</span><span class="sxs-lookup"><span data-stu-id="dc3e1-116">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="dc3e1-117">**BizTalk Server (procesamiento, adaptador de archivo y hosts de seguimiento).**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-117">**BizTalk Server (processing, File adapter, and tracking hosts).**</span></span> <span data-ttu-id="dc3e1-118">Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-118">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="dc3e1-119">Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-119">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="dc3e1-120">Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="dc3e1-121">Asimismo, este host contiene instancias del host que ejecuta los adaptadores de recepción y envío de archivos.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-121">Additionally, this host contains instances of the host that runs the File send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc3e1-122">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dc3e1-122">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="dc3e1-123">Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e1-123">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="dc3e1-124">**Servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-124">**Master secret server.**</span></span> <span data-ttu-id="dc3e1-125">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e1-125">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="dc3e1-126">**Servidor SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-126">**SQL Server.**</span></span> <span data-ttu-id="dc3e1-127">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e1-127">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="dc3e1-128">**Controlador de dominio.**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-128">**Domain controller.**</span></span> <span data-ttu-id="dc3e1-129">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e1-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="dc3e1-130">**Herramientas de administración.**</span><span class="sxs-lookup"><span data-stu-id="dc3e1-130">**Administration tools.**</span></span> <span data-ttu-id="dc3e1-131">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e1-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3e1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc3e1-132">See Also</span></span>  
 <span data-ttu-id="dc3e1-133">[Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="dc3e1-133">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="dc3e1-134">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="dc3e1-134">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)
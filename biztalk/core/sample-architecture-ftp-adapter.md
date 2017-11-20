---
title: 'Arquitectura de ejemplo: Adaptador de FTP de | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-ftp-adapter"></a><span data-ttu-id="e6d8b-102">Arquitectura de ejemplo: Adaptador de FTP de</span><span class="sxs-lookup"><span data-stu-id="e6d8b-102">Sample Architecture: FTP Adapter</span></span>
<span data-ttu-id="e6d8b-103">En este tema se describe la arquitectura de ejemplo cuando se usa el adaptador de FTP para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-103">This topic describes the sample architecture when you use the FTP adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="e6d8b-104">La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-104">The following figure shows the components of the BizTalk Server sample architecture when you use the FTP adapter.</span></span>  
  
 <span data-ttu-id="e6d8b-105">**Figura 1: arquitectura de ejemplo que muestra el adaptador FTP**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-105">**Figure 1 Sample architecture that shows FTP adapter**</span></span>  
  
 <span data-ttu-id="e6d8b-106">![Ejemplo de arquitectura de adaptador de FTP](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span><span class="sxs-lookup"><span data-stu-id="e6d8b-106">![Sample architecture for FTP adapter](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span></span>  
  
 <span data-ttu-id="e6d8b-107">Esta arquitectura de ejemplo contiene los componentes como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-107">This sample architecture contains the components as discussed in following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="e6d8b-108">Red perimetral-Internet</span><span class="sxs-lookup"><span data-stu-id="e6d8b-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="e6d8b-109">Si utiliza el adaptador de FTP, habrá un servidor FTP en la red perimetral de Internet.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-109">When you use the FTP adapter, there is an FTP server in the Internet perimeter network.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6d8b-110">El servidor FTP también puede estar fuera de su entorno, en la red de un socio u hospedado por un proveedor de software independiente (ISV).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-110">The FTP server can also be located outside your environment—in the partner's network, or hosted by a third-party independent software vendor (ISV).</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="e6d8b-111">Red perimetral: intranet</span><span class="sxs-lookup"><span data-stu-id="e6d8b-111">Perimeter network―intranet</span></span>  
 <span data-ttu-id="e6d8b-112">Normalmente las compañías utilizan el protocolo FTP para las comunicaciones basadas en Internet y, por tanto, no necesita que ningún servidor de la red perimetral de la intranet admita este escenario.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-112">Companies commonly use the FTP protocol for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="e6d8b-113">Dominio de negocio electrónico</span><span class="sxs-lookup"><span data-stu-id="e6d8b-113">E-Business domain</span></span>  
 <span data-ttu-id="e6d8b-114">Los servidores de este domino son:</span><span class="sxs-lookup"><span data-stu-id="e6d8b-114">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="e6d8b-115">**BizTalk Server (procesamiento, adaptador de FTP y hosts de seguimiento).**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-115">**BizTalk Server (processing, FTP adapter, and tracking hosts).**</span></span> <span data-ttu-id="e6d8b-116">Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-116">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="e6d8b-117">Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-117">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="e6d8b-118">Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-118">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="e6d8b-119">Asimismo, este host contiene instancias del host que ejecuta los adaptadores de recepción y envío FTP.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-119">Additionally, this host contains instances of the host that runs the FTP send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6d8b-120">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e6d8b-120">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="e6d8b-121">Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-121">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="e6d8b-122">**Servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-122">**Master secret server.**</span></span> <span data-ttu-id="e6d8b-123">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-123">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e6d8b-124">**Servidor SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-124">**SQL Server.**</span></span> <span data-ttu-id="e6d8b-125">Igual que el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-125">Same as the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e6d8b-126">**Controlador de dominio.**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-126">**Domain controller.**</span></span> <span data-ttu-id="e6d8b-127">Igual que el mismo que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-127">Same as in the Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="e6d8b-128">**Herramientas de administración.**</span><span class="sxs-lookup"><span data-stu-id="e6d8b-128">**Administration tools.**</span></span> <span data-ttu-id="e6d8b-129">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="e6d8b-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d8b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d8b-130">See Also</span></span>  
 <span data-ttu-id="e6d8b-131">[Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8b-131">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="e6d8b-132">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="e6d8b-132">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)
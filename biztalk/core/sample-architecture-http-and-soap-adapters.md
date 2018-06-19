---
title: 'Arquitectura de ejemplo: Los adaptadores SOAP y HTTP | Documentos de Microsoft'
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
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269732"
---
# <a name="sample-architecture-http-and-soap-adapters"></a><span data-ttu-id="d5eed-102">Arquitectura de ejemplo: Los adaptadores SOAP y HTTP</span><span class="sxs-lookup"><span data-stu-id="d5eed-102">Sample Architecture: HTTP and SOAP Adapters</span></span>
<span data-ttu-id="d5eed-103">En esta sección se describe la arquitectura de ejemplo cuando se usan los adaptadores de HTTP y SOAP para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5eed-103">This topic describes the sample architecture when you use the HTTP and SOAP adapters to send and receive messages.</span></span>  
  
 <span data-ttu-id="d5eed-104">La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar los adaptadores de HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="d5eed-104">The following figure shows the components of the BizTalk Server sample architecture when you use the HTTP or SOAP adapters.</span></span>  
  
 <span data-ttu-id="d5eed-105">**Figura 1: arquitectura de ejemplo que muestra los adaptadores de HTTP y SOAP**</span><span class="sxs-lookup"><span data-stu-id="d5eed-105">**Figure 1 Sample architecture that shows HTTP or SOAP adapters**</span></span>  
  
 <span data-ttu-id="d5eed-106">![Ejemplo de arquitectura de adaptador de HTTP o SOAP](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span><span class="sxs-lookup"><span data-stu-id="d5eed-106">![Sample architecture for HTTP or SOAP adapter](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span></span>  
  
 <span data-ttu-id="d5eed-107">Esta arquitectura de ejemplo contiene los componentes que se analizan en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d5eed-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="d5eed-108">Red perimetral-Internet</span><span class="sxs-lookup"><span data-stu-id="d5eed-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="d5eed-109">Si se usan los adaptadores de HTTP y SOAP, se recomienda emplear reglas de proxy inverso (la implementación de servidor TMG se denomina Publicación en Web) para retransmitir el mensaje del firewall conectado a Internet (Firewall 1) al firewall que protege el dominio de negocio electrónico (Firewall 2) y de éste al servidor BizTalk Server que ejecuta el host aislado.</span><span class="sxs-lookup"><span data-stu-id="d5eed-109">When you use the SOAP and HTTP adapters, we recommend that you use reverse proxy rules (the TMG Server implementation is called Web Publishing) to relay the message from the Internet-facing firewall (Firewall 1) to the firewall that helps protect the E-Business domain (Firewall 2), and from this firewall to the BizTalk Server that runs the isolated host.</span></span> <span data-ttu-id="d5eed-110">Para obtener más información acerca de las reglas de publicación en Web, vea el sitio Web de Microsoft en [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span><span class="sxs-lookup"><span data-stu-id="d5eed-110">For more information about Web Publishing rules, see the Microsoft Web site at [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5eed-111">Si utiliza un proxy inverso, no necesita servidores Web en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="d5eed-111">When you use reverse proxy, you do not need Web servers in the perimeter network.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="d5eed-112">Red perimetral: intranet</span><span class="sxs-lookup"><span data-stu-id="d5eed-112">Perimeter network―intranet</span></span>  
 <span data-ttu-id="d5eed-113">Normalmente las compañías utilizan los protocolos HTTP y SOAP para las comunicaciones basadas en Internet y, por tanto, no es necesario que ningún servidor de la red perimetral de la intranet admita este escenario.</span><span class="sxs-lookup"><span data-stu-id="d5eed-113">Companies commonly use the HTTP and SOAP protocols for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span> <span data-ttu-id="d5eed-114">Si en la intranet hay una aplicación interna que está integrada en BizTalk Server mediante los protocolos HTTP o SOAP, debe seguir las recomendaciones de la red perimetral de Internet.</span><span class="sxs-lookup"><span data-stu-id="d5eed-114">If you have an internal application in the intranet that integrates with BizTalk Server through the HTTP or SOAP protocols, you should follow the recommendations for the Internet perimeter network.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="d5eed-115">Dominio de negocio electrónico</span><span class="sxs-lookup"><span data-stu-id="d5eed-115">E-Business domain</span></span>  
 <span data-ttu-id="d5eed-116">Este dominio contiene toda la infraestructura y aplicaciones que utiliza la implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d5eed-116">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="d5eed-117">Los servidores de este domino son:</span><span class="sxs-lookup"><span data-stu-id="d5eed-117">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="d5eed-118">**BizTalk Server (procesamiento y hosts de seguimiento).**</span><span class="sxs-lookup"><span data-stu-id="d5eed-118">**BizTalk Server (processing and tracking hosts).**</span></span> <span data-ttu-id="d5eed-119">Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="d5eed-119">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="d5eed-120">Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio.</span><span class="sxs-lookup"><span data-stu-id="d5eed-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5eed-121">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d5eed-121">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="d5eed-122">**BizTalk Server (hosts aislados para adaptadores de SOAP y HTTP).**</span><span class="sxs-lookup"><span data-stu-id="d5eed-122">**BizTalk Server (isolated hosts for SOAP and HTTP adapters).**</span></span> <span data-ttu-id="d5eed-123">Este servidor contiene una instalación del tiempo de ejecución de BizTalk Server y sólo tiene instancias de los hosts que contienen los adaptadores de HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="d5eed-123">This server has an installation of the BizTalk Server runtime, and has only instances of the hosts that contain the HTTP and SOAP adapters.</span></span> <span data-ttu-id="d5eed-124">Estos hosts se ejecutan en un servidor independiente, ya que para ejecutar los adaptadores es necesario instalar los Servicios de Internet Information Server (IIS) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d5eed-124">These hosts run in a separate server because these adapters require that you install Internet Information Services (IIS) on the computer where they run.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5eed-125">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de los adaptadores de HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="d5eed-125">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your HTTP and SOAP adapter hosts.</span></span> <span data-ttu-id="d5eed-126">Al hacerlo, deberá configurar además el equilibrio de carga de red (NBL).</span><span class="sxs-lookup"><span data-stu-id="d5eed-126">When you do this, you must also configure Network Load Balancing (NLB).</span></span> <span data-ttu-id="d5eed-127">Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).</span><span class="sxs-lookup"><span data-stu-id="d5eed-127">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="d5eed-128">**Servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="d5eed-128">**Master secret server.**</span></span> <span data-ttu-id="d5eed-129">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5eed-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d5eed-130">**Servidor SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="d5eed-130">**SQL Server.**</span></span> <span data-ttu-id="d5eed-131">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5eed-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d5eed-132">**Controlador de dominio.**</span><span class="sxs-lookup"><span data-stu-id="d5eed-132">**Domain controller.**</span></span> <span data-ttu-id="d5eed-133">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5eed-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d5eed-134">**Herramientas de administración.**</span><span class="sxs-lookup"><span data-stu-id="d5eed-134">**Administration tools.**</span></span> <span data-ttu-id="d5eed-135">Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5eed-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5eed-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5eed-136">See Also</span></span>  
 <span data-ttu-id="d5eed-137">[Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="d5eed-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="d5eed-138">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="d5eed-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)
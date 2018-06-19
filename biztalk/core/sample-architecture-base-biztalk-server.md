---
title: 'Arquitectura de ejemplo: Servidor BizTalk Server Base | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea815c0165f58c28cea8ce7cae35fd6ed7437323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271196"
---
# <a name="sample-architecture-base-biztalk-server"></a><span data-ttu-id="e4bfd-102">Arquitectura de ejemplo: servidor BizTalk Server base</span><span class="sxs-lookup"><span data-stu-id="e4bfd-102">Sample Architecture: Base BizTalk Server</span></span>
<span data-ttu-id="e4bfd-103">En este tema, se analiza la arquitectura de ejemplo básica.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-103">This topic discusses the base sample architecture.</span></span> <span data-ttu-id="e4bfd-104">y se describen los componentes de una implementación de BizTalk Server que son independientes de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-104">It describes the components in a BizTalk Server deployment that are adapter-independent.</span></span> <span data-ttu-id="e4bfd-105">Se recomienda que todas las implementaciones de BizTalk Server cuenten, como mínimo, con estos componentes.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-105">We recommend that any BizTalk Server deployment have at least these components.</span></span>  
  
 <span data-ttu-id="e4bfd-106">La siguiente ilustración muestra los componentes de la arquitectura de ejemplo básica de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-106">The following figure shows the components of the base BizTalk Server sample architecture.</span></span> <span data-ttu-id="e4bfd-107">Estos componentes aparecen en todas las arquitecturas de BizTalk Server específicas de adaptadores que se analizarán en otras secciones.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-107">These components appear in all the adapter-specific BizTalk Server architectures that we discuss in later sections.</span></span>  
  
 <span data-ttu-id="e4bfd-108">**Componentes de la arquitectura de Base de la figura 1**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-108">**Figure 1 Base architecture components**</span></span>  
  
 <span data-ttu-id="e4bfd-109">![Componentes de la arquitectura de base](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span><span class="sxs-lookup"><span data-stu-id="e4bfd-109">![Base architecture components](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")</span></span>  
  
 <span data-ttu-id="e4bfd-110">Esta arquitectura de ejemplo contiene los elementos que se analizan en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-110">This sample architecture contains the items discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="e4bfd-111">Red perimetral: Internet</span><span class="sxs-lookup"><span data-stu-id="e4bfd-111">Perimeter network―internet</span></span>  
  
-   <span data-ttu-id="e4bfd-112">La red perimetral (también denominada DMZ, zona desmilitarizada y subred protegida) contiene servidores que proporcionan servicios relacionados con Internet.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-112">This perimeter network (also known as DMZ, demilitarized zone, and screened subnet) contains servers that provide Internet-related services.</span></span> <span data-ttu-id="e4bfd-113">En este dominio no hay servidores de BizTalk, ubicaciones de recepción de BizTalk ni servidores de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-113">There are no BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers in this domain.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="e4bfd-114">Red perimetral: intranet</span><span class="sxs-lookup"><span data-stu-id="e4bfd-114">Perimeter network―intranet</span></span>  
 <span data-ttu-id="e4bfd-115">La red perimetral contiene servidores que proporcionan servicios relacionados con la intranet.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-115">This perimeter network contains servers that provide intranet-related services.</span></span> <span data-ttu-id="e4bfd-116">Proporciona un nivel de seguridad adicional entre la intranet (por ejemplo, una red corporativa) y los servidores que ejecutan la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-116">It provides an additional layer of security between your intranet (for example, a corporate network) and the servers that run the application.</span></span> <span data-ttu-id="e4bfd-117">Como la red perimetral de Internet, la red perimetral de la intranet no contiene servidores de BizTalk Server, ubicaciones de recepción de BizTalk ni servidores de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-117">Like the Internet perimeter network, the intranet perimeter network does not contain BizTalk Servers, BizTalk receive locations, or Enterprise Single Sign-On servers.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="e4bfd-118">Dominio de negocio electrónico</span><span class="sxs-lookup"><span data-stu-id="e4bfd-118">E-Business Domain</span></span>  
 <span data-ttu-id="e4bfd-119">Este dominio contiene toda la infraestructura y aplicaciones que utiliza la implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-119">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="e4bfd-120">Los servidores de este domino son:</span><span class="sxs-lookup"><span data-stu-id="e4bfd-120">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="e4bfd-121">**Servidor BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-121">**BizTalk Server.**</span></span> <span data-ttu-id="e4bfd-122">Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server e instancias de varios hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-122">This server has an installation of the BizTalk Server runtime and instances of various BizTalk Hosts.</span></span> <span data-ttu-id="e4bfd-123">El número de servidores de BizTalk del entorno depende del tipo de hosts que ejecuten y de las necesidades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-123">The number of BizTalk Servers in the environment depends on the type of hosts they run and the performance needs.</span></span> <span data-ttu-id="e4bfd-124">A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-124">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="e4bfd-125">**Servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-125">**Master secret server.**</span></span> <span data-ttu-id="e4bfd-126">Este es el servidor secreto principal de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-126">This server is the Enterprise Single Sign-On (SSO) master secret server.</span></span> <span data-ttu-id="e4bfd-127">Contiene el secreto principal (clave de cifrado) que utiliza el sistema SSO para cifrar los datos en la base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-127">It holds the master secret (encryption key) that the SSO system uses to encrypt the data in the SSO database.</span></span>  
  
-   <span data-ttu-id="e4bfd-128">**Servidor SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-128">**SQL Server.**</span></span> <span data-ttu-id="e4bfd-129">Este servidor contiene las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-129">This server contains the BizTalk databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e4bfd-130">Para la protección de conmutación por error, es recomendable agrupar las bases de datos de BizTalk en clústeres.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-130">For failover protection, we recommend that you cluster each BizTalk database.</span></span> <span data-ttu-id="e4bfd-131">Para obtener más información acerca de los clústeres de conmutación por error de Microsoft SQL Server, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-131">For more information about Microsoft SQL Server failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4bfd-132">Según sus necesidades de rendimiento, puede que tenga que separar las bases de datos de BizTalk en varios equipos que ejecuten SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-132">Depending on your performance needs, you might have to separate the BizTalk databases into multiple computers that run SQL Server.</span></span>  
  
-   <span data-ttu-id="e4bfd-133">**Controlador de dominio.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-133">**Domain controller.**</span></span> <span data-ttu-id="e4bfd-134">Este servidor aloja el dominio de negocio electrónico de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-134">This server hosts the E-Business Active Directory domain.</span></span> <span data-ttu-id="e4bfd-135">Contiene información acerca de todos los grupos y cuentas individuales que necesitan tener acceso a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-135">It contains information about all the groups and individual accounts that need access to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="e4bfd-136">**Herramientas de administración.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-136">**Administration tools.**</span></span> <span data-ttu-id="e4bfd-137">Uno de los servidores de este dominio contiene las herramientas administrativas siguientes: la consola de administración de BizTalk y la utilidad de administración de inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-137">One of the servers in this domain hosts the administration tools: BizTalk Administration console and Enterprise Single Sign-On (SSO) administration utility.</span></span>  
  
## <a name="firewalls-and-domains"></a><span data-ttu-id="e4bfd-138">Servidores de seguridad y dominios</span><span class="sxs-lookup"><span data-stu-id="e4bfd-138">Firewalls and Domains</span></span>  
 <span data-ttu-id="e4bfd-139">En la Figura 1, el servidor Forefront Threat Management Gateway (TMG) 2010 actúa como firewall de software para proteger y contener cada uno de estos dominios.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-139">In Figure 1, Forefront Threat Management Gateway (TMG) 2010 server acts as a software firewall to help protect and contain each of these domains.</span></span> <span data-ttu-id="e4bfd-140">Asimismo, el dominio de negocio electrónico tiene su propio controlador de dominio y no confía en ningún otro dominio.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-140">Additionally, the E-Business domain has its own domain controller, and this domain does not trust any other domain.</span></span> <span data-ttu-id="e4bfd-141">Para obtener más información acerca de cómo configurar un firewall para dominios y confianzas, consulte el sitio Web de soporte técnico y Microsoft Help en [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-141">For more information about how to configure a firewall for domains and trusts, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).</span></span>  
  
 <span data-ttu-id="e4bfd-142">En esta arquitectura de ejemplo hay dos servidores de seguridad:</span><span class="sxs-lookup"><span data-stu-id="e4bfd-142">The sample architecture has two firewalls:</span></span>  
  
-   <span data-ttu-id="e4bfd-143">**Firewall 1.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-143">**Firewall 1.**</span></span> <span data-ttu-id="e4bfd-144">Este servidor de seguridad tiene tres interfaces de red: enruta el tráfico procedente de Internet, la intranet y las redes perimetrales.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-144">This firewall has three network interfaces: It routes traffic from the Internet, the intranet, and the perimeter networks.</span></span>  
  
-   <span data-ttu-id="e4bfd-145">**Servidor de seguridad 2.**</span><span class="sxs-lookup"><span data-stu-id="e4bfd-145">**Firewall 2.**</span></span> <span data-ttu-id="e4bfd-146">Este servidor es de base dual: enruta el tráfico procedente de las redes perimetrales (Internet e intranet) y el dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-146">This firewall is dual-homed: It routes traffic from the perimeter networks (both Internet and intranet) and the E-Business domain.</span></span>  
  
 <span data-ttu-id="e4bfd-147">Los equipos de las redes perimetrales no son miembros de ningún dominio y no se comunican entre sí.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-147">The computers in the perimeter networks are not members of any domain, and they do not communicate with each other.</span></span>  
  
## <a name="ipsec"></a><span data-ttu-id="e4bfd-148">IPsec</span><span class="sxs-lookup"><span data-stu-id="e4bfd-148">IPsec</span></span>  
 <span data-ttu-id="e4bfd-149">Se recomienda utilizar seguridad de Protocolo de Internet (IPSec) para proteger la comunicación entre todos los servidores del dominio de negocio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-149">We recommend that you use Internet Protocol security (IPSec) to help secure the communication between all the servers in the E-Business domain.</span></span> <span data-ttu-id="e4bfd-150">Las reglas de IPsec son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4bfd-150">The IPsec rules are as follows:</span></span>  
  
-   <span data-ttu-id="e4bfd-151">Permitir el tráfico autenticado entre BizTalk Server y el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-151">Allow authenticated traffic between BizTalk Server and the domain controller.</span></span>  
  
-   <span data-ttu-id="e4bfd-152">Permitir el tráfico autenticado entre BizTalk Server y el servidor de herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-152">Allow authenticated traffic between BizTalk Server and the administration tools server.</span></span>  
  
-   <span data-ttu-id="e4bfd-153">Permitir el tráfico autenticado entre BizTalk Server y el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-153">Allow authenticated traffic between BizTalk Server and the master secret server.</span></span>  
  
-   <span data-ttu-id="e4bfd-154">Permitir el tráfico autenticado entre BizTalk Server y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-154">Allow authenticated traffic between BizTalk Server and the SQL Server.</span></span>  
  
-   <span data-ttu-id="e4bfd-155">Permitir el tráfico autenticado entre el servidor secreto principal y el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-155">Allow authenticated traffic between the master secret server and the domain controller.</span></span>  
  
-   <span data-ttu-id="e4bfd-156">Permitir el tráfico autenticado entre el servidor secreto principal y BizTalk Server (hosts de seguimiento, en proceso, de procesamiento y aislados).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-156">Allow authenticated traffic between the master secret server and the BizTalk Server (isolated, processing, in-process, and tracking hosts.)</span></span>  
  
-   <span data-ttu-id="e4bfd-157">Permitir el tráfico autenticado entre el servidor secreto principal y el servidor SQL Server (bases de datos SSO).</span><span class="sxs-lookup"><span data-stu-id="e4bfd-157">Allow authenticated traffic between the master secret server and the SQL Server (SSO databases).</span></span>  
  
-   <span data-ttu-id="e4bfd-158">Permitir el tráfico autenticado entre el controlador de dominio y todos los servidores del dominio.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-158">Allow authenticated traffic between the domain controller and all the servers in the domain.</span></span>  
  
-   <span data-ttu-id="e4bfd-159">Permitir el tráfico autenticado entre el servidor de herramientas administrativas y todos los servidores del dominio.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-159">Allow authenticated traffic between the administration tools server and all the servers in the domain.</span></span>  
  
 <span data-ttu-id="e4bfd-160">Si en el dominio hay otras aplicaciones que no necesitan obtener acceso al servidor BizTalk Server, SQL Server, el servidor secreto principal ni al servidor de herramientas administrativas, bloquee el tráfico entre esas aplicaciones y los servidores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e4bfd-160">If you have other applications in the domain that do not need access to the BizTalk Server, SQL Server, master secret server, or administration tools server, block traffic between those applications and the appropriate servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4bfd-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4bfd-161">See Also</span></span>  
 <span data-ttu-id="e4bfd-162">[Planear la seguridad](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="e4bfd-162">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="e4bfd-163">[Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="e4bfd-163">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="e4bfd-164">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="e4bfd-164">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)
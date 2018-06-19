---
title: Diseñar las arquitecturas de sistema de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18656a2d4d3827cd38a3f791af2ac856df8ce36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239276"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a><span data-ttu-id="432d9-102">Diseñar las arquitecturas del sistema de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="432d9-102">Designing the System Architectures for BizTalk Server</span></span>
<span data-ttu-id="432d9-103">Los requisitos de la implementación de Microsoft® BizTalk® Server en cuanto a seguridad, rendimiento, disponibilidad y funcionamiento dependen en gran medida de las necesidades, los requisitos, los socios comerciales, el tamaño, etc., de la empresa.</span><span class="sxs-lookup"><span data-stu-id="432d9-103">The requirements of your Microsoft® BizTalk® Server deployment for security, performance, availability, and operation are highly dependent on your business needs, requirements, partners, company size, and so on.</span></span> <span data-ttu-id="432d9-104">Aunque es difícil considerar una configuración cualquiera de componentes de BizTalk Server como típica y proporcionar instrucciones para ella, en esta sección se proporcionan instrucciones y recomendaciones sobre cómo configurar las distintas características de BizTalk Server en una configuración segura distribuida para el entorno de producción de una empresa de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="432d9-104">While it is difficult to consider any single configuration of BizTalk Server components as typical and provide prescriptive guidance for it, this section provides guidance and recommendations on how to configure the different BizTalk Server features in a distributed, secure configuration for the production environment of a large enterprise.</span></span>  
  
 <span data-ttu-id="432d9-105">Las arquitecturas que se presentan en esta sección tienen como objetivo ofrecerle información de referencia sobre la implementación de BizTalk Server en un entorno altamente distribuido en el que los aspectos de seguridad y defensa tienen mucha importancia.</span><span class="sxs-lookup"><span data-stu-id="432d9-105">The architectures presented in this section aim to provide you with reference information about deploying BizTalk Server in a highly distributed environment where you take into consideration defense in depth.</span></span> <span data-ttu-id="432d9-106">Todas las aplicaciones de BizTalk Server es probable que tenga su propio conjunto único de requisitos de seguridad basados en el dominio del problema, los protocolos usados, y el entorno en particular la solución funciona en.</span><span class="sxs-lookup"><span data-stu-id="432d9-106">Every application for BizTalk Server is likely to have its own unique set of security requirements based on the problem domain, the protocols used, and the particular environment the solution operates in.</span></span> <span data-ttu-id="432d9-107">Rendimiento, disponibilidad y las consideraciones de costo más influyen en estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="432d9-107">Performance, availability, and cost considerations further influence these requirements.</span></span> <span data-ttu-id="432d9-108">Debe utilizar estas arquitecturas y las recomendaciones que se indican en este documento como la base para crear una implementación de BizTalk Server propia que se adapte a las necesidades, las amenazas y los activos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="432d9-108">You should use these architectures and the recommendations within this document as the building blocks to create your own BizTalk Server deployment tailored to the needs, threats and assets of your company.</span></span>  
  
 <span data-ttu-id="432d9-109">Esta sección contiene información acerca de cómo puede diseñar la arquitectura del sistema de BizTalk Server con el fin de proteger las distintas características de BizTalk Server y, por consiguiente, los datos que los servidores procesan y almacenan, además de cómo integrar los servidores en un entorno distribuido que reduzca al mínimo los riesgos potenciales a los que se pueden ver sometidos los datos y servidores principales ante un ataque o desastre.</span><span class="sxs-lookup"><span data-stu-id="432d9-109">This section contains information about how you can design the system architecture for BizTalk Server to secure the different features in BizTalk Server, and consequently, secure the data that the servers process and store, and how to place the servers in a distributed environment that minimize the potential for critical data and servers being compromised in the event of an attack or disaster.</span></span> <span data-ttu-id="432d9-110">Esta sección no ofrece recomendaciones para configurar entornos de desarrollo o de pruebas, ni detalles para implementar un ensamblado en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="432d9-110">This section does not provide recommendations for configuring development, or test environments, or details for deploying an assembly into a production environment.</span></span> <span data-ttu-id="432d9-111">Para obtener más información sobre cómo implementar ensamblados, vea [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).</span><span class="sxs-lookup"><span data-stu-id="432d9-111">For more information about deploying assemblies, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="432d9-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="432d9-112">In This Section</span></span>  
  
-   [<span data-ttu-id="432d9-113">Diseñar una arquitectura segura</span><span class="sxs-lookup"><span data-stu-id="432d9-113">Designing a Secure Architecture</span></span>](../core/designing-a-secure-architecture.md)  
  
-   [<span data-ttu-id="432d9-114">Diseñar una arquitectura distribuida</span><span class="sxs-lookup"><span data-stu-id="432d9-114">Designing a Distributed Architecture</span></span>](../core/designing-a-distributed-architecture.md)  
  
-   [<span data-ttu-id="432d9-115">Arquitecturas de BizTalk Server de ejemplo</span><span class="sxs-lookup"><span data-stu-id="432d9-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)
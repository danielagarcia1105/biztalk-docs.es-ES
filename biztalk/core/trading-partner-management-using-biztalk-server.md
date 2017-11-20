---
title: "Uso de BizTalk Server de administración de socios comerciales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f31a5e49-ef19-41a3-9cf3-cf85d0685a59
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5a1ac3c072b21633c3b6f6226aa7cce20729077
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="trading-partner-management-using-biztalk-server"></a><span data-ttu-id="4aaea-102">Administración de socios comerciales mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4aaea-102">Trading Partner Management Using BizTalk Server</span></span>
## <a name="introduction-to-tpm"></a><span data-ttu-id="4aaea-103">Introducción a TPM</span><span class="sxs-lookup"><span data-stu-id="4aaea-103">Introduction to TPM</span></span>
<span data-ttu-id="4aaea-104">La Administración de socios comerciales (TPM) de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] vuelve a crear los conceptos fundamentales sobre cómo administrar y almacenar información acerca de los socios comerciales y sus negocios.</span><span class="sxs-lookup"><span data-stu-id="4aaea-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Trading Partner Management (TPM) rebuilds the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="4aaea-105">La solución TPM mejorada refleja las entidades de negocio y las relaciones en el campo, mediante la habilitación de organizaciones para administrar mejor las asociaciones empresariales con socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="4aaea-105">The enhanced TPM solution reflects the business entities and relationships in the field, thereby enabling organizations to better manage your business partnerships with trading partners.</span></span> <span data-ttu-id="4aaea-106">Para obtener más información sobre cómo la solución TPM modela las asociaciones comerciales en un entorno de BizTalk, consulte [bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md).</span><span class="sxs-lookup"><span data-stu-id="4aaea-106">For more information on how the TPM solution models trading partnerships in a BizTalk environment, see [Building Blocks of a Trading Partner Management Solution](../core/building-blocks-of-a-trading-partner-management-solution.md).</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4aaea-107">incluye compatibilidad nativa para el intercambio de datos de Electronic Data Interchange (EDI) y el transporte de datos de AS2.</span><span class="sxs-lookup"><span data-stu-id="4aaea-107"> includes native support for Electronic Data Interchange (EDI) data exchange and AS2 data transport.</span></span> <span data-ttu-id="4aaea-108">Gracias a esto, las empresas pueden ampliar sus soluciones de administración de procesos empresariales basados en EDI y aprovechar las mejoras de productividad que el intercambio automático de las transacciones proporciona.</span><span class="sxs-lookup"><span data-stu-id="4aaea-108">This support enables businesses to extend their EDI-based business process management solutions, taking advantage of the productivity improvements that the automated exchange of EDI transactions provides.</span></span> <span data-ttu-id="4aaea-109">BizTalk Server proporciona a estas empresas un medio de conexión más seguro y confiable de los socios comerciales con procesos empresariales de cadena de suministros de importancia fundamental a través de EDI y de EDIINT/AS2.</span><span class="sxs-lookup"><span data-stu-id="4aaea-109">BizTalk Server provides these businesses with the means to more securely and reliably connect partners to critical supply-chain business processes using EDI and EDIINT/AS2.</span></span>  
  
 <span data-ttu-id="4aaea-110">La solución TPM junto con la compatibilidad EDI y AS2 proporcionan una solución sólida y escalable para la administración de socios comerciales en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4aaea-110">The TPM solution coupled with the EDI and AS2 support provide a robust and scalable solution for managing trading partners in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4aaea-111">En los temas de esta sección, y en otros temas indicados más abajo, se proporciona información general de alto nivel sobre cómo usar TPM para administrar socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="4aaea-111">The topics in this section, and other topics listed below, provide a high-level overview of TPM and how to use TPM to manage trading partners.</span></span> <span data-ttu-id="4aaea-112">Los temas también proporcionan la descripción de cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realiza el procesamiento de EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="4aaea-112">The topics also provide description of how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performs EDI and AS2 processing.</span></span>  
  
## <a name="in-this-section-and-more-good-info"></a><span data-ttu-id="4aaea-113">En esta sección y la información buena más</span><span class="sxs-lookup"><span data-stu-id="4aaea-113">In this section and more good info</span></span>

<span data-ttu-id="4aaea-114">**Obtenga información acerca de, introducción y los tutoriales**</span><span class="sxs-lookup"><span data-stu-id="4aaea-114">**Learn, get started, and tutorials**</span></span>  

-   [<span data-ttu-id="4aaea-115">Bloques de creación de una solución de administración de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="4aaea-115">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)  
  
-   [<span data-ttu-id="4aaea-116">Funcionalidad de EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4aaea-116">BizTalk Server EDI Functionality</span></span>](../core/biztalk-server-edi-functionality.md)  
  
-   [<span data-ttu-id="4aaea-117">Funcionalidad de AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4aaea-117">BizTalk Server AS2 Functionality</span></span>](../core/biztalk-server-as2-functionality.md)  

- [<span data-ttu-id="4aaea-118">Arquitectura de la solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-118">EDI and AS2 solution architecture</span></span>](../core/edi-and-as2-solution-architecture.md)

-   [<span data-ttu-id="4aaea-119">Pasos posteriores a la configuración para optimizar el entorno</span><span class="sxs-lookup"><span data-stu-id="4aaea-119">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) 

- [<span data-ttu-id="4aaea-120">Tutoriales y visitas guiadas de EDI, AS2 y EDIFACT</span><span class="sxs-lookup"><span data-stu-id="4aaea-120">Tutorials and walkthroughs for EDI, AS2, and EDIFACT</span></span>](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)


<span data-ttu-id="4aaea-121">**En profundidad en la creación de soluciones EDI y AS2**</span><span class="sxs-lookup"><span data-stu-id="4aaea-121">**Deep-dive in creating EDI and AS2 solutions**</span></span>
- [<span data-ttu-id="4aaea-122">Crear artefactos de EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-122">Create EDI and AS2 artifacts</span></span>](../core/managing-edi-and-as2-solutions.md)

- [<span data-ttu-id="4aaea-123">Desarrollar y configurar soluciones EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4aaea-123">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)

- [<span data-ttu-id="4aaea-124">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4aaea-124">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)

-   [<span data-ttu-id="4aaea-125">Ejemplos de EDI y AS2 SDK)</span><span class="sxs-lookup"><span data-stu-id="4aaea-125">EDI and AS2 SDK samples)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  


 <span data-ttu-id="4aaea-126">**Usar archivos de enlace**</span><span class="sxs-lookup"><span data-stu-id="4aaea-126">**Using binding files**</span></span>  

- [<span data-ttu-id="4aaea-127">Usar archivos de enlace para importar o exportar - nuevos en BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="4aaea-127">Use binding files to import or export - NEW in BizTalk Server 2016</span></span>](../core/use-binding-files-to-import-or-export.md)  

-   [<span data-ttu-id="4aaea-128">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-128">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="4aaea-129">Cómo importar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-129">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)  
  
-   [<span data-ttu-id="4aaea-130">Personalizar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="4aaea-130">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  


<span data-ttu-id="4aaea-131">**Supervisar y solucionar problemas**</span><span class="sxs-lookup"><span data-stu-id="4aaea-131">**Monitor and troubleshoot**</span></span>

- [<span data-ttu-id="4aaea-132">Supervisión de soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-132">Monitoring EDI and AS2 Solutions</span></span>](../core/monitoring-edi-and-as2-solutions.md)

- [<span data-ttu-id="4aaea-133">Solución de problemas de soluciones EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="4aaea-133">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)
  
-   <span data-ttu-id="4aaea-134">Ver detalles de la interfaz de usuario[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4aaea-134">View UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
  
-   [<span data-ttu-id="4aaea-135">Errores y eventos de AS2 y EDI</span><span class="sxs-lookup"><span data-stu-id="4aaea-135">EDI and AS2 Events and Errors</span></span>](../core/edi-and-as2-events-and-errors.md)
 


  

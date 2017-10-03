---
title: Ejemplos del SDK | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SDK
- SDK examples
- examples
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42429ed2aa9b6a074a62e472ca804caad676f84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="b5b50-102">Ejemplos del SDK</span><span class="sxs-lookup"><span data-stu-id="b5b50-102">Samples in the SDK</span></span>
## <a name="folder-paths"></a><span data-ttu-id="b5b50-103">Rutas de acceso de carpeta</span><span class="sxs-lookup"><span data-stu-id="b5b50-103">Folder paths</span></span>
<span data-ttu-id="b5b50-104">Esta sección describen más de 30 ejemplos incluidos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Kit de desarrollo de Software (SDK).</span><span class="sxs-lookup"><span data-stu-id="b5b50-104">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="b5b50-105">Además, se proporciona información detallada acerca de cada uno de los ejemplos, incluidas las instrucciones para la generación del ejemplo, cómo ejecutarlo y los resultados que se esperan obtener.</span><span class="sxs-lookup"><span data-stu-id="b5b50-105">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  
  
 <span data-ttu-id="b5b50-106">La documentación de los ejemplos utiliza la abreviatura de ruta de acceso \< *ruta de ejemplos*> para denotar la ruta de acceso a los ejemplos de la instalación.</span><span class="sxs-lookup"><span data-stu-id="b5b50-106">The samples documentation uses the path abbreviation \<*Samples Path*> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="b5b50-107">El valor predeterminado de la ruta de acceso puede variar en función de las decisiones tomadas durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="b5b50-107">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="b5b50-108">En la tabla siguiente se proporciona la ruta de acceso predeterminada para los escenarios comunes de instalación.</span><span class="sxs-lookup"><span data-stu-id="b5b50-108">The following table provides the default path for common installation scenarios.</span></span>  
  
|<span data-ttu-id="b5b50-109">Description</span><span class="sxs-lookup"><span data-stu-id="b5b50-109">Description</span></span>|<span data-ttu-id="b5b50-110">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="b5b50-110">Path</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="b5b50-111">Instalación en una plataforma de 32 bits</span><span class="sxs-lookup"><span data-stu-id="b5b50-111">Installation on 32-bit platform</span></span>|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b5b50-112">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="b5b50-112">\SDK\Samples</span></span>|  
|<span data-ttu-id="b5b50-113">Instalación en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b5b50-113">Installation on a 64-bit platform.</span></span>|[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="b5b50-114">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="b5b50-114">\SDK\Samples</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="b5b50-115">Por cuestión de simplicidad, los ejemplos de este SDK y esta documentación, suponen que va a usar una instalación del programador en un único equipo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b5b50-115">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="b5b50-116">Si no lleva a cabo la instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que algunos ejemplos no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5b50-116">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5b50-117">Todos los elementos de SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se proporcionan en inglés y solo son compatibles con las instalaciones en inglés de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b50-117">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="available-samples"></a><span data-ttu-id="b5b50-118">Ejemplos disponibles</span><span class="sxs-lookup"><span data-stu-id="b5b50-118">Available samples</span></span> 
  
-   [<span data-ttu-id="b5b50-119">Obtener más ejemplos</span><span class="sxs-lookup"><span data-stu-id="b5b50-119">Get More Samples</span></span>](../core/get-more-samples.md)  
  
-   [<span data-ttu-id="b5b50-120">Ejemplos de adaptador: desarrollo</span><span class="sxs-lookup"><span data-stu-id="b5b50-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  
  
-   [<span data-ttu-id="b5b50-121">Ejemplos de adaptadores - uso</span><span class="sxs-lookup"><span data-stu-id="b5b50-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  
  
-   [<span data-ttu-id="b5b50-122">Admin (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-123">Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-124">(Carpeta de ejemplos de BizTalk Server) de supervisión de la actividad de negocio</span><span class="sxs-lookup"><span data-stu-id="b5b50-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-125">Reglas de negocios (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-126">EDI y AS2 (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-127">Mensajería (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-128">Orquestaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-129">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-130">SSO (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="b5b50-131">Herramientas XML (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="b5b50-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)
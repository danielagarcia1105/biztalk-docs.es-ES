---
title: Ejemplos de SDK | Microsoft Docs
description: Adaptador, implementación de aplicaciones, BAM, las reglas de negocios, orquestación, canalización y más ejemplos SDK disponibles en BizTalk Server
ms.custom: ''
ms.date: 10/17/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dc386b29a2b6070a50570080697d2a54ed537b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009461"
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="001e5-103">Ejemplos del SDK</span><span class="sxs-lookup"><span data-stu-id="001e5-103">Samples in the SDK</span></span>

## <a name="folder-paths"></a><span data-ttu-id="001e5-104">Rutas de acceso de carpeta</span><span class="sxs-lookup"><span data-stu-id="001e5-104">Folder paths</span></span>
<span data-ttu-id="001e5-105">Esta sección describen más de 30 ejemplos incluidos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Kit de desarrollo de Software (SDK).</span><span class="sxs-lookup"><span data-stu-id="001e5-105">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="001e5-106">Además, se proporciona información detallada acerca de cada uno de los ejemplos, incluidas las instrucciones para la generación del ejemplo, cómo ejecutarlo y los resultados que se esperan obtener.</span><span class="sxs-lookup"><span data-stu-id="001e5-106">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  

 <span data-ttu-id="001e5-107">La documentación de ejemplos usa la abreviatura de ruta de acceso \< *ruta de ejemplos* \> para denotar la ruta de acceso a los ejemplos de la instalación.</span><span class="sxs-lookup"><span data-stu-id="001e5-107">The samples documentation uses the path abbreviation \<*Samples Path*\> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="001e5-108">El valor predeterminado de la ruta de acceso puede variar en función de las decisiones tomadas durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="001e5-108">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="001e5-109">En la tabla siguiente se proporciona la ruta de acceso predeterminada para los escenarios comunes de instalación.</span><span class="sxs-lookup"><span data-stu-id="001e5-109">The following table provides the default path for common installation scenarios.</span></span>  


|            <span data-ttu-id="001e5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="001e5-110">Description</span></span>             |                                            <span data-ttu-id="001e5-111">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="001e5-111">Path</span></span>                                            |
|------------------------------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="001e5-112">Instalación en una plataforma de 32 bits</span><span class="sxs-lookup"><span data-stu-id="001e5-112">Installation on 32-bit platform</span></span>   |    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="001e5-113">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="001e5-113">\SDK\Samples</span></span>    |
| <span data-ttu-id="001e5-114">Instalación en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="001e5-114">Installation on a 64-bit platform.</span></span> | [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="001e5-115">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="001e5-115">\SDK\Samples</span></span> |

> [!IMPORTANT]
>  <span data-ttu-id="001e5-116">Por cuestión de simplicidad, los ejemplos de este SDK y esta documentación, suponen que va a usar una instalación del programador en un único equipo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="001e5-116">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="001e5-117">Si no lleva a cabo la instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que algunos ejemplos no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="001e5-117">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="001e5-118">Todos los elementos de SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se proporcionan en inglés y solo son compatibles con las instalaciones en inglés de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="001e5-118">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="available-samples"></a><span data-ttu-id="001e5-119">Ejemplos disponibles</span><span class="sxs-lookup"><span data-stu-id="001e5-119">Available samples</span></span> 

-   [<span data-ttu-id="001e5-120">Ejemplos de adaptador: desarrollo</span><span class="sxs-lookup"><span data-stu-id="001e5-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  

-   [<span data-ttu-id="001e5-121">Ejemplos de adaptadores: uso</span><span class="sxs-lookup"><span data-stu-id="001e5-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  

-   [<span data-ttu-id="001e5-122">Admin (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-123">Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-124">Supervisión de la actividad económica (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-125">Reglas de negocio (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-126">EDI y AS2 (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-127">Messaging (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-128">Orquestaciones (carpetas de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-129">Canalizaciones (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-130">SSO (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="001e5-131">Herramientas XML (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="001e5-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)
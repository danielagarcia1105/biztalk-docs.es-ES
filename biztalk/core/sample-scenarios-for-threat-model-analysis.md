---
title: Análisis de modelo de escenario de muestra de amenaza | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, security
- security examples [TMA]
- TMA, examples
- examples, TMA
ms.assetid: e35d1d7f-a71a-42f5-b1f4-fe3234ba7686
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc1e375945ec7b40c56274adc5e18cb1ee67f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269116"
---
# <a name="sample-scenarios-for-threat-model-analysis"></a><span data-ttu-id="94465-102">Escenarios de ejemplo para el análisis del modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="94465-102">Sample Scenarios for Threat Model Analysis</span></span>
<span data-ttu-id="94465-103">Esta sección proporciona los pasos y resultados de un análisis de modelo de amenaza (TMA) para cada escenario de uso de la arquitectura de ejemplo identificada en [arquitecturas de ejemplo para pequeñas y compañías de Medium-Sized](../core/sample-architectures-for-small-medium-sized-companies.md).</span><span class="sxs-lookup"><span data-stu-id="94465-103">This section provides the steps and results of a threat model analysis (TMA) for each usage scenario for the sample architecture identified in [Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md).</span></span> <span data-ttu-id="94465-104">El objeto de esta sección es mostrarle los pasos de un TMA.</span><span class="sxs-lookup"><span data-stu-id="94465-104">The purpose of this section is to show you the steps of a TMA.</span></span> <span data-ttu-id="94465-105">El contenido de esta sección le ayudará a comprender el funcionamiento de un TMA; incluye una descripción de las amenazas potenciales que identificamos en la aplicación de ejemplo y ofrece recomendaciones para reducir sus efectos.</span><span class="sxs-lookup"><span data-stu-id="94465-105">This helps you understand how a TMA works, and describes for you the potential threats we identified for the sample architecture and how we recommend that you reduce their effect.</span></span>  
  
 <span data-ttu-id="94465-106">Los escenarios de uso se clasifican en función de los distintos adaptadores que se pueden utilizar en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el uso del inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="94465-106">We categorize the usage scenarios based on the different adapters you can use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and the use of Enterprise Single-Sign On.</span></span>  
  
 <span data-ttu-id="94465-107">En cada escenario, seguimos los pasos que se indican a continuación para completar el análisis del modelo de amenazas:</span><span class="sxs-lookup"><span data-stu-id="94465-107">For each scenario, we followed these steps to complete the Threat Model Analysis:</span></span>  
  
-   <span data-ttu-id="94465-108">Recopilar información general</span><span class="sxs-lookup"><span data-stu-id="94465-108">Collect background information</span></span>  
  
-   <span data-ttu-id="94465-109">Crear y analizar el modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="94465-109">Create and analyze the threat model</span></span>  
  
-   <span data-ttu-id="94465-110">Analizar las amenazas</span><span class="sxs-lookup"><span data-stu-id="94465-110">Review threats</span></span>  
  
-   <span data-ttu-id="94465-111">Identificar las tecnologías y técnicas de mitigación</span><span class="sxs-lookup"><span data-stu-id="94465-111">Identify mitigation techniques and technologies</span></span>  
  
 <span data-ttu-id="94465-112">Para obtener más información análisis de modelo de amenazas, consulte [análisis de modelo de amenazas](../core/threat-model-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="94465-112">For more information Threat Model Analysis, see [Threat Model Analysis](../core/threat-model-analysis.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94465-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="94465-113">In This Section</span></span>  
  
-   [<span data-ttu-id="94465-114">Información general acerca de escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="94465-114">Background Information for Sample Scenarios</span></span>](../core/background-information-for-sample-scenarios.md)  
  
-   [<span data-ttu-id="94465-115">TMA de ejemplo: Los adaptadores SOAP y HTTP</span><span class="sxs-lookup"><span data-stu-id="94465-115">Sample TMA: HTTP and SOAP Adapters</span></span>](../core/sample-tma-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="94465-116">TMA de ejemplo: El adaptador de BizTalk para Message Queue</span><span class="sxs-lookup"><span data-stu-id="94465-116">Sample TMA: BizTalk Message Queuing Adapter</span></span>](../core/sample-tma-biztalk-message-queuing-adapter.md)  
  
-   [<span data-ttu-id="94465-117">TMA de ejemplo: Adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="94465-117">Sample TMA: File Adapter</span></span>](../core/sample-tma-file-adapter.md)  
  
-   [<span data-ttu-id="94465-118">TMA de ejemplo: Adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="94465-118">Sample TMA: FTP Adapter</span></span>](../core/sample-tma-ftp-adapter.md)  
  
-   [<span data-ttu-id="94465-119">TMA de ejemplo: Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="94465-119">Sample TMA: Enterprise Single Sign-On</span></span>](../core/sample-tma-enterprise-single-sign-on.md)
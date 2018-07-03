---
title: Ejecución del ejemplo de servicio de resolución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c569f0be544292b4a70d49f4c75a038e2fed65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006677"
---
# <a name="running-the-resolver-service-sample"></a><span data-ttu-id="e9eb3-102">Ejecución del ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="e9eb3-102">Running the Resolver Service Sample</span></span>
<span data-ttu-id="e9eb3-103">El ejemplo de servicio de resolución muestra los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="e9eb3-103">The Resolver Service sample demonstrates the following scenarios:</span></span>  

- <span data-ttu-id="e9eb3-104">Resolver un URI de UDDI3 mediante una clave de enlace del extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="e9eb3-104">Resolve a service endpoint URI from UDDI3 using a binding key</span></span>  

- <span data-ttu-id="e9eb3-105">Resolver un URI de UDDI3 mediante una búsqueda de categorización del extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="e9eb3-105">Resolve a service endpoint URI from UDDI3 using a categorization search</span></span>  

- <span data-ttu-id="e9eb3-106">Resolver una transformación (tipo de asignación de BizTalk) con una resolución estática</span><span class="sxs-lookup"><span data-stu-id="e9eb3-106">Resolve a transformation (BizTalk Map type) using a STATIC resolver</span></span>  

- <span data-ttu-id="e9eb3-107">Resolver un punto de conexión de servicio URI con una resolución estática</span><span class="sxs-lookup"><span data-stu-id="e9eb3-107">Resolve a service endpoint URI using a STATIC resolver</span></span>  

- <span data-ttu-id="e9eb3-108">Resolver un punto de conexión de servicio URI utilizando una expresión XPath</span><span class="sxs-lookup"><span data-stu-id="e9eb3-108">Resolve a service endpoint URI using an XPath expression</span></span>  

- <span data-ttu-id="e9eb3-109">Resolver un itinerario mediante una resolución estática de itinerario</span><span class="sxs-lookup"><span data-stu-id="e9eb3-109">Resolve an itinerary using a static ITINERARY resolver</span></span>  

- <span data-ttu-id="e9eb3-110">Resolver un itinerario mediante un solucionador de itinerario estático (Unity)</span><span class="sxs-lookup"><span data-stu-id="e9eb3-110">Resolve an itinerary using an ITINERARY-STATIC (Unity) resolver</span></span>  

- <span data-ttu-id="e9eb3-111">Resolver un itinerario mediante BRE (BRI resolución)</span><span class="sxs-lookup"><span data-stu-id="e9eb3-111">Resolve an itinerary using BRE (BRI Resolver)</span></span>  

- <span data-ttu-id="e9eb3-112">Resolver un itinerario mediante BRE (resolución BRI) con el mensaje</span><span class="sxs-lookup"><span data-stu-id="e9eb3-112">Resolve an Itinerary using BRE (BRI Resolver) with the Message</span></span>  

- <span data-ttu-id="e9eb3-113">Resolver un identificador URI del extremo de servicio con el BRE</span><span class="sxs-lookup"><span data-stu-id="e9eb3-113">Resolve a service endpoint URI using BRE</span></span>  

- <span data-ttu-id="e9eb3-114">Resolver una transformación mediante BRE</span><span class="sxs-lookup"><span data-stu-id="e9eb3-114">Resolve a transformation using BRE</span></span>  

  <span data-ttu-id="e9eb3-115">**Para ejecutar todos los escenarios de resolución mediante la implementación de ASMX, el servicio de resolución**</span><span class="sxs-lookup"><span data-stu-id="e9eb3-115">**To run all the resolution scenarios using the ASMX implementation of the Resolver service**</span></span>  

1. <span data-ttu-id="e9eb3-116">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-116">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  

2. <span data-ttu-id="e9eb3-117">En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_ASMX.cmd.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-117">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_ASMX.cmd.</span></span>  

3. <span data-ttu-id="e9eb3-118">Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-118">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>  

   <span data-ttu-id="e9eb3-119">**Para ejecutar todos los escenarios de resolución mediante la implementación de WCF del servicio de resolución**</span><span class="sxs-lookup"><span data-stu-id="e9eb3-119">**To run all the resolution scenarios using the WCF implementation of the Resolver service**</span></span>  

4. <span data-ttu-id="e9eb3-120">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-120">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  

5. <span data-ttu-id="e9eb3-121">En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_WCF.cmd.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-121">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_WCF.cmd.</span></span>  

6. <span data-ttu-id="e9eb3-122">Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e9eb3-122">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>

---
title: ¿Qué es una agregación? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24dced4d7075e85b8b002bf90b821ce745f91e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289164"
---
# <a name="what-is-an-aggregation"></a><span data-ttu-id="df2b7-103">¿Qué es una agregación?</span><span class="sxs-lookup"><span data-stu-id="df2b7-103">What Is an Aggregation?</span></span>
<span data-ttu-id="df2b7-104">Excel define las agregaciones como resúmenes de datos precalculados que mejoran el tiempo de respuesta de consultas al tener preparadas las respuestas antes de que se planteen las preguntas.</span><span class="sxs-lookup"><span data-stu-id="df2b7-104">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="df2b7-105">Por ejemplo, cuando una tabla de hechos de almacén de datos contiene cientos de miles de filas, una consulta que solicita las programaciones de envío de dos productos en concreto puede tardar en responder si la tabla de hechos se tiene que analizar para calcular la respuesta.</span><span class="sxs-lookup"><span data-stu-id="df2b7-105">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="df2b7-106">Sin embargo, la respuesta podría ser casi inmediata si los datos de resumen para responder a esta consulta se ha calculado previamente.</span><span class="sxs-lookup"><span data-stu-id="df2b7-106">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="df2b7-107">En la siguiente ilustración se muestra un ejemplo de los datos de agregación precalculados.</span><span class="sxs-lookup"><span data-stu-id="df2b7-107">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="df2b7-108">Cubo OLAP de BAM</span><span class="sxs-lookup"><span data-stu-id="df2b7-108">BAM OLAP Cube</span></span>  
  
 <span data-ttu-id="df2b7-109">En la ilustración anterior se proporciona un resumen de los números de cada producto, enviados a las ubicaciones determinadas durante un período de tiempo de dos meses.</span><span class="sxs-lookup"><span data-stu-id="df2b7-109">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="df2b7-110">Excel normalmente define estos datos como medida.</span><span class="sxs-lookup"><span data-stu-id="df2b7-110">Excel typically defines this data as measure.</span></span> <span data-ttu-id="df2b7-111">Excel define como dimensión los datos que se usan para el filtrado y la categorización.</span><span class="sxs-lookup"><span data-stu-id="df2b7-111">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="df2b7-112">Para saber más acerca de la experiencia del usuario cuando examina datos multidimensionales, consulte el tema relativo a las tablas dinámicas en la Ayuda de Excel.</span><span class="sxs-lookup"><span data-stu-id="df2b7-112">For the user experience of browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
 <span data-ttu-id="df2b7-113">Puede crear agregaciones de actividad multidimensionales que estén basadas en los datos disponibles en una vista específica.</span><span class="sxs-lookup"><span data-stu-id="df2b7-113">You can create multidimensional activity aggregations based on the data available in a specific view.</span></span> <span data-ttu-id="df2b7-114">Aquellas agregaciones contienen medidas (datos que se van a agregar, como la cantidad de dólares) y dimensiones (que se utilizan para filtrar o agrupar, como Estado y Ciudad).</span><span class="sxs-lookup"><span data-stu-id="df2b7-114">Those aggregations contain measures (data to aggregate, such as dollar amount) and dimensions (used for filtering or grouping, such as State and City).</span></span>  
  
 <span data-ttu-id="df2b7-115">Puede crear las agregaciones en forma de cubos de procesamiento analítico en línea (OLAP) que representen una instantánea del negocio a una hora determinada o como agregaciones en tiempo real, que determinan el escenario empresarial y que puede ver si utiliza la estructura multidimensional en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="df2b7-115">You can create the aggregations in the form of online analytical processing (OLAP) cubes, which represent a snapshot of the business at a specific time, or as real-time aggregations, which the business scenario determines and you see using the multidimensional structure in real time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df2b7-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="df2b7-116">In This Section</span></span>  
  
-   [<span data-ttu-id="df2b7-117">Agregaciones programadas</span><span class="sxs-lookup"><span data-stu-id="df2b7-117">Scheduled Aggregations</span></span>](../core/scheduled-aggregations.md)  
  
-   [<span data-ttu-id="df2b7-118">Agregaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="df2b7-118">Real-Time Aggregations</span></span>](../core/real-time-aggregations.md)
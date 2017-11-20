---
title: "Definición de agregaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3412615d03fc9a9776d86fddfb062ab343c5aaeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-aggregations"></a><span data-ttu-id="f7dd0-102">Definir agregaciones</span><span class="sxs-lookup"><span data-stu-id="f7dd0-102">Defining Aggregations</span></span>
<span data-ttu-id="f7dd0-103">Excel define **agregaciones** como resúmenes precalculados de datos que mejoran el tiempo de respuesta de consulta debido a las respuestas listo antes de que se planteen las preguntas.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-103">Excel defines **aggregations** as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="f7dd0-104">Por ejemplo, cuando una tabla de hechos de almacén de datos contiene cientos de miles de filas, una consulta que solicita las programaciones de envío de dos productos en concreto puede tardar en responder si la tabla de hechos se tiene que analizar para calcular la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-104">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="f7dd0-105">Sin embargo, la respuesta podría ser casi inmediata si los datos de resumen para responder a esta consulta se ha calculado previamente.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-105">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="f7dd0-106">En la siguiente ilustración se muestra un ejemplo de los datos de agregación precalculados.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-106">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="f7dd0-107">Datos de agregación precalculados</span><span class="sxs-lookup"><span data-stu-id="f7dd0-107">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="f7dd0-108">En la ilustración anterior se proporciona un resumen de los números de cada producto, enviados a las ubicaciones determinadas durante un período de tiempo de dos meses.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-108">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="f7dd0-109">Excel normalmente define estos datos como **medida**.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-109">Excel typically defines this data as **measure**.</span></span> <span data-ttu-id="f7dd0-110">Los datos utilizados para el filtrado y categorización, Excel define como **dimensión**.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-110">The data used for filtering and categorization, Excel defines as **dimension**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7dd0-111">BAM no admite el uso de instancias con nombre para los servicios de análisis de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7dd0-111">BAM does not support using named instances for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services.</span></span>  
  
 <span data-ttu-id="f7dd0-112">Para saber más acerca de la experiencia del usuario al examinar datos multidimensionales, consulte el tema sobre tablas dinámicas de la Ayuda de Excel.</span><span class="sxs-lookup"><span data-stu-id="f7dd0-112">For the user experience of browsing multidimensional data, see the Pivot table topic in Excel Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7dd0-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f7dd0-113">In This Section</span></span>  
  
-   [<span data-ttu-id="f7dd0-114">Cómo definir medidas</span><span class="sxs-lookup"><span data-stu-id="f7dd0-114">How to Define Measures</span></span>](../core/how-to-define-measures.md)  
  
-   [<span data-ttu-id="f7dd0-115">Definir dimensiones</span><span class="sxs-lookup"><span data-stu-id="f7dd0-115">Defining Dimensions</span></span>](../core/defining-dimensions.md)  
  
-   [<span data-ttu-id="f7dd0-116">Cómo utilizar la tabla dinámica</span><span class="sxs-lookup"><span data-stu-id="f7dd0-116">How to Use the PivotTable</span></span>](../core/how-to-use-the-pivottable.md)  
  
-   [<span data-ttu-id="f7dd0-117">Definición de agregaciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="f7dd0-117">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a><span data-ttu-id="f7dd0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7dd0-118">See Also</span></span>  
 [<span data-ttu-id="f7dd0-119">Definir una vista de SAE</span><span class="sxs-lookup"><span data-stu-id="f7dd0-119">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)
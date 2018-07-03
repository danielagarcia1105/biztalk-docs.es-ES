---
title: ¿Qué son medidas y dimensiones? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6b12a4c-9be5-4cac-b5b9-ece376d28cb1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb494246741699dfdbdab704c8fca0a3c9d55301
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994349"
---
# <a name="what-are-measures-and-dimensions"></a><span data-ttu-id="d909f-103">¿Qué son medidas y dimensiones?</span><span class="sxs-lookup"><span data-stu-id="d909f-103">What Are Measures and Dimensions?</span></span>
<span data-ttu-id="d909f-104">Las dimensiones y las medidas son los aspectos físicos de la agregación de datos.</span><span class="sxs-lookup"><span data-stu-id="d909f-104">Dimensions and measures are the physical aspects of data aggregation.</span></span> <span data-ttu-id="d909f-105">En este tema se definen los conceptos de medidas y dimensiones en el contexto de un escenario de BAM.</span><span class="sxs-lookup"><span data-stu-id="d909f-105">This topic describes what measures and dimensions are, using a BAM scenario to provide context.</span></span>  
  
## <a name="measures"></a><span data-ttu-id="d909f-106">medidas</span><span class="sxs-lookup"><span data-stu-id="d909f-106">Measures</span></span>  
 <span data-ttu-id="d909f-107">Suponga que define una actividad de BAM para un proceso de administración de pedidos en términos sumamente simples, con tres elementos:</span><span class="sxs-lookup"><span data-stu-id="d909f-107">Suppose that you define a BAM activity for an order management process in extremely simple terms consisting of three items:</span></span>  
  
1. <span data-ttu-id="d909f-108">Hora de inicio del proceso (un evento del mundo real)</span><span class="sxs-lookup"><span data-stu-id="d909f-108">Process start time (an event in the real world)</span></span>  
  
2. <span data-ttu-id="d909f-109">Hora de fin del proceso (otro evento real)</span><span class="sxs-lookup"><span data-stu-id="d909f-109">Process end time (also a real-world event)</span></span>  
  
3. <span data-ttu-id="d909f-110">Duración del proceso (calculada sustrayendo 1 a 2)</span><span class="sxs-lookup"><span data-stu-id="d909f-110">Process duration (a calculation of #2 - #1)</span></span>  
  
   <span data-ttu-id="d909f-111">En este caso agregar datos consiste simplemente en aplicar una función de agregación (por ejemplo promedio, mínimo, máximo, etc.) a una serie de valores de duración individuales (es decir la duración de procesamiento de cada pedido).</span><span class="sxs-lookup"><span data-stu-id="d909f-111">Aggregating data in this case is simply a matter of applying an aggregation function (for example, average, minimum, maximum, etc.) to a series of individual duration values (that is, the processing duration for each order).</span></span>  
  
   <span data-ttu-id="d909f-112">El concepto de "duración promedio" es una medida y un valor individual.</span><span class="sxs-lookup"><span data-stu-id="d909f-112">The concept of "average duration" is a measure, and it is a single value.</span></span> <span data-ttu-id="d909f-113">Por sí misma, esta medida produce información relevante para la administración de procesos en el sentido de que indica si el proceso global funciona (en cuanto a precisión/rendimiento) de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="d909f-113">By itself, this measure yields information relevant to process management in that it indicates whether or not the process overall is behaving (in terms of timliness/throughput) as expected.</span></span> <span data-ttu-id="d909f-114">No obstante, en ausencia de otros datos (ya que la "duración promedio" es un solo valor) es más difícil comprender el significado del valor real de la medida. Por ejemplo, ¿por qué hubo un aumento anormal de la duración esta semana?</span><span class="sxs-lookup"><span data-stu-id="d909f-114">However, in the absence of any other data (because "average duration" is a single value), understanding the meaning of the measure's actual value is harder For example, why did we have a spike in average duration this week?</span></span> <span data-ttu-id="d909f-115">¿Fue debido a un socio, un programa o un producto concretos?</span><span class="sxs-lookup"><span data-stu-id="d909f-115">Was it due to a particular partner, program, product?</span></span>  
  
## <a name="dimensions"></a><span data-ttu-id="d909f-116">Dimensions</span><span class="sxs-lookup"><span data-stu-id="d909f-116">Dimensions</span></span>  
 <span data-ttu-id="d909f-117">Las dimensiones son el contexto que ayuda al consumidor de medidas a entender el significado de éstas.</span><span class="sxs-lookup"><span data-stu-id="d909f-117">Dimensions are the context that help the consumer of measures understand the meaning of those measures.</span></span>  
  
 <span data-ttu-id="d909f-118">Siguiendo con el ejemplo anterior, suponga que agrega tres elementos más a la actividad de BAM para el proceso de administración del pedido:</span><span class="sxs-lookup"><span data-stu-id="d909f-118">Continuing the above example, suppose you add three additional items to the BAM activity for the order management process:</span></span>  
  
1. <span data-ttu-id="d909f-119">Nombre del socio comercial (el que hizo el pedido)</span><span class="sxs-lookup"><span data-stu-id="d909f-119">trading partner name (who sent the order)</span></span>  
  
2. <span data-ttu-id="d909f-120">Nombre del responsable comercial (el contacto de ventas)</span><span class="sxs-lookup"><span data-stu-id="d909f-120">account manager name (who is the sales contact)</span></span>  
  
3. <span data-ttu-id="d909f-121">Región de venta</span><span class="sxs-lookup"><span data-stu-id="d909f-121">sales region</span></span>  
  
   <span data-ttu-id="d909f-122">Como la actividad ahora incluye tres posibles tablas dinámicas de datos (socio, responsable comercial y región), la agregación de estos datos resulta literalmente en la creación de un cubo tridimensional en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d909f-122">Since the activity now includes three possible data pivots (partner, account manager, region), aggregating this data now literally results in the creation of a three-dimensional cube at run-time.</span></span>  
  
   <span data-ttu-id="d909f-123">Sigue comenzando con el primer elemento de trabajo, lo que crea una medida "duración promedio" individual.</span><span class="sxs-lookup"><span data-stu-id="d909f-123">It still begins with the first item of work, resulting in the creation of a single "average duration" measure.</span></span> <span data-ttu-id="d909f-124">Al finalizar el siguiente elemento de trabajo (iniciado por la llegada de otro pedido), si el socio comercial, el responsable comercial y la región son los mismos que para el primer elemento, todo lo que ocurre es que se vuelve a calcular la medida de "duración promedio", ahora a partir de los dos elementos (por ejemplo, el promedio de las dos duraciones) para obtener un solo valor de medida de "duración promedio".</span><span class="sxs-lookup"><span data-stu-id="d909f-124">When the next item of work (initiated by the arrival of another purchase order) completes, if trading partner, account manager, and region are all the same as they were for the first item of work, then all that happens is that the "average duration" measure is recalculated, based now on two items (for example, the average of the two durations), to achieve a single "average duration" measure value.</span></span>  
  
   <span data-ttu-id="d909f-125">En cuanto se recibe un elemento cuyo socio comercial, responsable comercial o región son diferentes de los anteriores, se crea un nuevo valor de medida de "duración promedio" que se mantiene aparte del primero.</span><span class="sxs-lookup"><span data-stu-id="d909f-125">As soon as an item comes where any of trading partner, account manager, or region are different than the set encountered so far, a new "average duration" measure value is created and maintained separate from the first one.</span></span>  
  
   <span data-ttu-id="d909f-126">Por ejemplo, si el socio comercial del tercer elemento de trabajo es diferente de los dos anteriores, el resultado es la creación de un segundo valor de medida de "duración promedio" a lo largo de la dimensión de socio comercial.</span><span class="sxs-lookup"><span data-stu-id="d909f-126">For example, if the trading partner on the third item of work was different than the previous two, the result is creation of a second "average duration" measure value along the trading partner dimension.</span></span> <span data-ttu-id="d909f-127">Ahora puede revisar los valores de "duración promedio" a lo largo de la dimensión de socio comercial, y ver aspectos tales como: "de promedio, se tarda casi el doble en procesar los pedidos de SocioComercialX respecto de los de SocioComercialY".</span><span class="sxs-lookup"><span data-stu-id="d909f-127">Now you can review "average duration" values along the trading partner dimension and see things like "it takes us almost twice as long on average to process the orders from TradingPartnerX as it does for TradingPartnerY."</span></span> <span data-ttu-id="d909f-128">Asimismo, las dimensiones pueden contraerse para su visualización para poder seguir viendo la "duración promedio" global del proceso, independientemente de cualquier socio comercial o de otra dimensión.</span><span class="sxs-lookup"><span data-stu-id="d909f-128">And dimensions can be collapsed for viewing so that one can still see the overall "average duration" for the process independent of any trading partner or other dimension.</span></span>  
  
   <span data-ttu-id="d909f-129">Finalmente, si el socio comercial, el responsable comercial y la región tienen cada uno tres y sólo tres valores diferentes, una vez realizadas todas las permutaciones el resultado es un Cubo de Rubik® de datos, en el que los usuarios pueden ver cada uno de los 27 valores de "duración promedio" mantenidos de forma independiente y las dimensiones son tres aristas del cubo.</span><span class="sxs-lookup"><span data-stu-id="d909f-129">Finally, if trading partner, account manager, and region each have three and only three distinct values, once all permutations have occurred, the result is a Rubik's® Cube of data, where users can view each of 27 independently maintained "average duration" values, and the dimensions are each of three edges on the cube.</span></span>  
  
   <span data-ttu-id="d909f-130">Para obtener más información acerca de dimensiones y medidas, vea el tema sobre los datos de origen de OLAP en informes de tablas dinámicas y de gráficos dinámicos de la Ayuda de Excel.</span><span class="sxs-lookup"><span data-stu-id="d909f-130">For additional information about dimensions and measures, see "About OLAP source data in PivotTable and PivotChart reports" in Excel Help.</span></span>
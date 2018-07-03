---
title: Prueba de carga sostenible | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d8d38323f7933c8e60cb2b87e0ec312d270c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015653"
---
# <a name="sustainable-load-test"></a><span data-ttu-id="23dd4-102">Prueba de carga sostenible</span><span class="sxs-lookup"><span data-stu-id="23dd4-102">Sustainable Load Test</span></span>
<span data-ttu-id="23dd4-103">La información de este tema hace referencia a las pruebas se explica en [escenarios de prueba para medir MST del motor](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span><span class="sxs-lookup"><span data-stu-id="23dd4-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="23dd4-104">Para la primera prueba, el sistema se colocó en estado MST para que se pudiesen realizar observaciones de un sistema en buen estado.</span><span class="sxs-lookup"><span data-stu-id="23dd4-104">For the first test, the system was driven to MST so that observations of a healthy system can be made.</span></span>  
  
 <span data-ttu-id="23dd4-105">El siguiente gráfico muestra los indicadores principales después de utilizar este enfoque para hallar el rendimiento sostenible máximo del sistema de prueba.</span><span class="sxs-lookup"><span data-stu-id="23dd4-105">The following graph shows key indicators after using this approach to find the maximum sustainable throughput of the test system.</span></span>  
  
 <span data-ttu-id="23dd4-106">**Perfil de carga de prueba de carga sostenible**</span><span class="sxs-lookup"><span data-stu-id="23dd4-106">**Load profile of sustainable load test**</span></span>  
  
 <span data-ttu-id="23dd4-107">![Monitor de sistema de medición de carga sostenible](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span><span class="sxs-lookup"><span data-stu-id="23dd4-107">![Performance monitor measuring sustainable load](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span></span>  
  
 <span data-ttu-id="23dd4-108">Este gráfico muestra que, durante la hora de la prueba, la profundidad de la cola fue estable y no creció:</span><span class="sxs-lookup"><span data-stu-id="23dd4-108">This graph shows that, for the hour of the test, the spool depth was stable and not growing:</span></span>  
  
- <span data-ttu-id="23dd4-109">Las líneas negras situadas en la parte superior del gráfico indican el total de mensajes recibidos por segundo en el sistema (por ejemplo, en los dos servidores de recepción).</span><span class="sxs-lookup"><span data-stu-id="23dd4-109">The black lines at the top of the graph show the total messages received per second by the system (for example, for both of the receiving servers).</span></span>  
  
- <span data-ttu-id="23dd4-110">Las líneas que se encuentran en la parte inferior del gráfico especifican la profundidad de la cola del cuadro de mensajes en cada uno de los servidores SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23dd4-110">The lines at the bottom of the graph indicate the MessageBox spool depth on each of the SQL Servers.</span></span>  
  
  <span data-ttu-id="23dd4-111">Una vez que el sistema alcanza el punto máximo de profundidad de cola estable, se mide el valor MST mediante el número de mensajes recibidos por segundo.</span><span class="sxs-lookup"><span data-stu-id="23dd4-111">Once the system is driven to the point of the maximum stable spool depth, MST is measured by the number of messages received per second.</span></span> <span data-ttu-id="23dd4-112">Para este escenario y con el hardware descrito, se logró un valor MST de 290 mensajes por segundo.</span><span class="sxs-lookup"><span data-stu-id="23dd4-112">For this scenario, on the hardware described, an MST of 290 messages per second was achieved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23dd4-113">Cuando el sistema alcanza un punto en el que la profundidad de la cola deja de ser estable en el tiempo significa que se ha superado el valor MST.</span><span class="sxs-lookup"><span data-stu-id="23dd4-113">Once the system is driven to a point where the spool depth is no longer stable over time, MST has been exceeded.</span></span> <span data-ttu-id="23dd4-114">Es posible que sea necesario llevar a cabo varias ejecuciones de prueba con distinta carga para evaluar la carga máxima con la que la profundidad de la cola se mantiene estable y con la que el sistema puede controlar el registro de mensajes sin incurrir en un registro adicional de mensajes.</span><span class="sxs-lookup"><span data-stu-id="23dd4-114">Several test runs with varying load may be required to evaluate the maximum load at which spool depth remains stable and your system can handle the message backlog without incurring additional message backlog.</span></span>  
  
 <span data-ttu-id="23dd4-115">Cualquier análisis de rendimiento de una implementación de BizTalk debe incluir una comprobación de algunos indicadores clave para comprender los cuellos de botella de recursos.</span><span class="sxs-lookup"><span data-stu-id="23dd4-115">Part of any analysis of a BizTalk deployment performance should include checking some key indicators to understand resource bottlenecks.</span></span> <span data-ttu-id="23dd4-116">Las medidas clave y los valores correspondientes utilizados en esta implementación ejecutada con el rendimiento sostenible máximo fueron los siguientes:</span><span class="sxs-lookup"><span data-stu-id="23dd4-116">The key measures and their values used for this deployment running under maximum sustainable throughput were as follows:</span></span>  
  
 <span data-ttu-id="23dd4-117">**Uso de CPU**</span><span class="sxs-lookup"><span data-stu-id="23dd4-117">**CPU Utilization**</span></span>  
  
|<span data-ttu-id="23dd4-118">Servidor</span><span class="sxs-lookup"><span data-stu-id="23dd4-118">Server</span></span>|<span data-ttu-id="23dd4-119">Uso promedio de la CPU</span><span class="sxs-lookup"><span data-stu-id="23dd4-119">Average CPU Utilization</span></span>|  
|------------|-----------------------------|  
|<span data-ttu-id="23dd4-120">Servidores BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="23dd4-120">BizTalk Servers</span></span>|<span data-ttu-id="23dd4-121">55%</span><span class="sxs-lookup"><span data-stu-id="23dd4-121">55%</span></span>|  
|<span data-ttu-id="23dd4-122">Servidor SQL Server (servidor de cuadro de mensajes principal)</span><span class="sxs-lookup"><span data-stu-id="23dd4-122">SQL Server (Master MessageBox Server)</span></span>|<span data-ttu-id="23dd4-123">76%</span><span class="sxs-lookup"><span data-stu-id="23dd4-123">76%</span></span>|  
|<span data-ttu-id="23dd4-124">Servidor SQL Server (otros servidores de cuadro de mensajes)</span><span class="sxs-lookup"><span data-stu-id="23dd4-124">SQL Server (Other MessageBox Servers)</span></span>|<span data-ttu-id="23dd4-125">83%</span><span class="sxs-lookup"><span data-stu-id="23dd4-125">83%</span></span>|  
  
 <span data-ttu-id="23dd4-126">**Tiempo de inactividad de disco físico**</span><span class="sxs-lookup"><span data-stu-id="23dd4-126">**Physical Disk Idle Time**</span></span>  
  
|<span data-ttu-id="23dd4-127">Servidor</span><span class="sxs-lookup"><span data-stu-id="23dd4-127">Server</span></span>|<span data-ttu-id="23dd4-128">Promedio de tiempo de inactividad del disco</span><span class="sxs-lookup"><span data-stu-id="23dd4-128">Average Disk Idle Time</span></span>|  
|------------|----------------------------|  
|<span data-ttu-id="23dd4-129">Promedio para todos los servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="23dd4-129">Average for all SQL Servers</span></span>|<span data-ttu-id="23dd4-130">69%</span><span class="sxs-lookup"><span data-stu-id="23dd4-130">69%</span></span>|  
  
 <span data-ttu-id="23dd4-131">**Bloqueos de SQL en SQL Server**</span><span class="sxs-lookup"><span data-stu-id="23dd4-131">**SQL Locks on SQL Server**</span></span>  
  
|<span data-ttu-id="23dd4-132">Parámetro</span><span class="sxs-lookup"><span data-stu-id="23dd4-132">Parameter</span></span>|<span data-ttu-id="23dd4-133">Valor</span><span class="sxs-lookup"><span data-stu-id="23dd4-133">Value</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="23dd4-134">Promedio de total de tiempos de espera de bloqueos por segundo (por servidor SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23dd4-134">Average Total Lock Timeouts per second (per SQL Server)</span></span>|<span data-ttu-id="23dd4-135">1980</span><span class="sxs-lookup"><span data-stu-id="23dd4-135">1980</span></span>|  
|<span data-ttu-id="23dd4-136">Promedio de total de tiempo de espera de bloqueos (ms)</span><span class="sxs-lookup"><span data-stu-id="23dd4-136">Average Total Lock Wait Time (ms)</span></span>|<span data-ttu-id="23dd4-137">495</span><span class="sxs-lookup"><span data-stu-id="23dd4-137">495</span></span>|  
  
 <span data-ttu-id="23dd4-138">Durante esta prueba, no se generaron errores en el registro de la aplicación de BizTalk o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23dd4-138">During this test no errors were generated in the BizTalk or SQL Server application log.</span></span>  
  
 <span data-ttu-id="23dd4-139">A partir de estos datos se pueden extraer las siguientes conclusiones:</span><span class="sxs-lookup"><span data-stu-id="23dd4-139">From this data, we can draw the following conclusions:</span></span>  
  
- <span data-ttu-id="23dd4-140">No existen cuellos de botella de recursos obvios en el sistema.</span><span class="sxs-lookup"><span data-stu-id="23dd4-140">There are no obvious resource bottlenecks in our system.</span></span>  
  
- <span data-ttu-id="23dd4-141">Todos los indicadores se encuentran dentro de los límites de buen estado de funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="23dd4-141">All of these indicators are well within healthy limits.</span></span>  
  
- <span data-ttu-id="23dd4-142">Los tiempos de inactividad de la CPU y del disco ponen de manifiesto que existe una elevada capacidad y ni tan siquiera se aproximan a valores críticos.</span><span class="sxs-lookup"><span data-stu-id="23dd4-142">CPU and Disk Idle Times show that there is plenty of headroom and they are not even close to being pegged.</span></span>  
  
- <span data-ttu-id="23dd4-143">Los indicadores de bloqueo SQL se ven bien, **tiempos de espera de bloqueo/s** no empieza a ser un problema hasta alrededor de 5000 ó es así (dependiendo de su servidor SQL Server) y espera de bloqueo de horas de menos de 1 segundo también están en buen estado.</span><span class="sxs-lookup"><span data-stu-id="23dd4-143">The SQL lock indicators look good, **Lock Timeouts/sec** doesn’t start to become an issue until around 5000 or so (depending on your SQL Server) and Lock Wait times under 1 second are also healthy.</span></span>  
  
  <span data-ttu-id="23dd4-144">Tras haber demostrado cómo hallar el rendimiento sostenible máximo y haber visto cuáles son los valores de los indicadores clave en un sistema sostenible en buen estado, examinaremos algunos comportamientos asociados con un sistema que recibe más rápido de lo que procesa y que recopila elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="23dd4-144">Now that we have shown how to find the maximum sustainable throughput and seen what the key indicators look like for a sustainable, healthy system, let’s explore some behavior associated with a system that is receiving faster than it is processing and collecting garbage.</span></span> <span data-ttu-id="23dd4-145">Continúe con [sobrecarga (porcentaje) prueba de carga](../core/overdrive-load-test.md).</span><span class="sxs-lookup"><span data-stu-id="23dd4-145">Proceed to [Overdrive Load Test](../core/overdrive-load-test.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dd4-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="23dd4-146">See Also</span></span>  
 <span data-ttu-id="23dd4-147">[Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="23dd4-147">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="23dd4-148">Prueba de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="23dd4-148">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)
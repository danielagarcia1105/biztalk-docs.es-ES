---
title: Prueba de carga de control de tráfico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74954d8b94207832ceee5bbb699a7de1a245f61b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246212"
---
# <a name="floodgate-load-test"></a><span data-ttu-id="20142-102">Prueba de carga de control de tráfico (floodgate)</span><span class="sxs-lookup"><span data-stu-id="20142-102">Floodgate Load Test</span></span>
<span data-ttu-id="20142-103">La información de este tema hace referencia a las pruebas que se explican en [escenarios de prueba para medir el rendimiento máximo Sostenible del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span><span class="sxs-lookup"><span data-stu-id="20142-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
## <a name="what-causes-floodgate-events"></a><span data-ttu-id="20142-104">¿Qué provoca un evento de control de tráfico (floodgate)?</span><span class="sxs-lookup"><span data-stu-id="20142-104">What Causes Floodgate Events?</span></span>  
 <span data-ttu-id="20142-105">Hay varios escenarios donde solo unos pocos valores máximos (también conocido como **eventos de control de tráfico**) de los mensajes llegan en el sistema, cada día.</span><span class="sxs-lookup"><span data-stu-id="20142-105">There are a number of scenarios where just a few large peaks (also known as **floodgate events**) of messages arrive at the system each day.</span></span> <span data-ttu-id="20142-106">Entre estos valores máximos, el rendimiento puede ser muy bajo.</span><span class="sxs-lookup"><span data-stu-id="20142-106">Between these peaks, the throughput can be very low.</span></span> <span data-ttu-id="20142-107">Entre los ejemplos de estos tipos de escenarios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="20142-107">Examples of these types of scenarios include:</span></span>  
  
-   <span data-ttu-id="20142-108">Operaciones de patrimonio neto, por ejemplo, en la apertura y el cierre de los mercados</span><span class="sxs-lookup"><span data-stu-id="20142-108">Equity trading, for example, at market open and market close</span></span>  
  
-   <span data-ttu-id="20142-109">Sistemas bancarios, por ejemplo, durante la conciliación de las transacciones del día</span><span class="sxs-lookup"><span data-stu-id="20142-109">Banking systems, for example, during end of day transaction reconciliation</span></span>  
  
 <span data-ttu-id="20142-110">Otros tipos de eventos puede producir un comportamiento de acumulación similar a los eventos de control de tráfico (floodgate).</span><span class="sxs-lookup"><span data-stu-id="20142-110">Other types of events can cause backlog behavior similar to floodgate events.</span></span> <span data-ttu-id="20142-111">Por ejemplo, si la dirección de envío de un socio comercial queda sin conexión de modo que los mensajes cuyo destino era dicha dirección deben volver a intentarse o suspenderse, esto puede provocar la generación de una acumulación.</span><span class="sxs-lookup"><span data-stu-id="20142-111">For example, if a partner send address goes off line so that messages destined for that address must be re-tried and/or suspended, this can result in backlog building up.</span></span> <span data-ttu-id="20142-112">Cuando el socio comercial vuelva a estar conectado, podría haber un gran número de mensajes suspendidos que deben reanudarse, lo que provocaría otro tipo de evento de control de tráfico (floodgate).</span><span class="sxs-lookup"><span data-stu-id="20142-112">When the partner comes back on line, there may be a large number of suspended messages that need to be resumed, resulting in another type of floodgate event.</span></span> <span data-ttu-id="20142-113">La siguiente prueba del sistema ilustra este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="20142-113">The following test of the system illustrates this behavior.</span></span>  
  
## <a name="simulating-a-floodgate-event"></a><span data-ttu-id="20142-114">Simular un evento de control de tráfico (floodgate)</span><span class="sxs-lookup"><span data-stu-id="20142-114">Simulating a Floodgate Event</span></span>  
 <span data-ttu-id="20142-115">A fines de esta prueba, el sistema se puso aproximadamente a la mitad del rendimiento máximo sostenible, valor que por supuesto era muy estable</span><span class="sxs-lookup"><span data-stu-id="20142-115">For this test, the system was initially driven at around half the maximum sustainable throughput which of course was very stable.</span></span> <span data-ttu-id="20142-116">A continuación, para simular un evento de control de tráfico (floodgate), se configuró la herramienta de generación de cargas para que enviara unos 419 mensajes/segundo durante un corto período de tiempo (el mismo valor que para la prueba de sobrecarga).</span><span class="sxs-lookup"><span data-stu-id="20142-116">Then, to simulate a floodgate event, the load generation tool was configured to send in about 410 msgs/sec for a short period of time (the same as for the overdrive test).</span></span> <span data-ttu-id="20142-117">A continuación, se muestra el perfil de carga resultante que mide los mensajes recibidos por segundo y la profundidad de la cola.</span><span class="sxs-lookup"><span data-stu-id="20142-117">The resultant load profile measuring messages received per second and spool depth is displayed below.</span></span>  
  
 <span data-ttu-id="20142-118">**Perfil de carga de prueba de carga de control de tráfico**</span><span class="sxs-lookup"><span data-stu-id="20142-118">**Load profile of floodgate load test**</span></span>  
  
 <span data-ttu-id="20142-119">![Pantalla del monitor de rendimiento de carga de control de tráfico](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span><span class="sxs-lookup"><span data-stu-id="20142-119">![Performance monitor display of floodgate load](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span></span>  
  
 <span data-ttu-id="20142-120">Observe en el gráfico que las tablas de colas generan una acumulación rápidamente durante el evento de control de tráfico (floodgate).</span><span class="sxs-lookup"><span data-stu-id="20142-120">Note from the graph that the spool tables quickly built up a backlog during the floodgate event.</span></span> <span data-ttu-id="20142-121">Sin embargo, puesto que el evento fue relativamente corto y la velocidad de recepción posterior fue inferior a la velocidad máxima sostenible, los trabajos de limpieza pudieron ejecutarse y recuperarse del evento sin necesidad de una interrupción de recepción en el sistema</span><span class="sxs-lookup"><span data-stu-id="20142-121">However, because the event was relatively short lived and the subsequent receive rate after the event was below the maximum sustainable rate, the cleanup jobs were able to run and recover from the event without requiring a system receive outage.</span></span> <span data-ttu-id="20142-122">Para esta prueba específica, el cuadro de mensajes se alojó en SQL Server 2005. La duración de esta prueba, de principio a fin, fue de aproximadamente 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="20142-122">For this particular test, the MessageBox was housed on SQL Server 2005; the duration of this test from beginning to end was approximately 45 minutes.</span></span>  
  
 <span data-ttu-id="20142-123">Por supuesto, todos los sistemas son diferentes, por lo tanto, los datos serán distintos</span><span class="sxs-lookup"><span data-stu-id="20142-123">Of course, every system is different, so "your mileage will vary."</span></span> <span data-ttu-id="20142-124">El mejor modo de comprobar que puede recuperarse es probar con una carga representativa antes de pasar a producción.</span><span class="sxs-lookup"><span data-stu-id="20142-124">The best way to verify that you can recover is to test with a representative load before going into production.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20142-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="20142-125">See Also</span></span>  
 <span data-ttu-id="20142-126">[Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="20142-126">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="20142-127">[Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="20142-127">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 <span data-ttu-id="20142-128">[Prueba de sobrecarga](../core/overdrive-load-test.md) </span><span class="sxs-lookup"><span data-stu-id="20142-128">[Overdrive Load Test](../core/overdrive-load-test.md) </span></span>  
 [<span data-ttu-id="20142-129">Prueba de carga sostenible</span><span class="sxs-lookup"><span data-stu-id="20142-129">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)
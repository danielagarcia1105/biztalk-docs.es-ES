---
title: Sobrecargar la prueba de carga | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overdrive load test
- LoadGen tool, overdrive load test
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54ea40d17bdb59fa3fcdc2db31a18b3286b70659
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overdrive-load-test"></a><span data-ttu-id="f020b-102">Prueba de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f020b-102">Overdrive Load Test</span></span>
<span data-ttu-id="f020b-103">La información de este tema hace referencia a las pruebas que se explican en [escenarios de prueba para medir el rendimiento máximo Sostenible del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f020b-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="f020b-104">La herramienta para la generación de cargas, LoadGen 2007, le permite simular cargas pesadas en un sistema de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f020b-104">The Load Generation tool, LoadGen 2007, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f020b-105">La herramienta LoadGen 2007 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span><span class="sxs-lookup"><span data-stu-id="f020b-105">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span> <span data-ttu-id="f020b-106">La versión anterior de esta herramienta, la herramienta de generación de cargas de BizTalk Server 2004 está disponible para su descarga en [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span><span class="sxs-lookup"><span data-stu-id="f020b-106">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span>  
  
 <span data-ttu-id="f020b-107">Para simular un sistema continuamente sobrecargado, LoadGen 2007 se ha configurado para enviar alrededor de 410 mensajes por segundo, 120 mensajes por segundo más que el rendimiento máximo sostenible medido.</span><span class="sxs-lookup"><span data-stu-id="f020b-107">To simulate a continuously overdriven system, LoadGen 2007 was configured to send about 410 msgs/sec, 120 msgs/sec more than the measured maximum sustainable throughput.</span></span>  
  
 <span data-ttu-id="f020b-108">La prueba se ha diseñado no sólo para sobrecargar el sistema, sino también para tener una idea de cuánto tardará en recuperarse de una profundidad de trabajo acumulado en la cola de impresión de alrededor de 2 millones de registros.</span><span class="sxs-lookup"><span data-stu-id="f020b-108">The test was designed not only to overdrive the system, but also to get an idea of how long it would take to recover from a spool backlog depth of around 2 million records.</span></span>  
  
 <span data-ttu-id="f020b-109">Para esto, el sistema se ha ido controlando a velocidad creciente hasta que la profundidad de cola de impresión fuera de alrededor de 2 millones de registros.</span><span class="sxs-lookup"><span data-stu-id="f020b-109">To accomplish this, the system was driven at the increased rate until the spool depth was around 2 million records.</span></span> <span data-ttu-id="f020b-110">Una vez que la profundidad de cola de impresión ha alcanzado el nivel deseado, no se ha generado más carga.</span><span class="sxs-lookup"><span data-stu-id="f020b-110">Once the spool depth reached the desired level then no further load was generated.</span></span>  
  
 <span data-ttu-id="f020b-111">Para asegurarse de que el mecanismo de limitación de BizTalk no limitar el host de recepción, lo que impediría la acumulación de un trabajo pendiente de tabla de cola de impresión, el **recuento en la base de datos del mensaje** umbral de limitación para el host de recepción se cambió desde la valor predeterminado de 50000 a 2000000.</span><span class="sxs-lookup"><span data-stu-id="f020b-111">To ensure that the BizTalk throttling mechanism did not throttle the receive host, which would prevent the accumulation of a spool table backlog, the **Message count in DB** throttling threshold for the receive host was changed from the default value of 50000 to 2000000.</span></span> <span data-ttu-id="f020b-112">Para obtener información acerca de cómo cambiar la **recuento en la base de datos del mensaje** umbral de limitación, consulte [cómo modificar recursos según configuración de la limitación](../core/how-to-modify-resource-based-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f020b-112">For information on changing the **Message count in DB** throttling threshold, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span> <span data-ttu-id="f020b-113">Para obtener información sobre la configuración de limitación de host predeterminado, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span><span class="sxs-lookup"><span data-stu-id="f020b-113">For information about the default host throttling settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="f020b-114">En el gráfico siguiente se muestran los mismos indicadores que en el gráfico anterior.</span><span class="sxs-lookup"><span data-stu-id="f020b-114">The following graph shows the same indicators as in the graph above.</span></span>  
  
 <span data-ttu-id="f020b-115">**Perfil de carga de prueba de sobrecarga**</span><span class="sxs-lookup"><span data-stu-id="f020b-115">**Load profile of overdrive load test**</span></span>  
  
 <span data-ttu-id="f020b-116">![Mostrar en el Monitor de rendimiento de la sobrecarga](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span><span class="sxs-lookup"><span data-stu-id="f020b-116">![Performance montor display of overdrive load](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span></span>  
  
 <span data-ttu-id="f020b-117">Como se puede ver en el gráfico, la profundidad de cola de impresión empezó a generarse inmediatamente, y alcanzó el máximo justo por encima de los 2 millones de registros.</span><span class="sxs-lookup"><span data-stu-id="f020b-117">As can be seen from the graph, the spool depth started building up immediately, peaking at just above 2 million records.</span></span> <span data-ttu-id="f020b-118">A esta velocidad, se necesitaron unas 2,5 horas en alcanzar los 2 millones de registros de trabajo acumulado que se habían marcado como objetivo.</span><span class="sxs-lookup"><span data-stu-id="f020b-118">At this rate, it took just about 2.5 hours to get to the targeted 2 million record backlog.</span></span> <span data-ttu-id="f020b-119">Una vez detenida la carga, se necesitaron alrededor 8 horas de trabajos de limpieza para recuperarse del trabajo acumulado.</span><span class="sxs-lookup"><span data-stu-id="f020b-119">After the load was stopped, it took around 8 hours for the cleanup jobs to recover from the backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f020b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f020b-120">See Also</span></span>  
 <span data-ttu-id="f020b-121">[Escenarios de prueba para medir MST del motor de](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f020b-121">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="f020b-122">[Mediante el panel de configuración de BizTalk Server ajuste del rendimiento](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="f020b-122">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 [<span data-ttu-id="f020b-123">Prueba de carga sostenible</span><span class="sxs-lookup"><span data-stu-id="f020b-123">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)
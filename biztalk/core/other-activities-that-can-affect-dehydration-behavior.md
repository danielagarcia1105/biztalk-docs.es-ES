---
title: "Otras actividades que pueden afectar al comportamiento de deshidratación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4622c77876607664b210de2581929154973b45d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a><span data-ttu-id="e3f4b-102">Otras actividades que pueden afectar al comportamiento de deshidratación</span><span class="sxs-lookup"><span data-stu-id="e3f4b-102">Other Activities That Can Affect Dehydration Behavior</span></span>
<span data-ttu-id="e3f4b-103">Las siguientes actividades afectan de forma directa o indirecta a la deshidratación y al rendimiento general; por tanto, deben tenerse en cuenta en cualquier escenario de pruebas.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-103">The following activities directly or indirectly impact dehydration and overall performance and so should be factored into any testing scenarios.</span></span>  
  
-   <span data-ttu-id="e3f4b-104">**Consultas de la consola de administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-104">**BizTalk Server Administration Console queries.**</span></span> <span data-ttu-id="e3f4b-105">Estas consultas consumen recursos y afectan al rendimiento global en función del tipo y la frecuencia de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-105">These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
-   <span data-ttu-id="e3f4b-106">**Copia de seguridad, archivado y purga las actividades.**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-106">**Backup, archiving, and purging activities.**</span></span> <span data-ttu-id="e3f4b-107">Estas actividades también consumen recursos y deben tenerse en cuenta en cualquier escenario de prueba.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-107">These activities also consume resources and should be factored into any testing scenarios.</span></span>  
  
-   <span data-ttu-id="e3f4b-108">**Combinación de hosts de 32 bits y 64 bits.**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-108">**Mixed 32-bit and 64-bit hosts.**</span></span> <span data-ttu-id="e3f4b-109">Hay algunas cuestiones que deben tenerse en cuenta cuando se usa una combinación de hosts de 32 bits y 64 bits:</span><span class="sxs-lookup"><span data-stu-id="e3f4b-109">Here are some things to consider when using mixed 32-bit and 64-bit hosts:</span></span>  
  
    -   <span data-ttu-id="e3f4b-110">Procedimos a medir la memoria virtual y física consumida en condiciones de sobrecarga y, a continuación, comparamos los resultados con determinados umbrales.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-110">Under stress we measure consumed virtual and physical memory and compare that against certain thresholds.</span></span> <span data-ttu-id="e3f4b-111">En los sistemas de 64 bits, el proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa más memoria y, por tanto, habrá una diferencia en la directiva de deshidratación con respecto a los sistemas de 32 bits que empleen el mismo sistema y los mismos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-111">In 64 bit systems the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process uses more memory so there will be a difference in dehydration policy from 32-bits using the same system and the same default values.</span></span> <span data-ttu-id="e3f4b-112">Asegúrese de separar los hosts de orquestación, recepción, envío y cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-112">Be sure to separate orchestration, receive, send and message box hosts.</span></span>  
  
         <span data-ttu-id="e3f4b-113">No se ha encontrado ninguna diferencia obvia al usar los umbrales predeterminados de 32 bits en los sistemas de 64 bits cuando el host de orquestación se encuentra en el cuadro de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-113">There is not an obvious difference when using the default 32-bit thresholds for 64-bit systems, as long as only the orchestration host is on the 64 bit box.</span></span> <span data-ttu-id="e3f4b-114">Sin embargo, en condiciones de sobrecarga, **MemoryThrottlingCriteria** configuración debe estar como mínimo duplicar o triplicar (siempre y cuando tenga suficiente memoria), pero el escenario debe optimizarse para maximizar el rendimiento porque hay muchos factores que entran en juego.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-114">However, under stress the various **MemoryThrottlingCriteria** settings should be at least doubled or tripled (as long as you have enough memory), but the scenario should be tuned for maximizing throughput because there are many factors that come into play.</span></span> <span data-ttu-id="e3f4b-115">Ajuste los umbrales de deshidratación en condiciones de sobrecarga para hallar los valores óptimos.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-115">You should tune the dehydration thresholds under stress to find what is optimal for them.</span></span>  
  
    -   <span data-ttu-id="e3f4b-116">El comportamiento de deshidratación depende del historial de tiempo de entrega de cada una de las suscripciones; tenga en cuenta que los historiales pueden ser distintos de una a otra suscripción al ajustar los valores de las propiedades de deshidratación.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-116">Dehydration behavior depends on delivery time history of every subscription; the histories could be different for different subscriptions so consider this in tuning your dehydration property values.</span></span>  
  
    -   <span data-ttu-id="e3f4b-117">Cuando el servicio del host de orquestación se recicle en un host, pero no en otro, los historiales serán diferentes.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-117">When the orchestration host service is recycled on one host, but not on another, the histories will be different.</span></span>  
  
    -   <span data-ttu-id="e3f4b-118">Cuando los servidores usan diferentes versiones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], habrá una diferencia en la directiva de deshidratación entre los dos.</span><span class="sxs-lookup"><span data-stu-id="e3f4b-118">When servers are using different versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there will be a difference in dehydration policy between the two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f4b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3f4b-119">See Also</span></span>  
 [<span data-ttu-id="e3f4b-120">Archivo BTSNTSvc.exe.config</span><span class="sxs-lookup"><span data-stu-id="e3f4b-120">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)
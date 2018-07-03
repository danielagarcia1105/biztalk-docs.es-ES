---
title: Procedimientos recomendados para la configuración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 461e2e1a4256d79112e4eec94047c25df34a4511
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001126"
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="5407b-102">Procedimientos recomendados para la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5407b-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="5407b-103">Este tema enumeran los procedimientos recomendados que debe seguir al realizar los procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5407b-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5407b-104">**Configurar el mensaje de procesamiento por lotes para aumentar el rendimiento del adaptador**</span><span class="sxs-lookup"><span data-stu-id="5407b-104">**Configure message batching to increase adapter performance**</span></span>  
  
- <span data-ttu-id="5407b-105">Minimizar el número de transacciones realizadas por un adaptador mediante la combinación de más de una operación en un único lote.</span><span class="sxs-lookup"><span data-stu-id="5407b-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
- <span data-ttu-id="5407b-106">Limitar el tamaño del lote en función del número total de bytes en el lote, además de recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5407b-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="5407b-107">Para obtener más información acerca de cómo limitar el tamaño del lote, vea [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span><span class="sxs-lookup"><span data-stu-id="5407b-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
  <span data-ttu-id="5407b-108">**Ajustar el umbral de mensajes de gran tamaño**</span><span class="sxs-lookup"><span data-stu-id="5407b-108">**Adjust the large message threshold**</span></span>  
  
- <span data-ttu-id="5407b-109">Para mejorar el rendimiento, aumentar el umbral de mensajes de gran tamaño, lo que reduce el número de mensajes de gran tamaño que se almacenan en búfer en el disco durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="5407b-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
  <span data-ttu-id="5407b-110">**Determinar la información que necesita para realizar un seguimiento durante la planeación**</span><span class="sxs-lookup"><span data-stu-id="5407b-110">**Determine the information you need to track during planning**</span></span>  
  
- <span data-ttu-id="5407b-111">Debe decidir durante las fases de planeamiento de la información que necesita para realizar el seguimiento. De este modo, después de implementar el proyecto, puede establecer las opciones de seguimiento y limitar la cantidad de datos de seguimiento para proporcionar solo la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="5407b-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="5407b-112">Para obtener más información acerca de las prácticas recomendadas para seguimiento, vea [planificación del seguimiento](../technical-guides/planning-for-tracking.md) en esta guía y [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span><span class="sxs-lookup"><span data-stu-id="5407b-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
  <span data-ttu-id="5407b-113">**No realizar seguimiento de todos los mensajes**</span><span class="sxs-lookup"><span data-stu-id="5407b-113">**Do not track all messages**</span></span>  
  
- <span data-ttu-id="5407b-114">Se recomienda realizar un seguimiento no todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5407b-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="5407b-115">Esto es porque cada vez que se toca un mensaje, BizTalk Server crea otra copia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5407b-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="5407b-116">En su lugar, puede restringir el ámbito mediante el seguimiento solo a un puerto específico.</span><span class="sxs-lookup"><span data-stu-id="5407b-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="5407b-117">Esto ayuda a maximizar el rendimiento del sistema y a mantener despejado las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5407b-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
  <span data-ttu-id="5407b-118">**Establecer el seguimiento en los puertos de envío y puertos en lugar de en una canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="5407b-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
- <span data-ttu-id="5407b-119">Si configura las opciones de seguimiento de canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización.</span><span class="sxs-lookup"><span data-stu-id="5407b-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="5407b-120">Esto puede producir a su vez en muchos más datos de seguimiento que desea, lo que ralentizan el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="5407b-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="5407b-121">En su lugar, puede establecer las opciones de seguimiento en el envío de puertos y los puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="5407b-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
  <span data-ttu-id="5407b-122">**Ajustar la limitación basada en la utilización de recursos**</span><span class="sxs-lookup"><span data-stu-id="5407b-122">**Adjust throttling based on resource utilization**</span></span>  
  
- <span data-ttu-id="5407b-123">Limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está configurado de forma predeterminada para proporcionar una buena protección para el sistema.</span><span class="sxs-lookup"><span data-stu-id="5407b-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="5407b-124">Supervisar los contadores de rendimiento para la limitación de Estados para ver si la limitación está teniendo lugar.</span><span class="sxs-lookup"><span data-stu-id="5407b-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="5407b-125">Analice, a continuación, si se basa el recurso en qué tipo de limitación (por ejemplo, base de datos de uso de memoria o de tamaño) se utiliza debajo o por encima.</span><span class="sxs-lookup"><span data-stu-id="5407b-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="5407b-126">A continuación, ajustar la limitación de peticiones umbrales hacia arriba o hacia abajo según corresponda.</span><span class="sxs-lookup"><span data-stu-id="5407b-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="5407b-127">Para obtener más información, consulte [ajustar umbrales de limitación: cuándo y por qué](http://go.microsoft.com/fwlink/p/?LinkId=154188) (<http://go.microsoft.com/fwlink/p/?LinkId=154188>).</span><span class="sxs-lookup"><span data-stu-id="5407b-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (<http://go.microsoft.com/fwlink/p/?LinkId=154188>).</span></span>  
  
  <span data-ttu-id="5407b-128">**Usar la canalización PassThruTransmit si es posible**</span><span class="sxs-lookup"><span data-stu-id="5407b-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
- <span data-ttu-id="5407b-129">Si no es necesario ningún procesamiento de documentos antes de enviar un mensaje a su destino, use la canalización PassThruTransmit en lugar de la canalización de envío XML.</span><span class="sxs-lookup"><span data-stu-id="5407b-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
  <span data-ttu-id="5407b-130">**Minimizar el uso de orquestación "de forma Inicio y de finalización" eventos de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="5407b-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
- <span data-ttu-id="5407b-131">Aunque la forma orquestación de seguimiento tiene ventajas evidentes para la depuración de orquestación, tiene implicaciones de escalabilidad y de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5407b-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="5407b-132">El **forma Inicio y finalización** evento de seguimiento puede provocar una sobrecarga considerable.</span><span class="sxs-lookup"><span data-stu-id="5407b-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="5407b-133">Es mejor minimizar su uso en entornos de producción donde es necesario un alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5407b-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="5407b-134">**Forma Inicio y finalización** eventos de seguimiento están habilitados de forma predeterminada en todas las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="5407b-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5407b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5407b-135">See Also</span></span>  
 [<span data-ttu-id="5407b-136">Lista de comprobación: configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5407b-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)
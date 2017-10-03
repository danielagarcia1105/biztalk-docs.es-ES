---
title: "Prácticas recomendadas para la configuración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="fbab9-102">Prácticas recomendadas para la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fbab9-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="fbab9-103">Este tema enumeran las prácticas recomendadas que debería seguir al realizar procedimientos de preparación operativa para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbab9-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fbab9-104">**Configurar el procesamiento por lotes de mensajes para aumentar el rendimiento de adaptador**</span><span class="sxs-lookup"><span data-stu-id="fbab9-104">**Configure message batching to increase adapter performance**</span></span>  
  
-   <span data-ttu-id="fbab9-105">Minimice el número de transacciones realizadas por un adaptador mediante la combinación de más de una operación en un único lote.</span><span class="sxs-lookup"><span data-stu-id="fbab9-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
-   <span data-ttu-id="fbab9-106">Limitar el tamaño del lote en función del número total de bytes en el lote, además de recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fbab9-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="fbab9-107">Para obtener más información acerca de cómo limitar el tamaño del lote, consulte [configuración de procesamiento por lotes para mejorar el rendimiento del adaptador](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span><span class="sxs-lookup"><span data-stu-id="fbab9-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="fbab9-108">**Ajustar el umbral de mensajes de gran tamaño**</span><span class="sxs-lookup"><span data-stu-id="fbab9-108">**Adjust the large message threshold**</span></span>  
  
-   <span data-ttu-id="fbab9-109">Para mejorar el rendimiento, aumentar el umbral de mensajes de gran tamaño, lo que reduce el número de mensajes de gran tamaño que se almacenan en búfer en el disco durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="fbab9-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
 <span data-ttu-id="fbab9-110">**Determinar la información que necesita para realizar un seguimiento durante la planeación**</span><span class="sxs-lookup"><span data-stu-id="fbab9-110">**Determine the information you need to track during planning**</span></span>  
  
-   <span data-ttu-id="fbab9-111">Debe decidir durante las fases de planeamiento la información que necesita para realizar el seguimiento. De este modo, después de implementar el proyecto, puede establecer las opciones de seguimiento y limitar la cantidad de datos a fin de sólo la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="fbab9-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fbab9-112">Para obtener más información sobre los procedimientos recomendados relacionados con el seguimiento, vea [planeación para el seguimiento de](../technical-guides/planning-for-tracking.md) en esta guía y [seguimiento de estado y actividad](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span><span class="sxs-lookup"><span data-stu-id="fbab9-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
 <span data-ttu-id="fbab9-113">**No realizar seguimiento de todos los mensajes**</span><span class="sxs-lookup"><span data-stu-id="fbab9-113">**Do not track all messages**</span></span>  
  
-   <span data-ttu-id="fbab9-114">Se recomienda que no realiza el seguimiento todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fbab9-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="fbab9-115">Esto es porque cada vez que se toca un mensaje, BizTalk Server crea otra copia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fbab9-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="fbab9-116">En su lugar, puede restringir el ámbito mediante el seguimiento solo un puerto específico.</span><span class="sxs-lookup"><span data-stu-id="fbab9-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="fbab9-117">Esto ayuda a maximizar el rendimiento del sistema y mantener las bases de datos ordenado.</span><span class="sxs-lookup"><span data-stu-id="fbab9-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
 <span data-ttu-id="fbab9-118">**Configurar seguimiento de los puertos de envío y puertos en lugar de en una canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="fbab9-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
-   <span data-ttu-id="fbab9-119">Si establece opciones de seguimiento en las canalizaciones, también establecerá las opciones de seguimiento globalmente para todos los puertos que usa la canalización.</span><span class="sxs-lookup"><span data-stu-id="fbab9-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="fbab9-120">Esto a su vez puede hacer mucho más datos sometidos a seguimiento que piensa, lo que ralentizan el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="fbab9-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="fbab9-121">En su lugar, puede establecer opciones de seguimiento en el envío de puertos y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="fbab9-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
 <span data-ttu-id="fbab9-122">**Ajustar la limitación basada en la utilización de recursos**</span><span class="sxs-lookup"><span data-stu-id="fbab9-122">**Adjust throttling based on resource utilization**</span></span>  
  
-   <span data-ttu-id="fbab9-123">Limitación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se configura de forma predeterminada para proporcionar una buena protección para el sistema.</span><span class="sxs-lookup"><span data-stu-id="fbab9-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="fbab9-124">Supervisar los contadores de rendimiento para la limitación de Estados para ver si la limitación está teniendo lugar.</span><span class="sxs-lookup"><span data-stu-id="fbab9-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="fbab9-125">Analice, a continuación, si se basa el recurso de la limitación (por ejemplo, la base de datos el uso de tamaño o memoria) es bajo o utilizando en exceso.</span><span class="sxs-lookup"><span data-stu-id="fbab9-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="fbab9-126">A continuación, ajustar la limitación de peticiones umbrales hacia arriba o hacia abajo según corresponda.</span><span class="sxs-lookup"><span data-stu-id="fbab9-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="fbab9-127">Para obtener más información, consulte [ajustar umbrales de limitación: cuándo y por qué](http://go.microsoft.com/fwlink/p/?LinkId=154188) (http://go.microsoft.com/fwlink/p/?LinkId=154188).</span><span class="sxs-lookup"><span data-stu-id="fbab9-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (http://go.microsoft.com/fwlink/p/?LinkId=154188).</span></span>  
  
 <span data-ttu-id="fbab9-128">**Si es posible usar la canalización PassThruTransmit**</span><span class="sxs-lookup"><span data-stu-id="fbab9-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
-   <span data-ttu-id="fbab9-129">Si no es necesario ningún procesamiento del documento antes de enviar un mensaje a su destino, use la canalización PassThruTransmit en lugar de la canalización de envío XML.</span><span class="sxs-lookup"><span data-stu-id="fbab9-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
 <span data-ttu-id="fbab9-130">**Minimizar el uso de orquestación "forma Inicio y finalización" eventos de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="fbab9-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
-   <span data-ttu-id="fbab9-131">Aunque forma orquestación de seguimiento tiene ventajas obvias para la depuración de orquestación, tiene implicaciones de escalabilidad y de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fbab9-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="fbab9-132">El **forma Inicio y finalización** evento de seguimiento puede provocar una sobrecarga significativa.</span><span class="sxs-lookup"><span data-stu-id="fbab9-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="fbab9-133">Es mejor minimizar su uso en entornos de producción donde es necesario un alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fbab9-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fbab9-134">**Forma Inicio y finalización** eventos de seguimiento están habilitados de forma predeterminada en todas las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="fbab9-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbab9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbab9-135">See Also</span></span>  
 [<span data-ttu-id="fbab9-136">Lista de comprobación: Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fbab9-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)
---
title: Optimización de la actividad económica (BAM) rendimiento de supervisión | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f28771f2611a8b5f7c2522b7cd45e875897645e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996205"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a><span data-ttu-id="db8e8-102">Optimización de la actividad económica (BAM) rendimiento de supervisión</span><span class="sxs-lookup"><span data-stu-id="db8e8-102">Optimizing Business Activity Monitoring (BAM) Performance</span></span>
<span data-ttu-id="db8e8-103">En este tema se describe los factores de rendimiento de supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="db8e8-103">This topic describes Business Activity Monitoring (BAM) performance factors.</span></span>  
  
## <a name="bam-disk-usage-configuration"></a><span data-ttu-id="db8e8-104">Configuración de uso de disco BAM</span><span class="sxs-lookup"><span data-stu-id="db8e8-104">BAM disk usage configuration</span></span>  
 <span data-ttu-id="db8e8-105">BAM supone una sobrecarga considerable cuando un sistema de BizTalk está bajo carga debido a la importante cantidad de datos que se conservan en la base de datos BAM.</span><span class="sxs-lookup"><span data-stu-id="db8e8-105">BAM incurs significant overhead when a BizTalk system is under load because of the significant amount of data that is persisted to the BAM database.</span></span> <span data-ttu-id="db8e8-106">Por lo tanto, juiciosamente uso de técnicas de E/S de disco para la base de datos BAM es muy importante.</span><span class="sxs-lookup"><span data-stu-id="db8e8-106">Therefore, judicious use of disk I/O techniques for the BAM database is critically important.</span></span>  
  
## <a name="bam-eventstream-apis"></a><span data-ttu-id="db8e8-107">API EventStream BAM</span><span class="sxs-lookup"><span data-stu-id="db8e8-107">BAM EventStream APIs</span></span>  
 <span data-ttu-id="db8e8-108">Cuatro tipos de EventStreams están disponibles para su uso en un escenario de BAM de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="db8e8-108">Four types of EventStreams are available for use in a BizTalk BAM scenario:</span></span>  
  
- <span data-ttu-id="db8e8-109">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="db8e8-109">DirectEventStream (DES)</span></span>  
  
- <span data-ttu-id="db8e8-110">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="db8e8-110">BufferedEventStream (BES)</span></span>  
  
- <span data-ttu-id="db8e8-111">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="db8e8-111">OrchestrationEventStream (OES)</span></span>  
  
- <span data-ttu-id="db8e8-112">MessageEventStream (MES)</span><span class="sxs-lookup"><span data-stu-id="db8e8-112">MessageEventStream (MES)</span></span>  
  
  <span data-ttu-id="db8e8-113">Debe elegir una de estas API según los factores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db8e8-113">You should choose one of these APIs based on the following factors:</span></span>  
  
- <span data-ttu-id="db8e8-114">Si lo que le interesa es la latencia, elija DES, donde los datos persisten sincrónicamente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="db8e8-114">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="db8e8-115">Si le interesa es el rendimiento y el rendimiento de inserción de eventos, elija una API asíncrona (BES, OES o MES).</span><span class="sxs-lookup"><span data-stu-id="db8e8-115">If your concern is performance and throughput of event insertion, choose an asynchronous API (BES, OES or MES).</span></span>  
  
- <span data-ttu-id="db8e8-116">Si está escribiendo una aplicación que se ejecuta en un equipo que no tiene instalado BizTalk Server, use DES y BES; Estas API pueden usarse en aplicaciones que no sean de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="db8e8-116">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES; these APIs can be used in non-BizTalk applications.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="db8e8-117">Existen escenarios en los que quizá desee mezclar tipos EventStream:</span><span class="sxs-lookup"><span data-stu-id="db8e8-117">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="db8e8-118">Por ejemplo, para el procesamiento de canalización, puede capturar los datos específicos de BAM independientemente de si la canalización está revirtiendo la transacción.</span><span class="sxs-lookup"><span data-stu-id="db8e8-118">For example, for pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="db8e8-119">En concreto, puede que desee capturar datos sobre cuántos mensajes de error o cuántos reintentos se produjeron durante el procesamiento de canalización.</span><span class="sxs-lookup"><span data-stu-id="db8e8-119">In particular, you may want capture data about how many messages failed or how many retries occurred during pipeline processing.</span></span> <span data-ttu-id="db8e8-120">Para capturar datos en esta situación, debe usar BES.</span><span class="sxs-lookup"><span data-stu-id="db8e8-120">To capture the data in this situation you should use BES.</span></span>  
  
- <span data-ttu-id="db8e8-121">Si la aplicación se ejecuta en un equipo que tiene BizTalk Server instalado, use MES y OES.</span><span class="sxs-lookup"><span data-stu-id="db8e8-121">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="db8e8-122">(Estas API están disponibles únicamente desde aplicaciones de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="db8e8-122">(These APIs are available only from BizTalk applications.)</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="db8e8-123">OES es el equivalente de MES pero para orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="db8e8-123">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
- <span data-ttu-id="db8e8-124">Si desea que la persistencia de eventos BAM esté sincronizada con la transacción de canalización, debe usar un Stream de eventos de mensajería (MES).</span><span class="sxs-lookup"><span data-stu-id="db8e8-124">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream (MES).</span></span>  
  
  <span data-ttu-id="db8e8-125">Todas las EventStreams asincrónicas (BES, MES y OES) conservar los datos primero a la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="db8e8-125">All the asynchronous EventStreams (BES, MES, and OES) persist data first to the BizTalk MessageBox database.</span></span> <span data-ttu-id="db8e8-126">De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="db8e8-126">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
  <span data-ttu-id="db8e8-127">Para obtener más información sobre las BAM EventStream APIs, consulte [clases EventStream](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) en la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="db8e8-127">For more information about the BAM EventStream APIs, see [EventStream Classes](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) in the BizTalk Server documentation.</span></span>  
  
## <a name="bam-performance-counters"></a><span data-ttu-id="db8e8-128">Contadores de rendimiento de BAM</span><span class="sxs-lookup"><span data-stu-id="db8e8-128">BAM performance counters</span></span>  
 <span data-ttu-id="db8e8-129">Para obtener una lista detallada de los contadores de rendimiento de BAM, consulte [contadores de rendimiento BAM](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) en la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="db8e8-129">For a detailed list of the performance counters for BAM, see [BAM Performance Counters](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) in the BizTalk Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8e8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="db8e8-130">See Also</span></span>  
 [<span data-ttu-id="db8e8-131">Optimización del rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="db8e8-131">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)
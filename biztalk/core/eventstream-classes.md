---
title: Clases EventStream | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4cb000d479a51d2215bda6349adfa6df39338a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973565"
---
# <a name="eventstream-classes"></a><span data-ttu-id="f6242-102">Clases EventStream</span><span class="sxs-lookup"><span data-stu-id="f6242-102">EventStream Classes</span></span>
<span data-ttu-id="f6242-103">Las API EventStream de BAM residen en el espacio de nombres Microsoft.BizTalk.BAM.EventObservation.</span><span class="sxs-lookup"><span data-stu-id="f6242-103">The EventStream APIs for BAM reside in the Microsoft.BizTalk.BAM.EventObservation namespace.</span></span> <span data-ttu-id="f6242-104">Para escribir código basado en las API, deberá instalar primero los siguientes DLL en el equipo de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="f6242-104">To code against the APIs, you must install the following DLLs on your development computer:</span></span>  
  
- <span data-ttu-id="f6242-105">Microsoft.BizTalk.BAM.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="f6242-105">Microsoft.BizTalk.BAM.EventObservation.dll</span></span>  
  
- <span data-ttu-id="f6242-106">Microsoft.Biztalk.BAM.Xlangs.dll: Este archivo DLL se requiere cuando se codifica para secuencias de eventos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="f6242-106">Microsoft.Biztalk.BAM.Xlangs.dll: This DLL is required when coding for Orchestration event streams.</span></span>  
  
- <span data-ttu-id="f6242-107">Microsoft.BizTalk.Pipeline.dll: Este archivo DLL necesario al usar contextos de canalizaciones de codificación para secuencias de eventos de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f6242-107">Microsoft.BizTalk.Pipeline.dll: This DLL required when using coding pipeline contexts for Messaging event streams.</span></span>  
  
  <span data-ttu-id="f6242-108">Agregue el DLL al proyecto de referencia e incluya el espacio de nombres en el código con la siguiente instrucción de uso:</span><span class="sxs-lookup"><span data-stu-id="f6242-108">Add the DLL to your project reference and include the namespace in your code with the following using statement:</span></span>  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 <span data-ttu-id="f6242-109">**Clases**</span><span class="sxs-lookup"><span data-stu-id="f6242-109">**Classes**</span></span>  
  
|<span data-ttu-id="f6242-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="f6242-110">Name</span></span>|<span data-ttu-id="f6242-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6242-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f6242-112">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="f6242-112">DirectEventStream (DES)</span></span>|<span data-ttu-id="f6242-113">Sincrónico, sin latencia</span><span class="sxs-lookup"><span data-stu-id="f6242-113">Synchronous, no latency</span></span>|  
|<span data-ttu-id="f6242-114">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="f6242-114">BufferedEventStream (BES)</span></span>|<span data-ttu-id="f6242-115">Asíncrono, alto rendimiento, alguna latencia</span><span class="sxs-lookup"><span data-stu-id="f6242-115">Asynchronous, high throughput, some latency</span></span>|  
|<span data-ttu-id="f6242-116">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="f6242-116">OrchestrationEventStream (OES)</span></span>|<span data-ttu-id="f6242-117">Asíncrono, participa en transacciones de orquestaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f6242-117">Asynchronous, participates in BizTalk orchestration transactions</span></span>|  
|<span data-ttu-id="f6242-118">IPipelineContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6242-118">IPipelineContext Interface</span></span>|<span data-ttu-id="f6242-119">Asíncrono, participa en transacciones de canalización de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f6242-119">Asynchronous, participates in BizTalk Server pipeline transactions.</span></span> <span data-ttu-id="f6242-120">Usado para crear secuencias de eventos de mensajería (MES).</span><span class="sxs-lookup"><span data-stu-id="f6242-120">Used to create Messaging Event Streams (MES).</span></span>|  
  
 <span data-ttu-id="f6242-121">Debería elegir una API según los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="f6242-121">You should choose an API based on the following factors:</span></span>  
  
- <span data-ttu-id="f6242-122">Si lo que le interesa es la latencia, elija DES, donde los datos persisten sincrónicamente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="f6242-122">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span> <span data-ttu-id="f6242-123">Excepto DES, todas las demás clases EventStream son asincrónicas y tienen alguna latencia.</span><span class="sxs-lookup"><span data-stu-id="f6242-123">Except for DES, all other EventStream classes are asynchronous and have some latency.</span></span> <span data-ttu-id="f6242-124">Primero se conservan los datos en MessageBox y posteriormente TDDS los procesa y los mueve a la base de datos BAMPrimaryImport.</span><span class="sxs-lookup"><span data-stu-id="f6242-124">The data is first persisted to MessageBox and subsequently processed by TDDS which moves data into the BAMPrimaryImport database.</span></span>  
  
- <span data-ttu-id="f6242-125">Si lo que le interesa es el rendimiento y la producción de inserción de eventos, elija una API asíncrona.</span><span class="sxs-lookup"><span data-stu-id="f6242-125">If your concern is performance and throughput of event insertion, choose an asynchronous API.</span></span>  
  
- <span data-ttu-id="f6242-126">Si está escribiendo una aplicación que se ejecuta en un equipo que no tiene BizTalk Server instalado, use DES y BES.</span><span class="sxs-lookup"><span data-stu-id="f6242-126">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES.</span></span> <span data-ttu-id="f6242-127">(Dicho de otro modo, estas API pueden usarse en aplicaciones que no sean de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="f6242-127">(In other words, these APIs can be used in non-BizTalk applications.)</span></span>  
  
- <span data-ttu-id="f6242-128">Si la aplicación se ejecuta en un equipo que tiene BizTalk Server instalado, use MES y OES.</span><span class="sxs-lookup"><span data-stu-id="f6242-128">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="f6242-129">(Estas API están disponibles únicamente desde aplicaciones de BizTalk).</span><span class="sxs-lookup"><span data-stu-id="f6242-129">(These APIs are available only from BizTalk applications.)</span></span>  
  
  -   <span data-ttu-id="f6242-130">Si quiere que la persistencia de eventos de BAM esté sincronizada con la transacción de canalización, deberá usar una secuencia de eventos de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f6242-130">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream.</span></span>  
  
  -   <span data-ttu-id="f6242-131">OES es el equivalente de MES pero para orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6242-131">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
  <span data-ttu-id="f6242-132">Existen escenarios en los que quizá desee mezclar tipos EventStream:</span><span class="sxs-lookup"><span data-stu-id="f6242-132">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="f6242-133">Por ejemplo, en un procesamiento de canalización puede que desee capturar los datos específicos de BAM independientemente de si la canalización está revirtiendo la transacción o no.</span><span class="sxs-lookup"><span data-stu-id="f6242-133">For example, in a pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="f6242-134">Concretamente, puede que desee capturar datos sobre cuántos mensajes produjeron un error o cuántos reintentos hubo durante el procesamiento de canalización.</span><span class="sxs-lookup"><span data-stu-id="f6242-134">In particular, you may want capture data about how many messages failed or how many retries there were during pipeline processing.</span></span> <span data-ttu-id="f6242-135">Para capturar datos en esta situación, debe usar BES.</span><span class="sxs-lookup"><span data-stu-id="f6242-135">To capture the data in this situation you should use BES.</span></span>  
  
  <span data-ttu-id="f6242-136">Todas las EventStreams (BES, MES y OES) asíncronas almacenan primero los datos en la base de datos de cuadro de mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f6242-136">All the asynchronous EventStreams (BES, MES, and OES) persist data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="f6242-137">De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="f6242-137">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6242-138">Para asegurarse de que las llamadas de EventStream no crean un cuello de botella desde una aplicación de BizTalk, es recomendable que use API asíncronas.</span><span class="sxs-lookup"><span data-stu-id="f6242-138">To ensure that EventStream calls do not create a bottleneck from a BizTalk application, we recommend that you use asynchronous APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6242-139">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f6242-139">In This Section</span></span>  
  
-   [<span data-ttu-id="f6242-140">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="f6242-140">OrchestrationEventStream</span></span>](../core/orchestrationeventstream.md)  
  
-   [<span data-ttu-id="f6242-141">Secuencias de eventos de mensajería</span><span class="sxs-lookup"><span data-stu-id="f6242-141">Messaging Event Streams</span></span>](../core/messaging-event-streams.md)
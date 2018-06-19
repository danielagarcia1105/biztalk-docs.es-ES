---
title: La inclusión de Back-end invocación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257188"
---
# <a name="inlining-back-end-invocation"></a><span data-ttu-id="b47e7-102">La inclusión de Back-end invocación</span><span class="sxs-lookup"><span data-stu-id="b47e7-102">Inlining Back-end Invocation</span></span>
<span data-ttu-id="b47e7-103">La versión de llamada en línea de las soluciones completas proporciona los tiempos más rápidos de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b47e7-103">The inline call version, of the full solutions, provides the fastest processing times.</span></span> <span data-ttu-id="b47e7-104">La versión en línea elimina la sobrecarga que se deriva de guardar los mensajes de solicitud y respuesta entre los sistemas servidor y la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b47e7-104">The inline version eliminates the overhead of persisting the request and response messages to and from the backend systems in the MessageBox database.</span></span> <span data-ttu-id="b47e7-105">En la versión de adaptador, el mensaje pasa de la orquestación de envío al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b47e7-105">In the adapter version, the message goes from the sending orchestration to the MessageBox.</span></span> <span data-ttu-id="b47e7-106">El host que ejecuta el adaptador recoge el mensaje y lo envía al proceso de servidor al enviarlo de nuevo al cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b47e7-106">The host running the adapter picks up the message, and sends the message to the back-end process by again posting it to the message box.</span></span>  
  
 <span data-ttu-id="b47e7-107">La eficacia de la versión en línea implica enlazar la orquestación directamente con los protocolos de transporte de los sistemas servidor.</span><span class="sxs-lookup"><span data-stu-id="b47e7-107">The efficiency of inlining comes at a cost of binding the orchestration directly to the transport protocols of the back-end systems.</span></span> <span data-ttu-id="b47e7-108">En la versión en línea, en vez de establecerse la comunicación mediante puertos lógicos, la orquestación llama a los sistemas servidor mediante tres ensamblados personalizados.</span><span class="sxs-lookup"><span data-stu-id="b47e7-108">In the inline version, rather than communicating through logical ports, the orchestration calls the back-end systems through three custom assemblies.</span></span> <span data-ttu-id="b47e7-109">Si se cambia un transporte de sistema servidor, debe volver a escribir y compilarse un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b47e7-109">If a back-end system transport changes, an assembly must be rewritten and recompiled.</span></span> <span data-ttu-id="b47e7-110">En la tabla siguiente se describen los ensamblados y su función:</span><span class="sxs-lookup"><span data-stu-id="b47e7-110">The following table describes the assemblies and their function:</span></span>  
  
|<span data-ttu-id="b47e7-111">Nombre de ensamblado</span><span class="sxs-lookup"><span data-stu-id="b47e7-111">Assembly Name</span></span>|<span data-ttu-id="b47e7-112">Conexión de servidor</span><span class="sxs-lookup"><span data-stu-id="b47e7-112">Back-end Connection</span></span>|  
|-------------------|--------------------------|  
|<span data-ttu-id="b47e7-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span><span class="sxs-lookup"><span data-stu-id="b47e7-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span></span>|<span data-ttu-id="b47e7-114">Utiliza MQSeries **obtener** y **colocar** las funciones de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b47e7-114">Uses MQSeries **get** and **put** message functions.</span></span>|  
|<span data-ttu-id="b47e7-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span><span class="sxs-lookup"><span data-stu-id="b47e7-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span></span>|<span data-ttu-id="b47e7-116">Invoca el servicio Web para el sistema de transacciones.</span><span class="sxs-lookup"><span data-stu-id="b47e7-116">Invokes the Web service for the transaction system.</span></span>|  
|<span data-ttu-id="b47e7-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span><span class="sxs-lookup"><span data-stu-id="b47e7-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span></span>|<span data-ttu-id="b47e7-118">Llama a los servicios Web que simulan SAP.</span><span class="sxs-lookup"><span data-stu-id="b47e7-118">Calls the web services simulating SAP.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b47e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b47e7-119">See Also</span></span>  
 <span data-ttu-id="b47e7-120">[Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b47e7-120">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="b47e7-121">[Desarrollar un servicio en la solución orientada a servicios](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b47e7-121">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="b47e7-122">[Traducir los patrones del servicio en la solución orientada a servicios](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b47e7-122">[Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="b47e7-123">El servicio de supervisión orientada a servicios solución con BAM</span><span class="sxs-lookup"><span data-stu-id="b47e7-123">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)
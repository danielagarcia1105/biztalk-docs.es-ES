---
title: Recopilación de excepciones y conservación de la carga mediante el procesador de excepciones de ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c43925006153ccfdcfa0c9700dd1ecf27fd3fd2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994821"
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a><span data-ttu-id="d8a85-102">Recopilación de excepciones y conservación de la carga mediante el procesador de excepciones de ESB</span><span class="sxs-lookup"><span data-stu-id="d8a85-102">Collecting Exceptions and Persisting the Payload Using the ESB Exception Processor</span></span>
<span data-ttu-id="d8a85-103">En este caso de uso, el controlador de excepciones para una orquestación publica un mensaje de error ESB en el cuadro de mensaje de BizTalk Server o el mecanismo de enrutamiento de mensajes de error de BizTalk genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d8a85-103">In this use case, either the exception handler for an orchestration publishes an ESB fault message to the BizTalk Server Message Box or the BizTalk Failed Message Routing mechanism generates a fault message.</span></span> <span data-ttu-id="d8a85-104">Un puerto de envío configurado previamente con el componente de canalización de codificador de excepciones de ESB, se suscribe a ambos de los tipos de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d8a85-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to both of the fault message types.</span></span> <span data-ttu-id="d8a85-105">Procesa los mensajes de error y los conserva como archivos de disco que se pueden ver mediante InfoPath, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="d8a85-105">It processes the fault messages and then persists them as disk files that you can view using InfoPath, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="d8a85-106">![Recopilar Carga de excepciones](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")</span><span class="sxs-lookup"><span data-stu-id="d8a85-106">![Collecting Exceptions Payload](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")</span></span>  
  
 <span data-ttu-id="d8a85-107">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="d8a85-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="d8a85-108">**Captura de un mensaje de error y guardarlos en un archivo de disco**</span><span class="sxs-lookup"><span data-stu-id="d8a85-108">**Capturing a fault message and persisting it to a disk file**</span></span>  
  
 <span data-ttu-id="d8a85-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8a85-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following:</span></span>  
  
- <span data-ttu-id="d8a85-110">**Un preconfigurada puerto de envío que usa la canalización de envío del procesador de errores de ESB.**</span><span class="sxs-lookup"><span data-stu-id="d8a85-110">**A preconfigured send port that uses the ESB Fault Processor send pipeline.**</span></span> <span data-ttu-id="d8a85-111">Puede configurar este puerto de envío según sus propios requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="d8a85-111">You can configure this send port according to your own specific requirements.</span></span>  
  
- <span data-ttu-id="d8a85-112">**El ejemplo de controlador de excepciones de mensaje persistencia personalizada.**</span><span class="sxs-lookup"><span data-stu-id="d8a85-112">**The Message Persisting Custom Exception Handler sample.**</span></span> <span data-ttu-id="d8a85-113">Este ejemplo muestra cómo un controlador de excepciones con acoplamiento flexible puede recibir mensajes de error, extraer los mensajes de BizTalk Server contienen, normalizar y enriquecer los mensajes y escribirlos como archivos de disco en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="d8a85-113">This sample shows how a loosely coupled generic exception handler can receive fault messages, extract the BizTalk Server messages they contain, normalize and enrich the messages, and write them as disk files to the file system.</span></span>  
  
- <span data-ttu-id="d8a85-114">**El ejemplo de enrutamiento de mensajes de error de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="d8a85-114">**The BizTalk Failed Message Routing sample.**</span></span> <span data-ttu-id="d8a85-115">En este ejemplo se muestra cómo el marco de administración de excepciones de ESB puede normalizar y enriquecer los mensajes de error generados de forma nativa mediante el mecanismo de enrutamiento de mensajes de error en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d8a85-115">This sample shows how the ESB Exception Management Framework can normalize and enrich fault messages natively generated by the Failed Message Routing mechanism in BizTalk Server.</span></span>  
  
  <span data-ttu-id="d8a85-116">Para obtener más información, consulte [ejecutando el mensaje de persistencia personalizado excepción ejemplo del controlador](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) y [ejecución del error mensaje enrutamiento ESB procesamiento ejemplo BizTalk](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d8a85-116">For more information, see [Running the Message Persisting Custom Exception Handler Sample](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) and [Running the BizTalk Failed Message Routing ESB Processing Sample](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).</span></span>
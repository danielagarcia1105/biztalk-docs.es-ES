---
title: "Recopilar excepciones y conservar la carga con el procesador de la excepción de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dd0ec42ab60636202a8ff99fa8fab8d96a95a19
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a><span data-ttu-id="99355-102">Recopilar excepciones y conservar la carga con el procesador de la excepción de ESB</span><span class="sxs-lookup"><span data-stu-id="99355-102">Collecting Exceptions and Persisting the Payload Using the ESB Exception Processor</span></span>
<span data-ttu-id="99355-103">En este caso de uso, el controlador de excepciones para una orquestación publica un mensaje de error ESB en el cuadro de mensaje de BizTalk Server o el mecanismo de enrutamiento de mensajes de error de BizTalk genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="99355-103">In this use case, either the exception handler for an orchestration publishes an ESB fault message to the BizTalk Server Message Box or the BizTalk Failed Message Routing mechanism generates a fault message.</span></span> <span data-ttu-id="99355-104">Un puerto de envío configurado previamente con el componente de canalización de codificador de excepción de ESB, se suscribe a los dos tipos de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="99355-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to both of the fault message types.</span></span> <span data-ttu-id="99355-105">Procesa los mensajes de error y, a continuación, los conserva como archivos de disco que se pueden ver con InfoPath, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="99355-105">It processes the fault messages and then persists them as disk files that you can view using InfoPath, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="99355-106">![Recopilar Carga de excepciones](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")</span><span class="sxs-lookup"><span data-stu-id="99355-106">![Collecting Exceptions Payload](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")</span></span>  
  
 <span data-ttu-id="99355-107">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="99355-107">**Figure 1**</span></span>  
  
 <span data-ttu-id="99355-108">**Captura de un mensaje de error y almacenarla en un archivo de disco**</span><span class="sxs-lookup"><span data-stu-id="99355-108">**Capturing a fault message and persisting it to a disk file**</span></span>  
  
 <span data-ttu-id="99355-109">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="99355-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following:</span></span>  
  
-   <span data-ttu-id="99355-110">**Un preconfiguradas puerto de envío que se usa la canalización de envío de procesador de error de ESB.**</span><span class="sxs-lookup"><span data-stu-id="99355-110">**A preconfigured send port that uses the ESB Fault Processor send pipeline.**</span></span> <span data-ttu-id="99355-111">Puede configurar este puerto de envío según sus propios requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="99355-111">You can configure this send port according to your own specific requirements.</span></span>  
  
-   <span data-ttu-id="99355-112">**El ejemplo del controlador de excepción de personalizada de conservación de mensaje.**</span><span class="sxs-lookup"><span data-stu-id="99355-112">**The Message Persisting Custom Exception Handler sample.**</span></span> <span data-ttu-id="99355-113">Este ejemplo muestra cómo un controlador de excepción genérica acoplamiento flexible puede recibir mensajes de error, extraer los mensajes de BizTalk Server contienen, normalizar y enriquecer los mensajes y escribirlos como archivos de disco en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="99355-113">This sample shows how a loosely coupled generic exception handler can receive fault messages, extract the BizTalk Server messages they contain, normalize and enrich the messages, and write them as disk files to the file system.</span></span>  
  
-   <span data-ttu-id="99355-114">**El ejemplo de enrutamiento de mensajes de error de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="99355-114">**The BizTalk Failed Message Routing sample.**</span></span> <span data-ttu-id="99355-115">Este ejemplo muestra cómo el marco de trabajo de administración de excepciones de ESB puede normalizar y enriquecer los mensajes de error de forma nativa generados por el mecanismo de enrutamiento de mensajes de error en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="99355-115">This sample shows how the ESB Exception Management Framework can normalize and enrich fault messages natively generated by the Failed Message Routing mechanism in BizTalk Server.</span></span>  
  
 <span data-ttu-id="99355-116">Para obtener más información, consulte [ejecuta el mensaje de persistencia personalizado excepción ejemplo del controlador](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) y [ejecutando el error mensaje enrutamiento ESB procesamiento de ejemplo de BizTalk](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="99355-116">For more information, see [Running the Message Persisting Custom Exception Handler Sample](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) and [Running the BizTalk Failed Message Routing ESB Processing Sample](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).</span></span>
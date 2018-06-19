---
title: Entrega ordenada de mensajes con el adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8b602adf93152f6af1e5dbbc576180d570a4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264532"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a><span data-ttu-id="50c41-102">Entrega ordenada de mensajes con el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="50c41-102">Ordered Delivery of Messages with the MQSeries Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="50c41-103">Proporciona un **entrega ordenada** puertos de envío de la opción para estático.</span><span class="sxs-lookup"><span data-stu-id="50c41-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="50c41-104">Establecer el **entrega ordenada** opción en un puerto de envío a **True** garantiza que BizTalk Server entrega mensajes al puerto de envío en el mismo orden que se publican en la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="50c41-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the BizTalk MessageBox database.</span></span> <span data-ttu-id="50c41-105">Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="50c41-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="50c41-106">Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="50c41-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="50c41-107">Por ejemplo, al recibir mensajes con el adaptador de recepción de MQSeries, la ubicación de recepción debe configurarse con la opción **orden con pausa** o **orden con suspensión**.</span><span class="sxs-lookup"><span data-stu-id="50c41-107">For example, when receiving messages with the MQSeries receive adapter, the receive location should be configured with the option **Order with Stop** or **Order with Suspend**.</span></span>  
  
-   <span data-ttu-id="50c41-108">Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción **True**.</span><span class="sxs-lookup"><span data-stu-id="50c41-108">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="50c41-109">Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="50c41-109">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="50c41-110">Utilizar el adaptador de MQSeries para la entrega ordenada de los mensajes</span><span class="sxs-lookup"><span data-stu-id="50c41-110">Using the MQSeries Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="50c41-111">El adaptador de recepción de MQSeries proporciona compatibilidad para conservar el orden de los mensajes cuando se envían a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="50c41-111">The MQSeries receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="50c41-112">To-end ordenada puede conseguir la entrega de mensajes a través de BizTalk Server cuando se reciben mensajes con el adaptador de MQSeries si los mensajes se procesan por un puerto de envío que se configura con el **entrega ordenada** opción establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="50c41-112">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MQSeries adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c41-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c41-113">See Also</span></span>  
 <span data-ttu-id="50c41-114">[Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="50c41-114">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="50c41-115">Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío</span><span class="sxs-lookup"><span data-stu-id="50c41-115">How to Configure MQSeries Adapter Receive Locations and Send Ports</span></span>](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)
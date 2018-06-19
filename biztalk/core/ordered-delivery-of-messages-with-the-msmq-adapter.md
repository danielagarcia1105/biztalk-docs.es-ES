---
title: Entrega ordenada de mensajes con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263588"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a><span data-ttu-id="d1dc2-102">Entrega ordenada de mensajes con el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="d1dc2-102">Ordered Delivery of Messages with the MSMQ Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d1dc2-103">Proporciona un **entrega ordenada** puertos de envío de la opción para estático.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="d1dc2-104">Establecer el **entrega ordenada** opción en un puerto de envío a **True** garantiza que BizTalk Server entrega mensajes al puerto de envío en el mismo orden que se publican en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the MessageBox database.</span></span> <span data-ttu-id="d1dc2-105">Para proporcionar una entrega ordenada de extremo a extremo, deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="d1dc2-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="d1dc2-106">Los mensajes se tienen que recibir con un adaptador que conserve el orden de los mensajes cuando se envíen al servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="d1dc2-107">Debe suscribirse a estos mensajes con un puerto de envío que tiene la **entrega ordenada** opción **True**.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-107">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="d1dc2-108">Si una orquestación se utiliza para procesar los mensajes, una sola instancia de la orquestación deben usarse, la orquestación debe estar configurada para utilizar un convoy secuencial y la **entrega ordenada** propiedad de la puerto de recepción de la orquestación debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-108">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="d1dc2-109">Utilizar el adaptador de MSMQ para la entrega ordenada de los mensajes</span><span class="sxs-lookup"><span data-stu-id="d1dc2-109">Using the MSMQ Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="d1dc2-110">El adaptador de recepción MSMQ proporciona compatibilidad para preservar el orden de los mensajes cuando se envíen a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-110">The MSMQ receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="d1dc2-111">To-end ordenada puede conseguir la entrega de mensajes a través de BizTalk Server cuando se reciben mensajes con el adaptador de MSMQ si los mensajes se procesan por un puerto de envío que se configura con el **entrega ordenada** opción establecida en  **True**.</span><span class="sxs-lookup"><span data-stu-id="d1dc2-111">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MSMQ adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1dc2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1dc2-112">See Also</span></span>  
 <span data-ttu-id="d1dc2-113">[Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d1dc2-113">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="d1dc2-114">Cómo configurar ubicación de recepción de MSMQ</span><span class="sxs-lookup"><span data-stu-id="d1dc2-114">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)
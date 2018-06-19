---
title: Recopilar excepciones y enrutamiento de mensajes para la reparación y vuelva a intentarlo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a61658a-0bac-4802-b506-02e61a3d2a9b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a1d080cc3b87cf371729c51e1b1f26e07ae521e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006765"
---
# <a name="collecting-exceptions-and-routing-messages-for-repair-and-resubmit"></a><span data-ttu-id="186e1-102">Recopilar excepciones y enrutamiento de mensajes para la reparación y vuelva a intentarlo</span><span class="sxs-lookup"><span data-stu-id="186e1-102">Collecting Exceptions and Routing Messages for Repair and Resubmit</span></span>
<span data-ttu-id="186e1-103">En este caso de uso, un controlador de excepciones personalizado recoge un mensaje de error recibido a través de un servicio Web y los enruta a un archivo de disco en un formato compatible con una plantilla de InfoPath que se incluye con la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="186e1-103">In this use case, a custom exception handler picks up a fault message received through a Web service and routes it to a disk file in a format compatible with an InfoPath template included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="186e1-104">El usuario puede abrir el archivo con Microsoft InfoPath, editar el contenido del mensaje y vuelva a enviar el mensaje para el procesamiento, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="186e1-104">The user can open the file using Microsoft InfoPath, edit the message contents, and resubmit the message for processing, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="186e1-105">![Recopilar reparación de excepciones](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")</span><span class="sxs-lookup"><span data-stu-id="186e1-105">![Collecting Exceptions Repair](../esb-toolkit/media/ch3-collectingexceptionsrepair.gif "Ch3-CollectingExceptionsRepair")</span></span>  
  
 <span data-ttu-id="186e1-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="186e1-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="186e1-107">**Enrutamiento de un mensaje para su reparación y reenvío**</span><span class="sxs-lookup"><span data-stu-id="186e1-107">**Routing a message for repair and resubmission**</span></span>  
  
 <span data-ttu-id="186e1-108">El ejemplo de reparación y volver a enviar controlador de excepciones personalizado que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="186e1-108">The Repair and Resubmit Custom Exception Handler sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="186e1-109">Cuando un proceso en una orquestación detecta un error, el controlador de excepciones en cuanto orquestación genera y publica un mensaje de error ESB.</span><span class="sxs-lookup"><span data-stu-id="186e1-109">When a process in an orchestration encounters an error, the exception handler in that orchestration generates and publishes an ESB fault message.</span></span> <span data-ttu-id="186e1-110">Este mensaje de error incluye, en su carga, los mensajes (incluidos sus propiedades de contexto que están relacionados con BizTalk Server) que estaban "en proceso" cuando se produjo la excepción y la excepción actual detectada por el motor de orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="186e1-110">This fault message includes, in its payload, the messages (including their context properties that are related to BizTalk Server) that were "in flight" when the exception occurred, and the current exception caught by the BizTalk Orchestration engine.</span></span> <span data-ttu-id="186e1-111">Cuando se publica un mensaje de error ESB, se anulará en cola para una orquestación de suscripción (un controlador de excepciones personalizado) que extrae e inspecciona los mensajes en curso y el objeto de excepción del sistema y enruta los mensajes en curso en una carpeta de archivos, desde el que un usuario puede editar el mensaje mediante InfoPath y reenviarlo a BizTalk Server para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="186e1-111">After an ESB fault message is published, it is de-queued to a subscribing orchestration (a custom exception handler) that extracts and inspects the in-flight messages and the system exception object, and routes the in-flight messages to a file folder, from which a user can edit the message using InfoPath and resubmit it to BizTalk Server for processing.</span></span>  
  
 <span data-ttu-id="186e1-112">Para obtener más información, consulte [ejecuta la reparación y volver a enviar ejemplo del controlador de excepción personalizada](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md).</span><span class="sxs-lookup"><span data-stu-id="186e1-112">For more information, see [Running the Repair and Resubmit Custom Exception Handler Sample](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md).</span></span>
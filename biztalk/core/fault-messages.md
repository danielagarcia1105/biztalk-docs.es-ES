---
title: Mensajes de error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4127fd5718ee910cb298436c0d0f7058ccba55b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245900"
---
# <a name="fault-messages"></a><span data-ttu-id="607ee-102">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="607ee-102">Fault Messages</span></span>
<span data-ttu-id="607ee-103">Los puertos de solicitud-respuesta pueden tener mensajes de error asociados de modo que si se produce un error después de que se ha enviado una solicitud, el servicio de respuesta puede comunicar el error al solicitante, en vez de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="607ee-103">Request-response ports can have fault messages associated with them, so that if something goes wrong after a request is sent, the responding service can communicate the error to the requester, in lieu of the response.</span></span>  
  
 <span data-ttu-id="607ee-104">Cada operación de un puerto de solicitud-respuesta puede controlar un número arbitrario de distintos errores.</span><span class="sxs-lookup"><span data-stu-id="607ee-104">Each operation of a request-response port can handle an arbitrary number of different faults.</span></span> <span data-ttu-id="607ee-105">Un mensaje de error puede tener cualquier tipo de mensaje aunque éste debe ser único para la operación no debe ser el que use la respuesta en esa operación de puerto.</span><span class="sxs-lookup"><span data-stu-id="607ee-105">A fault message can have any message type, but the message type must be unique for the operation, and it must not be the type used by the response in that port operation.</span></span>  
  
## <a name="receiving-fault-messages"></a><span data-ttu-id="607ee-106">Recibir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="607ee-106">Receiving fault messages</span></span>  
 <span data-ttu-id="607ee-107">Si la operación de puerto envía una solicitud y, después, recibe una respuesta, puede usarla para recibir uno o más tipos de mensajes de error diferentes.</span><span class="sxs-lookup"><span data-stu-id="607ee-107">If your port operation sends a request, then receives a response, you can use it to receive one or more different fault message types.</span></span>  
  
 <span data-ttu-id="607ee-108">Puede configurar un **excepción de filtrado** bloque para controlar un mensaje de error entrante, seleccione el error adecuado en la operación de puerto de solicitud-respuesta como su tipo de objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="607ee-108">You can configure a **Catch Exception** block to handle an incoming fault message by selecting the appropriate fault from the request-response port operation as its Exception Object Type.</span></span>  
  
## <a name="sending-fault-messages"></a><span data-ttu-id="607ee-109">Enviar mensajes de error</span><span class="sxs-lookup"><span data-stu-id="607ee-109">Sending fault messages</span></span>  
 <span data-ttu-id="607ee-110">Si la operación de puerto recibe una respuesta y, después, envía una solicitud, puede usarla para enviar uno o más tipos de mensajes de error diferentes.</span><span class="sxs-lookup"><span data-stu-id="607ee-110">If your port operation receives a response, then sends a request, you can use it to send one or more different fault message types.</span></span>  
  
 <span data-ttu-id="607ee-111">Por ejemplo si la orquestación detecta una condición de error y produce una excepción, puede enviar un mensaje de error desde el **excepción de filtrado** bloque que controla la excepción.</span><span class="sxs-lookup"><span data-stu-id="607ee-111">If for example your orchestration encounters an error condition and throws an exception, you can send a fault message from within the **Catch Exception** block that handles the exception.</span></span> <span data-ttu-id="607ee-112">Construirá un mensaje de error de un tipo adecuado para expresar la situación al servicio que participa y especificará ese mensaje de error en una forma Envío que usará el error correspondiente en la operación de puerto.</span><span class="sxs-lookup"><span data-stu-id="607ee-112">You construct a fault message of an appropriate type to convey the situation to the participating service, and specify that fault message on a Send shape that will use the corresponding fault in the port operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607ee-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="607ee-113">See Also</span></span>  
 [<span data-ttu-id="607ee-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="607ee-114">Exceptions</span></span>](../core/exceptions.md)
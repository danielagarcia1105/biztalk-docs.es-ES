---
title: Componente de canalización de ensamblador de BizTalk Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b1be8b898bc00e814bbb251682f2e2f474ade1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990253"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a><span data-ttu-id="49045-102">Componente de canalización de ensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="49045-102">BizTalk Framework Assembler Pipeline Component</span></span>
<span data-ttu-id="49045-103">BizTalk Framework es un enfoque para hacer una entrega garantizada exactamente una vez utilizando protocolos de transporte mediante conexión como HTTP o SMTP.</span><span class="sxs-lookup"><span data-stu-id="49045-103">The BizTalk Framework is one approach for doing exactly-once guaranteed delivery using over-the-wire transport protocols such as HTTP or SMTP.</span></span> <span data-ttu-id="49045-104">Este marco de trabajo existe desde 1998 y puede considerarse un precursor de las iniciativas de estándares pendientes basadas en servicios Web, específicamente WSReliable.</span><span class="sxs-lookup"><span data-stu-id="49045-104">This framework has existed since 1998, and can be thought of as a precursor to pending standards initiatives based on Web services, specifically WSReliable.</span></span> <span data-ttu-id="49045-105">Por lo general, el problema de la entrega de datos garantizada exactamente una vez ha sido el dominio de tecnologías como Message Queue Server (también conocida como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="49045-105">Typically, the problem of guaranteed exactly-once delivery of data has been the domain of technologies like Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="49045-106">Sin embargo, estas tecnologías suelen requerir software común en los dos extremos de un flujo de datos y tampoco hacen nada para resolver la utilización de protocolos de transporte abiertos basados en redes públicas, por ejemplo, datos que fluyen entre empresas a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="49045-106">However, such technologies usually require common software at the two endpoints of a data flow, and also do nothing to address the use of open transport protocols based on public networks, for example, data that flows across enterprise boundaries by using the Internet.</span></span>  
  
 <span data-ttu-id="49045-107">Obviamente, BizTalk Framework implementa algunos de los mismos mecanismos presentes en intentos previos de resolver el problema de la entrega de datos garantizada exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="49045-107">Not surprisingly, the BizTalk Framework implements some of the same mechanisms present in earlier attempts to solve this problem of guaranteed exactly-once delivery of data.</span></span> <span data-ttu-id="49045-108">Un buen ejemplo de otras soluciones al problema es el intercambio electrónico de datos (EDI), en el que los documentos de confirmación funcional del estándar 997 y los números de control de ANSI X12 forman la base de la garantía de que los datos se reciban solo una vez, y de que se notifique al remitente cualquier problema en el extremo receptor.</span><span class="sxs-lookup"><span data-stu-id="49045-108">A good example of other solutions to the problem is electronic data interchange (EDI), where ANSI X12 control numbers and standard 997 functional acknowledgment documents form the basis of guaranteeing that data is received only one time, and that the sender is notified of any problems on the receiving end.</span></span>  
  
 <span data-ttu-id="49045-109">BizTalk Framework asume que, por distintos que sean los sistemas de intercambio de datos, ambos entienden los requisitos del protocolo de BizTalk Framework respecto de:</span><span class="sxs-lookup"><span data-stu-id="49045-109">The BizTalk Framework assumes that, however disparate the systems trading data, they both understand the BizTalk Framework protocol requirements of:</span></span>  
  
- <span data-ttu-id="49045-110">Utilizar un formato de sobre previsible en el que ajustar las transmisiones.</span><span class="sxs-lookup"><span data-stu-id="49045-110">Using a predictable envelope format for wrapping transmissions.</span></span>  
  
- <span data-ttu-id="49045-111">Etiquetar todas las transmisiones de salida con un identificador único global.</span><span class="sxs-lookup"><span data-stu-id="49045-111">Tagging every outbound transmission with a globally unique identifier.</span></span>  
  
- <span data-ttu-id="49045-112">Devolver siempre al remitente una confirmación de recepción que incluya el identificador único global, incluso de datos que ya se hayan recibido, confirmado y procesado.</span><span class="sxs-lookup"><span data-stu-id="49045-112">Always returning to the sender an acknowledgment of receipt that includes the globally unique identifier, even for data already received, acknowledged, and processed.</span></span>  
  
- <span data-ttu-id="49045-113">Algunos medios por los que el remitente pueda repetir las transmisiones, bien hasta que llegue una notificación del receptor o bien pase un período de tiempo más allá del cual la transmisión ya no sea válida.</span><span class="sxs-lookup"><span data-stu-id="49045-113">Some means by which the sender can repeat transmission until either a receipt arrives from the receiver, or some time period passes beyond which the transmission is no longer valid.</span></span>  
  
  <span data-ttu-id="49045-114">El componente de canalización de ensamblador de BizTalk Framework es el responsable de serializar el sobre y los contenidos de BizTalk Framework en el mensaje antes de la transmisión y repetición del envío en caso de que no llegue una notificación en el período de tiempo asignado.</span><span class="sxs-lookup"><span data-stu-id="49045-114">The BizTalk Framework Assembler pipeline component is responsible for serializing the BizTalk Framework envelope and contents onto the message before transmission and resending in the event that a receipt does not arrive in the allotted time period.</span></span> <span data-ttu-id="49045-115">También es responsable de recibir y procesar las notificaciones y de eliminar la instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="49045-115">It is also responsible for receiving and processing the receipts and deleting the message instance.</span></span> <span data-ttu-id="49045-116">(Una copia de la instancia de mensaje del mensaje enviado se mantiene en la base de datos de cuadro de mensajes hasta que BizTalk recibe una notificación de recepción del destinatario.</span><span class="sxs-lookup"><span data-stu-id="49045-116">(A copy of the message instance of the sent message is kept in the MessageBox database until BizTalk receives a confirmation receipt from the destination.</span></span> <span data-ttu-id="49045-117">Una vez recibida, el motor de mensajería elimina la instancia de mensaje).</span><span class="sxs-lookup"><span data-stu-id="49045-117">After the confirmation receipt is received, the message instance is deleted by the Messaging Engine.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49045-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="49045-118">See Also</span></span>  
 <span data-ttu-id="49045-119">[Cómo configurar el componente de canalización de ensamblador de BizTalk Framework](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="49045-119">[How to Configure the BizTalk Framework Assembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="49045-120">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="49045-120">Pipeline Components</span></span>](../core/pipeline-components.md)
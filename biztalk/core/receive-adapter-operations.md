---
title: Operaciones del adaptador de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d4e5ee9d9afbbb687f415b42652d76a50bac4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980125"
---
# <a name="receive-adapter-operations"></a><span data-ttu-id="28f28-102">Operaciones del adaptador de recepción</span><span class="sxs-lookup"><span data-stu-id="28f28-102">Receive Adapter Operations</span></span>
<span data-ttu-id="28f28-103">Los adaptadores de recepción pueden realizar las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="28f28-103">Receive adapters can perform the following operations:</span></span>  

- <span data-ttu-id="28f28-104">**Envío unidireccional: void SubmitMessage (IBaseMessage msg).**</span><span class="sxs-lookup"><span data-stu-id="28f28-104">**One-way submit: void SubmitMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="28f28-105">Después de recibir un mensaje de un puerto de recepción, el adaptador lo envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ser procesados por suscripción de una orquestación o puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="28f28-105">After receiving a message from a receive port, the adapter submits it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be processed by a subscribing orchestration or send port.</span></span>  

- <span data-ttu-id="28f28-106">**Suspender: void MoveToSuspendQ (IBaseMessage msg).**</span><span class="sxs-lookup"><span data-stu-id="28f28-106">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="28f28-107">Cuando el adaptador determina un análisis, una transmisión, una serialización o se ha producido otro error de aplicación tras el envío, el mensaje se mueve a la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="28f28-107">When the adapter determines a parsing, transmission, serialization, or other applicable failure has occurred after submission, it moves the message to the Suspended queue.</span></span>  

- <span data-ttu-id="28f28-108">**Enviar solicitud: void SubmitRequestMessage (IBaseMessage requestMsg, cadena correlationToken, [MarshalAs (UnmanagedType.bool)] bool firstResponseOnly, expirationTime de fecha y hora, IBTTransmitter responseCallback).**</span><span class="sxs-lookup"><span data-stu-id="28f28-108">**Submit request: void SubmitRequestMessage(IBaseMessage requestMsg, string correlationToken, [MarshalAs(UnmanagedType.Bool)]bool firstResponseOnly, DateTime expirationTime, IBTTransmitter responseCallback).**</span></span> <span data-ttu-id="28f28-109">Un adaptador de recepción envía un mensaje entrante a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un par solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="28f28-109">A receive adapter submits an incoming message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a request-response pair.</span></span> <span data-ttu-id="28f28-110">Después de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa correctamente este mensaje de solicitud, envía la respuesta al adaptador para transmitirla a un extremo específico.</span><span class="sxs-lookup"><span data-stu-id="28f28-110">After [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] successfully processes this request message, it sends the response to the adapter to transmit it to the specific endpoint.</span></span>

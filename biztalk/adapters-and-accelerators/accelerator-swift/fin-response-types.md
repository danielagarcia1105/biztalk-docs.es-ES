---
title: Tipos de respuesta FIN | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-types"></a><span data-ttu-id="1523e-102">Tipos de respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="1523e-102">FIN Response Types</span></span>
<span data-ttu-id="1523e-103">Conciliación de respuesta FIN (FRR) reconcilia las respuestas a los mensajes de SWIFT FINÉS de categoría del 0 al 9.</span><span class="sxs-lookup"><span data-stu-id="1523e-103">FIN Response Reconciliation (FRR) reconciles responses to any Category 0 to 9 SWIFT FIN message.</span></span> <span data-ttu-id="1523e-104">En respuesta a uno de estos mensajes FIN, la aplicación de SWIFT FINÉS siempre envía al menos uno y posiblemente más de una confirmación (ACK) o un valor negativo (NAK) de confirmación.</span><span class="sxs-lookup"><span data-stu-id="1523e-104">In response to one of these FIN messages, the SWIFT FIN application always sends at least one, and possibly more than one, acknowledgment (ACK) or negative acknowledgment (NAK).</span></span> <span data-ttu-id="1523e-105">En la tabla siguiente muestra los tipos de mensajes de entrada y la salida (respuesta de) los mensajes procesados por FRR.</span><span class="sxs-lookup"><span data-stu-id="1523e-105">The following table shows the message types of the outbound and inbound (response) messages processed by FRR.</span></span>  
  
|<span data-ttu-id="1523e-106">Salida /</span><span class="sxs-lookup"><span data-stu-id="1523e-106">Outbound/</span></span><br /><br /> <span data-ttu-id="1523e-107">de entrada</span><span class="sxs-lookup"><span data-stu-id="1523e-107">inbound</span></span>|<span data-ttu-id="1523e-108">Tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="1523e-108">Message type</span></span>|<span data-ttu-id="1523e-109">Estado del mensaje</span><span class="sxs-lookup"><span data-stu-id="1523e-109">Message status</span></span>|  
|----------------------------|------------------|--------------------|  
|<span data-ttu-id="1523e-110">Salida</span><span class="sxs-lookup"><span data-stu-id="1523e-110">Outbound</span></span>|<span data-ttu-id="1523e-111">Todos los tipos de mensaje SWIFT FINÉS de categoría del 0 al 9</span><span class="sxs-lookup"><span data-stu-id="1523e-111">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="1523e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="1523e-112">N/A</span></span>|  
|<span data-ttu-id="1523e-113">Entrada</span><span class="sxs-lookup"><span data-stu-id="1523e-113">Inbound</span></span>|<span data-ttu-id="1523e-114">MQ Series PAN/NAN (confirmación de nivel de transporte MQ Series/NAK)</span><span class="sxs-lookup"><span data-stu-id="1523e-114">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="1523e-115">Confirmación de transporte de MQSeries</span><span class="sxs-lookup"><span data-stu-id="1523e-115">MQSeries transport acknowledgment</span></span>|  
||<span data-ttu-id="1523e-116">MT010 (advertencia de no entrega)</span><span class="sxs-lookup"><span data-stu-id="1523e-116">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="1523e-117">SWIFT enviado correctamente la versión original del mensaje al socio comercial, pero tiene ninguna indicación de que el socio comercial recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1523e-117">SWIFT successfully sent the original message to the partner, but has no indication that the partner received the message.</span></span> <span data-ttu-id="1523e-118">Si [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe varios mensajes de advertencia de no entrega (NDW), se ejecuta un bucle y espera a que el siguiente mensaje esperado.</span><span class="sxs-lookup"><span data-stu-id="1523e-118">If [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives multiple Non-Delivery Warning (NDW) messages, it loops and waits for the next expected message.</span></span>|  
||<span data-ttu-id="1523e-119">MT011 (notificación de entrega)</span><span class="sxs-lookup"><span data-stu-id="1523e-119">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="1523e-120">SWIFT enviado correctamente la versión original del mensaje al socio comercial y recibe una indicación de que el socio comercial recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1523e-120">SWIFT successfully sent the original message to the partner, and received an indication that the partner received the message.</span></span>|  
||<span data-ttu-id="1523e-121">MT012 (notificación de remitente)</span><span class="sxs-lookup"><span data-stu-id="1523e-121">MT012 (Sender Notification)</span></span>|<span data-ttu-id="1523e-122">SWIFT recibe correctamente el mensaje original desde [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1523e-122">SWIFT successfully received the original message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
||<span data-ttu-id="1523e-123">MT015 (DIN o NAK diferida)</span><span class="sxs-lookup"><span data-stu-id="1523e-123">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="1523e-124">SWIFT no ha enviado el mensaje original al socio comercial.</span><span class="sxs-lookup"><span data-stu-id="1523e-124">SWIFT has not successfully sent the original message to the partner.</span></span>|  
||<span data-ttu-id="1523e-125">MT019 (anular la notificación)</span><span class="sxs-lookup"><span data-stu-id="1523e-125">MT019 (Abort Notification)</span></span>|<span data-ttu-id="1523e-126">Se anuló la transmisión de mensajes en SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1523e-126">Message transmission aborted at SWIFT.</span></span>|  
||<span data-ttu-id="1523e-127">MTS21_FIN_ACKNAK (confirmación o una confirmación negativa de un mensaje FIN enviado por un LT (confirmación/NAK))</span><span class="sxs-lookup"><span data-stu-id="1523e-127">MTS21_FIN_ACKNAK (Acknowledgment or negative acknowledgment of a FIN message sent by an LT (ACK/NAK))</span></span>|<span data-ttu-id="1523e-128">SWIFT correctamente o no ha recibido el mensaje de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1523e-128">SWIFT successfully or unsuccessfully received the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="1523e-129">Este mensaje trata ambos casos.</span><span class="sxs-lookup"><span data-stu-id="1523e-129">This message covers both of these cases.</span></span> <span data-ttu-id="1523e-130">Si es una confirmación o un NAK viene determinado por el valor en el campo 451 del mensaje ("0" para ACK) y "1" para NAK.</span><span class="sxs-lookup"><span data-stu-id="1523e-130">Whether it is an ACK or a NAK is determined by the value in the 451 field of the message ("0" for ACK and "1" for NAK).</span></span> <span data-ttu-id="1523e-131">Se trata de la primera respuesta entregada a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1523e-131">This will be the first response delivered back to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
  
## <a name="deployment-of-schemas-for-frr"></a><span data-ttu-id="1523e-132">Implementación de esquemas para FRR</span><span class="sxs-lookup"><span data-stu-id="1523e-132">Deployment of Schemas for FRR</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="1523e-133">el programa de instalación implementa esquemas en FrrSchemas.dll para todos los mensajes de nivel de sistema (tal como se muestra en la tabla anterior).</span><span class="sxs-lookup"><span data-stu-id="1523e-133"> setup deploys schemas in FrrSchemas.dll for all system-level messages (as shown in the table above).</span></span> <span data-ttu-id="1523e-134">La orquestación FRR requiere estos esquemas para implementarse.</span><span class="sxs-lookup"><span data-stu-id="1523e-134">The FRR orchestration requires these schemas to be deployed.</span></span> <span data-ttu-id="1523e-135">Dado que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] el programa de instalación implementa estos esquemas en FrrSchemas.dll, no es necesario y no es así, debe implementar estos esquemas en otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="1523e-135">Because [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup deploys these schemas in FrrSchemas.dll, you do not have to, and must not, deploy these schemas in another project.</span></span> <span data-ttu-id="1523e-136">Si lo hace, se generará un error.</span><span class="sxs-lookup"><span data-stu-id="1523e-136">Doing so will generate an error.</span></span>  
  
 <span data-ttu-id="1523e-137">FRRSchemas.dll incluye los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="1523e-137">FRRSchemas.dll includes the following schemas:</span></span>  
  
-   <span data-ttu-id="1523e-138">TransportAck</span><span class="sxs-lookup"><span data-stu-id="1523e-138">TransportAck</span></span>  
  
-   <span data-ttu-id="1523e-139">MT010</span><span class="sxs-lookup"><span data-stu-id="1523e-139">MT010</span></span>  
  
-   <span data-ttu-id="1523e-140">MT011</span><span class="sxs-lookup"><span data-stu-id="1523e-140">MT011</span></span>  
  
-   <span data-ttu-id="1523e-141">MT012</span><span class="sxs-lookup"><span data-stu-id="1523e-141">MT012</span></span>  
  
-   <span data-ttu-id="1523e-142">MT015</span><span class="sxs-lookup"><span data-stu-id="1523e-142">MT015</span></span>  
  
-   <span data-ttu-id="1523e-143">MT019</span><span class="sxs-lookup"><span data-stu-id="1523e-143">MT019</span></span>  
  
-   <span data-ttu-id="1523e-144">MTS21_FIN_ACKNAK</span><span class="sxs-lookup"><span data-stu-id="1523e-144">MTS21_FIN_ACKNAK</span></span>
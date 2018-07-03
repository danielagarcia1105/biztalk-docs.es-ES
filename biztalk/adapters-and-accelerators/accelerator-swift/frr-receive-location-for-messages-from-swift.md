---
title: FRR ubicación de recepción para mensajes de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc4666e90510e7076a3f901ce6fc95b07ef16c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002085"
---
# <a name="frr-receive-location-for-messages-from-swift"></a><span data-ttu-id="0a7b6-102">FRR ubicación de recepción para mensajes de SWIFT</span><span class="sxs-lookup"><span data-stu-id="0a7b6-102">FRR Receive Location for Messages from SWIFT</span></span>
<span data-ttu-id="0a7b6-103">Para habilitar la conciliación de respuestas de FIN (FRR), debe configurar un FRR recibe el componente de canalización para recibir un mensaje de SAA y prepararla para el procesamiento por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7b6-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive pipeline component to receive a message from SAA and prepare it for processing by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="0a7b6-104">La canalización de recepción contiene los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="0a7b6-104">The receive pipeline contains the following components:</span></span>  
  
- <span data-ttu-id="0a7b6-105">En la fase de desensamblado del desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="0a7b6-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
- <span data-ttu-id="0a7b6-106">El componente de canalización de descodificador de FRR SWIFT en la fase de descodificador</span><span class="sxs-lookup"><span data-stu-id="0a7b6-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
- <span data-ttu-id="0a7b6-107">El componente de canalización de SWIFT FRR CorrelationSet solucionador en la fase de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="0a7b6-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
  <span data-ttu-id="0a7b6-108">Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe un panorámica o NAN, SWIFT FRR descodificador lee la propiedad de contexto de MQ comentarios para determinar si la respuesta es un panorámica o un NAN.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-108">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives a PAN/NAN, SWIFT FRR Decoder reads the MQ Feedback context property to determine whether the response is a PAN or a NAN.</span></span> <span data-ttu-id="0a7b6-109">Establece el transporte agnóstico [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]valores _FRRTransportLevelAck un valor booleano true para una panorámica o false para un NAN.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-109">It sets the transport-agnostic [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck Boolean values to true for a PAN or false for a NAN.</span></span>  
  
  <span data-ttu-id="0a7b6-110">El componente de canalización de resolución de SWIFT FRR CorrelationSet sobrescribe la propiedad de FRRCorrelationToken del mensaje de respuesta, que utiliza la orquestación de FRR, con el valor en el MQMD. Propiedad CorrelId.</span><span class="sxs-lookup"><span data-stu-id="0a7b6-110">The SWIFT FRR CorrelationSet Resolver pipeline component overwrites the response message's FRRCorrelationToken property, which the FRR orchestration uses, with the value in the MQMD.CorrelId property.</span></span>
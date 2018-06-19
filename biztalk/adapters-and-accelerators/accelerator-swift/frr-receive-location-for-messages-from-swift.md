---
title: FRR ubicación de recepción para mensajes de SWIFT. | Documentos de Microsoft
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
ms.openlocfilehash: 5d609cfc8c5177581f32ee0957a6a7ae7c1fe9a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207564"
---
# <a name="frr-receive-location-for-messages-from-swift"></a><span data-ttu-id="03417-102">FRR ubicación de recepción para mensajes de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="03417-102">FRR Receive Location for Messages from SWIFT</span></span>
<span data-ttu-id="03417-103">Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un FRR recibe el componente de canalización para recibir un mensaje de AAS y prepararlo para su procesamiento mediante [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03417-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive pipeline component to receive a message from SAA and prepare it for processing by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="03417-104">La canalización de recepción contiene los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="03417-104">The receive pipeline contains the following components:</span></span>  
  
-   <span data-ttu-id="03417-105">El Desensamblador SWIFT en la fase de desensamblado</span><span class="sxs-lookup"><span data-stu-id="03417-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
-   <span data-ttu-id="03417-106">El componente de canalización de descodificador de SWIFT FRR en la fase de descodificador</span><span class="sxs-lookup"><span data-stu-id="03417-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
-   <span data-ttu-id="03417-107">El componente de canalización de resolución de SWIFT FRR CorrelationSet en la fase de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="03417-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
 <span data-ttu-id="03417-108">Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe un PAN/NAN, SWIFT FRR descodificador lee la propiedad de contexto de comentarios de MQ para determinar si la respuesta es un panorámica o un valor NAN.</span><span class="sxs-lookup"><span data-stu-id="03417-108">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives a PAN/NAN, SWIFT FRR Decoder reads the MQ Feedback context property to determine whether the response is a PAN or a NAN.</span></span> <span data-ttu-id="03417-109">Establece el transporte independiente [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]valores _FRRTransportLevelAck un valor booleano en true para una panorámica o false para un valor NAN.</span><span class="sxs-lookup"><span data-stu-id="03417-109">It sets the transport-agnostic [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck Boolean values to true for a PAN or false for a NAN.</span></span>  
  
 <span data-ttu-id="03417-110">El componente de canalización de resolución de SWIFT FRR CorrelationSet sobrescribe la propiedad de FRRCorrelationToken del mensaje de respuesta, que usa la orquestación FRR, con el valor de la MQMD. Propiedad CorrelId.</span><span class="sxs-lookup"><span data-stu-id="03417-110">The SWIFT FRR CorrelationSet Resolver pipeline component overwrites the response message's FRRCorrelationToken property, which the FRR orchestration uses, with the value in the MQMD.CorrelId property.</span></span>
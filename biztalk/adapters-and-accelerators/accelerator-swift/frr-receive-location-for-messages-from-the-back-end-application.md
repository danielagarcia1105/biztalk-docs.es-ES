---
title: FRR ubicación de recepción para los mensajes de la aplicación de Back-End | Documentos de Microsoft
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
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d50f83feceac0238742cd474f70ecc1449f906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207540"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a><span data-ttu-id="d5e52-102">FRR ubicación de recepción para los mensajes de la aplicación de Back-End</span><span class="sxs-lookup"><span data-stu-id="d5e52-102">FRR Receive Location for Messages from the Back-End Application</span></span>
<span data-ttu-id="d5e52-103">Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un FRR ubicación de recepción que recibe mensajes de la aplicación de back-end y los enruta a BizTalk MessageBox para su uso por la orquestación FRR.</span><span class="sxs-lookup"><span data-stu-id="d5e52-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive location that receives messages from the back-end application and routes them to the BizTalk MessageBox for consumption by the FRR orchestration.</span></span> <span data-ttu-id="d5e52-104">La ubicación de recepción enruta un mensaje a través de una canalización de recepción FRR personalizada que debe crear con los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="d5e52-104">The receive location routes a message through a custom FRR receive pipeline that you must create with the following pipeline components:</span></span>  
  
-   <span data-ttu-id="d5e52-105">El Desensamblador SWIFT en la fase de desensamblado</span><span class="sxs-lookup"><span data-stu-id="d5e52-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
-   <span data-ttu-id="d5e52-106">El componente de canalización de descodificador de SWIFT FRR en la fase de descodificador</span><span class="sxs-lookup"><span data-stu-id="d5e52-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
-   <span data-ttu-id="d5e52-107">El componente de canalización de resolución de SWIFT FRR CorrelationSet en la fase de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="d5e52-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
 <span data-ttu-id="d5e52-108">El puerto de recepción controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True.</span><span class="sxs-lookup"><span data-stu-id="d5e52-108">The receive port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="d5e52-109">El mecanismo de transporte es lo que dicta la aplicación back-end.</span><span class="sxs-lookup"><span data-stu-id="d5e52-109">The transport mechanism is whatever the back-end application dictates.</span></span>  
  
 <span data-ttu-id="d5e52-110">Este puerto de recepción utiliza la misma canalización de recepción personalizada que se usa por la ubicación de recepción para los mensajes de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="d5e52-110">This receive port uses the same custom receive pipeline that is used by the receive location for messages from SWIFT.</span></span> <span data-ttu-id="d5e52-111">Sin embargo, la canalización lleva a cabo funciones diferentes para las dos ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="d5e52-111">However, the pipeline performs different functions for the two receive locations.</span></span> <span data-ttu-id="d5e52-112">En la ubicación de recepción de mensajes de la aplicación de back-end, el componente de canalización de resolución de SWIFT FRR CorrelationSet inicializa el token de correlación.</span><span class="sxs-lookup"><span data-stu-id="d5e52-112">In the receive location for messages from the back-end application, the SWIFT FRR CorrelationSet Resolver pipeline component initializes the correlation token.</span></span>
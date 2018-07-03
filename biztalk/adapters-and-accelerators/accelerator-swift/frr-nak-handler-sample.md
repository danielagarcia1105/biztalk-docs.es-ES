---
title: Ejemplo del controlador NAK de FRR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, NAKs
- examples, FRR
- NAKs
- acknowledgements
- FRR, examples
- examples, FRR NAK handler
ms.assetid: be992507-ba8c-461f-a563-f1d7b2ab221d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35574f47af789054bd8192da93ce5cffa1b3984b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996941"
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="b1f85-102">Ejemplo del controlador NAK de FRR</span><span class="sxs-lookup"><span data-stu-id="b1f85-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="b1f85-103">El ejemplo del controlador NAK de FRR muestra cómo crear un controlador personalizado para procesar los mensajes que se correlacionan conciliación de respuesta de FIN (FRR) con las respuestas de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="b1f85-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="b1f85-104">Este controlador personalizado procesa los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, que indica que SWIFT no recibido correctamente el mensaje de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="b1f85-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="b1f85-105">El controlador personalizado agrega un objeto de error para el mensaje, que el mensaje de un mensaje de dos partes y promociona las propiedades que provocan la orquestación de reparación de mensajes recoger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b1f85-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="b1f85-106">Como resultado, un taller de reparación puede corregir el mensaje y lo vuelva a enviar a SWIFT Alliance acceso (AAS).</span><span class="sxs-lookup"><span data-stu-id="b1f85-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="b1f85-107">**Componentes de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="b1f85-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="b1f85-108">El ejemplo del controlador NAK de FRR incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="b1f85-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
- <span data-ttu-id="b1f85-109">**RepairSWIFTRejectedMessage.odx.**</span><span class="sxs-lookup"><span data-stu-id="b1f85-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="b1f85-110">Esta orquestación es el controlador personalizado que procesa un mensaje que SWIFT podría no recibe correctamente, enrutarlo a la orquestación de reparación de mensajes para que pueda corregir y volver a enviar el mensaje de un taller de reparación.</span><span class="sxs-lookup"><span data-stu-id="b1f85-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
- <span data-ttu-id="b1f85-111">**RepairSWIFTRejectedMessage.btproj.**</span><span class="sxs-lookup"><span data-stu-id="b1f85-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="b1f85-112">Este proyecto incluye RepairSWIFTRejectedMessage.odx y las referencias necesarias para el proyecto para compilar e implementar.</span><span class="sxs-lookup"><span data-stu-id="b1f85-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
- <span data-ttu-id="b1f85-113">**RepairSWIFTRejectedMessage.sln.**</span><span class="sxs-lookup"><span data-stu-id="b1f85-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="b1f85-114">Esta solución incluye el proyecto RepairSWIFTRejectedMessage.btproj.</span><span class="sxs-lookup"><span data-stu-id="b1f85-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
  <span data-ttu-id="b1f85-115">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="b1f85-115">This section contains:</span></span>  
  
- [<span data-ttu-id="b1f85-116">Implementación del ejemplo del controlador NAK de FRR</span><span class="sxs-lookup"><span data-stu-id="b1f85-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
- [<span data-ttu-id="b1f85-117">Cómo funciona el ejemplo del controlador NAK de FRR</span><span class="sxs-lookup"><span data-stu-id="b1f85-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  

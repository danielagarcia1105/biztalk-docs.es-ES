---
title: Ejemplo del controlador NAK FRR | Documentos de Microsoft
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
ms.openlocfilehash: 2a3881b8bcf4b62af7653ef6214b4fccdf8402d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207412"
---
# <a name="frr-nak-handler-sample"></a><span data-ttu-id="af033-102">Ejemplo del controlador FRR NAK</span><span class="sxs-lookup"><span data-stu-id="af033-102">FRR NAK Handler Sample</span></span>
<span data-ttu-id="af033-103">El ejemplo del controlador de NAK FRR muestra cómo crear un controlador personalizado para procesar los mensajes que se correlacionan conciliación de respuesta de FIN (FRR) con las respuestas SWIFT.</span><span class="sxs-lookup"><span data-stu-id="af033-103">The FRR NAK Handler sample demonstrates how to create a custom handler to process messages that FIN Response Reconciliation (FRR) has correlated with SWIFT responses.</span></span> <span data-ttu-id="af033-104">Este controlador personalizado procesa los mensajes que se correlacionan FRR con un mensaje de confirmación negativo MTS21_FIN_ACKNAK, lo que indica que SWIFT no recibido correctamente el mensaje de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="af033-104">This custom handler processes messages that FRR has correlated with a MTS21_FIN_ACKNAK negative-acknowledgment message, which indicates that SWIFT did not successfully receive the message from A4SWIFT.</span></span> <span data-ttu-id="af033-105">El controlador personalizado agrega un objeto de error para el mensaje, hacer que el mensaje de un mensaje de dos partes y promociona las propiedades que provocan la orquestación de reparación de mensajes recoger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="af033-105">The custom handler adds an error object to the message, making the message a two-part message, and promotes the properties that cause the message-repair orchestration to pick up the message.</span></span> <span data-ttu-id="af033-106">Como resultado, un taller de reparación puede corregir el mensaje y enviarlo para SWIFT Alliance acceso (AAS).</span><span class="sxs-lookup"><span data-stu-id="af033-106">As a result, a repairer can fix the message and resend it to SWIFT Alliance Access (SAA).</span></span>  
  
 <span data-ttu-id="af033-107">**Componentes de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af033-107">**Sample Components**</span></span>  
  
 <span data-ttu-id="af033-108">El ejemplo del controlador de FRR NAK incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="af033-108">The FRR NAK Handler sample includes the following components:</span></span>  
  
-   <span data-ttu-id="af033-109">**RepairSWIFTRejectedMessage.odx.**</span><span class="sxs-lookup"><span data-stu-id="af033-109">**RepairSWIFTRejectedMessage.odx.**</span></span> <span data-ttu-id="af033-110">Esta orquestación es el controlador personalizado que procesa un mensaje que SWIFT podría no recibe correctamente, enviarlo a la orquestación de reparación de mensajes para que un taller de reparación puede corregir y volver a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="af033-110">This orchestration is the custom handler that processes a message that SWIFT could not successfully receive, routing it to the message-repair orchestration so a repairer can fix and resend the message.</span></span>  
  
-   <span data-ttu-id="af033-111">**RepairSWIFTRejectedMessage.btproj.**</span><span class="sxs-lookup"><span data-stu-id="af033-111">**RepairSWIFTRejectedMessage.btproj.**</span></span> <span data-ttu-id="af033-112">Este proyecto incluye RepairSWIFTRejectedMessage.odx y las referencias necesarias para el proyecto para generar e implementar.</span><span class="sxs-lookup"><span data-stu-id="af033-112">This project includes RepairSWIFTRejectedMessage.odx and the references required for the project to build and deploy.</span></span>  
  
-   <span data-ttu-id="af033-113">**RepairSWIFTRejectedMessage.sln.**</span><span class="sxs-lookup"><span data-stu-id="af033-113">**RepairSWIFTRejectedMessage.sln.**</span></span> <span data-ttu-id="af033-114">Esta solución incluye el proyecto RepairSWIFTRejectedMessage.btproj.</span><span class="sxs-lookup"><span data-stu-id="af033-114">This solution includes the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
 <span data-ttu-id="af033-115">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="af033-115">This section contains:</span></span>  
  
-   [<span data-ttu-id="af033-116">Implementar el ejemplo del controlador FRR NAK</span><span class="sxs-lookup"><span data-stu-id="af033-116">Implementing the FRR NAK Handler Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-frr-nak-handler-sample.md)  
  
-   [<span data-ttu-id="af033-117">Cómo funciona el ejemplo del controlador FRR NAK</span><span class="sxs-lookup"><span data-stu-id="af033-117">How the FRR NAK Handler Sample Works</span></span>](../../adapters-and-accelerators/accelerator-swift/how-the-frr-nak-handler-sample-works.md)  
  

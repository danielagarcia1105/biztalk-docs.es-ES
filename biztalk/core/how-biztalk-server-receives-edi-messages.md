---
title: "Cómo BizTalk Server recibe mensajes EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f3bb88c-9226-4791-b100-ba68dea45278
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb7cdda6a54db06c0388d8c72dcb65a2c8f21f02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-receives-edi-messages"></a><span data-ttu-id="d55d9-102">Cómo BizTalk Server recibe mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="d55d9-102">How BizTalk Server Receives EDI Messages</span></span>
<span data-ttu-id="d55d9-103">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje EDI, lleva a cabo la búsqueda de acuerdo de socio comercial y la detección de esquemas, valida el mensaje, envía una confirmación (si fuese necesario) y analiza el lote de EDI.</span><span class="sxs-lookup"><span data-stu-id="d55d9-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDI message, it performs trading partner agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and parses the EDI batch.</span></span> <span data-ttu-id="d55d9-104">Este procesamiento lo realiza el desensamblador EDI en la canalización de recepción EDI.</span><span class="sxs-lookup"><span data-stu-id="d55d9-104">This processing is performed by the EDI disassembler in the EDI Receive Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d55d9-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d55d9-105">In This Section</span></span>  
  
-   [<span data-ttu-id="d55d9-106">Componentes de recepción de EDI</span><span class="sxs-lookup"><span data-stu-id="d55d9-106">EDI Receive Components</span></span>](../core/edi-receive-components.md)  
  
-   [<span data-ttu-id="d55d9-107">Resolución de acuerdos, detección de esquemas y autorización para los mensajes EDI recibidos</span><span class="sxs-lookup"><span data-stu-id="d55d9-107">Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages</span></span>](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)  
  
-   [<span data-ttu-id="d55d9-108">Cómo funciona el Desensamblador EDI</span><span class="sxs-lookup"><span data-stu-id="d55d9-108">How the EDI Disassembler Works</span></span>](../core/how-the-edi-disassembler-works.md)  
  
-   [<span data-ttu-id="d55d9-109">Validación de mensajes EDI recibidos</span><span class="sxs-lookup"><span data-stu-id="d55d9-109">Validation of Received EDI Messages</span></span>](../core/validation-of-received-edi-messages.md)  
  
-   [<span data-ttu-id="d55d9-110">Enviar una confirmación EDI</span><span class="sxs-lookup"><span data-stu-id="d55d9-110">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)  
  
-   [<span data-ttu-id="d55d9-111">Procesamiento por lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="d55d9-111">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)
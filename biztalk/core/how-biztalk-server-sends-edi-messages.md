---
title: "Cómo BizTalk Server envía mensajes EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4eaf1085-4244-4df2-9d89-52ebdf6bcbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4727a407c28ede98bba67774576d4d43329a946
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-sends-edi-messages"></a><span data-ttu-id="2de07-102">Cómo BizTalk Server envía mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="2de07-102">How BizTalk Server Sends EDI Messages</span></span>
<span data-ttu-id="2de07-103">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía un mensaje EDI, lleva a cabo la búsqueda de acuerdo y la detección de esquemas, valida el mensaje, envía una confirmación (si fuese necesario) y serializa el lote de EDI.</span><span class="sxs-lookup"><span data-stu-id="2de07-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends an EDI message, it performs agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and serializes the EDI batch.</span></span> <span data-ttu-id="2de07-104">Este procesamiento lo realiza el ensamblador EDI en la canalización de envío EDI.</span><span class="sxs-lookup"><span data-stu-id="2de07-104">This processing is performed by the EDI assembler in the EDI Send Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2de07-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2de07-105">In This Section</span></span>  
  
-   [<span data-ttu-id="2de07-106">Componentes de envío de EDI</span><span class="sxs-lookup"><span data-stu-id="2de07-106">EDI Send Components</span></span>](../core/edi-send-components.md)  
  
-   [<span data-ttu-id="2de07-107">Resolución de acuerdos y determinación de esquemas para mensajes EDI salientes</span><span class="sxs-lookup"><span data-stu-id="2de07-107">Agreement Resolution and Schema Determination for Outgoing EDI Messages</span></span>](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="2de07-108">Cómo funciona el ensamblador EDI</span><span class="sxs-lookup"><span data-stu-id="2de07-108">How the EDI Assembler Works</span></span>](../core/how-the-edi-assembler-works.md)  
  
-   [<span data-ttu-id="2de07-109">Reemplazar los encabezados EDI</span><span class="sxs-lookup"><span data-stu-id="2de07-109">Overriding EDI Headers</span></span>](../core/overriding-edi-headers.md)  
  
-   [<span data-ttu-id="2de07-110">Validación de mensajes EDI salientes</span><span class="sxs-lookup"><span data-stu-id="2de07-110">Validation of Outgoing EDI Messages</span></span>](../core/validation-of-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="2de07-111">Procesamiento por lotes mensajes EDI salientes</span><span class="sxs-lookup"><span data-stu-id="2de07-111">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="2de07-112">Procesamiento de confirmaciones recibidas</span><span class="sxs-lookup"><span data-stu-id="2de07-112">Processing a Received Acknowledgment</span></span>](../core/processing-a-received-acknowledgment.md)
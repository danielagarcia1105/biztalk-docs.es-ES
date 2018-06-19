---
title: Estado del adaptador de FileAct supervisión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5b717a02631d47b864cc9180cba2fba673c5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223044"
---
# <a name="fileact-adapter-status-monitoring"></a><span data-ttu-id="54909-102">Estado del adaptador de FileAct supervisión</span><span class="sxs-lookup"><span data-stu-id="54909-102">FileAct Adapter Status Monitoring</span></span>
<span data-ttu-id="54909-103">Los Estados posibles de una transferencia de archivos y las transiciones entre los Estados se ilustran en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="54909-103">The possible states of a file transfer and the transitions between those states are illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="54909-104">![Estados de transferencia de archivo de adaptador FileAct](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span><span class="sxs-lookup"><span data-stu-id="54909-104">![FileAct adapter file transfer states](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span></span>  
  
 <span data-ttu-id="54909-105">Los Estados de transferencia de archivo son:</span><span class="sxs-lookup"><span data-stu-id="54909-105">The file transfer states are:</span></span>  
  
-   <span data-ttu-id="54909-106">**Inicia** : el cliente ha enviado el mensaje de negociación con el servidor, pero aún no ha recibido la respuesta.</span><span class="sxs-lookup"><span data-stu-id="54909-106">**Initiated** – The client has sent the negotiation message to the server, but has not yet received the response.</span></span> <span data-ttu-id="54909-107">El servidor ha recibido la solicitud de negociación, pero no ha enviado la respuesta.</span><span class="sxs-lookup"><span data-stu-id="54909-107">The server has received the negotiation request, but has not yet sent the response.</span></span>  
  
-   <span data-ttu-id="54909-108">**Acepta** : el servidor ha aceptado la solicitud y ha enviado el TransferAnswer en el mensaje de respuesta, y la transferencia aún está en curso.</span><span class="sxs-lookup"><span data-stu-id="54909-108">**Accepted** – The server has accepted the request and has sent the TransferAnswer in the response message, and the transfer is still in progress.</span></span>  
  
-   <span data-ttu-id="54909-109">**Rechazado** : el servidor ha rechazado la solicitud y tiene la TransferAnswer en el mensaje de respuesta y ha finalizado la transferencia.</span><span class="sxs-lookup"><span data-stu-id="54909-109">**Rejected** – The server has rejected the request and has the TransferAnswer in the response message, and has terminated the transfer.</span></span>  
  
-   <span data-ttu-id="54909-110">**En curso** : la transferencia está en curso y se está realizando (renovado periódicamente como anteriormente).</span><span class="sxs-lookup"><span data-stu-id="54909-110">**Ongoing** – The transfer is in progress and is proceeding (renewed periodically as above).</span></span>  
  
-   <span data-ttu-id="54909-111">**Completado** : la transferencia de archivos se completó correctamente en lo que se refiere esa parte de la transferencia, incluida la comparación del valor de síntesis.</span><span class="sxs-lookup"><span data-stu-id="54909-111">**Completed** – The file transfer has completed successfully as far as that side of the transfer is concerned, including the comparison of the digest value.</span></span>  
  
-   <span data-ttu-id="54909-112">**No se pudo** : la transferencia de archivos ha fallado por un acceso a los datos, procesar, excepción de comunicaciones o tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="54909-112">**Failed** – The file transfer has failed because of a data access, processing, communications or timeout exception.</span></span> <span data-ttu-id="54909-113">(Nota: SWIFTNet vínculo exige el tiempo de espera y el valor se determina mediante SWIFT).</span><span class="sxs-lookup"><span data-stu-id="54909-113">(Note: Timeout is enforced by SWIFTNet Link, and the value is determined by SWIFT).</span></span>  
  
-   <span data-ttu-id="54909-114">**Se anuló** : se ha anulado la transferencia de archivos (ya sea en paralelo mi problema la instrucción abort).</span><span class="sxs-lookup"><span data-stu-id="54909-114">**Aborted** – The file transfer has been aborted (either side my issue the abort).</span></span>  
  
-   <span data-ttu-id="54909-115">**Desconocido y duplicados** : este estado se produce solo debido a tiempo.</span><span class="sxs-lookup"><span data-stu-id="54909-115">**Unknown and Duplicated** – This state occurs only because of timing.</span></span> <span data-ttu-id="54909-116">En el caso de un remitente, el archivo debe ser vuelven a enviar marcado como posiblemente duplicado (PDIndicator).</span><span class="sxs-lookup"><span data-stu-id="54909-116">In the case of a sender, the file should be re-sent marked as possibly duplicated (PDIndicator).</span></span> <span data-ttu-id="54909-117">En el caso de un receptor, cuando la PDIndicator implica que el archivo podría haber ya se han enviado, el adaptador de FileAct comprobará la duplicación y si se encuentra, se devolverá un TransferAnswer de duplicados, que finalizará el intento actual.</span><span class="sxs-lookup"><span data-stu-id="54909-117">In the case of a receiver, when the PDIndicator implies that the file might have already been sent, the FileAct Adapter will check for the duplication, and if found, will return a TransferAnswer of Duplicated, which will terminate the current attempt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54909-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="54909-118">See Also</span></span>  
 <span data-ttu-id="54909-119">[Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="54909-119">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="54909-120">[Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="54909-120">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="54909-121">[Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="54909-121">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="54909-122">[Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="54909-122">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="54909-123">[Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="54909-123">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="54909-124">[Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="54909-124">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="54909-125">[Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="54909-125">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 [<span data-ttu-id="54909-126">Notificación de entrega del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="54909-126">FileAct Adapter Delivery Notification</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)
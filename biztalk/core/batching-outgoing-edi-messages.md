---
title: Procesamiento por lotes mensajes EDI salientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9f99849a812e859f527b3f39a2184508d244a29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004461"
---
# <a name="batching-outgoing-edi-messages"></a><span data-ttu-id="dbd5f-102">Procesar por lotes mensajes EDI salientes</span><span class="sxs-lookup"><span data-stu-id="dbd5f-102">Batching Outgoing EDI Messages</span></span>
<span data-ttu-id="dbd5f-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesará por lotes los conjuntos de transacciones EDI si se ha habilitado el procesamiento por lotes del acuerdo asociado con el socio comercial que lo recibirá.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will batch EDI transaction sets if batching has been enabled for the agreement associated with the business partner that will be receiving it.</span></span> <span data-ttu-id="dbd5f-104">Las propiedades EDI de un acuerdo le permiten hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbd5f-104">The EDI properties for an agreement enable you to do the following:</span></span>  
  
- <span data-ttu-id="dbd5f-105">Definir varios lotes salientes</span><span class="sxs-lookup"><span data-stu-id="dbd5f-105">Define multiple outgoing batches</span></span>  
  
- <span data-ttu-id="dbd5f-106">Definir el intercambio</span><span class="sxs-lookup"><span data-stu-id="dbd5f-106">Define the interchange</span></span>  
  
- <span data-ttu-id="dbd5f-107">Definir los grupos del intercambio</span><span class="sxs-lookup"><span data-stu-id="dbd5f-107">Define the groups in the interchange</span></span>  
  
- <span data-ttu-id="dbd5f-108">Definir los criterios de lanzamiento del procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="dbd5f-108">Set the batch release criteria</span></span>  
  
- <span data-ttu-id="dbd5f-109">Definir los criterios de activación del procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-109">Set the batch activation criteria.</span></span>  
  
  <span data-ttu-id="dbd5f-110">Microsoft BizTalk Server EDI y AS2 permite el procesamiento de intercambios EDI siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbd5f-110">Microsoft BizTalk Server EDI and AS2 enables the following processing of EDI interchanges:</span></span>  
  
- <span data-ttu-id="dbd5f-111">Los intercambios de EDI pueden incluir confirmaciones y/o conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-111">EDI interchanges can include transaction sets and/or acknowledgments.</span></span>  
  
- <span data-ttu-id="dbd5f-112">La canalización de recepción de EDI puede dividir un intercambio en conjuntos de transacciones para su posterior procesamiento por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], o bien puede conservar el intercambio pasándolo a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en su forma recibida.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-112">The EDI receive pipeline can split an interchange into XML transaction sets for further processing by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], or it can preserve the interchange, passing it through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in its received form.</span></span>  
  
- <span data-ttu-id="dbd5f-113">La orquestación de enrutamiento de EDI permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese por lotes un único conjunto de transacciones en más de un intercambio saliente.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-113">The EDI routing orchestration enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to batch a single transaction set into more than one outgoing interchange.</span></span>  
  
- <span data-ttu-id="dbd5f-114">La orquestación de procesamiento por lotes de EDI ensambla los conjuntos de transacciones XML en un intercambio EDI y valida y entrega el intercambio de acuerdo con las propiedades EDI del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-114">The EDI batching orchestration assembles XML transaction sets into an EDI interchange, and validates and delivers the interchange according to an agreement's EDI properties.</span></span>  
  
  <span data-ttu-id="dbd5f-115">Los lotes de EDI, llamados intercambios, contienen grupos de mensajes y, a su vez, los grupos de mensajes contienen mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-115">EDI batches, called interchanges, contain message groups, and message groups contain individual messages.</span></span> <span data-ttu-id="dbd5f-116">Los lotes salientes pueden incluir varios grupos, pero solo un grupo por tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-116">Outgoing batches can include multiple groups, but only one group per document type.</span></span> <span data-ttu-id="dbd5f-117">Un grupo puede contener varios conjuntos de transacciones, pero cada uno debe tener el mismo tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-117">A group can contain multiple transaction sets, but each must have the same document type.</span></span> <span data-ttu-id="dbd5f-118">Los sobres de los mensajes se utilizan para envolver conjuntos de transacciones individuales, grupos individuales y el intercambio completo.</span><span class="sxs-lookup"><span data-stu-id="dbd5f-118">Message envelopes are used to wrap individual transaction sets, individual groups, and the entire interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbd5f-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dbd5f-119">In This Section</span></span>  
  
-   [<span data-ttu-id="dbd5f-120">Configuración de un lote de salida</span><span class="sxs-lookup"><span data-stu-id="dbd5f-120">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
  
-   [<span data-ttu-id="dbd5f-121">Ensamblar un intercambio EDI por lotes</span><span class="sxs-lookup"><span data-stu-id="dbd5f-121">Assembling a Batched EDI Interchange</span></span>](../core/assembling-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="dbd5f-122">Envío de intercambios por lotes conservados</span><span class="sxs-lookup"><span data-stu-id="dbd5f-122">Sending a Preserved Batch Interchange</span></span>](../core/sending-a-preserved-batch-interchange.md)
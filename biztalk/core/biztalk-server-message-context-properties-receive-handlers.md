---
title: Propiedades de contexto de mensaje de recepción para TIBCO Rendezvous | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36f4de92dbe7c4c235a1c9ebd092b28b3a198c92
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015003"
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="c7553-102">Propiedades de contexto de mensaje de BizTalk Server (controladores de recepción)</span><span class="sxs-lookup"><span data-stu-id="c7553-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="c7553-103">Además de la carga del mensaje, se debe poder acceder a la información complementaria que compone un mensaje desde una orquestación de BizTalk Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7553-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="c7553-104">Información de mensaje de TIBCO RV promocionada como propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="c7553-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="c7553-105">En la tabla siguiente se enumera la información complementaria:</span><span class="sxs-lookup"><span data-stu-id="c7553-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="c7553-106">Identificación de datos</span><span class="sxs-lookup"><span data-stu-id="c7553-106">Data Identification</span></span>|<span data-ttu-id="c7553-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="c7553-107">Type</span></span>|<span data-ttu-id="c7553-108">Enrutable</span><span class="sxs-lookup"><span data-stu-id="c7553-108">Routable</span></span>|<span data-ttu-id="c7553-109">Ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="c7553-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="c7553-110">Enviar a asunto [nulo]</span><span class="sxs-lookup"><span data-stu-id="c7553-110">Send Subject [null]</span></span>|<span data-ttu-id="c7553-111">string</span><span class="sxs-lookup"><span data-stu-id="c7553-111">string</span></span>|<span data-ttu-id="c7553-112">Sí</span><span class="sxs-lookup"><span data-stu-id="c7553-112">Yes</span></span>|<span data-ttu-id="c7553-113">Indica a la orquestación a qué asunto se envío el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7553-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="c7553-114">Asunto de respuesta [nulo]</span><span class="sxs-lookup"><span data-stu-id="c7553-114">Reply Subject [null]</span></span>|<span data-ttu-id="c7553-115">string</span><span class="sxs-lookup"><span data-stu-id="c7553-115">string</span></span>|<span data-ttu-id="c7553-116">Sí</span><span class="sxs-lookup"><span data-stu-id="c7553-116">Yes</span></span>|<span data-ttu-id="c7553-117">Indica a la orquestación dónde espera el remitente que se envíe la respuesta, si se espera que una.</span><span class="sxs-lookup"><span data-stu-id="c7553-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="c7553-118">Recuento de campo [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="c7553-118">Field Count [read only]</span></span>|<span data-ttu-id="c7553-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="c7553-119">unsigned int</span></span>|<span data-ttu-id="c7553-120">No</span><span class="sxs-lookup"><span data-stu-id="c7553-120">No</span></span>|<span data-ttu-id="c7553-121">Número de campos en mensaje de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c7553-121">Number of fields in upper level message.</span></span> <span data-ttu-id="c7553-122">Una propiedad proporcionada por TIBCO RV.</span><span class="sxs-lookup"><span data-stu-id="c7553-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="c7553-123">Nombre del remitente CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="c7553-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="c7553-124">string</span><span class="sxs-lookup"><span data-stu-id="c7553-124">string</span></span>|<span data-ttu-id="c7553-125">Sí</span><span class="sxs-lookup"><span data-stu-id="c7553-125">Yes</span></span>|<span data-ttu-id="c7553-126">Nombre correspondiente de CM del remitente.</span><span class="sxs-lookup"><span data-stu-id="c7553-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="c7553-127">Número de secuencia CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="c7553-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="c7553-128">long</span><span class="sxs-lookup"><span data-stu-id="c7553-128">long</span></span>|<span data-ttu-id="c7553-129">No</span><span class="sxs-lookup"><span data-stu-id="c7553-129">No</span></span>|<span data-ttu-id="c7553-130">Número de secuencia asignado por el objeto de transporte TIBCO remitente.</span><span class="sxs-lookup"><span data-stu-id="c7553-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="c7553-131">Límite de tiempo CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="c7553-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="c7553-132">double</span><span class="sxs-lookup"><span data-stu-id="c7553-132">double</span></span>|<span data-ttu-id="c7553-133">No</span><span class="sxs-lookup"><span data-stu-id="c7553-133">No</span></span>|<span data-ttu-id="c7553-134">Un límite de tiempo, tras el cual el programa remitente no esperará que el transporte CM certifique la entrega del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7553-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7553-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7553-135">See Also</span></span>  
 <span data-ttu-id="c7553-136">[Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="c7553-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="c7553-137">Creación de controladores de recepción de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="c7553-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)
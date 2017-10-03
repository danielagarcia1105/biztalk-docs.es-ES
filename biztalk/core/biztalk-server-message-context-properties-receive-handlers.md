---
title: "Propiedades de contexto de mensaje de BizTalk Server (controladores de recepción) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties
- receive handlers, message context properties
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a60896a8e1cace909a160c1dc942e63e9258d85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="0f049-102">Propiedades de contexto de mensaje de BizTalk Server (controladores de recepción)</span><span class="sxs-lookup"><span data-stu-id="0f049-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="0f049-103">Además de la carga del mensaje, se debe poder acceder a la información complementaria que compone un mensaje desde una orquestación de BizTalk Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f049-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="0f049-104">Información de mensaje de TIBCO RV promocionada como propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="0f049-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="0f049-105">En la tabla siguiente se enumera la información complementaria:</span><span class="sxs-lookup"><span data-stu-id="0f049-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="0f049-106">Identificación de datos</span><span class="sxs-lookup"><span data-stu-id="0f049-106">Data Identification</span></span>|<span data-ttu-id="0f049-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0f049-107">Type</span></span>|<span data-ttu-id="0f049-108">Enrutable</span><span class="sxs-lookup"><span data-stu-id="0f049-108">Routable</span></span>|<span data-ttu-id="0f049-109">Ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="0f049-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="0f049-110">Enviar a asunto [nulo]</span><span class="sxs-lookup"><span data-stu-id="0f049-110">Send Subject [null]</span></span>|<span data-ttu-id="0f049-111">string</span><span class="sxs-lookup"><span data-stu-id="0f049-111">string</span></span>|<span data-ttu-id="0f049-112">Sí</span><span class="sxs-lookup"><span data-stu-id="0f049-112">Yes</span></span>|<span data-ttu-id="0f049-113">Indica a la orquestación a qué asunto se envío el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f049-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="0f049-114">Asunto de respuesta [nulo]</span><span class="sxs-lookup"><span data-stu-id="0f049-114">Reply Subject [null]</span></span>|<span data-ttu-id="0f049-115">string</span><span class="sxs-lookup"><span data-stu-id="0f049-115">string</span></span>|<span data-ttu-id="0f049-116">Sí</span><span class="sxs-lookup"><span data-stu-id="0f049-116">Yes</span></span>|<span data-ttu-id="0f049-117">Indica a la orquestación dónde espera el remitente que se envíe la respuesta, si se espera que una.</span><span class="sxs-lookup"><span data-stu-id="0f049-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="0f049-118">Recuento de campo [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="0f049-118">Field Count [read only]</span></span>|<span data-ttu-id="0f049-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="0f049-119">unsigned int</span></span>|<span data-ttu-id="0f049-120">No</span><span class="sxs-lookup"><span data-stu-id="0f049-120">No</span></span>|<span data-ttu-id="0f049-121">Número de campos en mensaje de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="0f049-121">Number of fields in upper level message.</span></span> <span data-ttu-id="0f049-122">Una propiedad proporcionada por TIBCO RV.</span><span class="sxs-lookup"><span data-stu-id="0f049-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="0f049-123">Nombre del remitente CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="0f049-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="0f049-124">string</span><span class="sxs-lookup"><span data-stu-id="0f049-124">string</span></span>|<span data-ttu-id="0f049-125">Sí</span><span class="sxs-lookup"><span data-stu-id="0f049-125">Yes</span></span>|<span data-ttu-id="0f049-126">Nombre correspondiente de CM del remitente.</span><span class="sxs-lookup"><span data-stu-id="0f049-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="0f049-127">Número de secuencia CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="0f049-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="0f049-128">long</span><span class="sxs-lookup"><span data-stu-id="0f049-128">long</span></span>|<span data-ttu-id="0f049-129">No</span><span class="sxs-lookup"><span data-stu-id="0f049-129">No</span></span>|<span data-ttu-id="0f049-130">Número de secuencia asignado por el objeto de transporte TIBCO remitente.</span><span class="sxs-lookup"><span data-stu-id="0f049-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="0f049-131">Límite de tiempo CM [solo lectura]</span><span class="sxs-lookup"><span data-stu-id="0f049-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="0f049-132">double</span><span class="sxs-lookup"><span data-stu-id="0f049-132">double</span></span>|<span data-ttu-id="0f049-133">No</span><span class="sxs-lookup"><span data-stu-id="0f049-133">No</span></span>|<span data-ttu-id="0f049-134">Un límite de tiempo, tras el cual el programa remitente no esperará que el transporte CM certifique la entrega del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f049-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f049-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f049-135">See Also</span></span>  
 <span data-ttu-id="0f049-136">[Asignación de mensaje de TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="0f049-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="0f049-137">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0f049-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)
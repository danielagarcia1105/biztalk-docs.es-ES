---
title: Uso de BizTalk Server desde TIBCO Rendezvous para recibir mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- receiving messages
- memory use
ms.assetid: 4eee9c3a-2966-4d5f-ba49-201bb488458c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac81f269e19526f5466e8c12115d617b8171da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a><span data-ttu-id="de263-102">Uso de BizTalk Server desde TIBCO Rendezvous para recibir mensajes</span><span class="sxs-lookup"><span data-stu-id="de263-102">Using BizTalk Server from TIBCO Rendezvous to Receive Messages</span></span>
<span data-ttu-id="de263-103">El adaptador de Microsoft BizTalk para TIBCO Rendezvous distribuye eventos de una cola en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de263-103">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="de263-104">Una ubicación de recepción de BizTalk Server está asociada con una cola de eventos TIBCO Rendezvous y su grupo de subprocesos de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="de263-104">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue and its pool of dispatcher threads.</span></span>  
  
## <a name="memory-use-and-errors"></a><span data-ttu-id="de263-105">Uso de memoria y errores</span><span class="sxs-lookup"><span data-stu-id="de263-105">Memory Use and Errors</span></span>  
 <span data-ttu-id="de263-106">Al procesar eventos, el adaptador vigila los recursos usados.</span><span class="sxs-lookup"><span data-stu-id="de263-106">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="de263-107">Si el uso de memoria supera el umbral de marca de agua superior, el adaptador deja de distribuir eventos hasta que llega al consumo de memoria de la marca de agua inferior.</span><span class="sxs-lookup"><span data-stu-id="de263-107">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="de263-108">Tenga en cuenta que, debido a esto, podrían perderse mensajes de TIBCO Rendezvous para mensajes no certificados (un consumidor de TIBCO RV tiene 60 segundos para quitar mensajes de una cola).</span><span class="sxs-lookup"><span data-stu-id="de263-108">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="de263-109">Esta pérdida de datos se notifica como un error.</span><span class="sxs-lookup"><span data-stu-id="de263-109">This data loss is reported as an error.</span></span> <span data-ttu-id="de263-110">Si el adaptador recibe un mensaje NO_MEMORY de aviso del sistema de TIBCO Rendezvous, significa que ya se han perdido mensajes.</span><span class="sxs-lookup"><span data-stu-id="de263-110">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="de263-111">El Adaptador de BizTalk para TIBCO Rendezvous mantiene un estado y ejecuta las tareas de diferente forma basándose en dicho estado.</span><span class="sxs-lookup"><span data-stu-id="de263-111">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="de263-112">Si el Motor de mensajes de BizTalk notifica un error y el adaptador está configurado para ser una escucha certificada, notificará el error a TIBCO Rendezvous de modo que pueda reenviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="de263-112">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de263-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="de263-113">See Also</span></span>  
 <span data-ttu-id="de263-114">[Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="de263-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="de263-115">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="de263-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)
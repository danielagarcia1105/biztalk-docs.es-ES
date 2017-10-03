---
title: "Propiedades de contexto de mensaje de BizTalk Server (controladores de envío) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, BizTalk Server
- reply subjects
- send handlers, BizTalk Server message context properties
- replies
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8e5ddb1feb02a015fdebd62d183d1b8442fe5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a><span data-ttu-id="4e6f4-102">Propiedades de contexto de mensaje de BizTalk Server (controladores de envío)</span><span class="sxs-lookup"><span data-stu-id="4e6f4-102">BizTalk Server Message Context Properties (Send Handlers)</span></span>
<span data-ttu-id="4e6f4-103">Además de la carga de mensaje, la información suplementaria que contiene un mensaje debe ser accesible desde la orquestación de BizTalk Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-103">In addition to the message payload, the supplementary information that a message contains must be accessible from the BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="4e6f4-104">Información de mensaje de TIBCO RV promocionada como propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="4e6f4-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
  
|<span data-ttu-id="4e6f4-105">Identificación de datos</span><span class="sxs-lookup"><span data-stu-id="4e6f4-105">Data Identification</span></span>|<span data-ttu-id="4e6f4-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e6f4-106">Type</span></span>|<span data-ttu-id="4e6f4-107">Enrutable</span><span class="sxs-lookup"><span data-stu-id="4e6f4-107">Routable</span></span>|<span data-ttu-id="4e6f4-108">Ubicación de envío</span><span class="sxs-lookup"><span data-stu-id="4e6f4-108">Send Location</span></span>|  
|-------------------------|----------|--------------|-------------------|  
|<span data-ttu-id="4e6f4-109">Asunto de envío</span><span class="sxs-lookup"><span data-stu-id="4e6f4-109">Send Subject</span></span>|<span data-ttu-id="4e6f4-110">string</span><span class="sxs-lookup"><span data-stu-id="4e6f4-110">string</span></span>|<span data-ttu-id="4e6f4-111">Sí</span><span class="sxs-lookup"><span data-stu-id="4e6f4-111">Yes</span></span>|<span data-ttu-id="4e6f4-112">La orquestación especifica el asunto de envío de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-112">Orchestration specifies the TIBCO Rendezvous send subject.</span></span> <span data-ttu-id="4e6f4-113">El valor predeterminado es Null.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-113">Default value is Null.</span></span> <span data-ttu-id="4e6f4-114">Es obligatorio a menos que se especifique un asunto predeterminado en la configuración del puerto.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-114">Mandatory unless a default subject is specified in the port configuration.</span></span>|  
|<span data-ttu-id="4e6f4-115">Asunto de respuesta</span><span class="sxs-lookup"><span data-stu-id="4e6f4-115">Reply Subject</span></span>|<span data-ttu-id="4e6f4-116">string</span><span class="sxs-lookup"><span data-stu-id="4e6f4-116">string</span></span>|<span data-ttu-id="4e6f4-117">Sí</span><span class="sxs-lookup"><span data-stu-id="4e6f4-117">Yes</span></span>|<span data-ttu-id="4e6f4-118">La orquestación proporciona un asunto para los mensajes de respuesta, cuando es pertinente.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-118">Orchestration provides a subject for reply messages, when pertinent.</span></span> <span data-ttu-id="4e6f4-119">El valor predeterminado es Null.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-119">Default value is Null.</span></span>|  
  
## <a name="getting-a-tibco-reply"></a><span data-ttu-id="4e6f4-120">Obtención de una respuesta de TIBCO</span><span class="sxs-lookup"><span data-stu-id="4e6f4-120">Getting a TIBCO Reply</span></span>  
 <span data-ttu-id="4e6f4-121">**Pregunta:** como lo hace el adaptador de BizTalk para TIBCO Rendezvous leer y manipular el asunto de respuesta dentro de una orquestación para que puedan usarla como asunto de envío para la respuesta?</span><span class="sxs-lookup"><span data-stu-id="4e6f4-121">**Question:** How does BizTalk Adapter for TIBCO Rendezvous read and manipulate the reply subject inside an orchestration so that you can use it as the send subject for the response?</span></span> <span data-ttu-id="4e6f4-122">¿Cómo llega el adaptador al contexto de un mensaje de entrada de Rendezvous?</span><span class="sxs-lookup"><span data-stu-id="4e6f4-122">How does the adapter get to the message context of an incoming message from Rendezvous?</span></span>  
  
 <span data-ttu-id="4e6f4-123">**Respuesta:** el asunto de respuesta se rellena en el contexto del mensaje entrante y la orquestación puede leerlo.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-123">**Answer:** The reply subject is populated in the context of the incoming message, and the orchestration can read it.</span></span> <span data-ttu-id="4e6f4-124">Si finalmente la orquestación produce una respuesta, puede usar ese valor para establecer el asunto de envío del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-124">If the orchestration ultimately produces a reply, it can use that value to set the send subject of the reply message.</span></span>  
  
1.  <span data-ttu-id="4e6f4-125">En un proyecto de BizTalk Server, agregue una referencia a <directorio_instalación>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-125">In a BizTalk Server project, add a reference to <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span>  
  
2.  <span data-ttu-id="4e6f4-126">En la orquestación (en algún lugar entre la forma Recepción que controla el mensaje Rendezvous entrante y la forma Envío que envía la respuesta), agregue una forma de construcción/asignación (o una forma de expresión) para realizar alguna acción como la del siguiente ejemplo en la respuesta que construyó:</span><span class="sxs-lookup"><span data-stu-id="4e6f4-126">In the orchestration (somewhere between the Receive shape that is handed the incoming Rendezvous message and the Send shape that is sending the reply), add a message construction/assignment shape (or an expression shape) to do something like the following example to the reply you constructed:</span></span>  
  
    ```  
    OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
    (Rendezvous.ReplySubject);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e6f4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e6f4-127">See Also</span></span>  
 <span data-ttu-id="4e6f4-128">[Asignación de tipos de datos para los controladores de envío de TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="4e6f4-128">[Data Type Mapping for Send Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="4e6f4-129">Crear controladores de envío TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="4e6f4-129">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)